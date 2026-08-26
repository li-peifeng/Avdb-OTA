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
- Release：[`20260826-0227`](https://github.com/li-peifeng/Avdb-OTA/releases/tag/20260826-0227)
- Manifest：[`manifest.json`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260826-0227/manifest.json)
- 版本：`20260826-0227`
- 加密包：[`avdb-20260826-0227.pkg.enc`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260826-0227/avdb-20260826-0227.pkg.enc)
- 签名算法：Ed25519
- 签名 `key_id`：`2026-next`
- 加密算法：AES-256-GCM
- 更新方式：`应用内 OTA`
- 更新摘要：
  添加 手动导入 R18 数据库
  修复修改头像时的分辨率显示
  修复网络下的标签栏在移动端重叠的问题
  统一 UI 的圆角显示，视觉上更加美观
  高清海报和封面图接入，Emby 插件同步支持
  优化 SQLite 导入 R18 的逻辑
  添加 R18 增量更新功能
- 公钥 keyring：[`ota-signing-keyring.json`](./ota-signing-keyring.json)
<!-- AVDB-OTA-CURRENT-RELEASE:END -->

当前发布版本使用 Manifest 指定的签名密钥，双 keyring 客户端可以从旧签名版本
跨到新签名版本。

## 注意： 修改任意文件内容会使签名失效，将不能安装使用。
