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
- Release：[`20260821-1700`](https://github.com/li-peifeng/Avdb-OTA/releases/tag/20260821-1700)
- Manifest：[`manifest.json`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260821-1700/manifest.json)
- 版本：`20260821-1700`
- 加密包：[`avdb-20260821-1700.pkg.enc`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260821-1700/avdb-20260821-1700.pkg.enc)
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

正式发布时，每个版本只构建并签名一次，由本地发布脚本创建 GitHub Release；GitHub Release 发布完成后，Actions workflow 会自动从该 GitHub Release 下载同一份 `manifest.json` 与 `.pkg.enc`，在 Gitee 创建或更新同名 Release，上传并校验同一组资产。本地不再直接上传 Gitee，避免大文件经过本地网络重复传输。main 分支仅保留 README 和公钥 keyring，不保存 Manifest 或加密 OTA 包。两端仅保留最新两个 Release 及其版本 tag，旧版本由同步 workflow 自动清理。

如果自动同步失败，可以在 Actions 中手动运行 `Sync GitHub Release to Gitee`，输入需要重试的 GitHub Release tag；手动重试与自动流程使用完全相同的下载、上传和资产校验逻辑。
该 workflow 需要在本仓库配置 `GITEE_TOKEN` Actions Secret。


入口地址：

```text
最新版 Release：
https://github.com/li-peifeng/Avdb-OTA/releases/latest

最新版 Manifest：
https://github.com/li-peifeng/Avdb-OTA/releases/latest/download/manifest.json
```

国内镜像：

```text
Gitee 仓库：
https://gitee.com/avdb/ota

最新版 Release：
https://gitee.com/avdb/ota/releases/latest
```

## 注意： 修改任意文件内容会使签名失效，将不能安装使用。
