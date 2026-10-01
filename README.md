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
- Release：[`20261001-1426`](https://github.com/li-peifeng/Avdb-OTA/releases/tag/20261001-1426)
- Manifest：[`manifest.json`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20261001-1426/manifest.json)
- 版本：`20261001-1426`
- 加密包：[`avdb-20261001-1426.pkg.enc`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20261001-1426/avdb-20261001-1426.pkg.enc)
- 签名算法：Ed25519
- 签名 `key_id`：`2026-next`
- 加密算法：AES-256-GCM
- 更新方式：`应用内 OTA`
- 更新摘要：
  添加爬取任务独立通知开关。
  添加 Telegram Bot 图片遮罩开关，可分别设置私聊和群聊。
  添加订阅成功项批量删除功能，删除后可重新下载。
  添加订阅影片/成功页面搜索筛选功能。
  类别改成真实 ID 显示，避免序号造成歧义。
  补全影片筛选标签。
  移除分类/标签搜索，添加导演搜索。
  添加订阅链接类型选项。
  修复下载记录对手动下载的详情缺失。
  修复订阅对评论区资源 ED2K 的匹配问题。
  新增订阅优先模式，按条件优选下载（高清+中文+破解选择 > 高清+中文 > 高清）。
  修复订阅磁链编码问题。
  添加本地字幕目录配置选项，仅用于显示本地匹配的字幕。
  增加 Telegram Bot 接受指令开关，可接受 /a, /s, 并支持解析磁力和 ED2K 链接。
  搜索结果增加结果筛选。
  修复收藏清单显示错误的问题。
  添加订阅同步配置（完成/新增/删除/想看/看过）。
  添加订阅资源优先级排序。
  优化演员映射表更新逻辑，避免如果进行过手动导入后在线更新依旧使用旧数据的问题。
  添加 JavDB Authorization 登录方式。
- 公钥 keyring：[`ota-signing-keyring.json`](./ota-signing-keyring.json)
<!-- AVDB-OTA-CURRENT-RELEASE:END -->

当前发布版本使用 Manifest 指定的签名密钥，双 keyring 客户端可以从旧签名版本
跨到新签名版本。

## 注意： 修改任意文件内容会使签名失效，将不能安装使用。
