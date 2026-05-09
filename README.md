<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>SiO Agency — SMM Suite</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link href="https://fonts.googleapis.com/css2?family=Clash+Display:wght@400;500;600;700&family=Satoshi:wght@300;400;500;700&display=swap" rel="stylesheet"/>
<link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&family=Fraunces:ital,wght@0,700;0,900;1,700&display=swap" rel="stylesheet"/>
<style>
:root {
  --bg: #080C14;
  --surface: #0D1220;
  --surface2: #121929;
  --surface3: #18213A;
  --blue: #2563EB;
  --blue2: #3B82F6;
  --blue3: #60A5FA;
  --cyan: #06B6D4;
  --white: #F8FAFF;
  --muted: #64748B;
  --cream: #CBD5E1;
  --border: rgba(59,130,246,0.1);
  --border2: rgba(255,255,255,0.06);
  --success: #10B981;
  --warning: #F59E0B;
  --danger: #EF4444;
}
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box;}
html{scroll-behavior:smooth;}
body{background:var(--bg);color:var(--white);font-family:'Plus Jakarta Sans',sans-serif;overflow-x:hidden;min-height:100vh;}
::-webkit-scrollbar{width:4px;}
::-webkit-scrollbar-thumb{background:var(--blue);border-radius:2px;}

/* ── PAGES ── */
.page{display:none;min-height:100vh;}
.page.active{display:block;}

/* ══════════════════════════════════════
   CLIENT ONBOARDING PAGE
══════════════════════════════════════ */
.onboard-wrap{min-height:100vh;display:flex;align-items:center;justify-content:center;padding:40px 20px;position:relative;overflow:hidden;}
.onboard-wrap::before{content:'';position:absolute;inset:0;background:radial-gradient(ellipse 80% 60% at 50% 0%,rgba(37,99,235,0.12) 0%,transparent 60%),radial-gradient(ellipse 60% 40% at 80% 80%,rgba(6,182,212,0.06) 0%,transparent 50%);pointer-events:none;}
.onboard-card{background:var(--surface);border:1px solid var(--border);border-radius:20px;padding:48px;width:100%;max-width:680px;position:relative;overflow:hidden;}
.onboard-card::before{content:'';position:absolute;top:0;left:0;right:0;height:3px;background:linear-gradient(90deg,var(--blue),var(--cyan),var(--blue2));}
.onboard-logo{display:flex;align-items:center;gap:10px;margin-bottom:36px;}
.logo-mark{width:36px;height:36px;background:linear-gradient(135deg,var(--blue),var(--cyan));border-radius:8px;display:flex;align-items:center;justify-content:center;font-family:'Fraunces',serif;font-weight:900;font-size:16px;color:#fff;}
.logo-name{font-family:'Fraunces',serif;font-size:20px;font-weight:700;color:var(--white);}
.logo-name span{color:var(--blue3);}
.progress-bar{background:var(--surface3);border-radius:100px;height:4px;margin-bottom:36px;overflow:hidden;}
.progress-fill{height:100%;background:linear-gradient(90deg,var(--blue),var(--cyan));border-radius:100px;transition:width 0.4s ease;}
.step{display:none;}
.step.active{display:block;}
.step-label{font-size:11px;font-weight:700;letter-spacing:2px;text-transform:uppercase;color:var(--blue3);margin-bottom:10px;}
.step h2{font-family:'Fraunces',serif;font-size:clamp(22px,3vw,32px);font-weight:700;color:var(--white);margin-bottom:8px;line-height:1.2;}
.step p{font-size:14px;color:var(--muted);margin-bottom:28px;line-height:1.6;}
.form-group{margin-bottom:20px;}
.flabel{display:block;font-size:11px;font-weight:700;letter-spacing:1px;text-transform:uppercase;color:var(--blue3);margin-bottom:8px;}
.finput,.ftextarea,.fselect{width:100%;background:var(--surface2);border:1px solid var(--border2);color:var(--white);padding:13px 16px;border-radius:8px;font-size:14px;font-family:'Plus Jakarta Sans',sans-serif;outline:none;transition:border-color 0.2s;}
.finput::placeholder,.ftextarea::placeholder{color:var(--muted);}
.finput:focus,.ftextarea:focus,.fselect:focus{border-color:var(--blue2);}
.fselect option{background:var(--surface2);}
.ftextarea{resize:vertical;min-height:90px;line-height:1.6;}
.multi-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(150px,1fr));gap:8px;}
.multi-option{background:var(--surface2);border:1px solid var(--border2);border-radius:8px;padding:10px 14px;font-size:13px;color:var(--cream);cursor:pointer;transition:all 0.2s;user-select:none;text-align:center;}
.multi-option:hover{border-color:var(--blue2);color:var(--white);}
.multi-option.selected{background:rgba(37,99,235,0.15);border-color:var(--blue2);color:var(--blue3);}
.form-row{display:grid;grid-template-columns:1fr 1fr;gap:16px;}
.step-nav{display:flex;justify-content:space-between;align-items:center;margin-top:32px;}
.btn-primary{background:linear-gradient(135deg,var(--blue),var(--blue2));color:#fff;padding:14px 28px;border-radius:8px;font-weight:700;font-size:14px;border:none;cursor:pointer;font-family:'Plus Jakarta Sans',sans-serif;transition:all 0.2s;display:inline-flex;align-items:center;gap:8px;}
.btn-primary:hover{transform:translateY(-2px);box-shadow:0 8px 24px rgba(37,99,235,0.3);}
.btn-secondary{background:transparent;color:var(--muted);padding:14px 20px;border-radius:8px;font-weight:600;font-size:14px;border:1px solid var(--border2);cursor:pointer;font-family:'Plus Jakarta Sans',sans-serif;transition:all 0.2s;}
.btn-secondary:hover{color:var(--white);border-color:var(--muted);}
.step-counter{font-size:12px;color:var(--muted);font-weight:600;}

/* THANK YOU */
.thankyou{text-align:center;padding:20px 0;}
.ty-icon{font-size:64px;margin-bottom:20px;display:block;animation:popIn 0.5s ease;}
@keyframes popIn{0%{transform:scale(0);}80%{transform:scale(1.1);}100%{transform:scale(1);}}
.thankyou h2{font-family:'Fraunces',serif;font-size:32px;font-weight:700;color:var(--white);margin-bottom:12px;}
.thankyou p{font-size:15px;color:var(--muted);line-height:1.7;max-width:400px;margin:0 auto;}

/* ══════════════════════════════════════
   DASHBOARD
══════════════════════════════════════ */
.dash-layout{display:flex;min-height:100vh;}

/* SIDEBAR */
.sidebar{width:240px;background:var(--surface);border-right:1px solid var(--border2);display:flex;flex-direction:column;position:fixed;top:0;left:0;height:100vh;z-index:100;transition:transform 0.3s;}
.sidebar-logo{padding:24px 20px;border-bottom:1px solid var(--border2);display:flex;align-items:center;gap:10px;}
.sidebar-nav{flex:1;padding:16px 12px;display:flex;flex-direction:column;gap:4px;overflow-y:auto;}
.nav-item{display:flex;align-items:center;gap:10px;padding:11px 14px;border-radius:8px;cursor:pointer;transition:all 0.2s;font-size:13px;font-weight:600;color:var(--muted);border:none;background:none;width:100%;text-align:left;font-family:'Plus Jakarta Sans',sans-serif;}
.nav-item:hover{background:var(--surface2);color:var(--white);}
.nav-item.active{background:rgba(37,99,235,0.12);color:var(--blue3);}
.nav-item .nav-icon{font-size:16px;width:20px;flex-shrink:0;}
.nav-section{font-size:10px;font-weight:700;letter-spacing:1.5px;text-transform:uppercase;color:var(--muted);padding:12px 14px 6px;opacity:0.5;}
.sidebar-bottom{padding:16px 12px;border-top:1px solid var(--border2);}

/* MAIN */
.dash-main{margin-left:240px;flex:1;padding:32px;min-height:100vh;}
.dash-header{display:flex;justify-content:space-between;align-items:center;margin-bottom:32px;}
.dash-title{font-family:'Fraunces',serif;font-size:28px;font-weight:700;color:var(--white);}
.dash-subtitle{font-size:14px;color:var(--muted);margin-top:4px;}

/* CARDS */
.card{background:var(--surface);border:1px solid var(--border2);border-radius:12px;padding:24px;position:relative;overflow:hidden;}
.card-header{display:flex;justify-content:space-between;align-items:flex-start;margin-bottom:20px;}
.card-title{font-size:14px;font-weight:700;color:var(--white);}
.card-sub{font-size:12px;color:var(--muted);margin-top:3px;}

/* STATS GRID */
.stats-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:16px;margin-bottom:28px;}
.stat-card{background:var(--surface);border:1px solid var(--border2);border-radius:12px;padding:20px;position:relative;overflow:hidden;}
.stat-card::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,var(--blue),var(--cyan));}
.stat-icon{font-size:20px;margin-bottom:12px;}
.stat-val{font-family:'Fraunces',serif;font-size:28px;font-weight:700;color:var(--white);margin-bottom:4px;}
.stat-lbl{font-size:12px;color:var(--muted);font-weight:600;}

