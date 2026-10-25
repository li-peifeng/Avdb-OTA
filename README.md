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
- Release：[`20261025-0315`](https://github.com/li-peifeng/Avdb-OTA/releases/tag/20261025-0315)
- Manifest：[`manifest.json`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20261025-0315/manifest.json)
- 版本：`20261025-0315`
- 加密包：[`avdb-20261025-0315.pkg.enc`](https://github.com/li-peifeng/Avdb-OTA/releases/download/20261025-0315/avdb-20261025-0315.pkg.enc)
- 签名算法：Ed25519
- 签名 `key_id`：`2026-next`
- 加密算法：AES-256-GCM
- 更新方式：`应用内 OTA`
- 更新摘要：
  补全 FT.A.V 的原盘/原档标签
  添加 FT.A.V 资源站点
  频道监控及导出同步支持 FT.A.V
  在线资源同步展示 LTX 破解版块资源
  订阅破解模式支持只限 LTX 和优先模式
  修复 LTX 导出：部分链接来源或番号不一致的警告问题
  修复CD2下载LTX版块提示接口返回异常的问题
  自动发现类订阅可按分类独立创建自定义下载目录
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
- 公钥 keyring：[`ota-signing-keyring.json`](./ota-signing-keyring.json)
<!-- AVDB-OTA-CURRENT-RELEASE:END -->

当前发布版本使用 Manifest 指定的签名密钥，双 keyring 客户端可以从旧签名版本
跨到新签名版本。

## 注意： 修改任意文件内容会使签名失效，将不能安装使用。
