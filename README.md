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
- Release：[`20261109-1955`](https://github.com/li-peifeng/Avdb-OTA/releases/tag/20261109-1955)
- Manifest：[`manifest.json`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20261109-1955/manifest.json)
- 版本：`20261109-1955`
- 加密包：[`avdb-20261109-1955.pkg.enc`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20261109-1955/avdb-20261109-1955.pkg.enc)
- 签名算法：Ed25519
- 签名 `key_id`：`2026-next`
- 加密算法：AES-256-GCM
- 更新方式：`应用内 OTA`
- 更新摘要：
  可选调整订阅已入库检查媒体库范围
  添加筛选 “已入库”的“媒体库”选项
  修复资源被误判已删除的逻辑漏洞，会重置已删除标识
  统一同号入库角标交互和显示媒体库名
  修复增量资源包立即更新的卡住问题
  修复手机端 TOTP 粘贴只有最后一位的问题
  修复左侧菜单被筛选弹窗遮盖丢失鼠标点击的问题
  优化登录时密码管理器的兼容性
  已下载/已入库 添加更严格的匹配条件
  演员订阅采用“记住用户删除选择”的方案
  下载记录保存网站、板块和资源身份快照
  资源卡片按具体资源判断“已下载”标识
  修复全量包发布的逻辑，添加按时发送的选项
  优化 TG 监控登录
  优化 Emby 加载速度
  修复 TG 监控推送历史消息
  可保存 X1080X 用户信息，登录失效时自动尝试
  添加下载记录可重新提交功能
  筛选中的「类目」现在支持：
  LTX 版块：98T、自制
- 公钥 keyring：[`ota-signing-keyring.json`](./ota-signing-keyring.json)
<!-- AVDB-OTA-CURRENT-RELEASE:END -->

当前发布版本使用 Manifest 指定的签名密钥，双 keyring 客户端可以从旧签名版本
跨到新签名版本。

## 注意： 修改任意文件内容会使签名失效，将不能安装使用。
