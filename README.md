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
- Release：[`20260821-1443`](https://github.com/li-peifeng/Avdb-OTA/releases/tag/20260821-1443)
- Manifest：[`manifest.json`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260821-1443/manifest.json)
- 版本：`20260821-1443`
- 加密包：[`avdb-20260821-1443.pkg.enc`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260821-1443/avdb-20260821-1443.pkg.enc)
- 签名算法：Ed25519
- 签名 `key_id`：`2026-next`
- 加密算法：AES-256-GCM
- 更新方式：`Docker 镜像`
- 需要更新镜像的文件：`launcher/remote_update.py`
- 更新摘要：
  影片详情页的 Tags 优化
  修复 OTA 更新检查
  OTA 进度窗口高度修正
- 公钥 keyring：[`ota-signing-keyring.json`](./ota-signing-keyring.json)
<!-- AVDB-OTA-CURRENT-RELEASE:END -->

当前发布版本使用 Manifest 指定的签名密钥，双 keyring 客户端可以从旧签名版本
跨到新签名版本。

正式发布时，每个版本只构建并签名一次，然后由本地发布脚本使用同一份 `.pkg.enc` 与
`manifest.json` 直接创建 GitHub Release 和 Gitee Release；main 分支仅保留 README 和公钥
keyring，不保存 Manifest 或加密 OTA 包。两端保留全部历史版本，便于回滚与审计；Actions
workflow 仅作为发布失败时的手动备用通道。

稳定入口地址（客户端通过 Release API 解析最新 Release 提交号，再使用版本化资产）：

```text
最新版 Release：
https://github.com/li-peifeng/Avdb-OTA/releases/latest

最新版 Manifest：
https://github.com/li-peifeng/Avdb-OTA/releases/latest/download/manifest.json
```

国内镜像（正常由本地发布脚本直传；Actions workflow 仅作手动备用）：

```text
Gitee 仓库：
https://gitee.com/avdb/ota

最新版 Release：
https://gitee.com/avdb/ota/releases/latest
```

正常本地发布时，在 `.env` 或环境变量中配置 `AVDB_OTA_GITEE_TOKEN`，令牌需要具备
`avdb/ota` 仓库 Release/附件的读写权限；`GITEE_TOKEN` 也可作为兼容名称。若本地
Gitee 发布中断，可在 GitHub Actions 手动运行
`.github/workflows/sync-gitee-release.yml`，输入 GitHub Release tag 作为备用通道。
Manifest 使用相对的加密包路径，GitHub 和 Gitee 可以复用同一份签名资产；客户端会先
校验 Release 资产和 Manifest，再从当前选中的发布源下载加密包。

## 注意： 修改任意文件内容会使签名失效，将不能安装使用。
