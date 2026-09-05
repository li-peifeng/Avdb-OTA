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
- Release：[`20260905-1747`](https://github.com/li-peifeng/Avdb-OTA/releases/tag/20260905-1747)
- Manifest：[`manifest.json`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260905-1747/manifest.json)
- 版本：`20260905-1747`
- 加密包：[`avdb-20260905-1747.pkg.enc`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260905-1747/avdb-20260905-1747.pkg.enc)
- 签名算法：Ed25519
- 签名 `key_id`：`2026-next`
- 加密算法：AES-256-GCM
- 更新方式：`应用内 OTA`
- 更新摘要：
  固化Emby Tab地址状态
  添加在线资源影片详情页的标签点击筛选跳转，系列/厂商/导演跳转至专用页。
  添加导演的收藏/订阅。
  修复订阅演员类别过滤的ID覆盖问题。
  优化入库判定逻辑和速度。
  添加账户VIP检测，非VIP不显示正片播放按钮。
  最新版块添加磁链更新，发布日期排序。
  添加类别标签。
  修复在线资源搜索弹窗在移动端被遮挡的问题。
  优化评论区资源提取。
  订阅严格模式破解需要明确选择，未选中时不进入匹配，高清可以匹配UHD/4K。
  修复番号搜索的问题。
  已支持影片详情里关联影片的订阅。
  已支持清单搜索和订阅。
  修复收藏的演员只能显示50个，并且没有翻页选项的问题。
  修复导入dbo 的订阅分享时演员头像不显示问题。
  修复部分按钮浅色模式撞色的问题。
  磁力资源添加排序选项，支持日期大小，文件数。
  修复 Gfriends 文件树 CDN 下载失败的问题，以后将通过 Release 提供。
  添加演员页。
- 公钥 keyring：[`ota-signing-keyring.json`](./ota-signing-keyring.json)
<!-- AVDB-OTA-CURRENT-RELEASE:END -->

当前发布版本使用 Manifest 指定的签名密钥，双 keyring 客户端可以从旧签名版本
跨到新签名版本。

## 注意： 修改任意文件内容会使签名失效，将不能安装使用。
