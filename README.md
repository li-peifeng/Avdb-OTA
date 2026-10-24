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
- Release：[`20261024-1603`](https://github.com/li-peifeng/Avdb-OTA/releases/tag/20261024-1603)
- Manifest：[`manifest.json`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20261024-1603/manifest.json)
- 版本：`20261024-1603`
- 加密包：[`avdb-20261024-1603.pkg.enc`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20261024-1603/avdb-20261024-1603.pkg.enc)
- 签名算法：Ed25519
- 签名 `key_id`：`2026-next`
- 加密算法：AES-256-GCM
- 更新方式：`应用内 OTA`
- 更新摘要：
  增加强制退出 TG 账号选项
  优化 Javtxt 加载可能阻塞详情页的问题
  优化监控 TG 频道的内存占用
  检测 TG 频道里的自制标签
  优化修改信息后重新匹配的逻辑
  导出添加手动匹配番号选项
  TG 监控添加清空记录和其它筛选功能
  优化 LTX 版块下载规则和工具的适配
  LTX 版块接入搜索和添加番号标识
  删除 主播精选/动漫原创/探花精选/韩国主播等版块
  优化 TG 监控取链逻辑
  降低 TG 请求速率避免引发限流
  修复 TG 监控取链由于超时卡住的问题
  增加 LTX 版块并增加导入导出的功能
  优化取链和发布速度和排版
  TG 资源监控支持自动取链功能并转发
  补全通知链接详情
  支持监控 TG 频道并自动下载资源
  支持添加企业微信群机器人通知
  优化TG Bot AI 说明和排版
- 公钥 keyring：[`ota-signing-keyring.json`](./ota-signing-keyring.json)
<!-- AVDB-OTA-CURRENT-RELEASE:END -->

当前发布版本使用 Manifest 指定的签名密钥，双 keyring 客户端可以从旧签名版本
跨到新签名版本。

## 注意： 修改任意文件内容会使签名失效，将不能安装使用。
