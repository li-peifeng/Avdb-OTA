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
- Release：[`20261103-0258`](https://github.com/li-peifeng/Avdb-OTA/releases/tag/20261103-0258)
- Manifest：[`manifest.json`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20261103-0258/manifest.json)
- 版本：`20261103-0258`
- 加密包：[`avdb-20261103-0258.pkg.enc`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20261103-0258/avdb-20261103-0258.pkg.enc)
- 签名算法：Ed25519
- 签名 `key_id`：`2026-next`
- 加密算法：AES-256-GCM
- 更新方式：`应用内 OTA`
- 更新摘要：
  修复在线的收藏页面分页记忆
  修复 TG 监控的 BOT 权限，避免影响源内容
  修复 LTX 和 FT.A.V 丢失番号的问题，升级后请重新刷新一次番号
  添加 X1080X 登录选项，并适配新改版的页面爬取，由于网站采用了浏览器指纹验证，重启 trawl 后需要重新登录
  更新TG监控资源导出格式化规则
  优化数据库文章查询索引
  添加 LTX 版块的#98T和#自制标签
  分离 LTX 版块的更新和发布流程
  优化TG监控发布去重逻辑和4K标签传参
  添加取链番号名称格式化选项
  优化 TG API 的会话逻辑
  修复番号核对并发布取链结果
  自动更新添加立即更新的选项
  订阅规则添加网站站点选项
  修复一些 UI 小问题，调整标签显示效果
  首页卡片排序优化
  海报和轮播图跟随开关维护，关闭的情况下不再主动互取
  补全 FT.A.V 的原盘/原档标签
  添加 FT.A.V 资源站点
  频道监控及导出同步支持 FT.A.V
- 公钥 keyring：[`ota-signing-keyring.json`](./ota-signing-keyring.json)
<!-- AVDB-OTA-CURRENT-RELEASE:END -->

当前发布版本使用 Manifest 指定的签名密钥，双 keyring 客户端可以从旧签名版本
跨到新签名版本。

## 注意： 修改任意文件内容会使签名失效，将不能安装使用。
