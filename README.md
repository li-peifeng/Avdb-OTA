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
- Release：[`20261119-1819`](https://github.com/li-peifeng/Avdb-OTA/releases/tag/20261119-1819)
- Manifest：[`manifest.json`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20261119-1819/manifest.json)
- 版本：`20261119-1819`
- 加密包：[`avdb-20261119-1819.pkg.enc`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20261119-1819/avdb-20261119-1819.pkg.enc)
- 签名算法：Ed25519
- 签名 `key_id`：`2026-next`
- 加密算法：AES-256-GCM
- 应用内 OTA 最低镜像版本：`20261118-0000`
- 更新摘要：
  修复资源标题中的 4K60 等画质和帧率标记被误拼进番号的问题。
  修复手机端左侧菜单无法向下滚动的问题。
  资源搜索接口支持用 num 参数只按番号查询。
  修复 TG 频道源帖核验反复补查历史消息、刷屏的问题，源帖全量核验完成后间隔一小时再查。
  统一影片、演员和清单订阅的未登录提示，缩短提示区域并增加与订阅卡片的间距。
  未登录 JavDB 时，订阅管理跳过在线类别请求并提示登录，本地订阅可继续使用，错误提示不再显示整页 HTML。
  降低资源包导入和设置备份的内存占用，导出边压缩边加密，发布包生成失败时保留上一版文件
  降低色花堂、X1080X 爬取和失败重爬的内存峰值，帖子分批入库，X1080X 文件大小分批回填
  降低服务启动、演员搜索和 Emby 入库匹配的内存峰值，大型库分批读取
  在线资源未登录或登录失效时隐藏类别、TOP 250、排行榜、热播和热门标签，登录后恢复显示
  修复演员映射在线更新时旧页面 ID 回填与在线映射冲突、导致整次更新失败的问题
  新增演员页面 ID 映射与 JSON 导入，浏览演员页时自动补全映射；未登录 JavDB 也可按姓名或别名搜索本地已收录演员并查看作品
  修复设置类别黑名单后，未登录或登录失效时演员订阅检查失败、误提示重新登录的问题
  优化搜索逻辑（番号/关键字）
  手动全量更新支持多选
  修正番号格式化逻辑
  资源已入库采用分层匹配：优先精确大小，磁力资源支持自定义附带文件大小容差，默认 30 MB，设为 0 关闭；容差唯一命中直接显示已入库，多版本不明确时保留同号入库，ED2K 保持严格匹配；保存 Emby 设置或完成媒体库刷新后更新资源列表状态
  修复演员信息补全按姓名查找 Emby 人物时，未找到同名演员却误用首条搜索结果的问题，避免将其他演员作为补全目标
  修复直接发送 ED2K 或磁力链接给 TG 机器人下载后未显示已下载的问题，按资源 hash 匹配已有资源，ED2K 同时核对文件大小，失败提交不标记已下载
  TG 频道检查时间、来源删除核验游标和导出内容快照持久保存，更新重启后接续未完成任务，已完成且内容未变的资源不重复自动导出；资源导出计数按等待、已处理、异常分别统计
- 公钥 keyring：[`ota-signing-keyring.json`](./ota-signing-keyring.json)
<!-- AVDB-OTA-CURRENT-RELEASE:END -->

当前发布版本使用 Manifest 指定的签名密钥，双 keyring 客户端可以从旧签名版本
跨到新签名版本。

## 注意： 修改任意文件内容会使签名失效，将不能安装使用。
