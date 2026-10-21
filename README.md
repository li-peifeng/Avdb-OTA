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
- Release：[`20261021-1825`](https://github.com/li-peifeng/Avdb-OTA/releases/tag/20261021-1825)
- Manifest：[`manifest.json`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20261021-1825/manifest.json)
- 版本：`20261021-1825`
- 加密包：[`avdb-20261021-1825.pkg.enc`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20261021-1825/avdb-20261021-1825.pkg.enc)
- 签名算法：Ed25519
- 签名 `key_id`：`2026-next`
- 加密算法：AES-256-GCM
- 更新方式：`Docker 镜像`
- 需要更新镜像的文件：`requirements.txt`
- 更新摘要：
  • 支持监控 TG 频道并自动下载资源
  • 支持添加企业微信群机器人通知
  • 优化TG Bot AI 说明和排版
  • X1080X 默认域名改成 x999x.me，国内用户可手动修改至 1080xin.com
  • 修复 R18 因容器意外重启残留临时文件的回收问题
  • 修复 Top 250 订阅选择特定年份时被默认订阅规则约束而发现不了资源的问题
  • 通知支持 Bark
  • 强化 AI 助手自然语言功能
  • 卡片角标显示下载状态
  • 在线资源影片卡片支持添加多选订阅
  • 在线演员关联影片添加排序选项
  • 增加 JavDB 新种订阅
  • 修复 TRAWL sessionId 格式问题
  • 修复 AVDB 向 TRAWL 发送了合法的 sessionId，但没有先创建这个会话的问题
  • 优化演员订阅标签滚动
  • 为订阅编辑添加完成和删除按钮逻辑
  • 修复一些 UI 溢出的小问题
  • 扩展演员头像可选写真内容
  • 修复 core dump 影响启动的问题
  • 订阅下载过滤评论区未验证番号资源
- 公钥 keyring：[`ota-signing-keyring.json`](./ota-signing-keyring.json)
<!-- AVDB-OTA-CURRENT-RELEASE:END -->

当前发布版本使用 Manifest 指定的签名密钥，双 keyring 客户端可以从旧签名版本
跨到新签名版本。

## 注意： 修改任意文件内容会使签名失效，将不能安装使用。
