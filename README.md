# Shadowrocket — 配置与模块集合

> 由 **Pomelo520** 维护的 Shadowrocket 配置、规则与模块集合。  
> 目标：为 iOS 上使用 Shadowrocket 的用户提供一套稳定、可更新的配置与模块管理方案。

[![Repo](https://img.shields.io/badge/Repo-Pomelo520%2FShadowrocket-blue)](https://github.com/Pomelo520/Shadowrocket)
[![Pages](https://img.shields.io/badge/Pages-pomelo520.github.io/Shadowrocket-9cf)](https://pomelo520.github.io/Shadowrocket/)
[![Release](https://img.shields.io/badge/Release-Modules-grey)](https://github.com/Pomelo520/Shadowrocket/tree/main/Release)
[![License](https://img.shields.io/badge/License-ASK-lightgrey)](LICENSE)

---

## 目录
- [简介](#简介)
- [快速安装](#快速安装)
- [核心内容](#核心内容)
  - [配置文件](#配置文件)
  - [融合模块（Module）](#融合模块)
  - [独立模块（Modules）与模块助手](#独立模块modules与模块助手)
- [推荐设置（简要）](#推荐设置简要)
- [工作流与自动化](#工作流与自动化)
- [常见问题与排查](#常见问题与排查)
- [贡献与鸣谢](#贡献与鸣谢)
- [许可说明](#许可说明)

---

## 简介
本项目维护 Shadowrocket 的配置规则、融合模块与多个独立模块，定期由 GitHub Actions 自动同步、构建与清理。设计目标是「开箱即用、自动更新、易于定制」。

---

## 快速安装
> 在 iPhone/iPad 上打开下面链接并点击即可一键安装（请确保设备已安装 Shadowrocket）：

- 一键安装 Shadowrocket 配置：  
  [![安装配置](https://img.shields.io/static/v1?label=一键安装&message=Shadowrocket配置文件&color=orange&logo=googledocs&labelColor=orange)](https://pomelo520.github.io/Shadowrocket/Static/Redirect.html?url=shadowrocket://config/add/https://pomelo520.github.io/Shadowrocket/Release/Pomelo520.conf)

- 一键安装 融合模块（Module）：  
  [![安装融合模块](https://img.shields.io/static/v1?label=一键安装&message=融合模块&color=blue&logo=googledocs&labelColor=blue)](https://pomelo520.github.io/Shadowrocket/Static/Redirect.html?url=shadowrocket://install?module=https://pomelo520.github.io/Shadowrocket/Release/Module.sgmodule)

- 模块助手（网页端，查看 / 安装独立模块）：  
  [![模块助手](https://img.shields.io/static/v1?label=模块助手&message=ModuleHelper&color=blue&logo=googledocs&labelColor=blue)](https://pomelo520.github.io/Shadowrocket/Static/ModuleHelper.html)

---

## 核心内容

### 配置文件
- 主配置文件（适合大多数用户）：`Release/Pomelo520.conf`。  
- 默认采用加密的 DoH/DoT 解析，并对未加密 DNS 进行加密转发。  
- 系统服务（Apple/Microsoft/Google）和国内外重要服务做了单独分流，减少误判与影响。

### 融合模块（Module）
- 文件：`Release/Module.sgmodule`。  
- 说明：融合模块由仓库内规则与外部规则整合生成（见下方“工作流与自动化”）。**使用融合模块需开启 MitM（HTTPS 解密）**。  
- 生成器：`Generator/Builder.py`。  
- 规则来源：包括 fmz200、QingRex、zirawell、以及本仓库自定义规则（如小红书 / 哔哩哔哩 / YouTube / 高德等）。

### 独立模块（Modules）与模块助手
- 独立模块存放：`Release/Modules/`（每个 `.sgmodule` 可单独安装）。  
- 使用模块助手 `Static/ModuleHelper.html` 可在线查看模块、复制反解密模块模板、直接跳转安装等。

---

## 推荐设置（简要）
- **必须**开启 HTTPS 解密（MitM）以使用重写/融合模块。  
- 建议为证书生成“证书模块”，并保持该模块启用以避免误删证书导致功能失效。  
- 代理分组建议包含：**英国 / 美国 / 韩国 / 香港**（优先保证节点多样性以覆盖地域路由策略）。  
- GeoLite2 数据库（用于地理分流）：可在 Settings → GeoLite2 填入 Pages 提供的链接并自动更新：
  - `https://pomelo520.github.io/Shadowrocket/GeoLite2/Country.mmdb`
  - `https://pomelo520.github.io/Shadowrocket/GeoLite2/ASN.mmdb`

---

## 工作流与自动化
- `Generate-ModuleFiles.yml`：运行 `Generator/Builder.py` 生成融合模块与 Release/Modules 内容。  
- `Sync-RewriteFiles.yml`：抓取/整理 Rewrite/JS 等远程资源，更新 `Rewrite/JavaScript/` 与 `Rewrite/JSInventory.md`。  
- `Sync-RuleFiles.yml`：每日同步黑名单/规则来源（如 blackmatrix7 repo）。  
> 注意：某些 workflow 包含 `git pull --rebase` 步骤可能在自动提交时遇到冲突（会导致 Action 失败），推荐将 stash/rebase 步骤替换为由 `EndBug/add-and-commit` 直接处理提交（可联系我帮你修改 workflow）。

---

## 常见问题与排查
- **页面打不开 / 无法安装配置**：请确认 GitHub Pages 已启用且 `Static/` 与 `Release/` 下文件已发布（`https://pomelo520.github.io/Shadowrocket/` 可访问）。  
- **一键安装跳转失败**：确认手机上已安装 Shadowrocket，并允许外部链接打开（iOS 上可能需允许）。  
- **Actions 失败（exit code 1）**：常见原因是 `git rebase` 冲突或 curl 下载失败，可把相关步骤改为容错（或删除 rebase）。  
- **融合模块不生效**：确认已开启 HTTPS 解密（MitM）并启用了证书模块；同时检查模块是否被 Shadowrocket 正常加载。

---

## 贡献与鸣谢
欢迎提交 PR / Issue。  
特别感谢（按拼音 / 随机顺序）：  
`001ProMax`, `app2smile`, `blackmatrix7`, `fmz200`, `godalming123`, `iab0x00`, `iKeLee`, `Keywos`, `kokoryh`, `LOWERTOP`, `Maasea`, `MaxMind`, `NobyDa`, `QingRex`, `Sliverkiss`, `zirawell`, `zZPiglet` 等。

---

## 许可说明
本项目仅提供规则/模块集合，**不鼓励任何侵犯版权或违法用途**。如认为本项目侵犯您的权益，请提交 Issue，我们会及时处理。  
（如需明确开源协议，请在仓库根放 `LICENSE` 文件并在此处注明）