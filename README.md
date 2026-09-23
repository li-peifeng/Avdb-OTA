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
- Release：[`20260923-1218`](https://github.com/li-peifeng/Avdb-OTA/releases/tag/20260923-1218)
- Manifest：[`manifest.json`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260923-1218/manifest.json)
- 版本：`20260923-1218`
- 加密包：[`avdb-20260923-1218.pkg.enc`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260923-1218/avdb-20260923-1218.pkg.enc)
- 签名算法：Ed25519
- 签名 `key_id`：`2026-next`
- 加密算法：AES-256-GCM
- 更新方式：`应用内 OTA`
- 更新摘要：
  添加订阅同步配置（完成/新增/删除/想看/看过）。
  添加订阅资源优先级排序。
  优化演员映射表更新逻辑，避免如果进行过手动导入后在线更新依旧使用旧数据的问题。
  添加 JavDB Authorization 登录方式。
  在线资源搜索弹窗下拉列表样式优化。
  修复115重新扫码显示错误的问题。
  优化运行日志的显示逻辑，修复偶发导致网页崩溃的问题。
  添加快捷订阅，不弹窗直接使用预设值订阅。
  优化订阅保存与编辑流程。
  影片/演员下添加批量选择/删除/启用/暂停的选项。
  预览图片时可切换源图/剧照模式。
  优化演员头像补全的逻辑。
  优化在线资源的地址栏固化。
  修复欧美和FC2番号请求错误引起服务器异常提示的问题。
  优化在线资源的演员简介，从演员映射表补全。
  修复 Emby 设置开关逻辑。
  优化在线资源详情页的操作按钮显示。
  无头像演员添加一键补全功能。
  重名演员管理添加全选推荐命名按钮和一键全部应用推荐的选项。
  编辑订阅时可直接标记已完成或删除订阅。
- 公钥 keyring：[`ota-signing-keyring.json`](./ota-signing-keyring.json)
<!-- AVDB-OTA-CURRENT-RELEASE:END -->

当前发布版本使用 Manifest 指定的签名密钥，双 keyring 客户端可以从旧签名版本
跨到新签名版本。

## 注意： 修改任意文件内容会使签名失效，将不能安装使用。
