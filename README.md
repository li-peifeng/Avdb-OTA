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
- Release：[`20260830-1524`](https://github.com/li-peifeng/Avdb-OTA/releases/tag/20260830-1524)
- Manifest：[`manifest.json`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260830-1524/manifest.json)
- 版本：`20260830-1524`
- 加密包：[`avdb-20260830-1524.pkg.enc`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260830-1524/avdb-20260830-1524.pkg.enc)
- 签名算法：Ed25519
- 签名 `key_id`：`2026-next`
- 加密算法：AES-256-GCM
- 更新方式：`应用内 OTA`
- 更新摘要：
  在线资源版块优化：
  修复在线资源从详情页返回列表时会回顶和定位不准的问题
  修复再次进入详情页会带入列表位置的问题
  点击磁链胶囊图标现在可直接展示磁链数据，可快捷复制下载。
  添加影片详情页只显示女演员选项（设置-个人-在线账户-Javdb卡片）
  TOP 250 支持有码，无码，FC2，欧美及年份筛选
  ----------历史更新----------
  添加 Javdb 在线资源。 原设置按钮移至更多里。
  在线播放正片；收藏；想看；Top 250，这些需要登录才会显示，可能需要VIP。
  不登录可以浏览，下载，播放预告片和使用大部分内容。
  登录请至 设置-个人-在线账户，登录 Javdb 账户。
  可单独设置 Javdb 代理例外
  图片预览组件增加方向键切换图片支持
  复制链接提示浏览器权限不够
  添加快捷复制番号的功能，点击番号胶囊或网站胶囊。
  修复在线资源从详情页返回列表时会回顶的问题
  优化统一本地资源-emby资源-在线资源的UI逻辑， 包括已入库样式，播放样式等等， 现在已入库资源点击封面上的播放按钮会直接播放 Emby 的本地资源。
  去除图片的隐藏模式，因为很多依赖图片显示的界面，隐藏模式会破坏排版。
- 公钥 keyring：[`ota-signing-keyring.json`](./ota-signing-keyring.json)
<!-- AVDB-OTA-CURRENT-RELEASE:END -->

当前发布版本使用 Manifest 指定的签名密钥，双 keyring 客户端可以从旧签名版本
跨到新签名版本。

## 注意： 修改任意文件内容会使签名失效，将不能安装使用。
