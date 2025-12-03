## [Shadowrocket](#项目简介)
本[项目](https://github.com/Pomelo520/Shadowrocket)由[Pomelo520](https://t.me/Pomelo520)维护，提供[Shadowrocket](https://apps.apple.com/app/shadowrocket/id932747118)的[配置文件](#配置文件)<br>
如果此项目对您有帮助，欢迎给予Star；若有其他需求或问题，请提交Issues！<br>

---

### [重要声明](#重要声明)
禁止在中国大陆的任何平台传播此项目！<br>
禁止将本项目中的任何内容用于违法活动或用于盈利目的！<br>
本项目仅供学习交流及测试，使用本项目中的内容所造成的一切后果，均由使用者承担！<br>

---

### [配置文件](#配置文件)
默认使用加密的**DoH**与**DoT**进行域名解析，并对未加密的DNS请求进行加密转发；<br>
苹果、微软、谷歌等**系统服务**已单独建立专属分流策略，避免与通用规则冲突；<br>
海外主流**AI平台**已独立分流，保障访问速度与稳定性；<br>
**微信**与**电报**已单独分流，降低因策略调整导致封号或异常的风险；<br>
针对**国内**与**国外**的**媒体**及**规则**，分别使用独立的分流策略，实现更灵活的控制；<br>

本项目所使用的**规则集**源自[blackmatrix7](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Shadowrocket)的仓库，由[GitHub Actions](https://github.com/Pomelo520/Shadowrocket/blob/main/.github/workflows/Sync-RuleFiles.yml)**每日自动同步**；<br>
本项目所使用的**GeoLite2数据库**源自[MaxMind](https://www.maxmind.com)提供的免费版本，由[GitHub Actions](https://github.com/Pomelo520/Shadowrocket/blob/main/.github/workflows/Sync-GeoLite2Files.yml)**每日自动同步**；<br>

如何安装：<br>
使用安装Shadowrocket的手机访问此页面，点击安装链接，一键跳转安装；<br>
如无法加载配置，请将**全局路由**切换至**代理**模式，或自行检查网络；<br>

[![一键安装 Shadowrocket 配置文件](https://img.shields.io/static/v1?label=一键安装&message=Shadowrocket配置文件&color=grey&logo=googledocs&logoColor=white&labelColor=orange&messageColor=white)](https://Pomelo520.github.io/Shadowrocket/Static/Redirect.html?url=shadowrocket://config/add/https://Pomelo520.github.io/Shadowrocket/Release/Pomelo520.conf)<br>

修改分流：<br>
打开Shadowrocket首页，下拉进入**代理分组**，选择你想要修改的代理分组，选择对应的**策略**即可；<br>

使用须知：若需使用部分模块，**必须开启MitM**，教程参考下方的[证书模块](#证书模块)；<br>
如果本项目侵犯了您的利益，或不希望我收集您的规则，请提交Issues，我会第一时间进行移除，谢谢！<br>

---

### [证书模块](#证书模块)
如需使用模块，**必须开启HTTPS解密**，否则模块将不能正常工作；<br>
建议添加**证书模块**，避免因配置变化导致HTTPS解密功能失效；<br>
证书信任之后，**请勿在设置中移除证书**，否则HTTPS解密功能将会失效；<br>
证书模块启用后，HTTPS解密功能默认**强制开启**，配置中的“HTTPS解密开关”将不再生效；<br>

如何安装：<br>
使用安装Shadowrocket的手机访问此页面，点击安装链接，一键跳转安装；<br>
如无法加载配置，请将**全局路由**切换至**代理**模式，或自行检查网络；<br>

[![一键安装 Shadowrocket证书模块](https://img.shields.io/static/v1?label=一键安装&message=Shadowrocket证书模块&color=grey&logo=googledocs&logoColor=white&labelColor=blue&messageColor=white)](https://Pomelo520.github.io/Shadowrocket/Static/Redirect.html?url=shadowrocket://install?module=https://Pomelo520.github.io/Shadowrocket/Release/Certificate.sgmodule)<br>

证书模块使用办法：<br>
**配置** > 点击**配置文件**的 **ⓘ图标** > **HTTPS解密** > **证书** > **生成新的CA证书** > **安装证书**；<br>
**系统设置** > **已下载描述文件** > **安装**；<br>
**系统设置** > **通用** > **关于本机** > **证书信任设置** > **启用**此证书的根证书完全信任；<br>
**配置** > 点击**已安装证书的配置文件**后面的**ⓘ图标** > **HTTPS解密** > 证书后面的**ⓘ图标** > **复制**；<br>
**配置** > **模块** > **单击证书模块**跳出弹窗后**编辑参数** > 在**证书内容 = **后面粘贴有效证书**并**保存**；<br>
**配置** > 点击**已安装证书的配置文件**后面的**ⓘ图标** > **HTTPS解密** > **密码** > **复制内容**；<br>
**配置** > **模块** > **单击证书模块**跳出弹窗后**编辑参数** > 在**证书密码 = **后面粘贴有效密码** 并**保存**；<br>
开启iCloud同步的多设备用户，其他设备**请勿重新生成新的证书**，可在**复制证书内容**后，通过隔空投送或者其他方式传送内容，然后在新设备上点击**证书** > 后面的**ⓘ图标**，选择**粘贴** ，输入**证书密码** > **安装证书**，否则原设备的证书将会失效，同时请确认证书模块保持同步；<br>

软件配置：<br>
首页-全局路由：
选择**配置**；<br>
首页-全局路由：
**关闭**启用回退；<br>
设置-按需求连接：
**开启**始终开启；<br>
设置-代理：
代理类型选择**HTTP**，代理地址选择**127.0.0.1**；<br>
设置-配置：
**关闭**自动后台更新；<br>
设置-订阅：
**开启**自动后台更新，间隔选择**24**；<br>
设置-GeoLite2数据库：
**开启**自动后台更新，间隔选择**7**；<br>
设置-GeoLite2数据库：
拷贝链接：[Country.mmdb](https://Pomelo520.github.io/Shadowrocket/GeoLite2/Country.mmdb) & [ASN.mmdb](https://Pomelo520.github.io/Shadowrocket/GeoLite2/ASN.mmdb)，粘贴至对应的**URL输入框**中 ，并点击**更新**；<br>
设置-温和策略机制：
选择**开启**；<br>
设置-排除路由0.0.0.0/31：
选择**关闭**；<br>

更多使用说明，可参阅：[Shadowrocket使用手册](https://github.com/LOWERTOP/Shadowrocket)<br>

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