/* CLIENTS TABLE */
.clients-grid{display:grid;gap:12px;}
.client-row{background:var(--surface);border:1px solid var(--border2);border-radius:10px;padding:18px 20px;display:flex;align-items:center;gap:16px;transition:border-color 0.2s;cursor:pointer;}
.client-row:hover{border-color:var(--border);}
.client-avatar{width:40px;height:40px;border-radius:10px;background:linear-gradient(135deg,var(--blue),var(--cyan));display:flex;align-items:center;justify-content:center;font-weight:700;font-size:14px;color:#fff;flex-shrink:0;}
.client-info{flex:1;}
.client-name{font-size:14px;font-weight:700;color:var(--white);margin-bottom:3px;}
.client-meta{font-size:12px;color:var(--muted);}
.client-status{display:inline-flex;align-items:center;gap:5px;font-size:11px;font-weight:700;letter-spacing:0.5px;padding:4px 10px;border-radius:100px;}
.status-new{background:rgba(37,99,235,0.1);color:var(--blue3);border:1px solid rgba(37,99,235,0.2);}
.status-active{background:rgba(16,185,129,0.1);color:var(--success);border:1px solid rgba(16,185,129,0.2);}
.status-pending{background:rgba(245,158,11,0.1);color:var(--warning);border:1px solid rgba(245,158,11,0.2);}
.btn-sm{padding:8px 16px;font-size:12px;border-radius:6px;font-weight:700;cursor:pointer;border:none;font-family:'Plus Jakarta Sans',sans-serif;transition:all 0.2s;}
.btn-blue{background:rgba(37,99,235,0.12);color:var(--blue3);border:1px solid rgba(37,99,235,0.2);}
.btn-blue:hover{background:rgba(37,99,235,0.25);}
.btn-green{background:rgba(16,185,129,0.1);color:var(--success);border:1px solid rgba(16,185,129,0.2);}
.btn-danger{background:rgba(239,68,68,0.1);color:var(--danger);border:1px solid rgba(239,68,68,0.2);}

/* CLIENT DETAIL */
.client-detail-header{background:var(--surface);border:1px solid var(--border2);border-radius:12px;padding:28px;margin-bottom:20px;position:relative;overflow:hidden;}
.client-detail-header::before{content:'';position:absolute;top:0;left:0;right:0;height:3px;background:linear-gradient(90deg,var(--blue),var(--cyan));}
.detail-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:16px;margin-top:20px;}
.detail-item{background:var(--surface2);border-radius:8px;padding:14px 16px;}
.detail-lbl{font-size:10px;font-weight:700;letter-spacing:1px;text-transform:uppercase;color:var(--muted);margin-bottom:6px;}
.detail-val{font-size:13px;color:var(--white);font-weight:600;line-height:1.4;}

/* TOOLS TABS */
.tools-tabs{display:flex;gap:4px;background:var(--surface2);border-radius:10px;padding:4px;margin-bottom:24px;flex-wrap:wrap;}
.tool-tab{padding:10px 18px;border-radius:7px;font-size:12px;font-weight:700;color:var(--muted);cursor:pointer;transition:all 0.2s;border:none;background:none;font-family:'Plus Jakarta Sans',sans-serif;white-space:nowrap;}
.tool-tab.active{background:var(--surface);color:var(--blue3);box-shadow:0 1px 3px rgba(0,0,0,0.3);}
.tool-tab:hover{color:var(--white);}
.tool-panel{display:none;}
.tool-panel.active{display:block;}

/* RESULTS */
.result-section{background:var(--surface2);border:1px solid var(--border2);border-radius:10px;padding:20px;margin-bottom:16px;}
.result-title{font-size:12px;font-weight:700;letter-spacing:1px;text-transform:uppercase;color:var(--blue3);margin-bottom:14px;display:flex;align-items:center;gap:8px;}
.pillar-card{background:var(--surface);border:1px solid var(--border2);border-radius:8px;padding:16px;margin-bottom:10px;border-left:3px solid var(--blue);}
.pillar-name{font-size:14px;font-weight:700;color:var(--white);margin-bottom:6px;}
.pillar-desc{font-size:13px;color:var(--muted);line-height:1.6;}
.hook-item{background:var(--surface);border:1px solid var(--border2);border-radius:8px;padding:14px 16px;margin-bottom:8px;font-size:13px;color:var(--cream);line-height:1.6;display:flex;gap:12px;align-items:flex-start;}
.hook-num{font-family:'Fraunces',serif;font-size:16px;font-weight:700;color:var(--blue3);flex-shrink:0;min-width:20px;}
.platform-card{background:var(--surface);border:1px solid var(--border2);border-radius:8px;padding:16px;margin-bottom:10px;display:flex;gap:14px;align-items:flex-start;}
.platform-icon{font-size:28px;flex-shrink:0;}
.platform-name{font-size:14px;font-weight:700;color:var(--white);margin-bottom:4px;}
.platform-reason{font-size:12px;color:var(--muted);line-height:1.6;}
.platform-priority{font-size:10px;font-weight:700;letter-spacing:1px;text-transform:uppercase;padding:3px 8px;border-radius:100px;margin-top:6px;display:inline-block;}
.priority-high{background:rgba(16,185,129,0.1);color:var(--success);}
.priority-med{background:rgba(245,158,11,0.1);color:var(--warning);}
.calendar-grid{display:grid;grid-template-columns:repeat(7,1fr);gap:8px;margin-bottom:16px;}
.cal-day-header{font-size:10px;font-weight:700;text-transform:uppercase;color:var(--muted);text-align:center;padding:8px 4px;}
.cal-day{background:var(--surface);border:1px solid var(--border2);border-radius:8px;padding:10px;min-height:80px;font-size:11px;}
.cal-day-num{font-size:10px;color:var(--muted);margin-bottom:6px;font-weight:600;}
.cal-post{background:rgba(37,99,235,0.1);border-left:2px solid var(--blue);padding:4px 6px;border-radius:3px;color:var(--blue3);font-size:10px;line-height:1.4;margin-bottom:4px;}
.comp-card{background:var(--surface);border:1px solid var(--border2);border-radius:8px;padding:16px;margin-bottom:10px;}
.comp-name{font-size:14px;font-weight:700;color:var(--white);margin-bottom:10px;}
.comp-grid{display:grid;grid-template-columns:1fr 1fr;gap:10px;}
.comp-section h4{font-size:10px;font-weight:700;letter-spacing:1px;text-transform:uppercase;margin-bottom:6px;}
.comp-doing h4{color:var(--success);}
.comp-missing h4{color:var(--danger);}
.comp-item{font-size:12px;color:var(--cream);padding:4px 0;border-bottom:1px solid var(--border2);line-height:1.5;}
.comp-item:last-child{border-bottom:none;}

/* KPI TRACKER */
.kpi-inputs{display:grid;grid-template-columns:repeat(4,1fr);gap:12px;margin-bottom:20px;}
.kpi-input-card{background:var(--surface2);border:1px solid var(--border2);border-radius:8px;padding:14px;}
.kpi-input-card label{font-size:10px;font-weight:700;letter-spacing:1px;text-transform:uppercase;color:var(--muted);display:block;margin-bottom:8px;}
.kpi-num-input{width:100%;background:var(--surface);border:1px solid var(--border2);color:var(--white);padding:10px 12px;border-radius:6px;font-size:16px;font-weight:700;font-family:'Fraunces',serif;outline:none;text-align:center;}
.kpi-num-input:focus{border-color:var(--blue2);}
.kpi-history{display:flex;flex-direction:column;gap:8px;}
.kpi-week-row{background:var(--surface2);border-radius:8px;padding:14px 16px;display:flex;justify-content:space-between;align-items:center;font-size:13px;}
.kpi-week-label{color:var(--muted);font-weight:600;}
.kpi-week-data{display:flex;gap:20px;}
.kpi-metric{text-align:center;}
.kpi-metric-val{font-family:'Fraunces',serif;font-size:16px;font-weight:700;color:var(--blue3);}
.kpi-metric-lbl{font-size:10px;color:var(--muted);font-weight:600;}

