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
- Release：[`20261106-1836`](https://github.com/li-peifeng/Avdb-OTA/releases/tag/20261106-1836)
- Manifest：[`manifest.json`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20261106-1836/manifest.json)
- 版本：`20261106-1836`
- 加密包：[`avdb-20261106-1836.pkg.enc`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20261106-1836/avdb-20261106-1836.pkg.enc)
- 签名算法：Ed25519
- 签名 `key_id`：`2026-next`
- 加密算法：AES-256-GCM
- 更新方式：`应用内 OTA`
- 更新摘要：
  修复全量包发布的逻辑，添加按时发送的选项
  优化 TG 监控登录
  优化 Emby 加载速度
  修复 TG 监控推送历史消息
  可保存 X1080X 用户信息，登录失效时自动尝试
  添加下载记录可重新提交功能
  筛选中的「类目」现在支持：
  LTX 版块：98T、自制
  FT.A.V 版块：原档、破解
  支持 NGi 自定义演员映射表，并应用相同的演员命名逻辑
  按站点拆分资源库发布绑定
  修复在线的收藏页面分页记忆
  修复 TG 监控的 BOT 权限，避免影响源内容
  修复 LTX 和 FT.A.V 丢失番号的问题，升级后请重新刷新一次番号
  添加 X1080X 登录选项，并适配新改版的页面爬取，由于网站采用了浏览器指纹验证，重启 trawl 后需要重新登录
  更新TG监控资源导出格式化规则
  优化数据库文章查询索引
  添加 LTX 版块的#98T和#自制标签
  分离 LTX 版块的更新和发布流程
  优化TG监控发布去重逻辑和4K标签传参
- 公钥 keyring：[`ota-signing-keyring.json`](./ota-signing-keyring.json)
<!-- AVDB-OTA-CURRENT-RELEASE:END -->

当前发布版本使用 Manifest 指定的签名密钥，双 keyring 客户端可以从旧签名版本
跨到新签名版本。

## 注意： 修改任意文件内容会使签名失效，将不能安装使用。
