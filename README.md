<p align="center">
  <a href="https://peifeng.li"><img width="184" alt="AVDB logo" src="https://github.com/li-peifeng/AVdb-Only/raw/main/public/logo.svg" /></a>
</p>
<p align="center">
  <a href="https://hub.docker.com/r/leolitaly/avdb"><img src="https://img.shields.io/docker/pulls/leolitaly/avdb?color=%2348BB78&logo=docker&label=pulls" alt="Docker pulls" /></a>
</p>

# Avdb-OTA

Avdb 应用层 OTA 发布仓库。Docker 镜像中的稳定 Launcher 从这里读取公开
Manifest，下载加密的应用 Release，并在容器内完成校验、解密、原子切换和健康检查。

## 当前发布

- Manifest：[`manifest.json`](./manifest.json)
- 版本：`2026.8.15.100`
- 加密包：[`avdb-2026.8.15.100.pkg.enc`](./avdb-2026.8.15.100.pkg.enc)
- 签名算法：Ed25519
- 签名 `key_id`：`2026-main`
- 加密算法：AES-256-GCM
- 公钥 keyring：[`ota-signing-keyring.json`](./ota-signing-keyring.json)
  （当前包含 `2026-main` 与预发布的 `2026-next`）

稳定入口地址：

```text
https://raw.githubusercontent.com/li-peifeng/Avdb-OTA/main/manifest.json
```

## 部署端配置

部署端必须通过 Docker Secret、只读挂载或等效的 root-owned 文件提供 AES 密钥；
AES 密钥不会提交到本仓库。Manifest 公钥 keyring 只包含公开的 Ed25519 公钥，
可以从本仓库取得后审阅并挂载到部署端。当前线上 Manifest 仍使用
`2026-main`，`2026-next` 只是提前加入 keyring，尚未用于当前 Release。

```text
AVDB_OTA_MANIFEST_URL=https://raw.githubusercontent.com/li-peifeng/Avdb-OTA/main/manifest.json
AVDB_OTA_KEY_FILE=/run/secrets/avdb_ota.key
AVDB_OTA_SIGNING_PUBLIC_KEYRING_FILE=/run/secrets/avdb_ota_keyring.json
```

手动触发更新示例：

```bash
python /opt/avdb/launcher/update.py \
  --manifest-url https://raw.githubusercontent.com/li-peifeng/Avdb-OTA/main/manifest.json \
  --key-file /run/secrets/avdb_ota.key \
  --public-keyring-file /run/secrets/avdb_ota_keyring.json \
  --activate
```

生产环境不应使用 `--allow-http`、`--allow-unsigned-manifest` 或明文 OTA 包。
更新流程会先验证 Manifest 签名、加密包 SHA-256 和 AES-GCM 认证标签，再解压到
持久化 Release 目录；切换失败会回滚到上一版本。

## 密钥轮换

本仓库已经完成第一步轮换准备：keyring 同时包含 `2026-main` 和
`2026-next`，但当前 `2026.8.15.100` Manifest 仍由 `2026-main` 签名，
AES 解密密钥保持不变。

正式切换时必须遵循以下顺序：

1. 先将包含旧公钥和新公钥的 keyring 部署到客户端。
2. 确认旧 `2026-main` Manifest 仍可验证。
3. 再发布带有 `key_id=2026-next` 的新版本 Manifest。
4. 保留旧公钥覆盖一个完整更新周期，确认客户端迁移后再移除。

签名私钥只保留在发布机或 CI Secret 中，绝不上传到 GitHub。当前 keyring
只负责 Ed25519 Manifest 签名密钥轮换；AES OTA 密钥没有做轮换，避免旧客户端
下载新包后无法解密。
