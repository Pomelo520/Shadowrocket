# 🚀 Shadowrocket 配置文件项目

本项目由 **[Pomelo520](https://t.me/Pomelo520)** 维护，专注于提供高质量的 **[Shadowrocket](https://apps.apple.com/app/shadowrocket/id932747118)** 配置文件。

如果此项目对您有帮助，欢迎给予 **Star** ⭐️。如有其他需求或问题，请提交 Issues。

---

## 🛑 重要声明

> **⚠️ 严禁传播与违法使用**
> 1.  **禁止**在中国大陆的任何平台传播此项目！
> 2.  **禁止**将本项目中的任何内容用于违法活动或用于盈利目的！
> 
> 本项目仅供学习交流及测试，使用本项目中的内容所造成的一切后果，均由使用者承担！

---

## ⚙️ 配置文件核心特性

默认配置使用了加密的 **DoH/DoT** 进行域名解析，并包含以下精细分流策略：

* **🛡️ 系统服务**：苹果、微软、谷歌等系统服务已建立专属分流策略。
* **🧠 AI 平台**：海外主流 AI 平台已独立分流，保障访问速度与稳定性。
* **📱 社交应用**：**微信**与**电报 (Telegram)** 已单独分流，降低风险。
* **🌐 媒体/规则**：针对**国内**与**国外**的媒体及规则，分别使用独立策略。

### 自动化同步

* **规则集**：源自 **[blackmatrix7](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Shadowrocket)**，由 GitHub Actions **每日自动同步**。
* **GeoLite2 数据库**：源自 **[MaxMind](https://www.maxmind.com)** 免费版本，由 GitHub Actions **每日自动同步**。

### 安装与修改

| 操作 | 描述 |
| :--- | :--- |
| **一键安装配置** | 点击链接跳转安装：[![一键安装 Shadowrocket 配置文件](https://img.shields.io/static/v1?label=一键安装&message=Shadowrocket配置文件&color=orange&logo=googledocs&labelColor=orange&messageColor=white)](https://Pomelo520.github.io/Shadowrocket/Static/Redirect.html?url=shadowrocket://config/add/https://Pomelo520.github.io/Shadowrocket/Release/Pomelo520.conf) |
| **修改分流策略** | 打开 Shadowrocket 首页，下拉进入**代理分组**，选择对应策略。 |

---

## 🔑 证书模块 (MitM) 启用指南

**重要提示**：如需使用部分模块，**必须开启 HTTPS 解密**，否则模块将不能正常工作。建议添加**证书模块**，以确保功能稳定。

| 操作 | 描述 |
| :--- | :--- |
| **一键安装模块** | 点击链接跳转安装：[![一键安装 Shadowrocket证书模块](https://img.shields.io/static/v1?label=一键安装&message=Shadowrocket证书模块&color=blue&logo=googledocs&labelColor=blue&messageColor=white)](https://Pomelo520.github.io/Shadowrocket/Static/Redirect.html?url=shadowrocket://install?module=https://Pomelo520.github.io/Shadowrocket/Release/Certificate.sgmodule) |
| **启用特性** | 启用证书模块后，HTTPS 解密功能将**强制开启**，配置中的“HTTPS解密开关”将不再生效。 |

### 模块详细使用步骤 (P12 证书粘贴)

1.  **生成证书**：**配置** > 配置文件 **ⓘ图标** > **HTTPS解密** > **证书** > **生成新的CA证书** > **安装证书**。
2.  **系统信任**：进入 iOS **系统设置** > **已下载描述文件** > **安装**，随后在 **通用** > **关于本机** > **证书信任设置** 中，**启用**此证书的根证书完全信任。
3.  **复制证书内容**：配置文件 **ⓘ图标** > **HTTPS解密** > 证书后的 **ⓘ图标** > **复制**。
4.  **粘贴证书内容**：**配置** > **模块** > **单击证书模块** > **编辑参数** > 在 `证书内容` 后面粘贴。
5.  **复制证书密码**：配置文件 **ⓘ图标** > **HTTPS解密** > **密码** > **复制内容**。
6.  **粘贴证书密码**：**配置** > **模块** > **单击证书模块** > **编辑参数** > 在 `证书密码` 后面粘贴并保存。

> ℹ️ **多设备用户须知**：其他设备**请勿重新生成新的证书**。只需在新设备上选择 **证书** > **粘贴**，然后安装信任即可。

### 软件配置推荐

为达到最佳使用体验，推荐以下设置：

* **首页-全局路由**：选择 **配置**；**关闭** 启用回退。
* **设置-按需求连接**：**开启** 始终开启。
* **设置-代理**：代理类型选择 **HTTP**，代理地址选择 **127.0.0.1**。
* **设置-配置**：**关闭** 自动后台更新。
* **设置-订阅**：**开启** 自动后台更新，间隔选择 **24** 小时。
* **GeoLite2 数据库**：**开启** 自动后台更新，间隔选择 **7** 天。
* **GeoLite2 数据库链接**：
    * Country.mmdb：`https://Pomelo520.github.io/Shadowrocket/GeoLite2/Country.mmdb`
    * ASN.mmdb：`https://Pomelo520.github.io/Shadowrocket/GeoLite2/ASN.mmdb`
* **设置-温和策略机制**：选择 **开启**。
* **设置-排除路由0.0.0.0/31**：选择 **关闭**。

---

## 💖 特别鸣谢

感谢以下贡献者和项目：

* [@001ProMax](https://github.com/001ProMax)
* [@app2smile](https://github.com/app2smile)
* [@blackmatrix7](https://github.com/blackmatrix7)
* ... (此处省略其余鸣谢名单以保持简洁)

更多使用说明，请参阅：**[Shadowrocket使用手册](https://github.com/LOWERTOP/Shadowrocket)**

---