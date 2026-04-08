<!DOCTYPE html>
<html lang="zh-Hant">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width,initial-scale=1.0"/>
<title>神隊友感謝牆</title>
<style>
/* ══════════════════════════════════════════
   色彩系統
   主色   --brand  : #00D2BE  青綠
   輔色1  --accent : #d30c7b  深粉紅
   輔色2  --yellow : #fde74c  亮黃
   輔色3  --cream  : #fbf5f3  米白
   背景   --bg     : #0b2027
   ══════════════════════════════════════════ */
:root{
  --bg-deep:#06101e;
  --bg-mid:#0a1628;
  --bg-card:rgba(6,16,30,.84);
  --line:rgba(0,210,190,.1);
  --line2:rgba(0,210,190,.18);
  --text:#f0faf9;
  --muted:#7ab8b2;
  --muted2:#5a9490;
  --brand:#00D2BE;
  --brand2:#00ecd6;
  --accent:#d30c7b;
  --accent2:#f03a96;
  --yellow:#fde74c;
  --yellow2:#fff2a0;
  --cream:#fbf5f3;
  --shadow:0 24px 48px rgba(0,0,0,.42);
  --r-xl:22px;
  --r-lg:16px;
  --r-md:12px;
  --logo:url("https://duk.tw/6LH1sf.jpg");
  --maxw:1300px;
}
*{box-sizing:border-box;margin:0;padding:0;}
html,body{min-height:100vh;overflow-x:hidden;}
body{
  font-family:"Segoe UI","PingFang TC","Noto Sans TC","Microsoft JhengHei",sans-serif;
  color:var(--text);
  background:
    radial-gradient(ellipse 55% 38% at 8%  4%, rgba(0,210,190,.1) 0%,transparent 58%),
    radial-gradient(ellipse 45% 32% at 92% 10%,rgba(211,12,123,.09) 0%,transparent 52%),
    radial-gradient(ellipse 38% 28% at 55% 92%,rgba(253,231,76,.05) 0%,transparent 50%),
    linear-gradient(160deg,#06101e 0%,#0a1628 50%,#081420 100%);
  position:relative;
}

/* ─── Logo Rain ─── */
.logo-rain{position:fixed;inset:0;pointer-events:none;z-index:0;overflow:hidden;}
.logo-drop{
  position:absolute;top:-200px;
  background-image:var(--logo);
  background-size:contain;background-repeat:no-repeat;background-position:center;
  opacity:var(--op,.18);
  filter:blur(.2px) drop-shadow(0 0 12px rgba(0,210,190,.25));
  animation:falling var(--dur,20s) linear var(--del,0s) infinite;
  width:var(--sz,90px);height:calc(var(--sz,90px)*.44);
}
@keyframes falling{
  from{transform:translateY(-200px) translateX(0) rotate(var(--rot,-6deg));}
  to{transform:translateY(115vh) translateX(var(--dx,50px)) rotate(calc(var(--rot,-6deg)+10deg));}
}

/* ─── Layout ─── */
.page{
  position:relative;z-index:1;
  width:min(var(--maxw),calc(100% - 32px));
  margin:0 auto;padding:28px 0 48px;
}

/* ─── Hero ─── */
.hero{text-align:center;padding:8px 0 26px;}
.hero-badge{
  display:inline-flex;align-items:center;gap:8px;
  padding:7px 16px;border-radius:999px;margin-bottom:14px;
  border:1px solid rgba(0,210,190,.28);background:rgba(0,210,190,.09);
  color:#a0ece6;font-size:13px;letter-spacing:.02em;
}
.hero h1{font-size:clamp(28px,4.5vw,52px);font-weight:900;line-height:1.08;letter-spacing:.01em;}
.gtext{
  background:linear-gradient(90deg,#ffbf3f 0%,#ffe08a 50%,#ffbf3f 100%);
  -webkit-background-clip:text;background-clip:text;color:transparent;
}
.hero p{margin:10px auto 0;max-width:680px;color:var(--muted);font-size:15px;line-height:1.8;}

/* ─── Panel base ─── */
.panel{
  background:linear-gradient(180deg,rgba(6,16,30,.38),rgba(4,12,24,.32));
  border:1px solid rgba(0,210,190,.13);
  border-radius:var(--r-xl);
  box-shadow:0 8px 32px rgba(0,0,0,.22);
  backdrop-filter:blur(6px);-webkit-backdrop-filter:blur(6px);
  position:relative;overflow:hidden;
}
.panel::before{
  content:"";position:absolute;inset:0;pointer-events:none;
  background:linear-gradient(135deg,rgba(0,210,190,.04) 0%,transparent 35%,transparent 68%,rgba(211,12,123,.03) 100%);
}

/* ─── Section 1: Stats ─── */
.stats-row{
  display:grid;grid-template-columns:repeat(3,1fr);gap:14px;
  padding:18px;
}
.stat-card{
  padding:20px 18px;border-radius:var(--r-lg);
  border:1px solid rgba(0,210,190,.1);background:rgba(0,210,190,.02);
  position:relative;overflow:hidden;min-height:112px;
}
.stat-card::after{
  content:"";position:absolute;right:-20px;top:-20px;
  width:88px;height:88px;border-radius:50%;
  background:radial-gradient(circle,rgba(0,210,190,.08),transparent 70%);
}
.stat-icon-row{display:flex;align-items:center;gap:10px;margin-bottom:8px;}
.sicon{
  width:36px;height:36px;border-radius:10px;
  display:inline-flex;align-items:center;justify-content:center;
  font-size:17px;flex-shrink:0;
  box-shadow:inset 0 0 0 1px rgba(255,255,255,.07),0 6px 16px rgba(0,0,0,.28);
}
.sicon.pink{background:rgba(211,12,123,.18);color:#f03a96;}
.sicon.teal{background:rgba(0,210,190,.18);color:var(--brand2);}
.sicon.gold{background:rgba(253,231,76,.18);color:var(--yellow);}
.stat-val{font-size:clamp(24px,3vw,36px);font-weight:900;line-height:1;letter-spacing:.02em;}
.stat-lbl{margin-top:6px;color:var(--muted);font-size:12.5px;}

/* ─── Section 2: Marquee ─── */
.marquee-wrap{padding:0 18px 18px;}
.marquee-bar{
  border:1px solid rgba(0,210,190,.1);border-radius:var(--r-lg);
  background:rgba(0,210,190,.015);overflow:hidden;min-height:52px;position:relative;
}
.marquee-bar::before,.marquee-bar::after{
  content:"";position:absolute;top:0;bottom:0;width:44px;z-index:2;pointer-events:none;
}
.marquee-bar::before{left:0;background:linear-gradient(90deg,rgba(7,24,30,.55),transparent);}
.marquee-bar::after{right:0;background:linear-gradient(-90deg,rgba(7,24,30,.55),transparent);}
.marquee-hd{
  display:flex;align-items:center;justify-content:space-between;
  margin-bottom:10px;
}
.marquee-ttl{display:flex;align-items:center;gap:9px;font-weight:700;font-size:13.5px;color:var(--cream);}
.live-dot{
  width:8px;height:8px;border-radius:50%;background:var(--accent);flex-shrink:0;
  box-shadow:0 0 0 0 rgba(211,12,123,.6);animation:pulse 1.8s infinite;
}
@keyframes pulse{
  0%{box-shadow:0 0 0 0 rgba(211,12,123,.6);}
  70%{box-shadow:0 0 0 9px rgba(211,12,123,0);}
  100%{box-shadow:0 0 0 0 rgba(211,12,123,0);}
}
.marquee-track{
  display:flex;gap:0;width:max-content;
  padding:14px 0;white-space:nowrap;
  animation:mq 30s linear infinite;will-change:transform;
}
.marquee-track:hover{animation-play-state:paused;}
@keyframes mq{0%{transform:translateX(0);}100%{transform:translateX(-50%);}}
.mq-item{
  display:inline-flex;align-items:center;gap:6px;
  padding:0 20px;color:#b8e8e4;font-size:13.5px;
}
.mq-sep{color:rgba(0,210,190,.25);margin:0 2px;}
.mq-heart{color:var(--accent);}

/* ─── Section 3: Toolbar ─── */
.toolbar{display:flex;gap:10px;align-items:center;flex-wrap:wrap;margin-top:20px;}
.chips{display:flex;gap:8px;flex-wrap:wrap;flex:1;}
.chip{
  padding:8px 14px;border-radius:999px;
  border:1px solid rgba(0,210,190,.15);
  background:rgba(0,210,190,.04);
  color:#8dd6d0;font-size:13px;cursor:pointer;user-select:none;
  transition:all .2s ease;white-space:nowrap;
}
.chip:hover,.chip.active{
  color:#fff;border-color:rgba(211,12,123,.55);
  background:linear-gradient(90deg,rgba(211,12,123,.22),rgba(240,58,150,.14));
  box-shadow:0 6px 18px rgba(211,12,123,.18);
}
.search-box{width:min(300px,100%);}
.search-box input{
  width:100%;height:42px;padding:0 14px;
  border:1px solid rgba(0,210,190,.15);border-radius:999px;
  background:rgba(0,210,190,.04);color:var(--text);outline:none;font-size:14px;
  transition:.2s ease;
}
.search-box input::placeholder{color:#5a8e8a;}
.search-box input:focus{border-color:rgba(0,210,190,.55);box-shadow:0 0 0 3px rgba(0,210,190,.12);}

/* ─── Section 4: Leaderboard ─── */
.leader-row{display:grid;grid-template-columns:1fr 1fr 1fr;gap:16px;margin-top:20px;}
.leader-card{padding:20px;display:flex;flex-direction:column;gap:10px;}
.leader-lbl{
  display:inline-flex;align-items:center;gap:6px;
  font-size:12px;font-weight:700;letter-spacing:.06em;text-transform:uppercase;
  color:var(--muted);margin-bottom:2px;
}
.leader-lbl .ldot{
  width:6px;height:6px;border-radius:50%;
  background:currentColor;opacity:.8;
}
.leader-lbl.lbl-pink{color:var(--accent2);}
.leader-lbl.lbl-teal{color:var(--brand);}
.leader-main{display:flex;align-items:center;gap:12px;}
.avatar{
  width:50px;height:50px;border-radius:14px;flex-shrink:0;
  display:inline-flex;align-items:center;justify-content:center;
  font-weight:900;font-size:18px;color:#fff;
  box-shadow:inset 0 0 0 1px rgba(255,255,255,.1),0 8px 18px rgba(0,0,0,.25);
}
/* Avatar palette updated to match new brand */
.av-gold{background:linear-gradient(135deg,#007a6e,#00D2BE);}
.av-teal{background:linear-gradient(135deg,#005e8a,#00b4d8);}
.av-pink{background:linear-gradient(135deg,#8c0050,#d30c7b);}
.av-green{background:linear-gradient(135deg,#006644,#00c87a);}
.av-purple{background:linear-gradient(135deg,#4a1090,#9050e0);}
.av-orange{background:linear-gradient(135deg,#7a2e00,#e07020);}
.av-gray{background:linear-gradient(135deg,#1e3a3a,#3a6060);}
.leader-info h3{font-size:18px;font-weight:800;line-height:1.2;}
.leader-info p{color:var(--muted);font-size:12.5px;margin-top:3px;}
.leader-score{
  margin-left:auto;align-self:flex-start;
  background:rgba(253,231,76,.12);color:var(--yellow2);
  border:1px solid rgba(253,231,76,.22);
  padding:6px 10px;border-radius:10px;font-size:12px;font-weight:800;
  min-width:44px;text-align:center;white-space:nowrap;
}
/* Add button card */
.add-card{
  padding:20px;cursor:pointer;
  display:flex;flex-direction:column;align-items:center;justify-content:center;
  gap:12px;text-align:center;min-height:110px;
  border:1px dashed rgba(0,210,190,.3);
  background:rgba(0,210,190,.04);
  transition:.25s ease;
}
.add-card:hover{
  border-color:rgba(0,210,190,.6);
  background:rgba(0,210,190,.09);
  transform:translateY(-2px);
  box-shadow:0 12px 28px rgba(0,210,190,.16);
}
.add-icon{
  width:48px;height:48px;border-radius:14px;
  background:linear-gradient(135deg,rgba(0,210,190,.22),rgba(0,236,214,.14));
  border:1px solid rgba(0,210,190,.25);
  display:flex;align-items:center;justify-content:center;
  font-size:22px;
}
.add-card p{color:#ffbf3f;font-weight:700;font-size:15px;}
.add-card span{color:var(--muted);font-size:12px;}

/* ─── Wall ─── */
.wall{
  display:grid;grid-template-columns:repeat(3,minmax(0,1fr));
  gap:16px;margin-top:20px;
}
.post-card{padding:20px;display:flex;flex-direction:column;}
.post-top{display:flex;align-items:flex-start;gap:11px;}
.post-info{flex:1;min-width:0;}
.post-name-row{display:flex;align-items:center;justify-content:space-between;gap:8px;flex-wrap:wrap;}
.post-name{font-size:18px;font-weight:800;line-height:1.2;word-break:break-word;}
.post-dept{font-size:12px;color:var(--muted);margin-top:3px;}
.post-time{color:var(--muted2);font-size:12px;white-space:nowrap;}
.post-body{
  margin-top:14px;color:#cdeae8;line-height:1.85;font-size:14px;
  min-height:72px;white-space:pre-wrap;word-break:break-word;flex:1;
}
.post-foot{
  margin-top:14px;padding-top:12px;
  border-top:1px solid rgba(0,210,190,.08);
  display:flex;align-items:center;gap:10px;
}
.act-btn{
  display:inline-flex;align-items:center;gap:6px;
  background:rgba(0,210,190,.04);border:1px solid rgba(0,210,190,.12);
  color:var(--muted);border-radius:999px;
  padding:6px 13px;font-size:13px;font-weight:600;cursor:pointer;
  transition:.2s ease;
}
.act-btn:hover{color:#fff;border-color:rgba(0,210,190,.35);background:rgba(0,210,190,.1);}
.act-btn.liked{
  color:#d30c7b;
  border-color:rgba(211,12,123,.4);
  background:rgba(211,12,123,.12);
}
.act-btn:active{transform:scale(.96);}

/* Comment section */
.comments-wrap{margin-top:12px;display:none;}
.comments-wrap.open{display:block;}
.comment-list{display:flex;flex-direction:column;gap:8px;margin-bottom:10px;}
.comment-item{
  background:rgba(0,210,190,.03);border:1px solid rgba(0,210,190,.09);
  border-radius:var(--r-md);padding:9px 12px;font-size:13px;
  color:#b0dcd8;line-height:1.6;word-break:break-word;
}
.comment-item .c-time{font-size:11px;color:var(--muted2);margin-top:4px;}
.comment-form{display:flex;gap:8px;}
.comment-input{
  flex:1;border:1px solid rgba(0,210,190,.14);border-radius:var(--r-md);
  background:rgba(0,210,190,.04);color:var(--text);
  padding:9px 12px;font-size:13px;outline:none;resize:none;min-height:40px;
  transition:.2s ease;
}
.comment-input::placeholder{color:#5a8e8a;}
.comment-input:focus{border-color:rgba(0,210,190,.5);box-shadow:0 0 0 3px rgba(0,210,190,.1);}
.comment-send{
  padding:0 14px;border:none;border-radius:var(--r-md);cursor:pointer;
  background:linear-gradient(90deg,var(--brand),var(--brand2));
  color:#071a1a;font-weight:700;font-size:13px;white-space:nowrap;
  transition:.15s ease;flex-shrink:0;height:40px;
}
.comment-send:hover{opacity:.85;}
.comment-limit{font-size:12px;color:var(--yellow);text-align:center;padding:8px;font-weight:600;}

.empty{
  grid-column:1/-1;text-align:center;padding:36px 20px;
  color:var(--muted);border:1px dashed rgba(0,210,190,.12);
  border-radius:var(--r-xl);background:rgba(0,210,190,.02);
}

/* ─── Modal ─── */
.modal-backdrop{
  position:fixed;inset:0;background:rgba(5,18,22,.82);
  backdrop-filter:blur(10px);-webkit-backdrop-filter:blur(10px);
  z-index:100;display:flex;align-items:center;justify-content:center;
  padding:20px;opacity:0;pointer-events:none;transition:.25s ease;
}
.modal-backdrop.open{opacity:1;pointer-events:all;}
.modal{
  background:linear-gradient(180deg,rgba(8,18,36,.98),rgba(5,13,26,.98));
  border:1px solid rgba(0,210,190,.25);border-radius:var(--r-xl);
  box-shadow:0 32px 64px rgba(0,0,0,.55),0 0 0 1px rgba(0,210,190,.06);
  width:min(520px,100%);max-height:90vh;overflow-y:auto;
  padding:28px;position:relative;
  transform:scale(.95) translateY(10px);transition:.25s ease;
}
.modal-backdrop.open .modal{transform:scale(1) translateY(0);}
.modal-close{
  position:absolute;top:16px;right:16px;
  width:32px;height:32px;border-radius:50%;
  border:1px solid rgba(0,210,190,.15);background:rgba(0,210,190,.06);
  color:var(--muted);font-size:16px;cursor:pointer;display:flex;align-items:center;justify-content:center;
  transition:.2s ease;
}
.modal-close:hover{background:rgba(211,12,123,.2);border-color:rgba(211,12,123,.35);color:#fff;}
.modal h2{font-size:20px;font-weight:800;margin-bottom:18px;letter-spacing:.01em;}
.modal .hint-top{font-size:12px;color:var(--muted);line-height:1.6;margin-bottom:18px;}

/* Form fields */
.field{display:flex;flex-direction:column;gap:7px;margin-bottom:14px;}
label{font-size:13px;color:#a8d8d4;font-weight:700;letter-spacing:.03em;}
input[type=text],select,textarea{
  width:100%;border:1px solid rgba(0,210,190,.14);
  background:rgba(0,210,190,.04);color:var(--text);
  border-radius:var(--r-md);padding:12px 14px;outline:none;font-size:14.5px;
  transition:.2s ease;
}
input[type=text]::placeholder,textarea::placeholder{color:#5a8e8a;}
input[type=text]:focus,select:focus,textarea:focus{
  border-color:rgba(0,210,190,.6);box-shadow:0 0 0 3px rgba(0,210,190,.12);
  background:rgba(0,210,190,.07);
}
select option{background:#06101e;color:var(--text);}
textarea{min-height:120px;resize:vertical;line-height:1.7;}
.form-2col{display:grid;grid-template-columns:1fr 1fr;gap:12px;}
.modal-foot{display:flex;gap:10px;justify-content:flex-end;margin-top:18px;}
.btn-primary{
  padding:11px 20px;border:none;border-radius:var(--r-md);cursor:pointer;
  background:linear-gradient(90deg,var(--brand),var(--brand2));
  color:#071a1a;font-weight:800;font-size:14px;
  box-shadow:0 8px 20px rgba(0,210,190,.28);
  transition:.15s ease;
}
.btn-primary:hover{opacity:.88;transform:translateY(-1px);}
.btn-secondary{
  padding:11px 18px;border:1px solid rgba(255,255,255,.1);border-radius:var(--r-md);cursor:pointer;
  background:rgba(255,255,255,.05);color:var(--text);font-weight:700;font-size:14px;
  transition:.15s ease;
}
.btn-secondary:hover{background:rgba(255,255,255,.09);}

/* ─── Toast ─── */
.toast{
  position:fixed;left:50%;bottom:24px;
  transform:translateX(-50%) translateY(12px);
  background:rgba(6,16,30,.96);color:var(--cream);
  border:1px solid rgba(0,210,190,.25);
  padding:12px 20px;border-radius:var(--r-lg);
  box-shadow:var(--shadow);font-size:14px;
  opacity:0;pointer-events:none;transition:.22s ease;
  z-index:200;min-width:220px;text-align:center;white-space:nowrap;
}
.toast.show{opacity:1;transform:translateX(-50%) translateY(0);}

/* ─── Footer ─── */
.footer{text-align:center;color:var(--muted2);font-size:12px;margin-top:28px;line-height:1.9;}

/* ─── Responsive ─── */
@media(max-width:1100px){
  .wall{grid-template-columns:repeat(2,1fr);}
  .leader-row{grid-template-columns:1fr 1fr;gap:12px;}
  .leader-row .add-leader-card{grid-column:1/-1;}
}
@media(max-width:760px){
  .stats-row{grid-template-columns:1fr;gap:10px;}
  .toolbar{align-items:stretch;}
  .search-box{width:100%;}
  .wall{grid-template-columns:1fr;}
  .leader-row{grid-template-columns:1fr;}
  .leader-row .add-leader-card{grid-column:auto;}
  .form-2col{grid-template-columns:1fr;}
  .post-name-row{flex-direction:column;align-items:flex-start;}
}
@media(max-width:540px){
  .page{padding:16px 0 32px;}
  .panel,.stat-card{border-radius:16px;}
  .hero h1{font-size:26px;}
  .modal{padding:20px;}
}
@media(prefers-reduced-motion:reduce){
  .logo-drop,.marquee-track,.live-dot{animation:none!important;}
  *{scroll-behavior:auto!important;}
}
</style>
</head>
<body>
<div class="logo-rain" id="logoRain" aria-hidden="true"></div>

<main class="page">
  <!-- Hero -->
  <section class="hero">
    <div class="hero-badge">還好有你｜感謝被看見，合作更有力量 🦸</div>
    <h1><span class="gtext">神隊友感謝牆</span></h1>
    <p>寫下感謝的那位同事，也許是他在你快爆炸時接住了事情，也許是他默默把最難的部分做好。每一份支持，成就了現在的我們。<br>別讓那句「謝謝」過期，讓我們大聲告訴對方：「還好有你」。</p>
  </section>

  <!-- 1.1 Stats -->
  <div class="panel" style="margin-top:0;">
    <div class="stats-row">
      <div class="stat-card">
        <div class="stat-icon-row">
          <div class="sicon pink">❤</div>
          <div class="stat-val" id="statLikes">0</div>
        </div>
        <div class="stat-lbl">總感謝按讚數</div>
      </div>
      <div class="stat-card">
        <div class="stat-icon-row">
          <div class="sicon teal">↗</div>
          <div class="stat-val" id="statWeekNew">0</div>
        </div>
        <div class="stat-lbl">本週新增感謝</div>
      </div>
      <div class="stat-card">
        <div class="stat-icon-row">
          <div class="sicon gold">💬</div>
          <div class="stat-val" id="statWeekComments">0</div>
        </div>
        <div class="stat-lbl">本週新增留言</div>
      </div>
    </div>

    <!-- 1.2 Marquee -->
    <div class="marquee-wrap">
      <div class="marquee-hd">
        <div class="marquee-ttl"><span class="live-dot"></span>72 小時內最新感謝</div>
        <span style="color:var(--muted);font-size:12px;">滑過可暫停</span>
      </div>
      <div class="marquee-bar">
        <div class="marquee-track" id="marqueeTrack"></div>
      </div>
    </div>
  </div>

  <!-- 1.3 Toolbar -->
  <div class="toolbar">
    <div class="chips" id="deptChips"></div>
    <div class="search-box">
      <input id="searchInput" type="text" placeholder="搜尋神隊友姓名或內容關鍵字"/>
    </div>
  </div>

  <!-- 1.4 Leaderboard -->
  <div class="leader-row" id="leaderRow">
    <!-- rendered by JS -->
  </div>

  <!-- 1.7 Wall -->
  <div class="wall" id="wall"></div>

  <div class="footer">感謝資料儲存於 Google Sheets，按讚與留言即時同步。</div>
</main>

<!-- 1.5 Modal Form -->
<div class="modal-backdrop" id="modalBackdrop" role="dialog" aria-modal="true" aria-label="送出感謝">
  <div class="modal">
    <button class="modal-close" id="modalClose" aria-label="關閉">✕</button>
    <h2>送出一則感謝</h2>
    <p class="hint-top">建議寫得具體一點：當時發生什麼、對方做了什麼、為什麼印象深刻。這樣感謝更有溫度。</p>
    <form id="thanksForm" novalidate>
      <div class="form-2col">
        <div class="field">
          <label for="heroName">神隊友</label>
          <input id="heroName" type="text" maxlength="40" placeholder="例如：ArthurWang" required/>
        </div>
        <div class="field">
          <label for="dept">部門</label>
          <select id="dept" required>
            <option value="">請選擇部門</option>
            <option>Research &amp; Development (RD)</option>
            <option>Marketing (市場)</option>
            <option>Executive Office (行政單位)</option>
            <option>Creator (TM)</option>
            <option>Customer Service (VIP)</option>
            <option>Product (PM)</option>
            <option>Design (設計)</option>
            <option>User Operation (OPS)</option>
            <option>Executive Office (行政單位,含HR)</option>
            <option>Finance (財務)</option>
          </select>
        </div>
      </div>
      <div class="field">
        <label for="story">他的超能力事蹟</label>
        <textarea id="story" maxlength="300" placeholder="例如：感謝他在跨部門協作時，幫助混亂的我理清溝通順序，並全力支持我的每一個執行決定" required></textarea>
      </div>
      <div class="modal-foot">
        <button type="submit" class="btn-primary">送出感謝 🚀</button>
      </div>
    </form>
  </div>
</div>

<div class="toast" id="toast" role="status" aria-live="polite"></div>

<script>
(function(){
'use strict';

/* ── 設定 ── */
const GAS_URL = 'https://script.google.com/a/macros/swag.live/s/AKfycbzARPUf_AdUcIKvLssrowFA63Y0-FxeBDhbE7LIsMSAY2lOZg1RHIgpf9cBKlNxxOEp/exec';
const LS_POSTS    = 'swag_wall_posts_v2';
const LS_LIKES    = 'swag_wall_likes_v2';
const LS_COMMENTS = 'swag_wall_comments_v2';
const MAX_COMMENTS = 100;
const HOUR72 = 72*3600*1000;
const WEEK   = 7*24*3600*1000;
const DEPTS  = [
  '全部',
  'Research & Development (RD)',
  'Marketing (市場)',
  'Executive Office (行政單位)',
  'Creator (TM)',
  'Customer Service (VIP)',
  'Product (PM)',
  'Design (設計)',
  'User Operation (OPS)',
  'Executive Office (行政單位,含HR)',
  'Finance (財務)'
];
const AV_CLASSES = ['av-gold','av-teal','av-pink','av-green','av-purple','av-orange'];
const DEMO_UNUSED = null; // removed

/* ── State ── */
const state = {
  posts:     [],
  likesMap:  {},     // {postId: bool}
  comments:  {},     // {postId: [{text,createdAt}]}
  dept:      '全部',
  kw:        '',
  openComments: {}   // {postId: bool}
};

/* ── Elements ── */
const el = id => document.getElementById(id);
const $ = {
  wall:            el('wall'),
  marquee:         el('marqueeTrack'),
  deptChips:       el('deptChips'),
  searchInput:     el('searchInput'),
  statLikes:       el('statLikes'),
  statWeekNew:     el('statWeekNew'),
  statWeekComments:el('statWeekComments'),
  leaderRow:       el('leaderRow'),
  modalBackdrop:   el('modalBackdrop'),
  modalClose:      el('modalClose'),
  form:            el('thanksForm'),
  heroName:        el('heroName'),
  dept:            el('dept'),
  story:           el('story'),
  demoBtn:         null, // removed
  toast:           el('toast'),
  logoRain:        el('logoRain')
};

/* ── LocalStorage helpers ── */
function lsGet(key, fallback){
  try{ const v=localStorage.getItem(key); return v ? JSON.parse(v) : fallback; }
  catch(e){ return fallback; }
}
function lsSet(key, val){
  try{ localStorage.setItem(key, JSON.stringify(val)); } catch(e){}
}

/* ── Init ── */
function init(){
  state.posts    = lsGet(LS_POSTS, []).filter(validPost);
  state.likesMap = lsGet(LS_LIKES, {});
  state.comments = lsGet(LS_COMMENTS, {});
  createLogoRain();
  renderChips();
  renderAll();
  bindEvents();
  loadFromServer();
}

/* ── Bind events ── */
function bindEvents(){
  $.form.addEventListener('submit', onSubmit);
  $.modalClose.addEventListener('click', closeModal);
  $.modalBackdrop.addEventListener('click', e => { if(e.target === $.modalBackdrop) closeModal(); });
  document.addEventListener('keydown', e => { if(e.key==='Escape') closeModal(); });
  $.searchInput.addEventListener('input', debounce(e => {
    state.kw = (e.target.value||'').trim().toLowerCase();
    renderAll();
  }, 150));
  window.addEventListener('resize', debounce(createLogoRain, 200));
}

function openModal(){
  $.modalBackdrop.classList.add('open');
  setTimeout(() => $.heroName.focus(), 100);
}
function closeModal(){
  $.modalBackdrop.classList.remove('open');
}

/* ── Server ── */
function loadFromServer(){
  if(!GAS_URL.startsWith('https://script.google.com')) return useDemo();
  const cb = 'cb_' + Date.now();
  const s = document.createElement('script');
  s.src = GAS_URL + '?action=list&callback=' + cb + '&_t=' + Date.now();
  window[cb] = function(result){
    delete window[cb];
    document.head.removeChild(s);
    const rows = result && Array.isArray(result.data) ? result.data : [];
    const normalized = rows.map(normalizePost).filter(Boolean);
    if(normalized.length){
      mergePosts(normalized);
      lsSet(LS_POSTS, state.posts);
      renderAll();
    } else if(!state.posts.length){
      useDemo();
    }
  };
  s.onerror = function(){
    delete window[cb];
    try{ document.head.removeChild(s); }catch(e){}
    if(!state.posts.length) useDemo();
  };
  document.head.appendChild(s);
}

function sendToServer(payload, onOk, onFail){
  const cb = 'cb_' + Date.now();
  const s = document.createElement('script');
  const params = new URLSearchParams({callback: cb, _t: Date.now()});
  Object.keys(payload).forEach(k => params.set(k, payload[k]));
  s.src = GAS_URL + '?' + params.toString();
  window[cb] = function(result){
    delete window[cb];
    try{ document.head.removeChild(s); }catch(e){}
    if(result && result.success === false) onFail && onFail(result.message);
    else onOk && onOk(result);
  };
  s.onerror = function(){
    delete window[cb];
    try{ document.head.removeChild(s); }catch(e){}
    onFail && onFail('network error');
  };
  document.head.appendChild(s);
}

function useDemo(){
  if(state.posts.length) return;
  const now = Date.now();
  state.posts = [
    {id:uid(),heroName:'ArthurWang',dept:'User Operation (OPS)',story:'昨天需求很急、資料又很亂時，他主動把資訊重新整理，還幫忙釐清優先順序，讓整件事可以在下班前順利收尾。',createdAt:now-2*3600000,likes:18},
    {id:uid(),heroName:'CindyLin',dept:'Design (設計)',story:'協助我把混亂的視覺稿整理得非常清楚，還主動提供備用方案，讓發佈時間縮短了整整兩天。',createdAt:now-10*3600000,likes:7},
    {id:uid(),heroName:'BrianChen',dept:'Product (PM)',story:'在最關鍵的時間點提出了一個讓大家都服氣的解法，把原本卡住兩週的需求討論直接收尾。',createdAt:now-22*3600000,likes:12},
  ];
  lsSet(LS_POSTS, state.posts);
  renderAll();
}

/* ── Submit ── */
async function onSubmit(e){
  e.preventDefault();
  const name  = ($.heroName.value||'').replace(/\s+/g,'').trim();
  const dept  = ($.dept.value||'').trim();
  const story = ($.story.value||'').trim();
  if(!name)  return toast('請填寫神隊友姓名');
  if(!dept)  return toast('請選擇部門');
  if(!story) return toast('請填寫超能力事蹟');
  if(!/^[A-Za-z0-9_\u4e00-\u9fff]{2,40}$/.test(name)) return toast('姓名格式建議為英數字，例如 ArthurWang');
  const post = {id:uid(),heroName:name,dept,story,createdAt:Date.now(),likes:0};
  state.posts.unshift(post);
  lsSet(LS_POSTS, state.posts);
  renderAll();
  closeModal();
  $.form.reset();
  toast('感謝已送出，正在寫入試算表…');
  sendToServer(
    {action:'create',heroName:name,dept,story},
    ()=> { toast('感謝已成功寫入 Google 試算表 ✅'); loadFromServer(); },
    ()=> { toast('已先顯示在畫面，試算表寫入失敗'); }
  );
  window.scrollTo({top:0,behavior:'smooth'});
}

/* ── Like ── */
function handleLike(postId){
  const post = state.posts.find(p => p.id === postId);
  if(!post) return;
  if(state.likesMap[postId]){
    post.likes = Math.max(0,(post.likes||0)-1);
    delete state.likesMap[postId];
  } else {
    post.likes = (post.likes||0)+1;
    state.likesMap[postId] = true;
  }
  lsSet(LS_POSTS, state.posts);
  lsSet(LS_LIKES, state.likesMap);
  // Sync to server
  sendToServer({action:'like',id:postId,likes:post.likes}, null, null);
  renderAll();
}

/* ── Comment ── */
function toggleComment(postId){
  state.openComments[postId] = !state.openComments[postId];
  const wrap = document.getElementById('cmtWrap_'+postId);
  if(wrap) wrap.classList.toggle('open', !!state.openComments[postId]);
}

function submitComment(postId){
  const inp = document.getElementById('cmtInput_'+postId);
  if(!inp) return;
  const text = (inp.value||'').trim();
  if(!text) return toast('留言不可為空');
  if(!state.comments[postId]) state.comments[postId] = [];
  if(state.comments[postId].length >= MAX_COMMENTS){
    return toast('留言已達上限，來增加新的感謝吧！');
  }
  const comment = {text, createdAt: Date.now()};
  state.comments[postId].push(comment);
  lsSet(LS_COMMENTS, state.comments);
  inp.value = '';
  // Sync to server
  sendToServer({action:'comment',id:postId,comment:text}, null, null);
  renderAll();
  // keep comment section open
  state.openComments[postId] = true;
}

/* ── Render ── */
function renderAll(){
  renderStats();
  renderMarquee();
  renderChips();
  renderLeaderboard();
  renderWall(filtered());
}

function renderStats(){
  const now = Date.now();
  const weekStart = now - WEEK;
  const totalLikes = state.posts.reduce((s,p)=>(s+(p.likes||0)),0);
  const weekNew    = state.posts.filter(p=>p.createdAt>=weekStart).length;
  const weekCmts   = state.posts.reduce((s,p)=>{
    const cmts = (state.comments[p.id]||[]).filter(c=>c.createdAt>=weekStart);
    return s+cmts.length;
  },0);
  $.statLikes.textContent        = fmt(totalLikes);
  $.statWeekNew.textContent      = '+' + fmt(weekNew);
  $.statWeekComments.textContent = fmt(weekCmts);
}

function renderMarquee(){
  const now = Date.now();
  const recent = state.posts.filter(p=>now-p.createdAt<=HOUR72)
    .sort((a,b)=>b.createdAt-a.createdAt).slice(0,12);
  const src = recent.length ? recent : [{heroName:'神隊友',story:'目前還沒有 72 小時內的新感謝，歡迎送出第一則！'}];
  const html = src.map(p=>{
    const preview = p.story.length>32 ? p.story.slice(0,32)+'…' : p.story;
    return `<span class="mq-item"><span class="mq-heart">❤</span>感謝 <strong>${esc(p.heroName)}</strong> 的超能力事蹟：${esc(preview)}<span class="mq-sep">·</span></span>`;
  }).join('');
  $.marquee.innerHTML = html + html; // duplicate for infinite loop
}

function renderChips(){
  $.deptChips.innerHTML = DEPTS.map(d=>`<button type="button" class="chip${state.dept===d?' active':''}" data-dept="${esc(d)}">${esc(d)}</button>`).join('');
  $.deptChips.querySelectorAll('.chip').forEach(btn=>{
    btn.addEventListener('click',()=>{ state.dept=btn.dataset.dept||'全部'; renderAll(); });
  });
}

function renderLeaderboard(){
  const twoWeek = Date.now() - 14*24*3600*1000;
  // likes leaderboard
  const likesMap={}, thanksMap={};
  state.posts.filter(p=>p.createdAt>=twoWeek).forEach(p=>{
    likesMap[p.heroName]  = (likesMap[p.heroName]||0)  + (p.likes||0);
    thanksMap[p.heroName] = (thanksMap[p.heroName]||0) + 1;
  });
  const topLikes  = topEntry(likesMap);
  const topThanks = topEntry(thanksMap);

  const likeCard = topLikes ? `
    <div class="panel leader-card">
      <div class="leader-lbl lbl-pink"><span class="ldot"></span>兩週按讚王</div>
      <div class="leader-main">
        <div class="avatar ${getAv(topLikes.name)}">${initial(topLikes.name)}</div>
        <div class="leader-info">
          <h3>${esc(topLikes.name)}</h3>
          <p>${esc(findDept(topLikes.name))}</p>
        </div>
        <div class="leader-score">❤ ${fmt(topLikes.val)}</div>
      </div>
    </div>` : `<div class="panel leader-card"><div class="leader-lbl lbl-pink"><span class="ldot"></span>兩週按讚王</div><p style="color:var(--muted);font-size:13px;margin-top:10px;">暫無資料</p></div>`;

  const thanksCard = topThanks ? `
    <div class="panel leader-card">
      <div class="leader-lbl lbl-teal"><span class="ldot"></span>兩週感謝王</div>
      <div class="leader-main">
        <div class="avatar ${getAv(topThanks.name)}">${initial(topThanks.name)}</div>
        <div class="leader-info">
          <h3>${esc(topThanks.name)}</h3>
          <p>${esc(findDept(topThanks.name))}</p>
        </div>
        <div class="leader-score">✨ ${fmt(topThanks.val)}</div>
      </div>
    </div>` : `<div class="panel leader-card"><div class="leader-lbl lbl-teal"><span class="ldot"></span>兩週感謝王</div><p style="color:var(--muted);font-size:13px;margin-top:10px;">暫無資料</p></div>`;

  const addCard = `
    <div class="panel add-card add-leader-card" id="openModalBtn" role="button" tabindex="0" aria-label="送出感謝">
      <div class="add-icon">✨</div>
      <p>送出一則感謝</p>
      <span>點擊填寫表單</span>
    </div>`;

  $.leaderRow.innerHTML = likeCard + thanksCard + addCard;
  const openBtn = el('openModalBtn');
  if(openBtn){
    openBtn.addEventListener('click', openModal);
    openBtn.addEventListener('keydown', e=>{ if(e.key==='Enter'||e.key===' ') openModal(); });
  }
}

function renderWall(posts){
  if(!posts.length){
    $.wall.innerHTML = '<div class="empty">目前沒有符合條件的感謝內容，試試看切換部門或搜尋其他關鍵字。</div>';
    return;
  }
  $.wall.innerHTML = posts.map((p,i)=>{
    const liked    = !!state.likesMap[p.id];
    const cmts     = state.comments[p.id] || [];
    const cmtCount = cmts.length;
    const isOpen   = !!state.openComments[p.id];
    const atLimit  = cmtCount >= MAX_COMMENTS;

    const commentItems = cmts.map(c=>`
      <div class="comment-item">
        <div>${esc(c.text)}</div>
        <div class="c-time">${relTime(c.createdAt)}</div>
      </div>`).join('');

    const limitMsg = atLimit
      ? `<div class="comment-limit">留言已達上限 ${MAX_COMMENTS}/${MAX_COMMENTS}，來增加新的感謝吧！</div>`
      : `<div class="comment-form">
           <textarea class="comment-input" id="cmtInput_${p.id}" placeholder="輸入留言…" rows="1" maxlength="200"></textarea>
           <button class="comment-send" data-cmt-send="${p.id}">送出</button>
         </div>`;

    return `
    <article class="panel post-card">
      <div class="post-top">
        <div class="avatar ${AV_CLASSES[i%AV_CLASSES.length]}">${initial(p.heroName)}</div>
        <div class="post-info">
          <div class="post-name-row">
            <div class="post-name">${esc(p.heroName)}</div>
            <div class="post-time">${relTime(p.createdAt)}</div>
          </div>
          <div class="post-dept">${esc(p.dept)}</div>
        </div>
      </div>
      <div class="post-body">${esc(p.story)}</div>
      <div class="post-foot">
        <button class="act-btn${liked?' liked':''}" data-like="${p.id}">
          ${liked?'❤':'♡'} ${fmt(p.likes||0)}
        </button>
        <button class="act-btn" data-cmt-toggle="${p.id}">
          💬 ${cmtCount} 留言
        </button>
      </div>
      <div class="comments-wrap${isOpen?' open':''}" id="cmtWrap_${p.id}">
        <div class="comment-list">${commentItems}</div>
        ${limitMsg}
      </div>
    </article>`;
  }).join('');

  // Bind events
  $.wall.querySelectorAll('[data-like]').forEach(btn=>{
    btn.addEventListener('click',()=>handleLike(btn.dataset.like));
  });
  $.wall.querySelectorAll('[data-cmt-toggle]').forEach(btn=>{
    btn.addEventListener('click',()=>toggleComment(btn.dataset.cmtToggle));
  });
  $.wall.querySelectorAll('[data-cmt-send]').forEach(btn=>{
    btn.addEventListener('click',()=>submitComment(btn.dataset.cmtSend));
  });
  // Allow Enter in comment box (Shift+Enter = newline)
  $.wall.querySelectorAll('.comment-input').forEach(inp=>{
    inp.addEventListener('keydown', e=>{
      if(e.key==='Enter' && !e.shiftKey){
        e.preventDefault();
        const pid = inp.id.replace('cmtInput_','');
        submitComment(pid);
      }
    });
  });
}

/* ── Helpers ── */
function filtered(){
  return state.posts.filter(p=>{
    const dm = state.dept==='全部' || p.dept===state.dept;
    const txt = (p.heroName+' '+p.dept+' '+p.story).toLowerCase();
    const km  = !state.kw || txt.includes(state.kw);
    return dm && km;
  }).sort((a,b)=>b.createdAt-a.createdAt);
}

function mergePosts(incoming){
  const likesByKey={};
  state.posts.forEach(p=>{ likesByKey[sigKey(p)]=p.likes||0; });
  state.posts = incoming.map(p=>({
    ...p,
    likes: Number(p.likes||likesByKey[sigKey(p)]||0)
  })).sort((a,b)=>b.createdAt-a.createdAt);
}

function normalizePost(row, idx){
  if(!row) return null;
  const heroName = str(row.heroName || row['神隊友（格式：ArthurWang）'] || row['神隊友'] || '');
  const dept     = str(row.dept     || row['部門'] || '');
  const story    = str(row.story    || row['他的超能力事蹟（當時發生了什麼？他做了什麼讓你難忘呢？）'] || row['他的超能力事蹟'] || '');
  const rawTime  = row.createdAt || row.time || row['time'] || '';
  if(!heroName||!dept||!story) return null;
  let createdAt = Date.parse(rawTime);
  if(isNaN(createdAt)) createdAt = Date.now() - idx*60000;
  return {id:str(row.id||uid()), heroName, dept, story, createdAt, likes:Number(row.likes||0)};
}

function validPost(p){ return p && typeof p.heroName==='string' && typeof p.dept==='string' && typeof p.story==='string' && typeof p.createdAt==='number'; }
function sigKey(p){ return [p.heroName,p.dept,p.story].join('||'); }
function topEntry(map){
  const keys=Object.keys(map);
  if(!keys.length) return null;
  let top=keys[0];
  keys.forEach(k=>{ if(map[k]>map[top]) top=k; });
  return {name:top, val:map[top]};
}
function findDept(name){
  const p=state.posts.find(p=>p.heroName===name);
  return p ? p.dept : '';
}
function getAv(name){
  let h=0; for(let i=0;i<name.length;i++) h=(h+name.charCodeAt(i))%AV_CLASSES.length;
  return AV_CLASSES[h];
}
function initial(name){ return String(name||'').slice(0,1).toUpperCase()||'神'; }
function fmt(n){ return new Intl.NumberFormat('zh-TW').format(Number(n)||0); }
function uid(){ return 'i'+Math.random().toString(36).slice(2,9)+Date.now().toString(36); }
function str(v){ return String(v||'').trim(); }
function esc(s){
  return String(s).replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;').replace(/'/g,'&#39;');
}
function relTime(ts){
  const d=Date.now()-ts;
  if(d<60000) return '剛剛';
  if(d<3600000) return Math.floor(d/60000)+'分鐘前';
  if(d<86400000) return Math.floor(d/3600000)+'小時前';
  if(d<604800000) return Math.floor(d/86400000)+'天前';
  const dt=new Date(ts);
  return `${dt.getFullYear()}/${String(dt.getMonth()+1).padStart(2,'0')}/${String(dt.getDate()).padStart(2,'0')}`;
}
function debounce(fn,ms){ let t; return function(){ clearTimeout(t); t=setTimeout(()=>fn.apply(this,arguments),ms); }; }

let _toastTimer=null;
function toast(msg){
  $.toast.textContent=msg;
  $.toast.classList.add('show');
  clearTimeout(_toastTimer);
  _toastTimer=setTimeout(()=>$.toast.classList.remove('show'),2400);
}

/* ── Logo Rain ── */
function createLogoRain(){
  $.logoRain.innerHTML='';
  const n = window.innerWidth<768 ? 10 : 20;
  for(let i=0;i<n;i++){
    const s=document.createElement('span');
    s.className='logo-drop';
    const sz=rand(65,180);
    s.style.cssText=`left:${rand(0,100)}%;--sz:${sz}px;--dur:${rand(14,28)}s;--del:${-rand(0,26)}s;--op:${(Math.random()*.16+.12).toFixed(3)};--rot:${rand(-14,12)}deg;--dx:${rand(-80,100)}px;`;
    $.logoRain.appendChild(s);
  }
}
function rand(a,b){ return Math.floor(Math.random()*(b-a+1))+a; }

init();
})();
</script>
</body>
</html>
