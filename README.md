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
- Release：[`20260901-1151`](https://github.com/li-peifeng/Avdb-OTA/releases/tag/20260901-1151)
- Manifest：[`manifest.json`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260901-1151/manifest.json)
- 版本：`20260901-1151`
- 加密包：[`avdb-20260901-1151.pkg.enc`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260901-1151/avdb-20260901-1151.pkg.enc)
- 签名算法：Ed25519
- 签名 `key_id`：`2026-next`
- 加密算法：AES-256-GCM
- 更新方式：`应用内 OTA`
- 更新摘要：
  添加订阅功能，支持影片/演员
  优化内存占用
  在线资源影片详情页缺失简介补全
  优化演员订阅逻辑
  -----历史更新-----
  优化个人页各页面的跳转逻辑
  修复详情页返回列表时定位不准的问题
  完善接口的查询逻辑
  修复 top 250 分类筛选没有生效的问题
  修复Chrome下翻页后不回顶的问题
  影片详情页添加相关清单的功能
  优化卡片封面显示效果，改成从右上放大
  修复在线资源从详情页返回列表时会回顶和定位不准的问题
  在线资源修复再次进入详情页会带入列表位置的问题
  点击磁链胶囊图标现在可直接展示磁链数据，可快捷复制下载。
  在线资源添加影片详情页只显示女演员选项（设置-个人-在线账户-Javdb卡片）
  在线资源TOP 250 支持有码，无码，FC2，欧美及年份筛选
- 公钥 keyring：[`ota-signing-keyring.json`](./ota-signing-keyring.json)
<!-- AVDB-OTA-CURRENT-RELEASE:END -->

当前发布版本使用 Manifest 指定的签名密钥，双 keyring 客户端可以从旧签名版本
跨到新签名版本。

## 注意： 修改任意文件内容会使签名失效，将不能安装使用。
