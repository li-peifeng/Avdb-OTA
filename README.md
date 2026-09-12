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
- Release：[`20260912-1755`](https://github.com/li-peifeng/Avdb-OTA/releases/tag/20260912-1755)
- Manifest：[`manifest.json`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260912-1755/manifest.json)
- 版本：`20260912-1755`
- 加密包：[`avdb-20260912-1755.pkg.enc`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260912-1755/avdb-20260912-1755.pkg.enc)
- 签名算法：Ed25519
- 签名 `key_id`：`2026-next`
- 加密算法：AES-256-GCM
- 更新方式：`应用内 OTA`
- 更新摘要：
  Telegram Bot 添加资源搜索，可添加到 TG 群。
  黑名单匹配和规则添加位数支持，单个 * 代表任意内容位数，多个 * 代表严格匹配多位数。
  修复对所有 textarea 强制单行高度的问题.
  优化已入库的匹配逻辑，加快显示速度。
  修复检查订阅时可能出现只显示父订阅，而不显示实际影片的进度以及数据库连接池耗尽和 SQLite 写锁的问题。
  优化订阅判定逻辑，并支持本地磁力资源参与匹配。
  修复 X1080X 的带 0 补全齐番号的匹配问题。
  完善下载记录，支持订阅的下载推送记录和筛选。
  默认规则里的下载工具和下载路径修改为全局设置，原设置订阅里选项的已删除。
  修复订阅/编辑时选择浏览自定义下载目录时不生效的问题。
  首页添加影片/演员订阅状态统计。
  Emby和在线资源列表和详情上添加评分显示。
  订阅管理全部页面都进行地址固化，防止返回退回第一页的情况。
  添加订阅调度开关，关闭后只支持手动检查订阅，关闭时也会跳过自动想看同步、排行榜和 TOP 250 的定时任务；这些功能的手动接口仍然保留。
  同步支持 Emby 调用 Javdb 评分。
  Emby 模式添加独立入口，可添加到侧边和底部导航栏。
  添加 Telegram AI 助手，可自然语言对话进行查询，下载，订阅。
  优化写真的 CDN 加载，404 时尝试其它 CDN。
  优化欧美资源的番号提取和 Emby/JavDB 匹配。
  修复 115/迅雷的动态目录下载路径问题。
- 公钥 keyring：[`ota-signing-keyring.json`](./ota-signing-keyring.json)
<!-- AVDB-OTA-CURRENT-RELEASE:END -->

当前发布版本使用 Manifest 指定的签名密钥，双 keyring 客户端可以从旧签名版本
跨到新签名版本。

## 注意： 修改任意文件内容会使签名失效，将不能安装使用。
