## Shadowrocket（项目简介）

本项目由 [Pomelo520](https://t.me/Pomelo520) 维护，提供 Shadowrocket 的配置文件与模块集合，便于在 iOS 上使用与管理。  
若本项目对您有帮助，欢迎 Star；如有问题或需求，请提交 Issues。

---

### 重要声明
- 请勿在中国大陆的任意平台传播此项目。  
- 禁止将本项目内容用于违法或营利用途。  
- 本项目仅供学习、研究与测试，使用者须自行承担使用风险。  
如认为本项目侵权或不希望被收录，请提交 Issue，我们会及时处理。

---

### 配置文件（概览）
- 默认使用加密的 DoH/DoT 解析并对未加密 DNS 请求加密转发。  
- 系统服务（Apple / Microsoft / Google 等）采用单独分流规则以避免冲突。  
- 海外主流 AI 平台、微信、Telegram 等有独立分流策略以保障稳定性。  
- 规则来源：基于 [blackmatrix7 的规则集](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Shadowrocket)，由 GitHub Actions 自动同步更新。

**快速安装（在手机上打开并点击）**：  
[![一键安装 Shadowrocket 配置文件](https://img.shields.io/static/v1?label=一键安装&message=Shadowrocket配置文件&color=grey&logo=googledocs&logoColor=white&labelColor=orange&messageColor=white)](https://pomelo520.github.io/Shadowrocket/Static/Redirect.html?url=shadowrocket://config/add/https://pomelo520.github.io/Shadowrocket/Release/Pomelo520.conf)

---

## 融合模块（Module）
[融合模块](https://github.com/pomelo520/Shadowrocket/blob/main/Release/Module.sgmodule) 由 [GitHub Actions](https://github.com/pomelo520/Shadowrocket/blob/main/.github/workflows/Generate-ModuleFiles.yml) 调用生成器构建，依据仓库内的规则列表自动更新。

规则构成：整合 fmz200、QingRex、zirawell 等项目规则，并结合个人维护的重写合集（包含小红书、哔哩哔哩、YouTube、高德地图、一汽大众等定制规则）。  
远程资源列表（JSInventory）由 [Sync-RewriteFiles workflow](https://github.com/pomelo520/Shadowrocket/blob/main/.github/workflows/Sync-RewriteFiles.yml) 根据 `Rewrite/JSGenerator.conf` 每日自动构建与清理。

使用须知：使用融合模块必须开启 MitM（HTTPS 解密），否则模块功能将无法正常工作。  
特别声明：融合模块不包含“解锁类”功能，请尊重版权与开发者。

[![一键安装 融合模块](https://img.shields.io/static/v1?label=一键安装&message=融合模块&color=grey&logo=googledocs&logoColor=white&labelColor=blue&messageColor=white)](https://pomelo520.github.io/Shadowrocket/Static/Redirect.html?url=shadowrocket://install?module=https://pomelo520.github.io/Shadowrocket/Release/Module.sgmodule)

---

## 独立模块（Modules）
独立模块位于：  
https://github.com/pomelo520/Shadowrocket/tree/main/Release/Modules  
可以使用 **模块助手** 查询/安装（支持查看原始模块、生成反解密模块等功能）：

[![一键跳转 模块助手](https://img.shields.io/static/v1?label=一键跳转&message=模块助手&color=grey&logo=googledocs&logoColor=white&labelColor=blue&messageColor=white)](https://pomelo520.github.io/Shadowrocket/Static/ModuleHelper.html)

> 融合模块已包含独立模块功能，通常无需重复安装。

---

## 推荐设置（简要）
- 必须开启 HTTPS 解密（MitM），并安装信任证书（可通过“证书模块”导入 CA）。  
- 首页全局路由：选择 **配置**；关闭启用回退（避免策略覆盖）。  
- 代理类型建议 HTTP，地址 `127.0.0.1`（按你本地设定）。  
- 订阅与 GeoLite2 数据库：建议开启自动更新（订阅间隔 24 小时，GeoLite 更新间隔 7 天）。  
- GeoLite2 下载链接（示例，请在 Pages 中确保文件存在）：  
  - Country.mmdb: `https://pomelo520.github.io/Shadowrocket/GeoLite2/Country.mmdb`  
  - ASN.mmdb: `https://pomelo520.github.io/Shadowrocket/GeoLite2/ASN.mmdb`

更多使用细节可参考 Shadowrocket 官方/第三方文档。

---

## 特别鸣谢
感谢以下项目/作者的规则、脚本与工具（排名不分先后）：

- [001ProMax](https://github.com/001ProMax)  
- [app2smile](https://github.com/app2smile)  
- [blackmatrix7](https://github.com/blackmatrix7)  
- [fmz200](https://github.com/fmz200)  
- [godalming123](https://github.com/godalming123)  
- [iab0x00](https://github.com/iab0x00)  
- [iKeLee](https://github.com/luestr)  
- [Keywos](https://github.com/Keywos)  
- [kokoryh](https://github.com/kokoryh)  
- [LOWERTOP](https://github.com/LOWERTOP)  
- [Maasea](https://github.com/Maasea)  
- [MaxMind](https://www.maxmind.com)  
- [NobyDa](https://github.com/NobyDa)  
- [QingRex](https://github.com/QingRex)  
- [Sliverkiss](https://github.com/Sliverkiss)  
- [zirawell](https://github.com/zirawell)  
- [zZPiglet](https://github.com/zZPiglet)

---