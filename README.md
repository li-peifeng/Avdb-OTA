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

<!-- AVDB-OTA-CURRENT-RELEASE:START -->
- Release：[`20260821-0036`](https://github.com/li-peifeng/Avdb-OTA/releases/tag/20260821-0036)
- Manifest：[`manifest.json`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260821-0036/manifest.json)
- 版本：`20260821-0036`
- 加密包：[`avdb-20260821-0036.pkg.enc`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260821-0036/avdb-20260821-0036.pkg.enc)
- 签名算法：Ed25519
- 签名 `key_id`：`2026-next`
- 加密算法：AES-256-GCM
- 更新方式：`Docker 镜像`
- 需要更新镜像的文件：`Dockerfile、launcher/ota_config.py、launcher/remote_update.py、launcher/update.py`
- 更新摘要：
  修复 OTA 更新检查
- 公钥 keyring：[`ota-signing-keyring.json`](./ota-signing-keyring.json)
<!-- AVDB-OTA-CURRENT-RELEASE:END -->

当前发布版本使用 Manifest 指定的签名密钥，双 keyring 客户端可以从旧签名版本
跨到新签名版本。

正式发布时，每个版本会创建一个 GitHub Release，并将签名 Manifest 与加密包作为 Release 资产上传；main 分支仅保留 README 和公钥 keyring，不保存 Manifest 或加密 OTA 包。GitHub Releases 是唯一的 OTA 发布来源，并保留全部历史版本，便于回滚与审计。

稳定入口地址（客户端通过 Release API 解析最新 Release 提交号，再使用版本化资产）：

```text
最新版 Release：
https://github.com/li-peifeng/Avdb-OTA/releases/latest

最新版 Manifest：
https://github.com/li-peifeng/Avdb-OTA/releases/latest/download/manifest.json
```

## 注意： 修改任意文件内容会使签名失效，将不能安装使用。
