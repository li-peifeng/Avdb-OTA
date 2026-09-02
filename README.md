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
- Release：[`20260903-0016`](https://github.com/li-peifeng/Avdb-OTA/releases/tag/20260903-0016)
- Manifest：[`manifest.json`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260903-0016/manifest.json)
- 版本：`20260903-0016`
- 加密包：[`avdb-20260903-0016.pkg.enc`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260903-0016/avdb-20260903-0016.pkg.enc)
- 签名算法：Ed25519
- 签名 `key_id`：`2026-next`
- 加密算法：AES-256-GCM
- 更新方式：`应用内 OTA`
- 更新摘要：
  添加 Telegram/Wechat 订阅成功通知
  优化订阅尺寸的匹配逻辑比如：资源的 4K、字幕、无码属性都相同，并且都符合订阅配置的大小范围时，会比较文件大小。5GB～15GB 范围内会选择 14GB，而不是列表中的第一个 6GB。
  图片显示模式现在改为数据库持久化。
  添加评论区链接提取功能。
  添加订阅导入导出选项，支持 DBO 导出的分享码。
  在线资源卡片下显示评论胶囊按钮，可快速查看影片评论。
  修复 CD2 下载成功但提示接口返回异常的问题。
  可自定义 JavDB 网页/API 镜像站地址。
  订阅支持影片/演员/系列/排行榜/TOP 250。
  收藏功能现支持影片/演员/系列。
  系列信息支持收藏/订阅。
  订阅可手动/自动选择下载工具和目录。
  优化内存占用。
  在线资源影片详情页缺失简介补全。
  优化演员订阅逻辑。
  所有资源卡片支持鼠标中键点击。
  修复Safari 侧边栏模式不能收缩的问题。
  各种 UI 小优化。
- 公钥 keyring：[`ota-signing-keyring.json`](./ota-signing-keyring.json)
<!-- AVDB-OTA-CURRENT-RELEASE:END -->

当前发布版本使用 Manifest 指定的签名密钥，双 keyring 客户端可以从旧签名版本
跨到新签名版本。

## 注意： 修改任意文件内容会使签名失效，将不能安装使用。