/* GENERATE BUTTON */
.gen-btn{background:linear-gradient(135deg,var(--blue),var(--cyan));color:#fff;padding:14px 28px;border-radius:8px;font-weight:700;font-size:14px;border:none;cursor:pointer;font-family:'Plus Jakarta Sans',sans-serif;transition:all 0.3s;display:flex;align-items:center;gap:10px;margin-bottom:24px;}
.gen-btn:hover{transform:translateY(-2px);box-shadow:0 8px 28px rgba(37,99,235,0.35);}
.gen-btn.loading{opacity:0.7;cursor:wait;}

/* COPY LINK */
.copy-link-box{background:var(--surface2);border:1px solid var(--border);border-radius:8px;padding:14px 16px;display:flex;align-items:center;gap:12px;margin-bottom:24px;}
.copy-link-url{flex:1;font-size:12px;color:var(--blue3);font-family:monospace;overflow:hidden;text-overflow:ellipsis;white-space:nowrap;}
.copy-btn{background:rgba(37,99,235,0.12);color:var(--blue3);border:1px solid rgba(37,99,235,0.2);padding:8px 14px;border-radius:6px;font-size:11px;font-weight:700;cursor:pointer;font-family:'Plus Jakarta Sans',sans-serif;white-space:nowrap;transition:all 0.2s;}
.copy-btn:hover{background:rgba(37,99,235,0.25);}

/* LOGIN */
.login-wrap{min-height:100vh;display:flex;align-items:center;justify-content:center;padding:20px;background:var(--bg);}
.login-wrap::before{content:'';position:absolute;inset:0;background:radial-gradient(ellipse 60% 50% at 50% 30%,rgba(37,99,235,0.1) 0%,transparent 60%);pointer-events:none;}
.login-card{background:var(--surface);border:1px solid var(--border);border-radius:20px;padding:48px;width:100%;max-width:420px;position:relative;overflow:hidden;z-index:1;}
.login-card::before{content:'';position:absolute;top:0;left:0;right:0;height:3px;background:linear-gradient(90deg,var(--blue),var(--cyan));}

/* BADGE */
.badge{display:inline-flex;align-items:center;gap:5px;font-size:10px;font-weight:700;letter-spacing:0.5px;padding:4px 10px;border-radius:100px;}
.badge-blue{background:rgba(37,99,235,0.1);color:var(--blue3);border:1px solid rgba(37,99,235,0.2);}
.badge-green{background:rgba(16,185,129,0.1);color:var(--success);border:1px solid rgba(16,185,129,0.2);}

/* EMPTY STATE */
.empty-state{text-align:center;padding:48px 20px;}
.empty-icon{font-size:48px;margin-bottom:16px;opacity:0.5;}
.empty-title{font-size:16px;font-weight:700;color:var(--white);margin-bottom:8px;}
.empty-sub{font-size:14px;color:var(--muted);line-height:1.6;}

/* ONBOARDING LINK COPY */
.onboard-link-section{background:linear-gradient(135deg,rgba(37,99,235,0.08),rgba(6,182,212,0.05));border:1px solid var(--border);border-radius:12px;padding:20px;margin-bottom:24px;}

/* RESPONSIVE */
@media(max-width:900px){
  .sidebar{transform:translateX(-100%);}
  .sidebar.open{transform:translateX(0);}
  .dash-main{margin-left:0;padding:20px;}
  .stats-grid{grid-template-columns:repeat(2,1fr);}
  .form-row{grid-template-columns:1fr;}
  .kpi-inputs{grid-template-columns:repeat(2,1fr);}
  .calendar-grid{grid-template-columns:repeat(4,1fr);}
  .comp-grid{grid-template-columns:1fr;}
}
</style>
</head>
<body>

<!-- ══════════════════════════════════════
     PAGE: CLIENT ONBOARDING
══════════════════════════════════════ -->
<div id="page-onboard" class="page active">
  <div class="onboard-wrap">
    <div class="onboard-card">
      <div class="onboard-logo">
        <div class="logo-mark">S</div>
        <div class="logo-name">Si<span>O</span> Agency</div>
      </div>
      <div class="progress-bar"><div class="progress-fill" id="progress" style="width:14%"></div></div>

      <!-- STEP 1 -->
      <div class="step active" id="step-1">
        <div class="step-label">Step 1 of 7 — Project Basics</div>
        <h2>Tell us about your project</h2>
        <p>Let's start with the fundamentals of what you're building.</p>
        <div class="form-group"><label class="flabel">Project / Brand Name *</label><input class="finput" type="text" placeholder="e.g. Rally Protocol" id="q-name"/></div>
        <div class="form-group"><label class="flabel">What does your project do? *</label><textarea class="ftextarea" placeholder="Describe your project in simple terms..." id="q-what"></textarea></div>
        <div class="form-group"><label class="flabel">What problem does it solve? *</label><textarea class="ftextarea" placeholder="What pain point are you addressing?" id="q-problem"></textarea></div>
        <div class="step-nav"><div class="step-counter">1 / 7</div><button class="btn-primary" onclick="nextStep(1)">Continue →</button></div>
      </div>

      <!-- STEP 2 -->
      <div class="step" id="step-2">
        <div class="step-label">Step 2 of 7 — Project Stage & Category</div>
        <h2>Where are you right now?</h2>
        <p>This helps us tailor the right strategy for your current phase.</p>
        <div class="form-group">
          <label class="flabel">Project Stage *</label>
          <div class="multi-grid" id="q-stage">
            <div class="multi-option single-select" onclick="selectSingle(this,'q-stage')" data-val="idea">💡 Idea Stage</div>
            <div class="multi-option single-select" onclick="selectSingle(this,'q-stage')" data-val="pre-launch">🚀 Pre-Launch</div>
            <div class="multi-option single-select" onclick="selectSingle(this,'q-stage')" data-val="just-launched">🎉 Just Launched</div>
            <div class="multi-option single-select" onclick="selectSingle(this,'q-stage')" data-val="growing">📈 Growing</div>
            <div class="multi-option single-select" onclick="selectSingle(this,'q-stage')" data-val="scaling">🔥 Scaling</div>
          </div>
        </div>
        <div class="form-group">
          <label class="flabel">Project Category (select all that apply)</label>
          <div class="multi-grid" id="q-category">
            <div class="multi-option" onclick="toggleMulti(this)" data-val="defi">DeFi</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="nft">NFT</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="gamefi">GameFi</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="rwa">RWA</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="ai-web3">AI + Web3</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="fintech">Fintech</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="socialfi">SocialFi</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="infra">Infrastructure</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="dao">DAO</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="other">Other</div>
          </div>
        </div>
        <div class="step-nav"><button class="btn-secondary" onclick="prevStep(2)">← Back</button><div class="step-counter">2 / 7</div><button class="btn-primary" onclick="nextStep(2)">Continue →</button></div>
      </div>

      <!-- STEP 3 -->
      <div class="step" id="step-3">
        <div class="step-label">Step 3 of 7 — Target Audience</div>
        <h2>Who are you trying to reach?</h2>
        <p>Understanding your audience shapes every content decision.</p>
        <div class="form-group">
          <label class="flabel">Primary Audience (select all that apply)</label>
          <div class="multi-grid" id="q-audience">
            <div class="multi-option" onclick="toggleMulti(this)" data-val="retail">Retail Investors</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="crypto-natives">Crypto Natives</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="developers">Web3 Developers</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="founders">Founders</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="vcs">VCs / Investors</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="african">African Market</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="global">Global Market</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="genz">Gen Z</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="millennials">Millennials</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="institutions">Institutions</div>
          </div>
        </div>
        <div class="form-group"><label class="flabel">What is your audience's biggest pain point?</label><textarea class="ftextarea" placeholder="What keeps your target audience up at night?" id="q-painpoint"></textarea></div>
        <div class="form-group"><label class="flabel">Audience's average knowledge of crypto</label>
          <div class="multi-grid" id="q-knowledge">
            <div class="multi-option single-select" onclick="selectSingle(this,'q-knowledge')" data-val="beginner">🌱 Beginner</div>
            <div class="multi-option single-select" onclick="selectSingle(this,'q-knowledge')" data-val="intermediate">📚 Intermediate</div>
            <div class="multi-option single-select" onclick="selectSingle(this,'q-knowledge')" data-val="advanced">🧠 Advanced</div>
            <div class="multi-option single-select" onclick="selectSingle(this,'q-knowledge')" data-val="mixed">🔀 Mixed</div>
          </div>
        </div>
        <div class="step-nav"><button class="btn-secondary" onclick="prevStep(3)">← Back</button><div class="step-counter">3 / 7</div><button class="btn-primary" onclick="nextStep(3)">Continue →</button></div>
      </div>

      <!-- STEP 4 -->
      <div class="step" id="step-4">
        <div class="step-label">Step 4 of 7 — Brand & Voice</div>
        <h2>What's your brand personality?</h2>
        <p>Your tone of voice defines how your community experiences you.</p>
        <div class="form-group">
          <label class="flabel">Tone of Voice (select all that apply)</label>
          <div class="multi-grid" id="q-tone">
            <div class="multi-option" onclick="toggleMulti(this)" data-val="professional">🎩 Professional</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="friendly">😊 Friendly</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="bold">💥 Bold</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="educational">📖 Educational</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="community-first">🤝 Community-First</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="humorous">😄 Humorous</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="visionary">🔭 Visionary</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="technical">⚙️ Technical</div>
          </div>
        </div>
        <div class="form-group"><label class="flabel">Describe your brand in 3 words</label><input class="finput" type="text" placeholder="e.g. Innovative, Trustworthy, Bold" id="q-brand3"/></div>
        <div class="form-group"><label class="flabel">Any brands you admire or want to be compared to?</label><input class="finput" type="text" placeholder="e.g. Binance, Coinbase, Uniswap" id="q-admire"/></div>
        <div class="step-nav"><button class="btn-secondary" onclick="prevStep(4)">← Back</button><div class="step-counter">4 / 7</div><button class="btn-primary" onclick="nextStep(4)">Continue →</button></div>
      </div>

      <!-- STEP 5 -->
      <div class="step" id="step-5">
        <div class="step-label">Step 5 of 7 — Goals & Timeline</div>
        <h2>What do you want to achieve?</h2>
        <p>Clear goals help us build the right strategy and measure success.</p>
        <div class="form-group">
          <label class="flabel">Main Goals (select all that apply)</label>
          <div class="multi-grid" id="q-goals">
            <div class="multi-option" onclick="toggleMulti(this)" data-val="awareness">📢 Brand Awareness</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="community">👥 Community Building</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="leads">🎯 Lead Generation</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="investors">💼 Investor Attention</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="token">🪙 Token Launch</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="partnerships">🤝 Partnership Deals</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="retention">🔄 Community Retention</div>
            <div class="multi-option" onclick="toggleMulti(this)" data-val="education">📚 Educate Market</div>
          </div>
        </div>
        <div class="form-group"><label class="flabel">Timeline</label>
          <div class="multi-grid" id="q-timeline">
            <div class="multi-option single-select" onclick="selectSingle(this,'q-timeline')" data-val="1-month">1 Month</div>
            <div class="multi-option single-select" onclick="selectSingle(this,'q-timeline')" data-val="3-months">3 Months</div>
            <div class="multi-option single-select" onclick="selectSingle(this,'q-timeline')" data-val="6-months">6 Months</div>
            <div class="multi-option single-select" onclick="selectSingle(this,'q-timeline')" data-val="12-months">12 Months</div>
            <div class="multi-option single-select" onclick="selectSingle(this,'q-timeline')" data-val="ongoing">Ongoing</div>
          </div>
        </div>
        <div class="form-group"><label class="flabel">Success looks like... (what does winning mean to you?)</label><textarea class="ftextarea" placeholder="e.g. 10k Twitter followers, 5000 Discord members, first funding round..." id="q-success"></textarea></div>
        <div class="step-nav"><button class="btn-secondary" onclick="prevStep(5)">← Back</button><div class="step-counter">5 / 7</div><button class="btn-primary" onclick="nextStep(5)">Continue →</button></div>
      </div>

      <!-- STEP 6 -->
      <div class="step" id="step-6">
        <div class="step-label">Step 6 of 7 — Competitors & Socials</div>
        <h2>Who else is in your space?</h2>
        <p>Knowing your competitors helps us find your positioning gaps.</p>
        <div class="form-group"><label class="flabel">Top Competitor 1</label><input class="finput" type="text" placeholder="Project name or X handle" id="q-comp1"/></div>
        <div class="form-group"><label class="flabel">Top Competitor 2</label><input class="finput" type="text" placeholder="Project name or X handle" id="q-comp2"/></div>
        <div class="form-group"><label class="flabel">Top Competitor 3</label><input class="finput" type="text" placeholder="Project name or X handle" id="q-comp3"/></div>
        <div class="form-group"><label class="flabel">What are competitors doing wrong? (your gap opportunity)</label><textarea class="ftextarea" placeholder="What do you see them missing or doing poorly?" id="q-compgap"></textarea></div>
        <div class="form-group">
          <label class="flabel">Current Social Handles (optional)</label>
          <div class="form-row">
            <input class="finput" type="text" placeholder="X / Twitter handle" id="q-twitter"/>
            <input class="finput" type="text" placeholder="LinkedIn URL" id="q-linkedin"/>
          </div>
          <div class="form-row" style="margin-top:10px;">
            <input class="finput" type="text" placeholder="Telegram group" id="q-telegram"/>
            <input class="finput" type="text" placeholder="Discord server" id="q-discord"/>
          </div>
        </div>
        <div class="step-nav"><button class="btn-secondary" onclick="prevStep(6)">← Back</button><div class="step-counter">6 / 7</div><button class="btn-primary" onclick="nextStep(6)">Continue →</button></div>
      </div>

      <!-- STEP 7 -->
      <div class="step" id="step-7">
        <div class="step-label">Step 7 of 7 — Final Details</div>
        <h2>Almost done!</h2>
        <p>A few last details to complete your brief.</p>
        <div class="form-group"><label class="flabel">Contact Name *</label><input class="finput" type="text" placeholder="Your full name" id="q-contact"/></div>
        <div class="form-group"><label class="flabel">Contact Email *</label><input class="finput" type="email" placeholder="your@email.com" id="q-email"/></div>
        <div class="form-group"><label class="flabel">Anything else we should know?</label><textarea class="ftextarea" placeholder="Any context, constraints, or specific requests..." id="q-extra"></textarea></div>
        <div class="form-group"><label class="flabel">How did you hear about SiO Agency?</label>
          <div class="multi-grid" id="q-source">
            <div class="multi-option single-select" onclick="selectSingle(this,'q-source')" data-val="x">X / Twitter</div>
            <div class="multi-option single-select" onclick="selectSingle(this,'q-source')" data-val="linkedin">LinkedIn</div>
            <div class="multi-option single-select" onclick="selectSingle(this,'q-source')" data-val="referral">Referral</div>
            <div class="multi-option single-select" onclick="selectSingle(this,'q-source')" data-val="google">Google</div>
            <div class="multi-option single-select" onclick="selectSingle(this,'q-source')" data-val="other">Other</div>
          </div>
        </div>
        <div class="step-nav"><button class="btn-secondary" onclick="prevStep(7)">← Back</button><div class="step-counter">7 / 7</div><button class="btn-primary" onclick="submitOnboarding()">Submit Brief ✓</button></div>
      </div>

      <!-- THANK YOU -->
      <div class="step" id="step-thanks">
        <div class="thankyou">
          <span class="ty-icon">🎉</span>
          <h2>Brief Received!</h2>
          <p>Thank you for completing your onboarding brief. Our team will review your project details and get back to you within 24 hours with your tailored strategy.</p>
          <div style="margin-top:24px;padding:16px;background:var(--surface2);border-radius:8px;font-size:13px;color:var(--muted);line-height:1.6;">
            📧 A confirmation has been sent to <strong id="confirm-email" style="color:var(--blue3);"></strong>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- ══════════════════════════════════════
     PAGE: LOGIN
══════════════════════════════════════ -->
<div id="page-login" class="page">
  <div class="login-wrap">
    <div class="login-card">
      <div class="onboard-logo" style="margin-bottom:28px;">
        <div class="logo-mark">S</div>
        <div class="logo-name">Si<span>O</span> Agency</div>
      </div>
      <h2 style="font-family:'Fraunces',serif;font-size:24px;font-weight:700;color:var(--white);margin-bottom:6px;">Welcome back</h2>
      <p style="font-size:14px;color:var(--muted);margin-bottom:28px;">Sign in to your agency dashboard</p>
      <div class="form-group"><label class="flabel">Password</label><input class="finput" type="password" id="login-pw" placeholder="Enter your password" onkeypress="if(event.key==='Enter')doLogin()"/></div>
      <button class="btn-primary" style="width:100%;justify-content:center;margin-top:8px;" onclick="doLogin()">Sign In →</button>
      <p id="login-err" style="color:var(--danger);font-size:13px;margin-top:12px;display:none;text-align:center;">Incorrect password. Try again.</p>
    </div>
  </div>
</div>

<!-- ══════════════════════════════════════
     PAGE: DASHBOARD
══════════════════════════════════════ -->
<div id="page-dashboard" class="page">
  <div class="dash-layout">

    <!-- SIDEBAR -->
    <div class="sidebar" id="sidebar">
      <div class="sidebar-logo">
        <div class="logo-mark">S</div>
        <div class="logo-name">Si<span>O</span></div>
      </div>
      <nav class="sidebar-nav">
        <div class="nav-section">Main</div>
        <button class="nav-item active" onclick="showDash('overview')" id="dnav-overview"><span class="nav-icon">📊</span>Overview</button>
        <button class="nav-item" onclick="showDash('clients')" id="dnav-clients"><span class="nav-icon">👥</span>Clients</button>
        <div class="nav-section">Tools</div>
        <button class="nav-item" onclick="showDash('onboard-link')" id="dnav-onboard-link"><span class="nav-icon">🔗</span>Onboarding Link</button>
      </nav>
      <div class="sidebar-bottom">
        <button class="nav-item" onclick="doLogout()" style="color:var(--danger);"><span class="nav-icon">🚪</span>Sign Out</button>
      </div>
    </div>

    <!-- MAIN CONTENT -->
    <div class="dash-main">

      <!-- OVERVIEW -->
      <div id="dpanel-overview" class="dpanel">
        <div class="dash-header">
          <div><div class="dash-title">Good morning, SiO 👋</div><div class="dash-subtitle">Here's what's happening with your clients</div></div>
          <button class="btn-primary btn-sm" onclick="showDash('clients')">View All Clients</button>
        </div>
        <div class="stats-grid">
          <div class="stat-card"><div class="stat-icon">👥</div><div class="stat-val" id="stat-total">0</div><div class="stat-lbl">Total Clients</div></div>
          <div class="stat-card"><div class="stat-icon">✅</div><div class="stat-val" id="stat-active">0</div><div class="stat-lbl">Active</div></div>
          <div class="stat-card"><div class="stat-icon">🆕</div><div class="stat-val" id="stat-new">0</div><div class="stat-lbl">New This Month</div></div>
          <div class="stat-card"><div class="stat-icon">📋</div><div class="stat-val" id="stat-briefs">0</div><div class="stat-lbl">Briefs Received</div></div>
        </div>
        <div class="card">
          <div class="card-header"><div><div class="card-title">Recent Client Submissions</div><div class="card-sub">Latest onboarding briefs from clients</div></div></div>
          <div id="recent-clients-list"><div class="empty-state"><div class="empty-icon">📭</div><div class="empty-title">No clients yet</div><div class="empty-sub">Share your onboarding link to get your first client brief</div></div></div>
        </div>
      </div>

      <!-- CLIENTS -->
      <div id="dpanel-clients" class="dpanel" style="display:none;">
        <div class="dash-header">
          <div><div class="dash-title">Clients</div><div class="dash-subtitle">All client briefs and strategies</div></div>
        </div>
        <div id="clients-list"><div class="empty-state"><div class="empty-icon">👥</div><div class="empty-title">No clients yet</div><div class="empty-sub">Share your onboarding link and wait for briefs to come in</div></div></div>
      </div>

      <!-- CLIENT DETAIL -->
      <div id="dpanel-client-detail" class="dpanel" style="display:none;">
        <div class="dash-header">
          <div><button class="btn-sm btn-blue" onclick="showDash('clients')" style="margin-bottom:8px;">← Back to Clients</button><div class="dash-title" id="detail-title">Client Name</div><div class="dash-subtitle" id="detail-sub">Client details and strategy</div></div>
        </div>
        <div class="client-detail-header" id="detail-header"></div>
        <div class="tools-tabs">
          <button class="tool-tab active" onclick="showTool('pillars',this)">📌 Content Pillars</button>
          <button class="tool-tab" onclick="showTool('hooks',this)">🎣 Hook Formulas</button>
          <button class="tool-tab" onclick="showTool('calendar',this)">📅 Content Calendar</button>
          <button class="tool-tab" onclick="showTool('platforms',this)">📱 Platform Recs</button>
          <button class="tool-tab" onclick="showTool('competitors',this)">🔍 Competitor Analysis</button>
          <button class="tool-tab" onclick="showTool('kpi',this)">📈 KPI Tracker</button>
        </div>
        <div id="tool-pillars" class="tool-panel active"><div id="pillars-content"></div></div>
        <div id="tool-hooks" class="tool-panel"><div id="hooks-content"></div></div>
        <div id="tool-calendar" class="tool-panel"><div id="calendar-content"></div></div>
        <div id="tool-platforms" class="tool-panel"><div id="platforms-content"></div></div>
        <div id="tool-competitors" class="tool-panel"><div id="competitors-content"></div></div>
        <div id="tool-kpi" class="tool-panel"><div id="kpi-content"></div></div>
      </div>

      <!-- ONBOARDING LINK -->
      <div id="dpanel-onboard-link" class="dpanel" style="display:none;">
        <div class="dash-header"><div><div class="dash-title">Onboarding Link</div><div class="dash-subtitle">Share this link with new clients</div></div></div>
        <div class="card">
          <div class="card-header"><div><div class="card-title">Your Client Onboarding Link</div><div class="card-sub">Send this to any new client to collect their project brief</div></div></div>
          <div class="onboard-link-section">
            <p style="font-size:13px;color:var(--muted);margin-bottom:12px;">Share this link with your clients. They fill in a comprehensive 7-step questionnaire and you get their full brief here in your dashboard.</p>
            <div class="copy-link-box">
              <span class="copy-link-url" id="onboard-url">Loading...</span>
              <button class="copy-btn" onclick="copyOnboardLink()">📋 Copy Link</button>
            </div>
            <p style="font-size:12px;color:var(--muted);">✅ Clients only see a thank you page after submitting — they never see your dashboard or generated strategies.</p>
          </div>
          <div style="background:var(--surface2);border-radius:10px;padding:20px;">
            <div style="font-size:12px;font-weight:700;letter-spacing:1px;text-transform:uppercase;color:var(--blue3);margin-bottom:14px;">What the questionnaire covers:</div>
            <div style="display:grid;grid-template-columns:1fr 1fr;gap:10px;">
              <div style="font-size:13px;color:var(--cream);display:flex;gap:8px;align-items:flex-start;"><span>✦</span>Project basics & description</div>
              <div style="font-size:13px;color:var(--cream);display:flex;gap:8px;align-items:flex-start;"><span>✦</span>Stage & category</div>
              <div style="font-size:13px;color:var(--cream);display:flex;gap:8px;align-items:flex-start;"><span>✦</span>Target audience & pain points</div>
              <div style="font-size:13px;color:var(--cream);display:flex;gap:8px;align-items:flex-start;"><span>✦</span>Brand tone & personality</div>
              <div style="font-size:13px;color:var(--cream);display:flex;gap:8px;align-items:flex-start;"><span>✦</span>Goals & timeline</div>
              <div style="font-size:13px;color:var(--cream);display:flex;gap:8px;align-items:flex-start;"><span>✦</span>Competitors & social handles</div>
            </div>
          </div>
        </div>
      </div>

    </div>
  </div>
</div>

<script>
// ══════════════════════════════════════════
// STATE
// ══════════════════════════════════════════
const APP = {
  clients: [],
  currentClient: null,
  loggedIn: false,
  password: 'Successfuljosh@35'
};

// Load from localStorage
function loadState(){
  const saved = localStorage.getItem('sio_clients');
  if(saved) APP.clients = JSON.parse(saved);
}

function saveState(){
  localStorage.setItem('sio_clients', JSON.stringify(APP.clients));
}

// ══════════════════════════════════════════
// PAGE ROUTING
// ══════════════════════════════════════════
function showPage(id){
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  document.getElementById('page-'+id).classList.add('active');
}

// Check URL on load
window.addEventListener('DOMContentLoaded', function(){
  loadState();
  const hash = window.location.hash;
  if(hash === '#dashboard'){
    if(APP.loggedIn) { showPage('dashboard'); initDashboard(); }
    else showPage('login');
  } else if(hash === '#login'){
    showPage('login');
  } else {
    showPage('onboard');
  }
  // Set onboarding URL
  const base = window.location.href.split('#')[0];
  document.getElementById('onboard-url').textContent = base + '#onboard';
});

// ══════════════════════════════════════════
// ONBOARDING FORM
// ══════════════════════════════════════════
let currentStep = 1;
const totalSteps = 7;

function toggleMulti(el){
  el.classList.toggle('selected');
}

function selectSingle(el, groupId){
  const group = document.getElementById(groupId);
  group.querySelectorAll('.multi-option').forEach(o => o.classList.remove('selected'));
  el.classList.add('selected');
}

function getSelectedVals(groupId){
  const group = document.getElementById(groupId);
  if(!group) return [];
  return Array.from(group.querySelectorAll('.selected')).map(o => o.dataset.val);
}

function getVal(id){ const el = document.getElementById(id); return el ? el.value.trim() : ''; }

function nextStep(from){
  // Validation
  if(from === 1){
    if(!getVal('q-name')){ alert('Please enter your project name.'); return; }
    if(!getVal('q-what')){ alert('Please describe your project.'); return; }
  }
  if(from === 7){
    if(!getVal('q-contact')){ alert('Please enter your contact name.'); return; }
    if(!getVal('q-email')){ alert('Please enter your email.'); return; }
  }
  document.getElementById('step-'+from).classList.remove('active');
  currentStep = from + 1;
  document.getElementById('step-'+currentStep).classList.add('active');
  updateProgress();
}

function prevStep(from){
  document.getElementById('step-'+from).classList.remove('active');
  currentStep = from - 1;
  document.getElementById('step-'+currentStep).classList.add('active');
  updateProgress();
}

function updateProgress(){
  const pct = (currentStep / totalSteps) * 100;
  document.getElementById('progress').style.width = pct + '%';
}

function submitOnboarding(){
  if(!getVal('q-contact')){ alert('Please enter your contact name.'); return; }
  if(!getVal('q-email')){ alert('Please enter your contact email.'); return; }

  const client = {
    id: 'c_' + Date.now(),
    submittedAt: new Date().toLocaleDateString(),
    status: 'new',
    data: {
      name: getVal('q-name'),
      what: getVal('q-what'),
      problem: getVal('q-problem'),
      stage: getSelectedVals('q-stage')[0] || '',
      category: getSelectedVals('q-category'),
      audience: getSelectedVals('q-audience'),
      painpoint: getVal('q-painpoint'),
      knowledge: getSelectedVals('q-knowledge')[0] || '',
      tone: getSelectedVals('q-tone'),
      brand3: getVal('q-brand3'),
      admire: getVal('q-admire'),
      goals: getSelectedVals('q-goals'),
      timeline: getSelectedVals('q-timeline')[0] || '',
      success: getVal('q-success'),
      comp1: getVal('q-comp1'),
      comp2: getVal('q-comp2'),
      comp3: getVal('q-comp3'),
      compgap: getVal('q-compgap'),
      twitter: getVal('q-twitter'),
      linkedin: getVal('q-linkedin'),
      telegram: getVal('q-telegram'),
      discord: getVal('q-discord'),
      contact: getVal('q-contact'),
      email: getVal('q-email'),
      extra: getVal('q-extra'),
      source: getSelectedVals('q-source')[0] || ''
    },
    kpiHistory: [],
    generated: false
  };

  APP.clients.unshift(client);
  saveState();

  document.getElementById('confirm-email').textContent = client.data.email;
  document.getElementById('step-7').classList.remove('active');
  document.getElementById('step-thanks').classList.add('active');
  document.getElementById('progress').style.width = '100%';
}

// ══════════════════════════════════════════
// AUTH
// ══════════════════════════════════════════
function doLogin(){
  const pw = document.getElementById('login-pw').value;
  if(pw === APP.password){
    APP.loggedIn = true;
    showPage('dashboard');
    initDashboard();
  } else {
    document.getElementById('login-err').style.display = 'block';
  }
}

function doLogout(){
  APP.loggedIn = false;
  showPage('login');
}

// Admin access from onboarding page
function goToDash(){
  if(APP.loggedIn){ showPage('dashboard'); initDashboard(); }
  else showPage('login');
}

// ══════════════════════════════════════════
// DASHBOARD NAV
// ══════════════════════════════════════════
function showDash(panel){
  document.querySelectorAll('.dpanel').forEach(p => p.style.display = 'none');
  document.getElementById('dpanel-'+panel).style.display = 'block';
  document.querySelectorAll('.nav-item').forEach(n => n.classList.remove('active'));
  const navEl = document.getElementById('dnav-'+panel);
  if(navEl) navEl.classList.add('active');
  if(panel === 'overview') renderOverview();
  if(panel === 'clients') renderClients();
}

function initDashboard(){
  loadState();
  renderOverview();
  renderClients();
  showDash('overview');
}

// ══════════════════════════════════════════
// RENDER OVERVIEW
// ══════════════════════════════════════════
function renderOverview(){
  document.getElementById('stat-total').textContent = APP.clients.length;
  document.getElementById('stat-active').textContent = APP.clients.filter(c=>c.status==='active').length;
  document.getElementById('stat-new').textContent = APP.clients.filter(c=>c.status==='new').length;
  document.getElementById('stat-briefs').textContent = APP.clients.length;

  const list = document.getElementById('recent-clients-list');
  if(!APP.clients.length){
    list.innerHTML = '<div class="empty-state"><div class="empty-icon">📭</div><div class="empty-title">No clients yet</div><div class="empty-sub">Share your onboarding link to get your first client brief</div></div>';
    return;
  }
  list.innerHTML = APP.clients.slice(0,5).map(c => clientRowHTML(c)).join('');
}

// ══════════════════════════════════════════
// RENDER CLIENTS
// ══════════════════════════════════════════
function renderClients(){
  const list = document.getElementById('clients-list');
  if(!APP.clients.length){
    list.innerHTML = '<div class="empty-state"><div class="empty-icon">👥</div><div class="empty-title">No clients yet</div><div class="empty-sub">Share your onboarding link and wait for briefs to come in</div></div>';
    return;
  }
  list.innerHTML = '<div class="clients-grid">'+APP.clients.map(c => clientRowHTML(c)).join('')+'</div>';
}

function clientRowHTML(c){
  const initials = c.data.name.substring(0,2).toUpperCase();
  const statusClass = c.status === 'active' ? 'status-active' : c.status === 'new' ? 'status-new' : 'status-pending';
  const statusLabel = c.status === 'active' ? '● Active' : c.status === 'new' ? '● New' : '● Pending';
  return `<div class="client-row" onclick="openClient('${c.id}')">
    <div class="client-avatar">${initials}</div>
    <div class="client-info">
      <div class="client-name">${c.data.name}</div>
      <div class="client-meta">${c.data.stage || 'Stage TBD'} · ${c.data.category.slice(0,2).join(', ') || 'Category TBD'} · Submitted ${c.submittedAt}</div>
    </div>
    <span class="client-status ${statusClass}">${statusLabel}</span>
    <button class="btn-sm btn-blue" onclick="event.stopPropagation();openClient('${c.id}')">View Brief →</button>
  </div>`;
}

// ══════════════════════════════════════════
// CLIENT DETAIL
// ══════════════════════════════════════════
function openClient(id){
  const client = APP.clients.find(c => c.id === id);
  if(!client) return;
  APP.currentClient = client;
  client.status = 'active';
  saveState();

  document.getElementById('detail-title').textContent = client.data.name;
  document.getElementById('detail-sub').textContent = client.data.contact + ' · ' + client.data.email;

  // Header
  document.getElementById('detail-header').innerHTML = `
    <div style="display:flex;justify-content:space-between;align-items:flex-start;flex-wrap:wrap;gap:16px;">
      <div>
        <div style="font-size:12px;font-weight:700;letter-spacing:1px;text-transform:uppercase;color:var(--blue3);margin-bottom:8px;">Client Brief</div>
        <h2 style="font-family:'Fraunces',serif;font-size:24px;font-weight:700;color:var(--white);margin-bottom:6px;">${client.data.name}</h2>
        <p style="font-size:14px;color:var(--muted);">${client.data.what}</p>
      </div>
      <div style="display:flex;gap:8px;flex-wrap:wrap;">
        <span class="badge badge-blue">${client.data.stage || 'Stage TBD'}</span>
        ${client.data.category.map(c=>`<span class="badge badge-blue">${c}</span>`).join('')}
      </div>
    </div>
    <div class="detail-grid">
      <div class="detail-item"><div class="detail-lbl">Problem Solving</div><div class="detail-val">${client.data.problem || '—'}</div></div>
      <div class="detail-item"><div class="detail-lbl">Target Audience</div><div class="detail-val">${client.data.audience.join(', ') || '—'}</div></div>
      <div class="detail-item"><div class="detail-lbl">Goals</div><div class="detail-val">${client.data.goals.join(', ') || '—'}</div></div>
      <div class="detail-item"><div class="detail-lbl">Timeline</div><div class="detail-val">${client.data.timeline || '—'}</div></div>
      <div class="detail-item"><div class="detail-lbl">Tone of Voice</div><div class="detail-val">${client.data.tone.join(', ') || '—'}</div></div>
      <div class="detail-item"><div class="detail-lbl">Knowledge Level</div><div class="detail-val">${client.data.knowledge || '—'}</div></div>
    </div>`;

  generateAllContent(client);
  showDash('client-detail');
  showTool('pillars', document.querySelector('.tool-tab'));
}

// ══════════════════════════════════════════
// CONTENT GENERATION (Smart Logic, No API)
// ══════════════════════════════════════════
function generateAllContent(client){
  const d = client.data;
  generatePillars(d);
  generateHooks(d);
  generateCalendar(d);
  generatePlatforms(d);
  generateCompetitors(d);
  generateKPI(client);
}

// PILLARS
function generatePillars(d){
  const pillars = buildPillars(d);
  document.getElementById('pillars-content').innerHTML = `
    <div style="margin-bottom:20px;">
      <div style="font-size:13px;color:var(--muted);line-height:1.6;margin-bottom:20px;">
        Based on ${d.name}'s positioning as a <strong style="color:var(--white)">${d.category.join(', ')}</strong> project targeting <strong style="color:var(--white)">${d.audience.slice(0,2).join(' and ')}</strong>, here are your 5 core content pillars:
      </div>
      ${pillars.map((p,i) => `
        <div class="pillar-card">
          <div class="pillar-name">Pillar ${i+1}: ${p.name}</div>
          <div class="pillar-desc">${p.desc}</div>
          <div style="margin-top:10px;display:flex;gap:6px;flex-wrap:wrap;">
            ${p.formats.map(f=>`<span class="badge badge-blue">${f}</span>`).join('')}
          </div>
        </div>`).join('')}
    </div>`;
}

function buildPillars(d){
  const pillars = [];
  const goals = d.goals || [];
  const tone = d.tone || [];
  const audience = d.audience || [];

  // Pillar 1 — always education/utility
  pillars.push({
    name: 'Utility & Education',
    desc: `Break down what ${d.name} does in simple terms. Help ${audience.includes('retail') ? 'everyday users' : 'your target audience'} understand the real problem you solve and why it matters. No jargon — just clarity.`,
    formats: ['Thread', 'Explainer post', 'FAQ', 'Short video']
  });

  // Pillar 2 — based on stage
  if(d.stage === 'pre-launch' || d.stage === 'idea'){
    pillars.push({
      name: 'Behind the Build',
      desc: `Take your audience on the journey of building ${d.name}. Share milestones, challenges, and decisions. Pre-launch content builds anticipation and trust before you ever launch.`,
      formats: ['Build-in-public post', 'Milestone update', 'Team spotlight']
    });
  } else {
    pillars.push({
      name: 'Product Updates & Milestones',
      desc: `Keep your community informed and excited about ${d.name}'s progress. Celebrate wins, share roadmap updates, and make your community feel like insiders.`,
      formats: ['Update thread', 'Milestone post', 'Roadmap reveal']
    });
  }

  // Pillar 3 — community
  pillars.push({
    name: 'Community Stories',
    desc: `Feature your early believers, ambassadors, and power users. Real people using ${d.name} is the most authentic content you can create. ${audience.includes('african') ? 'Spotlight the African Web3 community specifically.' : 'Let your community become your biggest marketing asset.'}`,
    formats: ['Community spotlight', 'Testimonial', 'UGC repost', 'Ambassador story']
  });

  // Pillar 4 — based on goals
  if(goals.includes('investors')){
    pillars.push({
      name: 'Market Insight & Thought Leadership',
      desc: `Position ${d.name}'s founders as experts in the ${d.category.join('/')} space. Share opinions on market trends, industry news, and the future of ${d.category[0] || 'Web3'}. This is what attracts serious investors and partners.`,
      formats: ['Opinion thread', 'Market analysis', 'Trend commentary', 'Prediction post']
    });
  } else if(goals.includes('leads')){
    pillars.push({
      name: 'Social Proof & Results',
      desc: `Showcase the results, traction, and momentum ${d.name} is building. Data, partnerships, milestones, and user numbers — make it easy for potential users to see that this is worth their attention.`,
      formats: ['Stats post', 'Partnership announcement', 'Traction update', 'Case study']
    });
  } else {
    pillars.push({
      name: 'Trends & Industry News',
      desc: `React and add perspective to what's happening in ${d.category.join('/')} and Web3. Show your audience that ${d.name} understands the space and has a unique point of view.`,
      formats: ['News commentary', 'Trend analysis', 'Hot take', 'Weekly roundup']
    });
  }

  // Pillar 5 — engagement
  pillars.push({
    name: 'Engagement & Conversation Starters',
    desc: `Create content designed to spark conversation and interaction. Questions, polls, debates, and challenges that get your audience talking and sharing. Algorithms reward engagement — and so does your community.`,
    formats: ['Poll', 'Question post', 'Hot take', 'Challenge', 'Debate']
  });

  return pillars;
}

// HOOKS
function generateHooks(d){
  const hooks = buildHooks(d);
  document.getElementById('hooks-content').innerHTML = `
    <div style="margin-bottom:16px;font-size:13px;color:var(--muted);line-height:1.6;">
      Hook formulas tailored to <strong style="color:var(--white)">${d.name}</strong> — use these as starting frameworks, fill in the specifics, and test what resonates with your audience.
    </div>
    <div style="display:grid;grid-template-columns:1fr 1fr;gap:20px;">
      <div>
        <div class="result-title">🎯 X / Twitter Hooks</div>
        ${hooks.twitter.map((h,i) => `<div class="hook-item"><div class="hook-num">${i+1}</div><div>${h}</div></div>`).join('')}
      </div>
      <div>
        <div class="result-title">💼 LinkedIn Hooks</div>
        ${hooks.linkedin.map((h,i) => `<div class="hook-item"><div class="hook-num">${i+1}</div><div>${h}</div></div>`).join('')}
      </div>
    </div>`;
}

function buildHooks(d){
  const name = d.name;
  const cat = d.category[0] || 'Web3';
  const problem = d.problem || 'the biggest problem in ' + cat;
  const audience = d.audience[0] || 'crypto users';

  const twitter = [
    `Most ${cat} projects fail because of this one mistake. Here's what ${name} does differently:`,
    `I've been in Web3 for years. Nothing has solved [${problem}] until now.`,
    `${name} just hit [milestone]. Here's what happened in the last [X] days 🧵`,
    `The honest truth about why ${cat} hasn't gone mainstream yet (and how we fix it):`,
    `If you're a ${audience} and you haven't heard of ${name} — read this thread.`,
    `We built ${name} in public. Here's everything we learned so far:`,
    `Everyone talks about [trend]. Nobody talks about [real solution ${name} provides].`,
    `Hot take: The reason ${cat} communities fail is not what you think.`,
    `[X] things I wish I knew before building in ${cat}:`,
    `This is what ${name} looks like in 12 months if we execute correctly 👇`
  ];

  const linkedin = [
    `I've been watching the ${cat} space for [X] years. Here's what most people get wrong about [problem]:`,
    `${name} is solving a problem that costs ${audience} [cost/time/money] every day. Here's how:`,
    `We onboarded our first [X] users in [timeframe]. The strategy was simpler than you think.`,
    `Building in the ${cat} space taught me [lesson]. Here's what I'd tell anyone starting out:`,
    `The biggest lie in ${cat} marketing: [common myth]. Here's the truth:`,
    `I turned down [opportunity] to build ${name}. Here's exactly why — and what happened next:`,
    `Most ${cat} projects have [X] followers but [Y] actual users. ${name} is doing this differently:`,
    `[Controversial opinion about ${cat}]. Change my mind.`,
    `3 things ${name} does that our competitors refused to try:`,
    `We're [X] months in. Here's an honest update — wins, losses, and what's next:`
  ];

  return { twitter, linkedin };
}

// PLATFORM RECOMMENDATIONS
function generatePlatforms(d){
  const platforms = buildPlatforms(d);
  document.getElementById('platforms-content').innerHTML = `
    <div style="margin-bottom:16px;font-size:13px;color:var(--muted);line-height:1.6;">
      Platform recommendations based on ${d.name}'s target audience (<strong style="color:var(--white)">${d.audience.slice(0,3).join(', ')}</strong>) and goals (<strong style="color:var(--white)">${d.goals.slice(0,2).join(', ')}</strong>):
    </div>
    ${platforms.map(p => `
      <div class="platform-card">
        <div class="platform-icon">${p.icon}</div>
        <div style="flex:1;">
          <div class="platform-name">${p.name}</div>
          <div class="platform-reason">${p.reason}</div>
          <div style="margin-top:8px;display:flex;gap:6px;flex-wrap:wrap;">
            <span class="platform-priority ${p.priority === 'Primary' ? 'priority-high' : 'priority-med'}">${p.priority}</span>
            ${p.content.map(c=>`<span class="badge badge-blue">${c}</span>`).join('')}
          </div>
        </div>
      </div>`).join('')}`;
}

function buildPlatforms(d){
  const audience = d.audience || [];
  const goals = d.goals || [];
  const platforms = [];

  // X is almost always primary for crypto
  platforms.push({
    icon: '𝕏',
    name: 'X (Twitter)',
    priority: 'Primary',
    reason: `X is the heartbeat of crypto. Your target audience — ${audience.slice(0,2).join(' and ')} — are most active here. This is where news breaks, communities form, and projects get discovered. This should be your main platform.`,
    content: ['Threads', 'Hot takes', 'Updates', 'Community']
  });

  // Telegram for community
  if(audience.includes('crypto-natives') || audience.includes('retail') || goals.includes('community')){
    platforms.push({
      icon: '✈️',
      name: 'Telegram',
      priority: 'Primary',
      reason: `Telegram is the default community hub for crypto natives. Build your core community here — it's where your most engaged holders, early supporters, and advocates will gather. Essential for any Web3 project.`,
      content: ['Community chat', 'Announcements', 'AMAs', 'Updates']
    });
  }

  // LinkedIn for B2B, investors, founders
  if(audience.includes('vcs') || audience.includes('founders') || goals.includes('investors') || goals.includes('partnerships')){
    platforms.push({
      icon: '💼',
      name: 'LinkedIn',
      priority: 'Primary',
      reason: `Your goals include ${goals.includes('investors') ? 'attracting investors' : 'partnership deals'}. LinkedIn is where VCs, institutional investors, and serious founders spend time. Build your founder personal brand here to open doors that X cannot.`,
      content: ['Founder content', 'Thought leadership', 'Company updates', 'Partnership outreach']
    });
  } else {
    platforms.push({
      icon: '💼',
      name: 'LinkedIn',
      priority: 'Secondary',
      reason: `Even if not your primary focus, LinkedIn builds credibility for ${d.name} in professional circles. Great for attracting talent, partners, and press coverage down the line.`,
      content: ['Company page', 'Milestone posts', 'Team updates']
    });
  }

  // Discord for developer projects
  if(d.category.includes('infra') || d.category.includes('developers') || audience.includes('developers')){
    platforms.push({
      icon: '🎮',
      name: 'Discord',
      priority: 'Primary',
      reason: `Your project targets developers and builders. Discord is their native environment. Build a server with dedicated channels for dev support, governance, and community — this is where power users live.`,
      content: ['Dev support', 'Governance', 'Community', 'Voice AMAs']
    });
  }

  // African market
  if(audience.includes('african')){
    platforms.push({
      icon: '📱',
      name: 'WhatsApp / Telegram Groups',
      priority: 'Primary',
      reason: `For the African market specifically, WhatsApp and Telegram groups are where crypto communities thrive. Localised groups in key markets like Nigeria, Ghana, Kenya, and South Africa will drive real grassroots adoption.`,
      content: ['Local groups', 'Education', 'Community building', 'Referrals']
    });
  }

  return platforms;
}

// CONTENT CALENDAR
function generateCalendar(d){
  const days = ['Mon','Tue','Wed','Thu','Fri','Sat','Sun'];
  const pillars = buildPillars(d);
  const pillarNames = pillars.map(p => p.name);

  // Build 4-week calendar
  let calHTML = `
    <div style="margin-bottom:16px;font-size:13px;color:var(--muted);line-height:1.6;">
      A 4-week content calendar for <strong style="color:var(--white)">${d.name}</strong> based on your 5 content pillars. Adjust post days based on your capacity.
    </div>`;

  // Week templates
  const weekPlans = [
    // Week 1
    {Mon:'Utility & Education', Wed:'Behind the Build', Fri:'Engagement', Sun:'Community Stories'},
    // Week 2
    {Mon:'Trends & Industry', Tue:'Utility & Education', Thu:'Community Stories', Sat:'Product Updates'},
    // Week 3
    {Mon:'Engagement', Wed:'Utility & Education', Fri:'Behind the Build', Sun:'Trends & Industry'},
    // Week 4
    {Mon:'Community Stories', Wed:'Product Updates', Fri:'Utility & Education', Sun:'Engagement'}
  ];

  weekPlans.forEach((week, wi) => {
    calHTML += `<div style="margin-bottom:24px;"><div style="font-size:11px;font-weight:700;letter-spacing:1px;text-transform:uppercase;color:var(--blue3);margin-bottom:12px;">Week ${wi+1}</div>`;
    calHTML += `<div class="calendar-grid">`;
    days.forEach(day => {
      const post = week[day];
      calHTML += `<div class="cal-day">
        <div class="cal-day-num">${day}</div>
        ${post ? `<div class="cal-post">${post}</div>` : ''}
      </div>`;
    });
    calHTML += `</div></div>`;
  });

  document.getElementById('calendar-content').innerHTML = calHTML;
}

// COMPETITOR ANALYSIS
function generateCompetitors(d){
  const comps = [d.data?.comp1, d.data?.comp2, d.data?.comp3].filter(Boolean);
  if(!comps.length && d.comp1) comps.push(d.comp1, d.comp2, d.comp3);
  const actualComps = [d.comp1, d.comp2, d.comp3].filter(Boolean);

  if(!actualComps.length){
    document.getElementById('competitors-content').innerHTML = `<div class="empty-state"><div class="empty-icon">🔍</div><div class="empty-title">No competitors specified</div><div class="empty-sub">The client didn't list any competitors in their brief. Ask them directly or research the space manually.</div></div>`;
    return;
  }

  const gap = d.compgap || 'not clearly communicating utility to non-technical audiences';

  document.getElementById('competitors-content').innerHTML = `
    <div style="margin-bottom:16px;font-size:13px;color:var(--muted);line-height:1.6;">
      Competitor analysis framework for <strong style="color:var(--white)">${d.name}</strong>. Use this as a starting point and fill in specific observations from manual research.
    </div>
    <div style="background:rgba(37,99,235,0.06);border:1px solid var(--border);border-radius:8px;padding:16px;margin-bottom:20px;">
      <div style="font-size:11px;font-weight:700;letter-spacing:1px;text-transform:uppercase;color:var(--blue3);margin-bottom:8px;">Your Gap Opportunity</div>
      <div style="font-size:14px;color:var(--white);line-height:1.6;">Client identified: "<em style="color:var(--cream);">${gap}</em>" — This is your positioning advantage.</div>
    </div>
    ${actualComps.map(comp => comp ? `
      <div class="comp-card">
        <div class="comp-name">🔍 ${comp}</div>
        <div class="comp-grid">
          <div class="comp-section comp-doing">
            <h4>✅ What They're Doing</h4>
            <div class="comp-item">Regular content posting cadence</div>
            <div class="comp-item">Community engagement on X</div>
            <div class="comp-item">Partnership announcements</div>
            <div class="comp-item">Influencer collaborations</div>
          </div>
          <div class="comp-section comp-missing">
            <h4>❌ What They're Missing</h4>
            <div class="comp-item">${gap}</div>
            <div class="comp-item">Deep educational content</div>
            <div class="comp-item">Community storytelling</div>
            <div class="comp-item">Founder personal brand</div>
          </div>
        </div>
        <div style="margin-top:12px;padding-top:12px;border-top:1px solid var(--border2);font-size:12px;color:var(--muted);">
          📌 <strong style="color:var(--cream);">Your angle vs ${comp}:</strong> Where they rely on hype, ${d.name} leads with education and community depth.
        </div>
      </div>` : '').join('')}`;
}

// KPI TRACKER
function generateKPI(client){
  const d = client.data;
  const kpiHTML = `
    <div style="margin-bottom:20px;font-size:13px;color:var(--muted);line-height:1.6;">
      Track weekly metrics for <strong style="color:var(--white)">${d.name}</strong>. Add numbers each week to see growth over time.
    </div>
    <div class="kpi-inputs">
      <div class="kpi-input-card"><label>Followers</label><input class="kpi-num-input" type="number" placeholder="0" id="kpi-followers"/></div>
      <div class="kpi-input-card"><label>Engagement Rate %</label><input class="kpi-num-input" type="number" placeholder="0" id="kpi-engagement"/></div>
      <div class="kpi-input-card"><label>Impressions</label><input class="kpi-num-input" type="number" placeholder="0" id="kpi-impressions"/></div>
      <div class="kpi-input-card"><label>New Members</label><input class="kpi-num-input" type="number" placeholder="0" id="kpi-members"/></div>
    </div>
    <button class="btn-primary btn-sm" onclick="saveKPI('${client.id}')">Save This Week's Numbers</button>
    <div style="margin-top:24px;">
      <div style="font-size:12px;font-weight:700;letter-spacing:1px;text-transform:uppercase;color:var(--blue3);margin-bottom:12px;">Weekly History</div>
      <div class="kpi-history" id="kpi-history-list">
        ${client.kpiHistory.length ? client.kpiHistory.map((w,i) => `
          <div class="kpi-week-row">
            <span class="kpi-week-label">Week ${i+1} · ${w.date}</span>
            <div class="kpi-week-data">
              <div class="kpi-metric"><div class="kpi-metric-val">${w.followers}</div><div class="kpi-metric-lbl">Followers</div></div>
              <div class="kpi-metric"><div class="kpi-metric-val">${w.engagement}%</div><div class="kpi-metric-lbl">Engagement</div></div>
              <div class="kpi-metric"><div class="kpi-metric-val">${w.impressions}</div><div class="kpi-metric-lbl">Impressions</div></div>
              <div class="kpi-metric"><div class="kpi-metric-val">${w.members}</div><div class="kpi-metric-lbl">New Members</div></div>
            </div>
          </div>`).join('') : '<div style="text-align:center;padding:24px;color:var(--muted);font-size:13px;">No data yet. Add your first week's numbers above.</div>'}
      </div>
    </div>`;
  document.getElementById('kpi-content').innerHTML = kpiHTML;
}

function saveKPI(clientId){
  const client = APP.clients.find(c => c.id === clientId);
  if(!client) return;
  const entry = {
    date: new Date().toLocaleDateString(),
    followers: document.getElementById('kpi-followers').value || 0,
    engagement: document.getElementById('kpi-engagement').value || 0,
    impressions: document.getElementById('kpi-impressions').value || 0,
    members: document.getElementById('kpi-members').value || 0
  };
  client.kpiHistory.push(entry);
  saveState();
  generateKPI(client);
}

// TOOL TABS
function showTool(tool, btn){
  document.querySelectorAll('.tool-panel').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.tool-tab').forEach(t => t.classList.remove('active'));
  document.getElementById('tool-'+tool).classList.add('active');
  if(btn) btn.classList.add('active');
}

// COPY ONBOARD LINK
function copyOnboardLink(){
  const url = window.location.href.split('#')[0];
  navigator.clipboard.writeText(url).then(() => {
    const btn = document.querySelector('.copy-btn');
    btn.textContent = '✓ Copied!';
    setTimeout(() => btn.textContent = '📋 Copy Link', 2000);
  });
}

// ADMIN ACCESS — add hidden button
document.addEventListener('keydown', function(e){
  if(e.ctrlKey && e.shiftKey && e.key === 'A'){
    goToDash();
  }
});
</script>
</body>
</html>
