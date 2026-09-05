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
- Release：[`20260905-0956`](https://github.com/li-peifeng/Avdb-OTA/releases/tag/20260905-0956)
- Manifest：[`manifest.json`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260905-0956/manifest.json)
- 版本：`20260905-0956`
- 加密包：[`avdb-20260905-0956.pkg.enc`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260905-0956/avdb-20260905-0956.pkg.enc)
- 签名算法：Ed25519
- 签名 `key_id`：`2026-next`
- 加密算法：AES-256-GCM
- 更新方式：`应用内 OTA`
- 更新摘要：
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
  优化筛选类型和日期的显示菜单。
  优化最新影片的显示逻辑，可按磁链，字幕排序。
  订阅时可自定义下载工具和路径，编辑演员、系列、片商、清单、番号类会同步修改全部订阅。
  评论按钮不再显示总数，只轻量探测是否有评论来决定是否显示评论胶囊，弹窗和进入详情页依旧显示。
  添加批量操作订阅内容的功能。
  添加了订阅检查会显示检查进度和手动停止的接口。
  订阅窗口类别过滤下拉菜单增加搜索过滤（限定5个可选项）。
- 公钥 keyring：[`ota-signing-keyring.json`](./ota-signing-keyring.json)
<!-- AVDB-OTA-CURRENT-RELEASE:END -->

当前发布版本使用 Manifest 指定的签名密钥，双 keyring 客户端可以从旧签名版本
跨到新签名版本。

## 注意： 修改任意文件内容会使签名失效，将不能安装使用。
