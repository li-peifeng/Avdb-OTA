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
- Release：[`20260820-0040`](https://github.com/li-peifeng/Avdb-OTA/releases/tag/20260820-0040)
- Manifest：[`manifest.json`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260820-0040/manifest.json)
- 版本：`20260820-0040`
- 加密包：[`avdb-20260820-0040.pkg.enc`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260820-0040/avdb-20260820-0040.pkg.enc)
- 签名算法：Ed25519
- 签名 `key_id`：`2026-next`
- 加密算法：AES-256-GCM
- 更新方式：`应用内 OTA`
- 更新摘要：
  修改并添加了前端界面与交互，优化页面使用体验。
  修改并添加了应用启动和更新流程，完善版本切换支持。
  可按需选择自动更新的站点最近 30 天增量包
- 公钥 keyring：[`ota-signing-keyring.json`](./ota-signing-keyring.json)
<!-- AVDB-OTA-CURRENT-RELEASE:END -->

当前发布版本使用 Manifest 指定的签名密钥，双 keyring 客户端可以从旧签名版本
跨到新签名版本。

正式发布时，每个版本会创建一个 GitHub Release，并将签名 Manifest 与加密包作为 Release 资产上传；main 分支只保留签名 Manifest 兼容指针，不再作为正式加密包下载源。 GitHub Releases 保留全部历史 OTA 版本，便于回滚与审计；删除 Release 不会改写 Git 历史和标签。
迁移窗口内，为兼容仍缓存旧 Raw Manifest 的客户端，main 可能暂留对应的旧包；正式新客户端下载以 Release 资产为准。

稳定入口地址：

```text
最新版 Release：
https://github.com/li-peifeng/Avdb-OTA/releases/latest

最新版 Manifest：
https://github.com/li-peifeng/Avdb-OTA/releases/latest/download/manifest.json

旧客户端兼容 Manifest：
https://raw.githubusercontent.com/li-peifeng/Avdb-OTA/refs/heads/main/manifest.json
```

## 注意： 修改任意文件内容会使签名失效，将不能安装使用。
