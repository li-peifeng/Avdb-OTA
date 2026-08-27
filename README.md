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
- Release：[`20260827-2229`](https://github.com/li-peifeng/Avdb-OTA/releases/tag/20260827-2229)
- Manifest：[`manifest.json`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260827-2229/manifest.json)
- 版本：`20260827-2229`
- 加密包：[`avdb-20260827-2229.pkg.enc`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260827-2229/avdb-20260827-2229.pkg.enc)
- 签名算法：Ed25519
- 签名 `key_id`：`2026-next`
- 加密算法：AES-256-GCM
- 更新方式：`应用内 OTA`
- 更新摘要：
  图片补全 R18 封面，海报，剧照 都使用独立开关控制。
  Telegram 发送通知的图片支持高清图（包括：下载、新增媒体、删除、已在库的磁力搜索），并支持自定义番号测试通知。
  首页轮播图优化，只要打开 R18 高清封面设置，轮播图就采用高清图，并支持爬取后及更新后立即更新轮播图素材。
- 公钥 keyring：[`ota-signing-keyring.json`](./ota-signing-keyring.json)
<!-- AVDB-OTA-CURRENT-RELEASE:END -->

当前发布版本使用 Manifest 指定的签名密钥，双 keyring 客户端可以从旧签名版本
跨到新签名版本。

## 注意： 修改任意文件内容会使签名失效，将不能安装使用。
