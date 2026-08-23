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
- Release：[`20260824-0155`](https://github.com/li-peifeng/Avdb-OTA/releases/tag/20260824-0155)
- Manifest：[`manifest.json`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260824-0155/manifest.json)
- 版本：`20260824-0155`
- 加密包：[`avdb-20260824-0155.pkg.enc`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260824-0155/avdb-20260824-0155.pkg.enc)
- 签名算法：Ed25519
- 签名 `key_id`：`2026-next`
- 加密算法：AES-256-GCM
- 更新方式：`应用内 OTA`
- 更新摘要：
  影片详情中的合格附加剧照少于 3 张时，按番号从本地 R18 数据库补充全部 full 剧照；触发后不会在数量达到 3 张时中途停止，也不会使用封面冒充剧照。
  新增供 Avdb Magic Tools 安全读取 R18 剧照候选和缓存图片的接口。
  支持插件接口获取剧照数据
- 公钥 keyring：[`ota-signing-keyring.json`](./ota-signing-keyring.json)
<!-- AVDB-OTA-CURRENT-RELEASE:END -->

当前发布版本使用 Manifest 指定的签名密钥，双 keyring 客户端可以从旧签名版本
跨到新签名版本。

## 注意： 修改任意文件内容会使签名失效，将不能安装使用。
