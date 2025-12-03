# Shadowrocket 配置项目

本项目由 [Pomelo520](https://t.me/Pomelo520) 维护，提供适用于  
[Shadowrocket](https://apps.apple.com/app/shadowrocket/id932747118) 的高质量配置文件与可选模块。  
如果此项目对你有所帮助，欢迎 Star 支持。若有问题或需求，请提交 Issues。

---

## ⚠️ 重要声明
- **禁止在中国大陆的任何平台传播本项目内容。**  
- **禁止将本项目内容用于任何违法活动或商业盈利。**  
- 本项目仅用于 **学习、研究与测试**，使用造成的一切后果由使用者自行承担。

---

## 📌 配置文件特性

- 默认启用 **DoH / DoT 加密解析**，并对所有未加密 DNS 请求进行加密转发。  
- 针对 **Apple / Microsoft / Google** 等系统服务建立独立策略，避免与通用规则冲突。  
- 针对主流 **AI 服务**（包括 OpenAI、Google AI、Claude、Gemini、Bing AI 等）构建独立策略，提升访问稳定性。  
- **微信 / Telegram** 独立分流策略，降低封号风险与连通性问题。  
- 国内 / 国外 **媒体与内容服务** 独立策略组，提供更灵活的访问控制。  
- 规则集来自 [blackmatrix7](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Shadowrocket) 仓库，**GitHub Actions 每日自动同步**。  
- GeoLite2 数据库来源于 [MaxMind](https://www.maxmind.com)，**每日自动更新**。

---

## 📲 一键安装配置（推荐）

> 使用已安装 Shadowrocket 的 iPhone / iPad 打开本页面，点击按钮即可一键导入。

<p align="center">
  <a href="https://Pomelo520.github.io/Shadowrocket/Static/Redirect.html?url=shadowrocket://config/add/https://Pomelo520.github.io/Shadowrocket/Release/Pomelo520.conf">
    <img src="https://img.shields.io/static/v1?label=一键安装&message=Shadowrocket配置文件&color=orange&logo=googledocs&logoColor=white">
  </a>
</p>

如无法加载，请将 **全局路由切换为“代理”**，或检查网络环境。

---

## 🔧 分流策略修改

Shadowrocket 首页 → **代理分组**  
选择需要修改的分组 → 选择新的策略即可。

---

## 🔐 证书模块（可选）

> 若需使用部分模块功能，必须启用 **HTTPS 解密（MitM）**。

<p align="center">
  <a href="https://Pomelo520.github.io/Shadowrocket/Static/Redirect.html?url=shadowrocket://install?module=https://Pomelo520.github.io/Shadowrocket/Release/Certificate.sgmodule">
    <img src="https://img.shields.io/static/v1?label=一键安装&message=Shadowrocket证书模块&color=blue&logo=googledocs&logoColor=white">
  </a>
</p>

### 📦 安装步骤（折叠区块）
<details>
<summary>展开查看完整步骤</summary>

1. **配置 → 配置文件 → ⓘ → HTTPS 解密 → 证书 → 生成新的 CA 证书 → 安装证书**  
2. 系统设置 → 已下载描述文件 → 安装  
3. 系统设置 → 通用 → 关于本机 → 证书信任设置 → 启用根证书完全信任  
4. 返回 Shadowrocket  
5. 配置 → 配置文件的 ⓘ → HTTPS 解密 → 证书 → ⓘ → **复制证书内容**  
6. 配置 → 模块 → 选择证书模块 → 编辑参数  
7. 将证书内容填入 `certificate=` 后  
8. 同样复制证书密码填入 `password=`  
9. （多设备）请勿重新生成证书，可使用隔空投送同步内容，并确认证书模块保持一致  
</details>

---

## ⚙️ Shadowrocket 推荐设置（折叠区块）
<details>
<summary>展开查看设置项</summary>

- 首页 → 全局路由：**配置**  
- 首页 → 启用回退：**关闭**  
- 设置 → 按需求连接：**始终开启**  
- 设置 → 代理 → 类型选择 **HTTP**，地址 **127.0.0.1**  
- 设置 → 配置：**关闭自动后台更新**  
- 设置 → 订阅：开启自动更新（24 小时）  
- 设置 → GeoLite2 数据库：开启自动更新（7 天）  
- 设置 → GeoLite2 数据库：
  - Country.mmdb  
  - ASN.mmdb  
  将链接填入对应 URL → 更新  
- 设置 → 温和策略机制：**开启**  
- 设置 → 排除路由 0.0.0.0/31：**关闭**

</details>

---

## 📚 更多说明
- 参考文档：[Shadowrocket 使用手册](https://github.com/LOWERTOP/Shadowrocket)
- 若本项目侵犯您的权益，请提交 Issues，我将及时处理。

---

## 🙏 特别鸣谢