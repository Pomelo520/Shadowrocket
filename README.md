> [!IMPORTANT] 
> # 🗂️ Shadowrocket
> **本[仓库](https://github.com/Pomelo520/Shadowrocket)由[Pomelo](https://t.me/Pomelo520)维护，诚挚感谢所有为[Shadowrocket](https://apps.apple.com/app/shadowrocket/id932747118)相关项目做出贡献的人！**
---
> [!WARNING]
> ### 🚨 重要声明
> **严禁在任何中国大陆平台分发本仓库内容！禁止将本仓库内容用于非法活动或商业盈利！本仓库仅供学习交流，用户需对使用后果承担全部责任!**
---
> [!NOTE]
> ### 📝 配置文件
> 默认使用代理组作为最终回退，接管全量流量。建议配合证书模块使用，支持全局参数、规则添加、URL 重写及脚本等
>
> [![懒人配置](https://img.shields.io/static/v1?label=安装配置&message=懒人配置&color=grey&logo=googledocs&logoColor=white&labelColor=orange&messageColor=white)](https://pomelo.us.kg/Web/Redirect.html?url=shadowrocket://config/add/https://pomelo.us.kg/Configs/Pomelo.conf "一键安装本配置文件")
> [![规则文件](https://img.shields.io/static/v1?label=规则文件&message=懒人配置&color=grey&logo=todoist&logoColor=white&labelColor=%2325A162&messageColor=white)](https://pomelo.us.kg/Configs/Pomelo.conf "点击访问规则集")
>
> <details>
> <summary>点击查看配置文件主要特色</summary>
>
> > ### 配置文件主要特色：<br>
> >
> > * 🛡️ **加密 DNS**：默认使用 DoH/DoT，拒绝 DNS 污染<br>
> > * 🍎 **系统服务**：Apple、Google 等服务走专用路由策略<br>
> > * 🤖 **AI 平台**：主流海外 AI 平台独立路由，确保连接稳定<br>
> > * 💬 **即时通讯**：微信、TG 独立路由，降低封号风险<br>
> > * 🎬 **流媒体**：国内外媒体平台灵活控制<br>
> > * 🔄 **自动同步**：规则集源自 [blackmatrix7](https://github.com/blackmatrix7)，由`GitHub Actions`每日更新<br>
> > * 🌍 **GeoLite2**：自动同步 [MaxMind](https://www.maxmind.com) 数据库：[Country.mmdb](https://pomelo.us.kg/GeoLite2/Country.mmdb) & [ASN.mmdb](https://pomelo.us.kg/GeoLite2/ASN.mmdb)<br>
> </details>
---
> [!NOTE]
> ### 🧩 证书模块
> 实现 HTTPS 解密状态跨配置持久化，无需重复安装 CA 证书。由于模块优先级最高，切换配置不影响解密
>
> [![证书模块](https://img.shields.io/static/v1?label=安装模块&message=证书模块&color=grey&logo=educative&logoColor=white&labelColor=blue&messageColor=white)](https://pomelo.us.kg/Web/Redirect.html?url=shadowrocket://install?module=https://pomelo.us.kg/Configs/Modules/Certificate.sgmodule "一键安装本模块")
> [![规则文件](https://img.shields.io/static/v1?label=规则文件&message=证书模块&color=grey&logo=todoist&logoColor=white&labelColor=%2325A162&messageColor=white)](https://pomelo.us.kg/Configs/Modules/Certificate.sgmodule "点击访问规则集")
> 
> <details>
> <summary>点击查看证书模块安装指南</summary>
>
> > ### 证书模块安装指南：<br>
> >
> > 1.  **生成证书**：配置 → ⓘ → HTTPS 解密 → 证书 → 生成新的 CA 证书 → 安装<br>
> > 2.  **系统安装**：系统设置 → 已下载描述文件 → 安装<br>
> > 3.  **开启信任**：系统设置 → 通用 → 关于本机 → 证书信任设置 → 开启全权信任<br>
> > 4.  **参数配置**：将证书内容与密码填入模块编辑参数（详见仓库教程）<br>
> > 5.  **多设备同步**：**切勿重新生成！** 请通过 AirDrop 传输现有证书，否则原设备证书将失效<br>
> > 6.  **注意**：启用后将强制开启 HTTPS 解密，配置文件的手动开关将失效<br>
> </details>
---
> [!NOTE]
> ### 🚏 Shadowrocket
> **[Shadowrocket](https://apps.apple.com/us/app/shadowrocket/id932747118)**（常被用户称为“小火箭”）是一款由 **[Shadow Launch Technology Limited](https://shadowlaunch.com/)** 专为 iOS 设备开发的网络代理工具，同时也支持 Apple TV 等设备，软件版本自 **[2.2.70 (2712)](https://t.me/ShadowrocketNews/1047)** 起已正式支持 macOS，同时支持 x86/64 和 arm64
>
> <details>
> <summary>点击查看Shadowrocket推荐设置</summary>
>
> > ### Shadowrocket推荐设置：<br>
> >
> > * **全局路由**：选择 `配置`<br>
> > * **启用回退**：`关闭`<br>
> > * **按需连接**：开启 `始终开启`<br>
> > * **代理设置**：类型 `HTTP`| 地址 `127.0.0.1`<br>
> > * **后台更新**：配置关闭自动更新，订阅开启自动更新（间隔 24 小时）<br>
> > * **GeoLite2数据库**：开启自动更新 7 天<br>
> </details>
>
>  官方群组：[Shadowrocket App](https://t.me/ShadowrocketApp)<br>
>  官方频道：[Shadowrocket News](https://t.me/ShadowrocketNews)<br>
>  官方邮箱：[buginapp@gmail.com](mailto:buginapp@gmail.com)
---
> [!Caution]
> ### 🙋 常见问题 
>  更换Shadowrocket配置文件（通常为.conf格式）主要用于快速设置和调整应用的核心功能。配置文件也可以在设备间同步或与他人共享，以便快速部署并简化手动配置
>
> <details>
> <summary>点击查看Shadowrocket常见问题</summary>
>
> > ### Shadowrocket常见问题：<br>
> >
> > 1.  **无法加载配置**：请检查您的网络或临时将全局路由切换为代理模式<br>
> > 2.  **证书模块不可用**：请确保您已生成并信任证书，并正确地将证书内容和密码粘贴到模块中<br>
> > 3.  **多设备证书无效**：请勿在不同设备上重新生成证书；请改为复制并传输证书内容<br>
> > 4.  **修改路由**：在 Shadowrocket 首页下拉进入代理组，选择您要修改的组，然后选择所需的策略<br>
> </details> 
>
>  更多详情请参考：[Shadowrocket 用户手册](https://github.com/LOWERTOP/Shadowrocket)
---
> [!TIP]
> ### 🎉 特别感谢
> [*@001ProMax*](https://github.com/001ProMax)
> [*@app2smile*](https://github.com/app2smile)
> [*@blackmatrix7*](https://github.com/blackmatrix7)
> [*@fmz200*](https://github.com/fmz200)
> [*@godalming123*](https://github.com/godalming123)
> [*@iKeLee*](https://github.com/luestr)
> [*@Keywos*](https://github.com/Keywos)
> [*@kokoryh*](https://github.com/kokoryh)
> [*@Maasea*](https://github.com/Maasea)
> [*@MaxMind*](https://github.com/maxmind)
> [*@NobyDa*](https://github.com/NobyDa)
> [*@QingRex*](https://github.com/QingRex)
> [*@zirawell*](https://github.com/zirawell)
> [*@zZPiglet*](https://github.com/zZPiglet)  
---