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
- Release：[`20261114-1626`](https://github.com/li-peifeng/Avdb-OTA/releases/tag/20261114-1626)
- Manifest：[`manifest.json`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20261114-1626/manifest.json)
- 版本：`20261114-1626`
- 加密包：[`avdb-20261114-1626.pkg.enc`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20261114-1626/avdb-20261114-1626.pkg.enc)
- 签名算法：Ed25519
- 签名 `key_id`：`2026-next`
- 加密算法：AES-256-GCM
- 更新方式：`应用内 OTA`
- 更新摘要：
  修复演员信息补全按姓名查找 Emby 人物时，未找到同名演员却误用首条搜索结果的问题，避免将其他演员作为补全目标
  修复直接发送 ED2K 或磁力链接给 TG 机器人下载后未显示已下载的问题，按资源 hash 匹配已有资源，ED2K 同时核对文件大小，失败提交不标记已下载
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
  修复 TG 监控由于带有 ：号而漏提取标题的问题
  修复 TG 监控导出将 R18 小图误判为有效图片、跳过频道原图，导致资源图片预览为空的问题；重新导出会重新校验旧图片缓存
  调整 TG 频道监控导出流程，番号、标题、标签从频道提取，图片按 R18 → 频道图片 → JavDB 的顺序补充，缺图不再影响信息齐全的资源导出
  资源图片优先使用 R18 高清封面、海报和剧照，无高清图时保留有效的 800 像素封面，过滤占位图及小于 30KiB 的图片；修复同番号 DVD 记录遮挡数字版大图及频道资源跳过补全的问题，JavDB 登录失效后暂停图片兜底，重新登录后恢复
  修复图片预览首张图片失效时停留空白的问题，自动选择后续有效图片，并过滤 JavDB 兜底列表中无效的 R18 封面
  定时订阅执行中检测到 JavDB 强制登录或登录失效，会中止本轮检查、暂停后续 JavDB 订阅调度，并通过系统已启用的通知渠道推送提醒
  可选调整订阅已入库检查媒体库范围
- 公钥 keyring：[`ota-signing-keyring.json`](./ota-signing-keyring.json)
<!-- AVDB-OTA-CURRENT-RELEASE:END -->

当前发布版本使用 Manifest 指定的签名密钥，双 keyring 客户端可以从旧签名版本
跨到新签名版本。

## 注意： 修改任意文件内容会使签名失效，将不能安装使用。
