<div align="center">

# 🚀 Shadowrocket 配置项目  
由 **[Pomelo520](https://t.me/Pomelo520)** 精心维护  

高质量分流配置、自动同步规则、可选证书模块  
**稳定 · 精准 · 按需分流**

<br/>

[![Install Configuration](https://img.shields.io/badge/一键安装-配置文件-orange?style=for-the-badge)](https://Pomelo520.github.io/Shadowrocket/Static/Redirect.html?url=shadowrocket://config/add/https://Pomelo520.github.io/Shadowrocket/Release/Pomelo520.conf)
[![Install Module](https://img.shields.io/badge/一键安装-证书模块-blue?style=for-the-badge)](https://Pomelo520.github.io/Shadowrocket/Static/Redirect.html?url=shadowrocket://install?module=https://Pomelo520.github.io/Shadowrocket/Release/Certificate.sgmodule)

</div>

---

## ⚠️ 重要声明
> 为确保合规性，请严格阅读以下内容：

- **禁止在中国大陆的任何平台传播本项目内容**
- **禁止将本项目用于违法行为或任何形式的盈利**
- 本项目仅用于 **学习、测试、研究**
- 使用本项目造成的一切后果，全部由使用者自行承担

---

## ✨ 配置特色（比原版更精炼清晰）

### 🛡️ 安全与解析
- 全面使用 **DoH / DoT 加密解析**
- 所有非加密 DNS 请求 → 自动加密转发

### 🔍 精准分流策略
- **Apple / Microsoft / Google 系统服务独立策略**
- **主流 AI 平台独立分流（OpenAI、Gemini、Claude 等）**
- **微信 / Telegram 独立分流**，降低封号风险

### 🎬 媒体增强策略
- 国内与国外媒体服务各自独立策略组
- 可灵活替换节点、策略或模块

### 🔄 自动同步机制
- 规则集来自 [blackmatrix7](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Shadowrocket)，**每日自动更新**
- GeoLite2 来自 [MaxMind](https://www.maxmind.com) 免费数据库，**每日同步**

---

## 📲 一键安装配置  
> 使用装有 Shadowrocket 的设备点击即可导入

<div align="center">
<a href="https://Pomelo520.github.io/Shadowrocket/Static/Redirect.html?url=shadowrocket://config/add/https://Pomelo520.github.io/Shadowrocket/Release/Pomelo520.conf">
<img src="https://img.shields.io/badge/INSTALL-配置文件-orange?style=for-the-badge">
</a>
</div>

如加载失败：  
- 请将 **全局路由切换为「代理」模式**  
- 或检查网络连通性  

---

## ⚙️ 分流策略修改
> 在 Shadowrocket 内快速变更策略，无需修改配置文件本体。

路径：  
**首页 → 代理分组 → 点选任意分组 → 切换到需要的策略**

---

## 🔐 证书模块（可选但推荐）
某些高级功能依赖 **HTTPS 解密（MitM）**。

<div align="center">
<a href="https://Pomelo520.github.io/Shadowrocket/Static/Redirect.html?url=shadowrocket://install?module=https://Pomelo520.github.io/Shadowrocket/Release/Certificate.sgmodule">
<img src="https://img.shields.io/badge/INSTALL-证书模块-blue?style=for-the-badge">
</a>
</div>

---

## 🧩 证书模块安装与使用说明（折叠）

<details>
<summary><b>展开完整步骤</b></summary>
<br/>

### 🔧 1. 生成并安装证书  
- 配置 → 配置文件 → ⓘ → HTTPS 解密 → 证书  
- 生成新的 CA → 安装证书  
- 设置 → 已下载描述文件 → 安装  
- 设置 → 通用 → 关于本机 → 证书信任设置 → 启用信任

### 📋 2. 将证书内容写入模块  
- 配置 → 配置文件的 ⓘ → HTTPS 解密 → 证书 → ⓘ → 复制内容  
- 配置 → 模块 → 证书模块 → 编辑参数  
- 填入：  
  `certificate=（证书内容）`  
  `password=（证书密码）`

### 📱 3. 多设备同步提示  
- 已启用 iCloud 的用户请勿在第二台设备重新生成证书  
- 请将证书内容与密码复制到新设备 → 粘贴 → 安装

</details>

---

## ⚙️ Shadowrocket 推荐设置（折叠区块）

<details>
<summary><b>展开查看建议设置</b></summary>
<br/>

- 首页 → 全局路由：**配置**
- 首页 → 启用回退：**关闭**
- 设置 → 按需求连接：**始终开启**
- 设置 → 代理：HTTP / 127.0.0.1
- 设置 → 配置：关闭自动更新
- 设置 → 订阅：开启自动后台更新（24 小时）
- 设置 → GeoLite2 数据库：开启自动更新（7 天）
- 填入数据库链接：  
  - Country.mmdb  
  - ASN.mmdb  
- 设置 → 温和策略机制：开启  
- 设置 → 排除路由 0.0.0.0/31：关闭  

</details>

---

## 📚 更多资料
- Shadowrocket 使用手册：  
  https://github.com/LOWERTOP/Shadowrocket

---

## 🙏 特别鸣谢

<div align="center">

`@001ProMax` · `@app2smile` · `@blackmatrix7`  
`@fmz200` · `@godalming123` · `@iab0x00`  
`@iKeLee` · `@Keywos` · `@kokoryh`  
`@LOWERTOP` · `@Maasea` · `@MaxMind`  
`@NobyDa` · `@QingRex` · `@Sliverkiss`  
`@zirawell` · `@zZPiglet`

</div>

---

<div align="center">
  
**感谢使用本项目，愿你拥有更稳定、智能、精准的网络体验。**

</div>