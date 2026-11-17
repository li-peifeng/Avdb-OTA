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
- Release：[`20261117-0147`](https://github.com/li-peifeng/Avdb-OTA/releases/tag/20261117-0147)
- Manifest：[`manifest.json`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20261117-0147/manifest.json)
- 版本：`20261117-0147`
- 加密包：[`avdb-20261117-0147.pkg.enc`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20261117-0147/avdb-20261117-0147.pkg.enc)
- 签名算法：Ed25519
- 签名 `key_id`：`2026-next`
- 加密算法：AES-256-GCM
- 更新方式：`应用内 OTA`
- 更新摘要：
  新增演员页面 ID 映射与 JSON 导入，浏览演员页时自动补全映射；未登录 JavDB 也可按姓名或别名搜索本地已收录演员并查看作品
  修复设置类别黑名单后，未登录或登录失效时演员订阅检查失败、误提示重新登录的问题
  优化搜索逻辑（番号/关键字）
  手动全量更新支持多选
  修正番号格式化逻辑
  资源已入库采用分层匹配：优先精确大小，磁力资源支持自定义附带文件大小容差，默认 30 MB，设为 0 关闭；容差唯一命中直接显示已入库，多版本不明确时保留同号入库，ED2K 保持严格匹配；保存 Emby 设置或完成媒体库刷新后更新资源列表状态
  修复演员信息补全按姓名查找 Emby 人物时，未找到同名演员却误用首条搜索结果的问题，避免将其他演员作为补全目标
  修复直接发送 ED2K 或磁力链接给 TG 机器人下载后未显示已下载的问题，按资源 hash 匹配已有资源，ED2K 同时核对文件大小，失败提交不标记已下载
  TG 频道检查时间、来源删除核验游标和导出内容快照持久保存，更新重启后接续未完成任务，已完成且内容未变的资源不重复自动导出；资源导出计数按等待、已处理、异常分别统计
  TG 频道源帖删除后，按具体资源指纹同步移除对应导出资源，保留同番号其它版本及仍有有效来源的资源；支持离线补查，后续增量包和全量包同步携带删除标记
  未登录 JAVDB 也可以进行演员订阅
  优化未登录时禁止再去探测在线影片详情页
  资源卡片和预览封面按 R18 → 原图 → JavDB 逐个尝试，全部候选失效后卡片才显示默认图；保留原封面及 TG 频道原图，已导出资源的 R18 图片失效时自动回退频道原图和 JavDB
  TG 用户账号退出或强制退出时，可分别选择保留取链记录、发布记录和处理记录，默认全部保留，并保留对应去重信息
  所有影片订阅统一支持未登录或登录失效时匹配本地资源；登录有效时按资源来源开关和优先级查询在线磁链及评论区资源，登录失效不再阻断本地影片订阅检查，演员作品列表仍匿名获取
  演员订阅通过公开列表获取番号，未登录或登录失效时照常匹配本地资源，登录有效时按资源来源开关和优先级匹配本地、在线磁链及评论区资源；分类过滤、动态目录与完成通知无需额外请求影片详情
  修复 TG 监控图片展示问题
  同步支持 NGi 的 strm Size 提取和匹配
  修复 actor 订阅动态路径报错
  修复 115 订阅使用“目录 CID/{actor}”等动态子目录时被误判为下载目录无效的问题
- 公钥 keyring：[`ota-signing-keyring.json`](./ota-signing-keyring.json)
<!-- AVDB-OTA-CURRENT-RELEASE:END -->

当前发布版本使用 Manifest 指定的签名密钥，双 keyring 客户端可以从旧签名版本
跨到新签名版本。

## 注意： 修改任意文件内容会使签名失效，将不能安装使用。
