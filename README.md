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
- Release：[`20260903-1553`](https://github.com/li-peifeng/Avdb-OTA/releases/tag/20260903-1553)
- Manifest：[`manifest.json`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260903-1553/manifest.json)
- 版本：`20260903-1553`
- 加密包：[`avdb-20260903-1553.pkg.enc`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260903-1553/avdb-20260903-1553.pkg.enc)
- 签名算法：Ed25519
- 签名 `key_id`：`2026-next`
- 加密算法：AES-256-GCM
- 更新方式：`应用内 OTA`
- 更新摘要：
  添加批量操作订阅内容的功能。
  添加了订阅检查会显示检查进度和手动停止的接口。
  订阅窗口类别过滤下拉菜单增加搜索过滤（限定5个可选项）。
  修改订阅默认规则后可直接同步修改后的配置到目前的订阅。
  修复订阅窗口文字悬停颜色。
  现已支持全部类型的收藏订阅（演员/番号/厂商/系列/清单）。
- 公钥 keyring：[`ota-signing-keyring.json`](./ota-signing-keyring.json)
<!-- AVDB-OTA-CURRENT-RELEASE:END -->

当前发布版本使用 Manifest 指定的签名密钥，双 keyring 客户端可以从旧签名版本
跨到新签名版本。

## 注意： 修改任意文件内容会使签名失效，将不能安装使用。
