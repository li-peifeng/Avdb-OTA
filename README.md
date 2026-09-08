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
- Release：[`20260908-1652`](https://github.com/li-peifeng/Avdb-OTA/releases/tag/20260908-1652)
- Manifest：[`manifest.json`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260908-1652/manifest.json)
- 版本：`20260908-1652`
- 加密包：[`avdb-20260908-1652.pkg.enc`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260908-1652/avdb-20260908-1652.pkg.enc)
- 签名算法：Ed25519
- 签名 `key_id`：`2026-next`
- 加密算法：AES-256-GCM
- 更新方式：`应用内 OTA`
- 更新摘要：
  优化欧美资源的番号提取和 Emby/JavDB 匹配。
  修复 115/迅雷的动态目录下载路径问题。
  qb 添加 Avdb 分类标识。
  添加已入库自动完成开关，打开后不再检查已入库媒体。
  现可在设置-个人里自定义菜单内容，可按个人喜好进行排序和开关选项。
  侧边栏和底部导航栏添加订阅管理快捷入口。
  修复媒体库数量和 emby 里库实际数量对不上的问题。
  订阅成功通知添加订阅模式和筛选条件的详情。
  手动删除订阅影片会自动加入例外黑名单，上级重新检查时不再重新订阅。
  修复剧照，封面扩展名和实际图片类型不一致引起的错误。
  优化插件的同源策略，避免被Emby 的 CSP 拦截。
  添加多彩开关，可选素色和多彩模式（素色减少彩色效果）。
  剧照补全改用Javdb，R18 只用来获取高清海报和封面。
  统一修复“列表 → 详情 → 返回”的桌面端滚动恢复问题，覆盖在线资源、资源模式、Emby 模式、演员列表及影片详情中的演员入口。
  订阅管理里的影片订阅也加入入库角标。
  固化Emby Tab地址状态。
  添加在线资源影片详情页的标签点击筛选跳转，系列/厂商/导演跳转至专用页。
  添加导演的收藏/订阅。
  修复订阅演员类别过滤的ID覆盖问题。
  优化入库判定逻辑和速度。
- 公钥 keyring：[`ota-signing-keyring.json`](./ota-signing-keyring.json)
<!-- AVDB-OTA-CURRENT-RELEASE:END -->

当前发布版本使用 Manifest 指定的签名密钥，双 keyring 客户端可以从旧签名版本
跨到新签名版本。

## 注意： 修改任意文件内容会使签名失效，将不能安装使用。
