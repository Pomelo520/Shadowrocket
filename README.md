<!doctype html>
<html lang="zh-CN">
<head>
  <!-- 基础元信息 -->
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Shadowrocket 配置项目 · Pomelo520</title>
  <meta name="description" content="由 Pomelo520 维护的 Shadowrocket 高质量配置与证书模块 — 支持 DoH/DoT、独立分流、每日自动同步规则与 GeoLite2 数据库。" />
  <link rel="canonical" href="https://pomelo520.github.io/Shadowrocket" />

  <!-- Open Graph / 社交卡片 -->
  <meta property="og:title" content="Shadowrocket 配置项目 · Pomelo520" />
  <meta property="og:description" content="高质量 Shadowrocket 配置与证书模块｜DoH/DoT、独立分流、每日自动同步。" />
  <meta property="og:type" content="website" />
  <meta property="og:url" content="https://pomelo520.github.io/Shadowrocket" />
  <!-- 若有可用的 Banner 图请替换下面 URL -->
  <meta property="og:image" content="https://pomelo520.github.io/Shadowrocket/static/banner.png" />
  <meta name="twitter:card" content="summary_large_image" />

  <!-- 移动端主题色 -->
  <meta name="theme-color" content="#0b74de" media="(prefers-color-scheme: light)">
  <meta name="theme-color" content="#0a2640" media="(prefers-color-scheme: dark)">

  <!-- JSON-LD 结构化数据（可选） -->
  <script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "SoftwareSourceCode",
    "name": "Shadowrocket 配置项目",
    "url": "https://pomelo520.github.io/Shadowrocket",
    "author": { "@type": "Person", "name": "Pomelo520" },
    "description": "由 Pomelo520 维护的 Shadowrocket 配置与证书模块，适用于学习、测试与研究用途。"
  }
  </script>

  <!-- 内嵌样式：响应式 + 深色模式 + 按钮样式 -->
  <style>
    :root{
      --bg:#ffffff; --card:#f7f9fc; --text:#0b1b2b; --muted:#4b5866; --accent:#ff8c42;
      --accent-2:#0b74de; --glass:rgba(255,255,255,0.55);
    }
    @media (prefers-color-scheme: dark) {
      :root{
        --bg:#061224; --card:#071428; --text:#e6eef8; --muted:#88a0c4; --accent:#ffb87a;
        --accent-2:#2ea3ff; --glass:rgba(10,20,30,0.45);
      }
    }
    html,body{height:100%;margin:0;font-family:system-ui,-apple-system,"Segoe UI",Roboto,"Helvetica Neue","Noto Sans",Arial,"PingFang SC","Hiragino Sans GB",sans-serif;background:var(--bg);color:var(--text);-webkit-font-smoothing:antialiased;}
    .container{max-width:1000px;margin:0 auto;padding:24px;}
    header.site-header{backdrop-filter: blur(6px); background:linear-gradient(180deg,rgba(255,255,255,0.02),transparent);border-bottom:1px solid rgba(0,0,0,0.04);}
    .hero{display:flex;gap:20px;align-items:center;justify-content:space-between;flex-wrap:wrap;padding:24px 0;}
    .brand{display:flex;gap:16px;align-items:center;min-width:0;}
    .logo{width:64px;height:64px;flex:0 0 64px;border-radius:10px;display:flex;align-items:center;justify-content:center;background:var(--card);box-shadow:0 6px 18px rgba(2,6,23,0.08);}
    .logo svg{width:40px;height:40px;display:block;}
    .title-small{font-size:14px;color:var(--muted);margin:0;}
    h1.project-title{font-size:20px;margin:0;line-height:1.05;}
    p.lead{margin:6px 0 0;color:var(--muted);font-size:14px;max-width:640px;}
    .actions{display:flex;gap:12px;align-items:center;flex-wrap:wrap;margin-left:auto;}
    .btn{display:inline-flex;align-items:center;gap:10px;padding:10px 14px;border-radius:10px;text-decoration:none;font-weight:600;border:1px solid transparent;cursor:pointer;}
    .btn.primary{background:linear-gradient(90deg,var(--accent),var(--accent-2));color:white;box-shadow:0 6px 18px rgba(11,20,40,0.12);}
    .btn.ghost{background:transparent;color:var(--text);border:1px solid rgba(0,0,0,0.06);}
    .btn.small{padding:8px 10px;font-size:13px;border-radius:8px;}
    .badges img{vertical-align:middle;height:26px;border-radius:6px;}
    nav.topnav{display:flex;gap:12px;align-items:center;margin-top:12px;flex-wrap:wrap;}
    nav.topnav a{color:var(--muted);text-decoration:none;font-size:14px;padding:8px 10px;border-radius:8px;}
    nav.topnav a:hover{color:var(--text);background:var(--glass);}
    .theme-toggle{background:transparent;border:1px solid rgba(255,255,255,0.06);padding:8px;border-radius:8px;cursor:pointer;}
    /* 响应式 */
    @media (max-width:720px){
      .actions{width:100%;justify-content:flex-start;}
      .brand{width:100%;}
      .logo{width:56px;height:56px;}
      h1.project-title{font-size:18px;}
    }
  </style>
