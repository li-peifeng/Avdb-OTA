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
- Release：[`20260826-0233`](https://github.com/li-peifeng/Avdb-OTA/releases/tag/20260826-0233)
- Manifest：[`manifest.json`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260826-0233/manifest.json)
- 版本：`20260826-0233`
- 加密包：[`avdb-20260826-0233.pkg.enc`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20260826-0233/avdb-20260826-0233.pkg.enc)
- 签名算法：Ed25519
- 签名 `key_id`：`2026-next`
- 加密算法：AES-256-GCM
- 更新方式：`应用内 OTA`
- 更新摘要：
  R18 数据库支持增量更新，支持 Gitee 下载
  优化资源库导出并上传仓库的流程
  修复 Gfriends 和 Jalbum 可能没有走代理的问题
  计划任务里的（批量海报/封面/剧照 补全任务）已拆开两个（批量海报/封面 补全任务）和（批量剧照补全任务），并且插件设置里的海报，封面，剧照覆盖开关都已独立分开
  轮播图在宽屏上主图宽度不变的情况下加大高度，避免海报裁减严重，并提供3档高度选择
  修复首页轮播图点击打开的资源不能复制的问题
- 公钥 keyring：[`ota-signing-keyring.json`](./ota-signing-keyring.json)
<!-- AVDB-OTA-CURRENT-RELEASE:END -->

当前发布版本使用 Manifest 指定的签名密钥，双 keyring 客户端可以从旧签名版本
跨到新签名版本。

## 注意： 修改任意文件内容会使签名失效，将不能安装使用。
