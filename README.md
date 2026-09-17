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
- Release：[`20260917-1651`](https://github.com/li-peifeng/Avdb-OTA/releases/tag/20260917-1651)
- Manifest：[`manifest.json`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260917-1651/manifest.json)
- 版本：`20260917-1651`
- 加密包：[`avdb-20260917-1651.pkg.enc`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260917-1651/avdb-20260917-1651.pkg.enc)
- 签名算法：Ed25519
- 签名 `key_id`：`2026-next`
- 加密算法：AES-256-GCM
- 更新方式：`应用内 OTA`
- 更新摘要：
  优化演员头像补全的逻辑。
  优化在线资源的地址栏固化。
  修复欧美和FC2番号请求错误引起服务器异常提示的问题。
  优化在线资源的演员简介，从演员映射表补全。
  修复 Emby 设置开关逻辑。
  优化在线资源详情页的操作按钮显示。
  无头像演员添加一键补全功能。
  重名演员管理添加全选推荐命名按钮和一键全部应用推荐的选项。
  编辑订阅时可直接标记已完成或删除订阅。
  优化订阅对 -U; -C; -UC; restored; 4k60fps的匹配逻辑。
  补全在线资源入库标识。
  修复后台挂起后的服务器异常，优化评分获取逻辑。
  新增了“资源更新通知”开关。
  Telegram Bot 添加资源搜索，可添加到 TG 群。
  黑名单匹配和规则添加位数支持，单个 * 代表任意内容位数，多个 * 代表严格匹配多位数。
  修复对所有 textarea 强制单行高度的问题.
  优化已入库的匹配逻辑，加快显示速度。
  修复检查订阅时可能出现只显示父订阅，而不显示实际影片的进度以及数据库连接池耗尽和 SQLite 写锁的问题。
  优化订阅判定逻辑，并支持本地磁力资源参与匹配。
  修复 X1080X 的带 0 补全齐番号的匹配问题。
- 公钥 keyring：[`ota-signing-keyring.json`](./ota-signing-keyring.json)
<!-- AVDB-OTA-CURRENT-RELEASE:END -->

当前发布版本使用 Manifest 指定的签名密钥，双 keyring 客户端可以从旧签名版本
跨到新签名版本。

## 注意： 修改任意文件内容会使签名失效，将不能安装使用。
