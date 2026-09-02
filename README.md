<!DOCTYPE html>
<html lang="en" dir="ltr" class="dark">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>BUILDPRO | Premium PC & Server Architecture</title>
  
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="https://unpkg.com/lucide@latest"></script>

  <script>
    tailwind.config = {
      darkMode: 'class',
      theme: {
        extend: {
          fontFamily: {
            sans: ['"Plus Jakarta Sans"', 'sans-serif'],
          },
          colors: {
            brand: {
              50: '#eff6ff',
              400: '#60a5fa',
              500: '#3b82f6',
              600: '#2563eb',
              accent: '#00f2fe',
              dark: '#05070d',
              card: 'rgba(13, 18, 30, 0.75)'
            }
          }
        }
      }
    }
  </script>

  <style>
    body {
      background-color: #05070d;
      color: #f1f5f9;
      overflow-x: hidden;
    }
    .glass-panel {
      background: rgba(13, 19, 33, 0.7);
      backdrop-filter: blur(16px);
      -webkit-backdrop-filter: blur(16px);
      border: 1px solid rgba(255, 255, 255, 0.08);
    }
    .glass-panel-hover:hover {
      border-color: rgba(59, 130, 246, 0.45);
      box-shadow: 0 0 25px rgba(37, 99, 235, 0.2);
    }
    .text-gradient {
      background: linear-gradient(135deg, #38bdf8 0%, #3b82f6 50%, #818cf8 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }
    .video-overlay {
      background: radial-gradient(circle at center, rgba(5, 7, 13, 0.5) 0%, #05070d 90%);
    }
    /* Hide scrollbars for clean look */
    ::-webkit-scrollbar { width: 8px; }
    ::-webkit-scrollbar-track { background: #05070d; }
    ::-webkit-scrollbar-thumb { background: #1e293b; border-radius: 4px; }
  </style>
</head>

<body class="min-h-screen relative antialiased selection:bg-blue-600 selection:text-white">

  <div class="fixed inset-0 w-full h-full overflow-hidden pointer-events-none -z-20">
    <video autoplay muted loop playsinline class="w-full h-full object-cover scale-105 filter brightness-50 contrast-125">
      <source src="https://assets.mixkit.co/videos/preview/mixkit-circuit-board-details-and-neon-lights-42581-large.mp4" type="video/mp4">
    </video>
    <div class="absolute inset-0 video-overlay -z-10"></div>
    <div class="absolute top-0 right-1/4 w-[500px] h-[500px] bg-blue-600/10 rounded-full blur-[140px] pointer-events-none"></div>
  </div>

  <header class="sticky top-0 z-40 w-full glass-panel border-b border-white/10">
    <div class="max-w-7xl mx-auto px-6 h-20 flex items-center justify-between gap-4">
      
      <a href="#" class="flex items-center gap-3 group">
        <div class="w-10 h-10 rounded-lg bg-gradient-to-tr from-blue-600 to-cyan-400 p-0.5 flex items-center justify-center shadow-lg shadow-blue-500/20 group-hover:scale-105 transition">
          <div class="w-full h-full bg-[#05070d] rounded-[7px] flex items-center justify-center">
            <i data-lucide="cpu" class="w-5 h-5 text-cyan-400"></i>
          </div>
        </div>
        <div class="flex flex-col">
          <span class="font-extrabold text-xl tracking-wider text-white">BUILD<span class="text-blue-500">PRO</span></span>
          <span class="text-[9px] tracking-[0.25em] text-slate-400 font-medium uppercase -mt-1">Built To Perform</span>
        </div>
      </a>

      <nav class="hidden lg:flex items-center gap-7 text-sm font-medium text-slate-300">
        <a href="#" class="text-blue-400 font-semibold" data-i18n="nav_home">Home</a>
        <a href="#pc-builds" class="hover:text-white transition" data-i18n="nav_pc_builds">PC Builds</a>
        <a href="#servers" class="hover:text-white transition" data-i18n="nav_servers">Servers</a>
        <a href="#workstations" class="hover:text-white transition" data-i18n="nav_workstations">Workstations</a>
        <a href="#components" class="hover:text-white transition" data-i18n="nav_components">Components</a>
        <a href="#solutions" class="hover:text-white transition" data-i18n="nav_solutions">Solutions</a>
        <a href="#contact" class="hover:text-white transition" data-i18n="nav_contact">Contact</a>
      </nav>

      <div class="flex items-center gap-3">
        
        <div class="relative">
          <button id="langMenuBtn" class="flex items-center gap-2 px-3 py-1.5 rounded-lg text-xs font-semibold glass-panel hover:bg-white/10 transition border border-white/10">
            <i data-lucide="globe" class="w-4 h-4 text-slate-400"></i>
            <span id="currentLangLabel">English</span>
            <i data-lucide="chevron-down" class="w-3.5 h-3.5 text-slate-400"></i>
          </button>

          <div id="langDropdown" class="hidden absolute right-0 mt-2 w-48 glass-panel rounded-xl shadow-2xl py-2 z-50 max-h-72 overflow-y-auto border border-white/10">
            <button onclick="setLanguage('en', 'English')" class="w-full text-left px-4 py-2 text-xs text-slate-200 hover:bg-blue-600/20 flex items-center justify-between"><span>🇬🇧 English</span></button>
            <button onclick="setLanguage('ta', 'தமிழ்')" class="w-full text-left px-4 py-2 text-xs text-slate-200 hover:bg-blue-600/20 flex items-center justify-between"><span>🇮🇳 தமிழ் (Tamil)</span></button>
            <button onclick="setLanguage('hi', 'हिन्दी')" class="w-full text-left px-4 py-2 text-xs text-slate-200 hover:bg-blue-600/20 flex items-center justify-between"><span>🇮🇳 हिन्दी (Hindi)</span></button>
            <button onclick="setLanguage('ar', 'العربية')" class="w-full text-left px-4 py-2 text-xs text-slate-200 hover:bg-blue-600/20 flex items-center justify-between"><span>🇸🇦 العربية (Arabic)</span></button>
            <button onclick="setLanguage('zh', '简体中文')" class="w-full text-left px-4 py-2 text-xs text-slate-200 hover:bg-blue-600/20 flex items-center justify-between"><span>🇨🇳 简体中文</span></button>
            <button onclick="setLanguage('ja', '日本語')" class="w-full text-left px-4 py-2 text-xs text-slate-200 hover:bg-blue-600/20 flex items-center justify-between"><span>🇯🇵 日本語</span></button>
            <button onclick="setLanguage('de', 'Deutsch')" class="w-full text-left px-4 py-2 text-xs text-slate-200 hover:bg-blue-600/20 flex items-center justify-between"><span>🇩🇪 Deutsch</span></button>
            <button onclick="setLanguage('fr', 'Français')" class="w-full text-left px-4 py-2 text-xs text-slate-200 hover:bg-blue-600/20 flex items-center justify-between"><span>🇫🇷 Français</span></button>
            <button onclick="setLanguage('es', 'Español')" class="w-full text-left px-4 py-2 text-xs text-slate-200 hover:bg-blue-600/20 flex items-center justify-between"><span>🇪🇸 Español</span></button>
            <button onclick="setLanguage('ru', 'Русский')" class="w-full text-left px-4 py-2 text-xs text-slate-200 hover:bg-blue-600/20 flex items-center justify-between"><span>🇷🇺 Русский</span></button>
            <button onclick="setLanguage('pt', 'Português')" class="w-full text-left px-4 py-2 text-xs text-slate-200 hover:bg-blue-600/20 flex items-center justify-between"><span>🇧🇷 Português</span></button>
          </div>
        </div>

        <button class="relative p-2 rounded-lg text-slate-300 glass-panel hover:text-white transition">
          <i data-lucide="shopping-cart" class="w-4 h-4"></i>
          <span class="absolute -top-1 -right-1 bg-blue-600 text-[10px] w-4 h-4 rounded-full flex items-center justify-center font-bold">0</span>
        </button>

        <button onclick="openAuthModal()" id="authButton" class="flex items-center gap-2 px-3 py-1.5 rounded-lg text-xs font-semibold glass-panel hover:border-blue-500/50 transition">
          <div class="w-5 h-5 rounded-full bg-slate-700 flex items-center justify-center text-white" id="userAvatar">
            <i data-lucide="user" class="w-3.5 h-3.5"></i>
          </div>
          <span id="authLabel" data-i18n="btn_login">Sign In</span>
        </button>

        <a href="#quote" class="hidden sm:inline-flex items-center justify-center px-4 py-2 text-xs font-semibold rounded-lg bg-blue-600 hover:bg-blue-500 text-white shadow-lg shadow-blue-600/30 transition duration-200" data-i18n="btn_quote">
          Get a Quote
        </a>
      </div>
    </div>
  </header>

  <main class="max-w-7xl mx-auto px-6 pt-12 pb-20">
    <div class="grid grid-cols-1 lg:grid-cols-12 gap-12 items-center min-h-[580px]">
      
      <div class="lg:col-span-6 space-y-6">
        
        <div class="inline-flex items-center gap-2 px-3.5 py-1.5 rounded-full glass-panel border border-blue-500/30 text-blue-400 text-xs font-semibold tracking-wider uppercase">
          <span class="inline-block w-1.5 h-1.5 rounded-full bg-blue-400 animate-pulse"></span>
          <span data-i18n="tagline">Premium Performance. Reliable Everytime.</span>
        </div>

        <h1 class="text-4xl sm:text-5xl lg:text-6xl font-extrabold tracking-tight text-white leading-[1.15]">
          <span data-i18n="hero_title_1">Premium PC & Server Building</span><br>
          <span class="text-gradient" data-i18n="hero_title_2">Built for Power. Designed for You.</span>
        </h1>

        <p class="text-base sm:text-lg text-slate-300 max-w-xl font-normal leading-relaxed" data-i18n="hero_subtitle">
          High performance custom PCs and enterprise grade servers engineered for gamers, creators, AI researchers, and businesses.
        </p>

        <div class="flex flex-wrap items-center gap-4 pt-3">
          <a href="#builder" class="flex items-center gap-2.5 px-6 py-3 rounded-xl bg-blue-600 hover:bg-blue-500 text-white text-sm font-semibold shadow-xl shadow-blue-600/30 transition transform hover:-translate-y-0.5">
            <i data-lucide="monitor" class="w-4 h-4"></i>
            <span data-i18n="cta_build_pc">Build Your PC</span>
          </a>

          <a href="#servers" class="flex items-center gap-2.5 px-6 py-3 rounded-xl glass-panel hover:bg-white/10 text-white text-sm font-semibold border border-white/20 transition transform hover:-translate-y-0.5">
            <i data-lucide="server" class="w-4 h-4"></i>
            <span data-i18n="cta_server">Configure Server</span>
          </a>

          <button class="flex items-center gap-2 px-4 py-3 rounded-xl text-slate-300 hover:text-white text-sm font-medium transition group">
            <div class="w-8 h-8 rounded-full glass-panel flex items-center justify-center group-hover:scale-110 transition border border-white/20">
              <i data-lucide="play" class="w-3.5 h-3.5 text-blue-400 fill-blue-400"></i>
            </div>
            <span data-i18n="cta_showcase">View Showcase</span>
          </button>
        </div>
      </div>

      <div class="lg:col-span-6 flex justify-center relative">
        <div class="relative w-full max-w-lg aspect-[4/3] rounded-2xl p-1 bg-gradient-to-b from-blue-500/20 via-cyan-500/10 to-transparent shadow-2xl">
          <div class="relative w-full h-full rounded-2xl overflow-hidden glass-panel border border-white/10 flex items-center justify-center group">
            
            <img 
              src="https://images.unsplash.com/photo-1587202372775-e229f172b9d7?auto=format&fit=crop&w=1200&q=80" 
              alt="Liquid Cooled Rig" 
              class="w-full h-full object-cover object-center group-hover:scale-105 transition duration-700 filter brightness-90"
            />
            
            <div class="absolute inset-0 bg-gradient-to-t from-[#05070d] via-transparent to-transparent"></div>

            <div class="absolute bottom-4 left-4 right-4 flex justify-between items-center glass-panel px-4 py-3 rounded-xl border border-white/10">
              <div>
                <p class="text-xs text-blue-400 font-semibold tracking-wider uppercase">Titan X Workstation</p>
                <p class="text-[13px] text-white font-medium">Dual RTX 4090 • 256GB ECC DDR5</p>
              </div>
              <span class="px-2.5 py-1 text-[11px] font-bold rounded-md bg-emerald-500/20 text-emerald-400 border border-emerald-500/30">Ready to Ship</span>
            </div>

          </div>
        </div>
      </div>

    </div>

    <div class="mt-14 glass-panel rounded-2xl p-6 border border-white/10 grid grid-cols-2 md:grid-cols-3 lg:grid-cols-5 gap-6">
      
      <div class="flex items-start gap-3.5">
        <div class="p-2.5 rounded-xl bg-blue-500/10 border border-blue-500/20 text-blue-400 shrink-0">
          <i data-lucide="cpu" class="w-5 h-5"></i>
        </div>
        <div>
          <h4 class="text-sm font-bold text-white" data-i18n="feat_custom">Custom Built</h4>
          <p class="text-xs text-slate-400 mt-0.5" data-i18n="feat_custom_desc">Tailored configurations to match your exact workflow.</p>
        </div>
      </div>

      <div class="flex items-start gap-3.5">
        <div class="p-2.5 rounded-xl bg-blue-500/10 border border-blue-500/20 text-blue-400 shrink-0">
          <i data-lucide="shield-check" class="w-5 h-5"></i>
        </div>
        <div>
          <h4 class="text-sm font-bold text-white" data-i18n="feat_quality">Premium Quality</h4>
          <p class="text-xs text-slate-400 mt-0.5" data-i18n="feat_quality_desc">Top tier components from verified global suppliers.</p>
        </div>
      </div>

      <div class="flex items-start gap-3.5">
        <div class="p-2.5 rounded-xl bg-blue-500/10 border border-blue-500/20 text-blue-400 shrink-0">
          <i data-lucide="gauge" class="w-5 h-5"></i>
        </div>
        <div>
          <h4 class="text-sm font-bold text-white" data-i18n="feat_perf">High Performance</h4>
          <p class="text-xs text-slate-400 mt-0.5" data-i18n="feat_perf_desc">Thermal stress tested for maximum sustained clocks.</p>
        </div>
      </div>

      <div class="flex items-start gap-3.5">
        <div class="p-2.5 rounded-xl bg-blue-500/10 border border-blue-500/20 text-blue-400 shrink-0">
          <i data-lucide="headphones" class="w-5 h-5"></i>
        </div>
        <div>
          <h4 class="text-sm font-bold text-white" data-i18n="feat_support">Expert Support</h4>
          <p class="text-xs text-slate-400 mt-0.5" data-i18n="feat_support_desc">Direct access to systems engineers 24/7/365.</p>
        </div>
      </div>

      <div class="flex items-start gap-3.5 col-span-2 md:col-span-1">
        <div class="p-2.5 rounded-xl bg-blue-500/10 border border-blue-500/20 text-blue-400 shrink-0">
          <i data-lucide="award" class="w-5 h-5"></i>
        </div>
        <div>
          <h4 class="text-sm font-bold text-white" data-i18n="feat_warranty">Warranty Protection</h4>
          <p class="text-xs text-slate-400 mt-0.5" data-i18n="feat_warranty_desc">3-Year standard with on-site replacement guarantee.</p>
        </div>
      </div>

    </div>

    <div class="mt-10 grid grid-cols-1 md:grid-cols-3 gap-6">
      
      <div id="pc-builds" class="group relative rounded-2xl glass-panel p-5 overflow-hidden glass-panel-hover transition duration-300 flex flex-col justify-between">
        <div class="h-44 w-full rounded-xl overflow-hidden relative mb-5">
          <img src="https://images.unsplash.com/photo-1550745165-9bc0b252726f?auto=format&fit=crop&w=800&q=80" 
               alt="PC Builds" class="w-full h-full object-cover group-hover:scale-110 transition duration-500 filter brightness-90">
          <div class="absolute inset-0 bg-gradient-to-t from-[#0d1321] to-transparent"></div>
          <span class="absolute top-3 left-3 text-[10px] font-bold uppercase tracking-wider px-2 py-0.5 rounded bg-blue-600 text-white">Custom</span>
        </div>
        <div>
          <h3 class="text-lg font-bold text-white group-hover:text-blue-400 transition" data-i18n="cat_pc_title">PC BUILDS</h3>
          <p class="text-xs text-slate-400 mt-2 mb-4 leading-relaxed" data-i18n="cat_pc_desc">
            Ultra-fast gaming systems and creator rigs calibrated for ray-tracing, zero frame drops, and whisper-quiet cooling.
          </p>
        </div>
        <a href="#" class="inline-flex items-center gap-1.5 text-xs font-bold text-blue-400 hover:text-blue-300">
          <span data-i18n="link_explore_pc">Explore PC Builds</span>
          <i data-lucide="arrow-right" class="w-3.5 h-3.5 group-hover:translate-x-1 transition"></i>
        </a>
      </div>

      <div id="servers" class="group relative rounded-2xl glass-panel p-5 overflow-hidden glass-panel-hover transition duration-300 flex flex-col justify-between">
        <div class="h-44 w-full rounded-xl overflow-hidden relative mb-5">
          <img src="https://images.unsplash.com/photo-1558494949-ef010cbdcc31?auto=format&fit=crop&w=800&q=80" 
               alt="Servers" class="w-full h-full object-cover group-hover:scale-110 transition duration-500 filter brightness-90">
          <div class="absolute inset-0 bg-gradient-to-t from-[#0d1321] to-transparent"></div>
          <span class="absolute top-3 left-3 text-[10px] font-bold uppercase tracking-wider px-2 py-0.5 rounded bg-cyan-600 text-white">Enterprise</span>
        </div>
        <div>
          <h3 class="text-lg font-bold text-white group-hover:text-blue-400 transition" data-i18n="cat_server_title">SERVERS</h3>
          <p class="text-xs text-slate-400 mt-2 mb-4 leading-relaxed" data-i18n="cat_server_desc">
            Scalable rackmount & blade nodes for LLM fine-tuning, cloud infrastructure, virtualization clusters, and high-frequency workloads.
          </p>
        </div>
        <a href="#" class="inline-flex items-center gap-1.5 text-xs font-bold text-blue-400 hover:text-blue-300">
          <span data-i18n="link_explore_servers">Explore Servers</span>
          <i data-lucide="arrow-right" class="w-3.5 h-3.5 group-hover:translate-x-1 transition"></i>
        </a>
      </div>

      <div id="workstations" class="group relative rounded-2xl glass-panel p-5 overflow-hidden glass-panel-hover transition duration-300 flex flex-col justify-between">
        <div class="h-44 w-full rounded-xl overflow-hidden relative mb-5">
          <img src="https://images.unsplash.com/photo-1593062096033-9a26b09da705?auto=format&fit=crop&w=800&q=80" 
               alt="Workstations" class="w-full h-full object-cover group-hover:scale-110 transition duration-500 filter brightness-90">
          <div class="absolute inset-0 bg-gradient-to-t from-[#0d1321] to-transparent"></div>
          <span class="absolute top-3 left-3 text-[10px] font-bold uppercase tracking-wider px-2 py-0.5 rounded bg-indigo-600 text-white">Workstation</span>
        </div>
        <div>
          <h3 class="text-lg font-bold text-white group-hover:text-blue-400 transition" data-i18n="cat_ws_title">WORKSTATIONS</h3>
          <p class="text-xs text-slate-400 mt-2 mb-4 leading-relaxed" data-i18n="cat_ws_desc">
            Threadripper & Xeon platforms certified for CAD, 3D simulation rendering, VFX suites, and heavy scientific computation.
          </p>
        </div>
        <a href="#" class="inline-flex items-center gap-1.5 text-xs font-bold text-blue-400 hover:text-blue-300">
          <span data-i18n="link_explore_ws">Explore Workstations</span>
          <i data-lucide="arrow-right" class="w-3.5 h-3.5 group-hover:translate-x-1 transition"></i>
        </a>
      </div>

    </div>

    <div class="mt-10 glass-panel rounded-2xl px-6 py-6 border border-white/10 grid grid-cols-2 md:grid-cols-5 gap-6 text-center">
      
      <div class="space-y-1">
        <div class="text-2xl lg:text-3xl font-extrabold text-white">5000+</div>
        <div class="text-[11px] font-semibold text-slate-400 uppercase tracking-wider" data-i18n="stat_builds">Systems Built</div>
      </div>

     
