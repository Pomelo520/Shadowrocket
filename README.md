# [Shadowrocket](#项目简介)
本[项目](https://github.com/Pomelo520/Shadowrocket)由[Pomelo520](https://t.me/Pomelo520)维护，提供[Shadowrocket](https://apps.apple.com/app/shadowrocket/id932747118)的[配置文件](#配置文件)<br>
如果此项目对您有帮助，欢迎给予Star；若有其他需求或问题，请提交Issues！<br>

---

### [重要声明](#重要声明)
禁止在中国大陆的任何平台传播此项目！<br>
禁止将本项目中的任何内容用于违法活动或用于盈利目的！<br>
本项目仅供学习交流及测试，使用本项目中的内容所造成的一切后果，均由使用者承担！<br>

---

### [配置文件](#配置文件)
如果本项目侵犯了您的利益，或不希望我收集您的规则，请提交Issues，我会第一时间进行移除，谢谢！<br>

[![一键安装 Shadowrocket 配置文件](https://img.shields.io/static/v1?label=一键安装&message=Shadowrocket配置文件&color=grey&logo=googledocs&logoColor=white&labelColor=orange&messageColor=white)](https://Pomelo520.github.io/Shadowrocket/Static/Redirect.html?url=shadowrocket://config/add/https://Pomelo520.github.io/Shadowrocket/Release/Pomelo520.conf)<br>

Shadowrocket分流规则特点：
1.	默认使用加密的 DoH / DoT 解析域名，并对未加密的 DNS 请求进行加密转发。<br>
2.	对苹果、微软、谷歌等系统服务使用专属分流策略，避免与通用规则冲突。<br>
3.	对海外主流 AI 平台 做了独立分流，提升访问速度与稳定性。<br>
4.	对 微信 / 电报 等即时通讯做独立分流，降低因规则调整导致的账号风险。<br>
5.	针对国内与国外的媒体与策略使用独立分流，实现更灵活控制。<br>
6.	配置文件使用的**规则集**源自[blackmatrix7](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Shadowrocket)的仓库，由[GitHub Actions](https://github.com/Pomelo520/Shadowrocket/blob/main/.github/workflows/Sync-RuleFiles.yml)**每日自动同步**；<br>
7.	项目所使用的**GeoLite2数据库**源自[MaxMind](https://www.maxmind.com)提供的免费版本，由[GitHub Actions](https://github.com/Pomelo520/Shadowrocket/blob/main/.github/workflows/Sync-GeoLite2Files.yml)**每日自动同步**[Country.mmdb](https://Pomelo520.github.io/Shadowrocket/GeoLite2/Country.mmdb) & [ASN.mmdb](https://Pomelo520.github.io/Shadowrocket/GeoLite2/ASN.mmdb)；<br>

---

### [证书模块](#证书模块)
证书安装后请不要在系统设置中移除证书，开启iCloud同步的多设备用户请勿在其它设备重新生成证书，建议复制证书内容并通过AirDrop等方式在设备间同步安装，否则原设备证书会失效。<br>

[![一键安装 Shadowrocket证书模块](https://img.shields.io/static/v1?label=一键安装&message=Shadowrocket证书模块&color=grey&logo=googledocs&logoColor=white&labelColor=blue&messageColor=white)](https://Pomelo520.github.io/Shadowrocket/Static/Redirect.html?url=shadowrocket://install?module=https://Pomelo520.github.io/Shadowrocket/Release/Certificate.sgmodule)<br>

证书安装与配置步骤简要：<br>
1.	Shadowrocket：配置 → 点击配置文件右侧 ⓘ → HTTPS 解密 → 证书 → 生成新的 CA 证书 → 安装证书。<br>
2.	系统设置：已下载的描述文件 → 安装。<br>
3.	系统设置：通用 → 关于本机 → 证书信任设置 → 启用该根证书完全信任。<br>
4.	模块配置：复制证书内容与密码到模块编辑参数中（详见仓库内证书模块说明）。<br>
5.	使用须知：证书模块启用后，HTTPS解密功能默认强制开启，配置中的“HTTPS解密开关”将不再生效。<br>

### [推荐Shadowrocket设置](#推荐Shadowrocket设置)
	•	首页 → 全局路由：选择配置。
	•	关闭“启用回退”。
	•	设置 → 按需连接：开启“始终开启”。
	•	设置 → 代理：类型选择 HTTP，地址 127.0.0.1。
	•	设置 → 配置：关闭“自动后台更新”。
	•	订阅：开启“自动后台更新”，间隔设为 24（小时）。
	•	GeoLite2 数据库：开启自动更新，间隔设为 7（天）。
	•	温和策略机制：建议开启。
	•	排除路由 0.0.0.0/31：建议关闭。

### [常见问题与排查](#常见问题与排查)
1.	如何安装：使用安装Shadowrocket的手机访问此页面，点击安装链接，一键跳转安装<br>
2.	无法加载配置：请检查网络或将全局路由切换为代理模式。<br>
3.	模块不可用：确认已生成并信任证书，且在模块中正确粘贴了证书内容与密码。<br>
4.	多设备证书失效：请勿在多设备上重复生成证书，请通过复制/传输证书内容方法安装到其它设备。<br>
5.	修改分流：打开Shadowrocket首页，下拉进入代理分组，选择你想要修改的代理分组，选择对应的策略即可。<br>

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