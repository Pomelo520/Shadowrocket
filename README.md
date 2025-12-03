## [Shadowrocket](#项目简介)
本[项目](https://github.com/Pomelo520/Shadowrocket)由[Pomelo520](https://t.me/Pomelo520)维护，提供[Shadowrocket](https://apps.apple.com/app/shadowrocket/id932747118)的一键配置、证书模块与优化分流规则。欢迎 Star 与提交 Issues（有问题或需求请提）！<br>

---

### [重要声明](#重要声明)
禁止在中国大陆的任何平台传播此项目！<br>
禁止将本项目中的任何内容用于违法活动或用于盈利目的！<br>
本项目仅供学习、交流与测试，使用本项目中的内容所造成的一切后果，均由使用者自行承担！<br>

---

### [项目亮点 / 概览](#项目亮点)
- 默认使用加密 **DoH / DoT** 做域名解析，并对未加密的 DNS 请求进行加密转发；<br>
- 苹果、微软、谷歌等 **系统服务** 单独分流，避免与通用规则冲突；<br>
- 海外主流 **AI 平台**、微信、Telegram 等已独立分流，提升访问速度、稳定性与兼容性；<br>
- 针对 **国内 / 国外 媒体与规则** 使用独立分流策略，实现更灵活的控制；<br>
- 规则来自 `blackmatrix7/ios_rule_script`（Shadowrocket 规则），并通过 [GitHub Actions](https://github.com/Pomelo520/Shadowrocket/blob/main/.github/workflows/Sync-RuleFiles.yml) **每日同步**；<br>
- GeoLite2（Country / ASN）来自 MaxMind 免费版，通过 [GitHub Actions](https://github.com/Pomelo520/Shadowrocket/blob/main/.github/workflows/Sync-GeoLite2Files.yml) **每日同步**。<br>

---

### [一键安装 / 快速上手](#一键安装)
使用安装 Shadowrocket 的手机打开下面链接，一键导入：<br>
[![一键安装 Shadowrocket 配置文件](https://img.shields.io/static/v1?label=一键安装&message=Shadowrocket配置文件&color=grey&logo=googledocs&logoColor=white&labelColor=orange&messageColor=white)](https://Pomelo520.github.io/Shadowrocket/Static/Redirect.html?url=shadowrocket://config/add/https://Pomelo520.github.io/Shadowrocket/Release/Pomelo520.conf)<br>

若无法加载配置：请将 Shadowrocket **全局路由切换到代理模式** 并确认网络可用。<br>

修改分流步骤：<br>
打开 Shadowrocket 首页 → 下拉进入 **代理分组** → 选择目标代理分组 → 选择对应 **策略**（直连 / 代理 / 阻断 等）。<br>

---

### [推荐设置（复制即用）](#推荐设置)
首页 - 全局路由：选择 **配置**；<br>
首页 - 全局路由：**关闭**“启用回退”；<br>
设置 - 按需连接：**开启（始终开启）**；<br>
设置 - 代理：代理类型选择 **HTTP**，代理地址 `127.0.0.1`；<br>
设置 - 配置：**关闭**自动后台更新（由订阅控制）；<br>
设置 - 订阅：**开启**自动后台更新，间隔 `24` 小时；<br>
设置 - GeoLite2 数据库：**开启**自动后台更新，间隔 `7` 天；<br>
GeoLite2 链接（复制到 GeoLite2 URL 输入框并点击更新）：<br>
- `Country.mmdb`：https://Pomelo520.github.io/Shadowrocket/GeoLite2/Country.mmdb<br>
- `ASN.mmdb`：https://Pomelo520.github.io/Shadowrocket/GeoLite2/ASN.mmdb<br>
设置 - 温和策略机制：选择 **开启**；<br>
设置 - 排除路由 `0.0.0.0/31`：选择 **关闭**。<br>

---

### [证书模块（HTTPS 解密 / MitM）](#证书模块)
若需使用部分模块或 HTTPS 解密功能，**必须**开启 HTTPS 解密并安装证书模块；证书启用后请勿在系统设置中移除证书，否则 HTTPS 解密将失效；证书模块启用后，HTTPS 解密默认**强制开启**，配置内的“HTTPS 解密开关”将不再生效。<br>

一键安装证书模块：<br>
[![一键安装 Shadowrocket证书模块](https://img.shields.io/static/v1?label=一键安装&message=Shadowrocket证书模块&color=grey&logo=googledocs&logoColor=white&labelColor=blue&messageColor=white)](https://Pomelo520.github.io/Shadowrocket/Static/Redirect.html?url=shadowrocket://install?module=https://Pomelo520.github.io/Shadowrocket/Release/Certificate.sgmodule)<br>

证书模块使用办法（步骤）：<br>
1. 在安装 Shadowrocket 的手机上点击**一键安装证书模块**并导入；<br>
2. **配置** → 点击配置文件右侧 **ⓘ 图标** → **HTTPS 解密** → **证书** → **生成新的 CA 证书** → **安装证书**；<br>
3. 系统设置 → **已下载的描述文件** → **安装**；<br>
4. 系统设置 → **通用** → **关于本机** → **证书信任设置** → **启用该证书的根证书完全信任**；<br>
5. 在 Shadowrocket 中复制证书内容与密码：<br>
   - 配置 → 已安装证书的配置文件右侧 **ⓘ** → **HTTPS 解密** → 证书右侧 **ⓘ** → **复制**（证书内容）；<br>
   - 配置 → 已安装证书的配置文件右侧 **ⓘ** → **HTTPS 解密** → **密码** → **复制**（证书密码）；<br>
6. 配置 → **模块** → 单击证书模块弹窗 → **编辑参数** → 在“证书内容”字段粘贴证书并保存；<br>
7. 在模块参数中粘贴证书密码并保存；启用模块后 HTTPS 解密将被强制开启。<br>

多设备 iCloud 同步注意事项：<br>
开启 iCloud 同步的多设备用户，请**勿在其它设备重新生成新的证书**。请在原设备复制证书内容并通过 AirDrop 或其它安全方式传送到新设备，在新设备粘贴并安装；否则会导致原设备证书失效。<br>

---

### [更多说明 / 资料](#更多说明)
- 规则集来源：`blackmatrix7/ios_rule_script`（Shadowrocket 规则目录）。<br>
- GitHub Actions 同步脚本（规则与 GeoLite2）位于本仓库 `.github/workflows`，每日自动同步。<br>
- 使用帮助参考：[Shadowrocket 使用手册](https://github.com/LOWERTOP/Shadowrocket)。<br>

---

### [特别鸣谢](#特别鸣谢)
[*@001ProMax*](https://github.com/001ProMax)  
[*@app2smile*](https://github.com/app2smile)  
[*@blackmatrix7*](https://github.com/blackmatrix7)  
[*@fmz200*](https://github.com/fmz200)  
[*@godalming123*](https://github.com/godalming123)  
[*@iab0x00*](https://github.com/iab0x00)  
[*@iKeLee*](https://github.com/luestr)  
[*@Keywos*](https://github.com/Keywos)  
[*@kokoryh*](https://github.com/kokoryh)  
[*@LOWERTOP*](https://github.com/LOWERTOP)  
[*@Maasea*](https://github.com/Maasea)  
[*@MaxMind*](https://github.com/maxmind)  
[*@NobyDa*](https://github.com/NobyDa)  
[*@QingRex*](https://github.com/QingRex)  
[*@Sliverkiss*](https://github.com/Sliverkiss)  
[*@zirawell*](https://github.com/zirawell)  
[*@zZPiglet*](https://github.com/zZPiglet)<br>

---