</head>
<body>
  <!-- 页头（复制到你的模板 header 区块） -->
  <header class="site-header" role="banner">
    <div class="container">
      <div class="hero">
        <div class="brand" aria-hidden="false">
          <div class="logo" aria-hidden="true">
            <!-- 简洁 SVG Logo（可替换为你的 logo 图像） -->
            <svg viewBox="0 0 64 64" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
              <rect x="4" y="4" width="56" height="56" rx="10" fill="url(#g)" />
              <defs>
                <linearGradient id="g" x1="0" x2="1" y1="0" y2="1">
                  <stop offset="0" stop-color="#0b74de"/>
                  <stop offset="1" stop-color="#ff8c42"/>
                </linearGradient>
              </defs>
              <path d="M18 36 L28 24 L46 24 L46 40 L36 40" stroke="white" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </div>
          <div class="meta">
            <div class="title-small">Pomelo520 / Shadowrocket</div>
            <h1 class="project-title">Shadowrocket 配置项目 <span style="font-weight:600;color:var(--muted);font-size:13px;">· 高质量分流与证书模块</span></h1>
            <p class="lead">基于 DoH/DoT 的安全解析 · 系统服务与 AI 平台独立分流 · 规则与 GeoLite2 每日同步</p>
          </div>
        </div>

        <div class="actions" role="region" aria-label="快速操作">
          <!-- 一键安装配置 -->
          <a class="btn primary" href="https://Pomelo520.github.io/Shadowrocket/Static/Redirect.html?url=shadowrocket://config/add/https://Pomelo520.github.io/Shadowrocket/Release/Pomelo520.conf" title="一键安装配置文件 (在已安装 Shadowrocket 的设备上点击)">
            <!-- 简单图标（SVG） -->
            <svg width="16" height="16" viewBox="0 0 24 24" fill="none" aria-hidden="true"><path d="M12 2v14" stroke="white" stroke-width="2" stroke-linecap="round"/><path d="M5 9l7-7 7 7" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/></svg>
            一键安装 配置文件
          </a>

          <!-- 一键安装证书模块 -->
          <a class="btn ghost" href="https://Pomelo520.github.io/Shadowrocket/Static/Redirect.html?url=shadowrocket://install?module=https://Pomelo520.github.io/Shadowrocket/Release/Certificate.sgmodule" title="一键安装证书模块 (启用 HTTPS 解密) ">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="none" aria-hidden="true"><path d="M12 2l7 4v6c0 6-7 10-7 10s-7-4-7-10V6l7-4z" stroke="currentColor" stroke-width="1.2" stroke-linejoin="round"/></svg>
            一键安装 证书模块
          </a>

          <!-- 主题切换 -->
          <button class="theme-toggle small" id="themeToggle" aria-label="切换深色/浅色主题">
            🌗 切换主题
          </button>
        </div>

        <!-- 次级导航 -->
      </div>

      <nav class="topnav" role="navigation" aria-label="主导航">
        <a href="#配置文件">配置文件</a>
        <a href="#证书模块">证书模块</a>
        <a href="#使用须知">使用须知</a>
        <a href="https://github.com/Pomelo520/Shadowrocket" target="_blank" rel="noopener">GitHub</a>
        <a href="https://github.com/Pomelo520/Shadowrocket/issues" target="_blank" rel="noopener">Issues</a>
      </nav>
    </div>
  </header>

  <!-- 可将后续页面内容放在此处 -->
  <main class="container" role="main" style="padding-top:18px;">
    <!-- 页面主体 -->
  </main>

  <!-- 主题切换脚本：读取/保存到 localStorage；兼容 prefers-color-scheme -->
  <script>
    (function(){
      const toggleBtn = document.getElementById('themeToggle');
      const root = document.documentElement;
      const stored = localStorage.getItem('site-theme');
      // 如果用户之前选择过主题，应用它；否则遵循系统设置
      if(stored){
        document.documentElement.dataset.theme = stored;
        if(stored === 'dark') document.documentElement.style.colorScheme = 'dark';
      } else {
        const prefersDark = window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches;
        if(prefersDark){ document.documentElement.dataset.theme = 'dark'; document.documentElement.style.colorScheme = 'dark'; }
      }
      toggleBtn.addEventListener('click', () => {
        const current = document.documentElement.dataset.theme === 'dark' ? 'dark' : 'light';
        const next = current === 'dark' ? 'light' : 'dark';
        document.documentElement.dataset.theme = next;
        document.documentElement.style.colorScheme = next === 'dark' ? 'dark' : 'light';
        localStorage.setItem('site-theme', next);
      });
    })();
  </script>
</body>
</html>