Shadowrocket 配置与模块集合

本项目由 Pomelo520 维护，为 iOS 端 Shadowrocket 提供一套持续更新、可复用、结构清晰的 配置文件、融合模块与独立模块合集。

如本项目对你有帮助，欢迎 Star；如遇问题，请提交 Issues。

⸻

重要声明
	•	禁止在中国大陆任何平台传播本项目。
	•	禁止用于违法活动或用于任何盈利目的。
	•	本项目仅供学习、测试与研究用途，一切后果由使用者自行承担。
	•	本项目部分结构借鉴 向晚（Xiangwan）Shadowrocket 项目，已在适当位置注明复刻来源。

⸻

项目内容总览
	•	配置文件（主配置）
	•	融合模块（Module）
	•	独立模块（Modules）
	•	自动同步构建体系（GitHub Actions）
	•	GeoLite2 数据库自动更新
	•	模块助手（ModuleHelper）

⸻

配置文件（主配置）

主配置默认启用：
	•	加密 DoH / DoT DNS
	•	未加密 DNS 自动加密转发
	•	Apple、Google、Microsoft 等系统级服务独立分流
	•	海外主流 AI 服务独立分流
	•	Telegram、WeChat 独立策略
	•	国内外媒体双策略分流
	•	默认策略集成 blackmatrix7 规则（每日自动同步）
	•	默认集成 GeoLite2（每日自动更新）

配置文件（主配置）：
👉 https://Pomelo520.github.io/Shadowrocket/Release/Pomelo520.conf

一键安装：


⸻

主配置默认行为
	•	自动测速选择最低延迟节点
	•	优先使用你节点列表中的：英国 / 美国 / 韩国 / 香港
	•	分流规则：
	•	Telegram → 英国
	•	Google / AI → 美国
	•	国内 → 直连
	•	未匹配 → 自动测速组
	•	首页节点选择被代理分组接管（不会生效）
	•	最推荐与”机场订阅”搭配使用
	•	若节点未包含 英美韩港，需要你自行调整

⸻

融合模块（Module）

融合模块：
👉 https://github.com/Pomelo520/Shadowrocket/blob/main/Release/Module.sgmodule

一键安装：

融合模块由：
	•	GitHub Actions（Generate-ModuleFiles.yml）
	•	生成器：Generator/Builder.py
	•	构建清单：Generator/Generate.conf

自动构建与更新。

模块内容来自以下规则项目的整合：
	•	fmz200
	•	QingRex
	•	zirawell
	•	以及本项目的定制规则（如下）

包含但不限于：
	•	小红书
	•	哔哩哔哩
	•	YouTube
	•	高德地图
	•	一汽大众
	•	等多个 JS/Rewrite 规则

所有远程资源每日由 GitHub Actions 自动同步：
→ Rewrite/JSInventory.md
→ Rewrite/JavaScript/

⚠ 使用须知：
	•	必须开启 HTTPS 解密（MitM）
	•	不包含任何解锁功能，请支持原作者
	•	若侵犯权益，请创建 Issues，我将及时处理

⸻

独立模块（Modules）

独立模块目录：
👉 https://github.com/Pomelo520/Shadowrocket/tree/main/Release/Modules

构建方式：由 Builder.py 自动生成。

推荐使用“模块助手”查看、安装、反解密模块模板：

⚠ 注意：
	•	融合模块 已经包含所有独立模块功能，无需重复安装。

⸻

推荐设置（MitM 必看）

融合模块工作依赖 HTTPS 解密（MitM）。

开启 MitM 步骤
	1.	Shadowrocket → 配置 → ⓘ → HTTPS 解密
	2.	生成新的 CA 证书并安装
	3.	系统设置 → 通用 → 关于本机 → 信任证书
	4.	建议制作 证书模块（避免丢失证书）

证书模块模板：

#!name = 证书模块
[MITM]
enable=true
ca-passphrase=
ca-p12=

⚠ 多设备使用
不要重新生成证书，请从原设备复制证书内容与密码。

⸻

软件设置建议（最佳实践）
	•	首页 → 全局路由 → 配置
	•	首页 → 启用回退 → 关闭
	•	设置 → 按需连接 → 始终开启
	•	设置 → 代理
	•	类型：HTTP
	•	地址：127.0.0.1
	•	设置 → 配置 → 自动后台更新：关闭
	•	设置 → 订阅 → 自动更新：开启（24 小时）
	•	设置 → GeoLite2 → 自动更新：开启（7 天）
	•	Country.mmdb
	•	ASN.mmdb
	•	设置 → 温和策略 → 开启
	•	设置 → 排除路由 0.0.0.0/31 → 关闭

更多文档：
👉 https://github.com/LOWERTOP/Shadowrocket

⸻

自动化工作流

已实现的 GitHub Actions：
	•	Sync-RuleFiles.yml
	•	每日同步 blackmatrix7 规则
	•	Sync-GeoLite2Files.yml
	•	每日同步 GeoLite2 数据库
	•	Generate-ModuleFiles.yml
	•	自动构建融合模块与独立模块
	•	Sync-RewriteFiles.yml
	•	自动抓取远程 JS/Rewrite 并构建清单

⚠ “git pull –rebase” 在 Action 中常导致失败
建议改为 EndBug/add-and-commit 处理提交。

⸻

特别鸣谢

感谢以下项目对规则生态的贡献：

001ProMax · app2smile · blackmatrix7 · fmz200 · godalming123 · iab0x00
iKeLee · Keywos · kokoryh · LOWERTOP · Maasea · MaxMind
NobyDa · QingRex · Sliverkiss · zirawell · zZPiglet

⸻

致谢引用说明（复刻声明）

本 README 部分结构、排版风格参考并复刻自 向晚（Xiangwan）Shadowrocket 项目，并根据本仓库需求进行重写与扩展。特此致谢。

⸻