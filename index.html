<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>TBFPUMBA — Gift Battle</title>
<meta name="description" content="Крути рулетку, выбивай гифты, копи звёзды и монетки, храни всё в банке.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Anton&family=IBM+Plex+Mono:wght@400;500;600&display=swap" rel="stylesheet">
<script src="https://telegram.org/js/telegram-widget.js?22"></script>
<style>
  :root{
    --bg-0:#0a0f1c; --bg-1:#111a30; --bg-2:#16223e;
    --blue:#3b82f6; --blue-dim:#1e4d8f; --cta:#0ea5e9; --gold:#f2b84b;
    --bone:#eaf1fb; --tan:#7d92b8; --line:rgba(234,241,251,0.14);
    --c-common:#7d92b8; --c-rare:#3b82f6; --c-epic:#8b5cf6; --c-legend:#f2b84b; --c-mythic:#eaf1fb;
    --danger:#ef476f;
  }
  *{box-sizing:border-box;margin:0;padding:0;}
  body{background:var(--bg-0);color:var(--bone);font-family:'IBM Plex Mono',monospace;line-height:1.6;}
  a{color:inherit;text-decoration:none;}
  h1,h2,h3{font-family:'Anton',sans-serif;font-weight:400;letter-spacing:0.01em;line-height:0.95;}
  button{font-family:'IBM Plex Mono',monospace;cursor:pointer;}
  input{font-family:'IBM Plex Mono',monospace;}
  input[type="text"], input[type="number"]{transition:border-color .18s ease, box-shadow .18s ease;}
  input[type="text"]:focus, input[type="number"]:focus{
    outline:none;border-color:var(--blue) !important;box-shadow:0 0 0 3px rgba(59,130,246,0.2);
  }
  button:focus-visible{outline:2px solid var(--blue);outline-offset:2px;}

  .nav{display:flex;align-items:center;justify-content:space-between;padding:18px 28px;border-bottom:1px solid var(--line);flex-wrap:wrap;gap:12px;}
  .brand{font-family:'Anton',sans-serif;font-size:20px;}
  .brand span{color:var(--blue);}
  .nav-right{display:flex;align-items:center;gap:10px;flex-wrap:wrap;}
  .balance{display:flex;align-items:center;gap:8px;background:var(--bg-1);border:1px solid var(--line);border-radius:999px;padding:9px 18px;font-size:15px;font-weight:600;color:var(--gold);transition:color .2s ease,border-color .2s ease;}
  .balance.negative{color:var(--danger);border-color:var(--danger);}
  .coin-balance{display:flex;align-items:center;gap:8px;background:var(--bg-1);border:1px solid var(--line);border-radius:999px;padding:9px 18px;font-size:15px;font-weight:600;color:#e0a94a;}
  .level-badge{display:flex;align-items:center;gap:8px;background:var(--bg-1);border:1px solid var(--line);border-radius:999px;padding:9px 16px;font-size:12px;color:var(--tan);}
  .level-badge b{color:var(--bone);}
  .bank-nav-btn{background:var(--blue);border:none;color:var(--bg-0);border-radius:999px;padding:11px 20px;font-size:13px;font-weight:700;transition:transform .18s ease, box-shadow .18s ease, background .18s ease;box-shadow:0 6px 16px rgba(59,130,246,0.35);}
  .bank-nav-btn:hover{transform:translateY(-2px);box-shadow:0 10px 22px rgba(59,130,246,0.5);background:#4f90ff;}
  .bank-nav-btn:active{transform:translateY(0);}
  .settings-btn{
    background:var(--bg-1);border:1px solid var(--line);color:var(--bone);
    border-radius:50%;width:42px;height:42px;font-size:17px;
    display:flex;align-items:center;justify-content:center;
    transition:transform .3s ease, border-color .2s ease;
  }
  .settings-btn:hover{transform:rotate(45deg);border-color:var(--blue);}
  .tg-chip{display:flex;align-items:center;}
  .tg-login-btn{
    background:#2aabee;border:none;color:#fff;border-radius:999px;
    padding:10px 16px;font-size:12px;font-weight:600;
    transition:transform .18s ease, box-shadow .18s ease;
  }
  .tg-login-btn:hover{transform:translateY(-2px);box-shadow:0 6px 16px rgba(42,171,238,0.4);}
  .tg-profile{
    display:flex;align-items:center;gap:8px;background:var(--bg-1);border:1px solid var(--line);
    border-radius:999px;padding:5px 14px 5px 5px;
  }
  .tg-profile img{width:30px;height:30px;border-radius:50%;object-fit:cover;}
  .tg-profile .tg-name{font-size:12px;color:var(--bone);max-width:110px;overflow:hidden;text-overflow:ellipsis;white-space:nowrap;}
  .tg-profile .tg-logout{background:transparent;border:none;color:var(--tan);font-size:14px;padding:0 2px;}
  .tg-profile .tg-logout:hover{color:var(--danger);}

  .wrap{max-width:1080px;margin:0 auto;padding:0 28px;}

  .intro{padding:28px 0 14px;max-width:620px;}
  .intro h1{font-size:clamp(28px,5vw,44px);text-transform:uppercase;}
  .intro h1 em{font-style:normal;color:var(--blue);}
  .intro p{margin-top:10px;color:var(--tan);font-size:14px;}

  .xp-bar-wrap{max-width:620px;margin:14px 0 6px;}
  .xp-bar-track{background:var(--bg-2);border:1px solid var(--line);height:9px;border-radius:999px;overflow:hidden;}
  .xp-bar-fill{background:linear-gradient(90deg, var(--blue), var(--cta));height:100%;width:0%;transition:width .3s ease;border-radius:999px;}
  .xp-label{font-size:11px;color:var(--tan);margin-top:6px;}

  /* ROULETTE */
  .roulette{padding:20px 0 50px;}
  .reel-frame{position:relative;background:var(--bg-1);border:1px solid var(--line);border-radius:20px;overflow:hidden;padding:20px 0;transition:box-shadow .3s ease, border-color .3s ease;}
  .reel-frame.spinning{box-shadow:0 0 34px rgba(59,130,246,0.4), inset 0 0 20px rgba(59,130,246,0.08);border-color:var(--blue);}
  .reel-viewport{position:relative;height:150px;overflow:hidden;}
  .reel-track{position:absolute;top:0;left:0;display:flex;will-change:transform;}
  .reel-item{width:140px;height:150px;flex:0 0 140px;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:8px;border-right:1px solid var(--line);}
  .reel-item .ico{font-size:52px;filter:drop-shadow(0 0 6px rgba(0,0,0,0.4));}
  .reel-item .rn{font-size:10px;text-transform:uppercase;color:var(--tan);}
  .rar-common .ico{color:var(--c-common);}
  .rar-rare .ico{color:var(--c-rare);}
  .rar-epic .ico{color:var(--c-epic);}
  .rar-legend .ico{color:var(--c-legend); text-shadow:0 0 18px rgba(242,184,75,0.6);}
  .rar-mythic .ico{color:var(--c-mythic);text-shadow:0 0 10px rgba(59,130,246,0.7), 0 0 22px rgba(139,92,246,0.5), 0 0 32px rgba(59,130,246,0.5);animation:mythicpulse 2.2s ease-in-out infinite;}
  @keyframes mythicpulse{0%,100%{filter:brightness(1);}50%{filter:brightness(1.35);}}

  .pointer{position:absolute;top:0;bottom:0;left:50%;width:2px;background:var(--cta);transform:translateX(-1px);z-index:3;}
  .pointer::before, .pointer::after{content:"";position:absolute;left:50%;transform:translateX(-50%);border:8px solid transparent;}
  .pointer::before{top:-2px;border-top-color:var(--cta);border-bottom:0;}
  .pointer::after{bottom:-2px;border-bottom-color:var(--cta);border-top:0;}

  .fade-l, .fade-r{position:absolute;top:0;bottom:0;width:80px;z-index:2;pointer-events:none;}
  .fade-l{left:0;background:linear-gradient(90deg, var(--bg-1), transparent);}
  .fade-r{right:0;background:linear-gradient(-90deg, var(--bg-1), transparent);}

  .spin-row{margin-top:18px;}
  .currency-toggle{display:flex;gap:8px;margin-bottom:14px;flex-wrap:wrap;}
  .curr-btn{
    background:var(--bg-2);border:1px solid var(--line);color:var(--tan);
    border-radius:999px;padding:8px 16px;font-size:12px;
    transition:background .18s ease, color .18s ease, border-color .18s ease;
  }
  .curr-btn.active{background:var(--blue);color:#08111f;border-color:var(--blue);font-weight:600;}
  .curr-btn:hover{border-color:var(--blue);}
  .spin-buttons{display:flex;gap:10px;flex-wrap:wrap;}
  .btn-primary{
    background:linear-gradient(135deg, var(--cta), var(--blue));
    color:#08111f;border:none;border-radius:999px;
    padding:15px 24px;font-weight:700;font-size:14px;
    transition:transform .18s ease, box-shadow .18s ease, background .18s ease;
    flex:1;min-width:130px;box-shadow:0 6px 16px rgba(14,165,233,0.3);
  }
  .btn-primary:hover{transform:translateY(-3px);box-shadow:0 10px 24px rgba(14,165,233,0.45);}
  .btn-primary:active{transform:translateY(0);}
  .btn-primary:disabled{background:var(--bg-2);color:var(--tan);cursor:not-allowed;box-shadow:none;transform:none;}
  .odds{font-size:12px;color:var(--tan);margin-top:12px;}
  .odds b{color:var(--bone);}

  /* PROFILE */
  .profile{padding:20px 0 60px;}
  .section-head{display:flex;align-items:baseline;justify-content:space-between;margin-bottom:22px;flex-wrap:wrap;gap:10px;}
  .section-head h2{font-size:clamp(26px,4vw,36px);text-transform:uppercase;}
  .section-head p{font-size:13px;color:var(--tan);}
  .empty-state{border:1px dashed var(--line);border-radius:16px;padding:40px;text-align:center;color:var(--tan);font-size:14px;}
  .inv-grid{display:grid;grid-template-columns:repeat(auto-fill, minmax(150px, 1fr));gap:14px;}
  .gift-card{background:var(--bg-1);border:1px solid var(--line);border-radius:18px;padding:20px 14px;text-align:center;cursor:pointer;transition:transform .18s ease, border-color .18s ease, box-shadow .18s ease;position:relative;}
  .gift-card:hover{transform:translateY(-6px);border-color:var(--blue);box-shadow:0 12px 24px rgba(0,0,0,0.35);}
  .gift-card .ico{font-size:44px;display:inline-block;animation:bob 3s ease-in-out infinite;}
  .gift-card.rar-legend .ico{animation:spin3d 3.5s linear infinite;}
  .gift-card.rar-mythic .ico{animation:spin3d 3.5s linear infinite, mythicpulse 2.2s ease-in-out infinite;}
  .gift-card.rar-mythic{border-color:var(--c-mythic);}
  .gift-card .name{margin-top:10px;font-size:12px;color:var(--bone);}
  .gift-card .count{position:absolute;top:8px;right:8px;background:var(--bg-2);border:1px solid var(--line);border-radius:999px;font-size:11px;padding:2px 9px;color:var(--tan);}
  @keyframes bob{0%,100%{transform:translateY(0);}50%{transform:translateY(-6px);}}
  @keyframes spin3d{from{transform:rotateY(0deg);}to{transform:rotateY(360deg);}}

  /* BANK */
  .bank-section{padding:30px 0 80px;border-top:1px solid var(--line);display:none;}
  .bank-section.active{display:block;}
  .bank-back{font-size:12px;color:var(--tan);border:1px solid var(--line);border-radius:999px;padding:9px 16px;display:inline-block;margin-bottom:22px;transition:border-color .18s ease,color .18s ease;}
  .bank-back:hover{border-color:var(--blue);color:var(--blue);}
  .bank-block{background:var(--bg-1);border:1px solid var(--line);border-radius:18px;padding:24px;margin-bottom:20px;}
  .bank-block h3{font-size:13px;text-transform:uppercase;color:var(--tan);margin-bottom:16px;letter-spacing:0.05em;}
  .bank-stars-row{display:flex;align-items:center;gap:14px;flex-wrap:wrap;}
  .bank-stars-amt{font-family:'Anton',sans-serif;font-size:26px;color:var(--gold);}
  .bank-input-row{display:flex;gap:10px;flex-wrap:wrap;align-items:center;margin-top:14px;}
  .bank-input-row input[type="number"]{width:130px;background:var(--bg-2);border:1px solid var(--line);border-radius:999px;color:var(--bone);padding:10px 16px;font-size:13px;}
  .bank-list{display:flex;flex-direction:column;gap:10px;}
  .bank-row{display:flex;align-items:center;justify-content:space-between;gap:10px;flex-wrap:wrap;background:var(--bg-2);border:1px solid var(--line);border-radius:14px;padding:12px 16px;transition:border-color .18s ease, transform .18s ease;}
  .bank-row:hover{border-color:var(--blue-dim);transform:translateX(2px);}
  .bank-row-left{display:flex;align-items:center;gap:12px;}
  .bank-row-left .ico{font-size:26px;}
  .bank-row-meta{font-size:11px;color:var(--tan);}
  .bank-row-name{font-size:13px;color:var(--bone);}

  .shop-grid{display:grid;grid-template-columns:repeat(auto-fill, minmax(180px,1fr));gap:12px;}
  .shop-card{background:var(--bg-2);border:1px solid var(--line);border-radius:16px;padding:16px;text-align:center;transition:transform .18s ease, border-color .18s ease, box-shadow .18s ease;}
  .shop-card:hover{transform:translateY(-4px);border-color:var(--blue);box-shadow:0 10px 20px rgba(0,0,0,0.3);}
  .shop-card .ico{font-size:34px;}
  .shop-card .name{font-size:12px;margin-top:6px;color:var(--bone);}
  .shop-card .price{font-size:12px;color:var(--gold);margin-top:6px;}

  .promo-row{display:flex;gap:10px;flex-wrap:wrap;}
  .promo-row input[type="text"]{flex:1;min-width:200px;background:var(--bg-2);border:1px solid var(--line);border-radius:999px;color:var(--bone);padding:11px 18px;font-size:13px;}
  .redeem-row{display:flex;gap:10px;flex-wrap:wrap;margin-bottom:20px;}
  .ref-block{background:var(--bg-1);border:1px solid var(--line);border-radius:16px;padding:18px;margin-bottom:16px;}
  .ref-block-label{font-size:12px;color:var(--tan);margin-bottom:12px;}
  .ref-block .redeem-row{margin-bottom:10px;}
  .ref-status{font-size:12px;color:var(--blue);}
  .redeem-row input[type="text"]{flex:1;min-width:200px;background:var(--bg-1);border:1px solid var(--line);border-radius:999px;color:var(--bone);padding:11px 18px;font-size:13px;}

  .btn-secondary{border:1px solid var(--blue);background:transparent;color:var(--bone);border-radius:999px;padding:10px 18px;font-size:12px;transition:background .18s ease,color .18s ease,transform .18s ease,box-shadow .18s ease;white-space:nowrap;}
  .btn-secondary:hover{background:var(--blue);color:#08111f;transform:translateY(-2px);box-shadow:0 6px 14px rgba(59,130,246,0.3);}
  .btn-secondary:active{transform:translateY(0);}
  .btn-secondary.gold{border-color:var(--gold);color:var(--gold);}
  .btn-secondary.gold:hover{background:var(--gold);color:#08111f;box-shadow:0 6px 14px rgba(242,184,75,0.3);}

  /* MODAL */
  .modal-overlay{position:fixed;inset:0;background:rgba(10,15,28,0.86);display:flex;align-items:center;justify-content:center;z-index:50;padding:20px;opacity:0;transition:opacity .22s ease;}
  .modal-overlay.hidden{display:none;opacity:0;}
  .modal-overlay.visible{opacity:1;}
  .modal-card{background:var(--bg-1);border:1px solid var(--line);border-radius:24px;max-width:420px;width:100%;padding:34px 30px;text-align:center;position:relative;transform:scale(0.9) translateY(14px);transition:transform .22s cubic-bezier(0.2,0.9,0.3,1.3);box-shadow:0 20px 50px rgba(0,0,0,0.5);}
  .modal-overlay.visible .modal-card{transform:scale(1) translateY(0);}
  .modal-close{position:absolute;top:14px;right:14px;background:transparent;border:1px solid var(--line);border-radius:50%;color:var(--bone);width:32px;height:32px;font-size:16px;line-height:1;transition:border-color .18s ease,color .18s ease;}
  .modal-close:hover{border-color:var(--blue);color:var(--blue);}
  .modal-rar{font-size:11px;text-transform:uppercase;letter-spacing:0.08em;}
  .modal-ico{display:none;}
  #special-canvas{width:100%;height:220px;display:block;background:radial-gradient(ellipse at 50% 65%, rgba(59,130,246,0.18) 0%, rgba(59,130,246,0.05) 45%, transparent 70%);border-radius:16px;}
  .modal-name{font-family:'Anton',sans-serif;font-size:26px;text-transform:uppercase;margin-top:8px;}
  .modal-desc{font-size:13px;color:var(--tan);margin-top:8px;}
  .modal-actions{display:flex;gap:10px;justify-content:center;margin-top:24px;flex-wrap:wrap;}

  /* BATCH MODAL */
  .batch-overlay{position:fixed;inset:0;background:rgba(10,15,28,0.9);display:flex;align-items:center;justify-content:center;z-index:55;padding:20px;opacity:0;transition:opacity .22s ease;}
  .batch-overlay.hidden{display:none;opacity:0;}
  .batch-overlay.visible{opacity:1;}
  .batch-card{background:var(--bg-1);border:1px solid var(--line);border-radius:24px;max-width:640px;width:100%;padding:30px;max-height:82vh;overflow:auto;transform:scale(0.92) translateY(14px);transition:transform .22s cubic-bezier(0.2,0.9,0.3,1.3);box-shadow:0 20px 50px rgba(0,0,0,0.5);}
  .batch-overlay.visible .batch-card{transform:scale(1) translateY(0);}
  .batch-card h3{font-size:22px;text-transform:uppercase;margin-bottom:6px;}
  .batch-sub{font-size:12px;color:var(--tan);margin-bottom:18px;}
  .batch-grid{display:grid;grid-template-columns:repeat(auto-fill, minmax(120px,1fr));gap:10px;}
  .batch-item{background:var(--bg-2);border:1px solid var(--line);border-radius:14px;padding:14px 8px;text-align:center;animation:popin .35s ease both;}
  .batch-item .ico{font-size:34px;}
  .batch-item .name{font-size:11px;margin-top:6px;color:var(--bone);}
  @keyframes popin{from{opacity:0;transform:scale(0.7);}to{opacity:1;transform:scale(1);}}
  .batch-actions{margin-top:20px;display:flex;gap:10px;justify-content:flex-end;flex-wrap:wrap;}

  .transition-overlay{position:fixed;inset:0;z-index:100;pointer-events:none;background:radial-gradient(circle, var(--cta) 0%, var(--blue-dim) 45%, var(--bg-0) 75%);clip-path:circle(0% at 50% 40%);transition:clip-path .55s cubic-bezier(0.6,0,0.3,1);}
  .transition-overlay.active{clip-path:circle(150% at 50% 40%);}

  .toast{position:fixed;bottom:24px;left:50%;transform:translateX(-50%);background:var(--bg-2);border:1px solid var(--blue);color:var(--bone);border-radius:999px;padding:12px 24px;font-size:13px;z-index:60;opacity:0;transition:opacity .25s ease, transform .25s ease;pointer-events:none;text-align:center;max-width:88vw;}
  .toast.show{opacity:1;transform:translateX(-50%) translateY(-6px);}

  .settings-row{margin-bottom:22px;text-align:left;}
  .settings-row h4{font-size:12px;text-transform:uppercase;color:var(--tan);letter-spacing:0.05em;margin-bottom:12px;}
  .swatch-row{display:flex;gap:12px;flex-wrap:wrap;}
  .swatch{
    width:38px;height:38px;border-radius:50%;border:2px solid transparent;cursor:pointer;
    transition:transform .15s ease, border-color .15s ease, box-shadow .15s ease;
    display:flex;align-items:center;justify-content:center;color:#08111f;font-size:14px;font-weight:700;
  }
  .swatch:hover{transform:scale(1.12);}
  .swatch.active{border-color:var(--bone);box-shadow:0 0 0 3px rgba(234,241,251,0.15);}
  .swatch.active::after{content:"✓";}
  .toggle-row{display:flex;align-items:center;justify-content:space-between;gap:14px;}
  .toggle-row span{font-size:13px;color:var(--bone);}
  .switch{position:relative;width:48px;height:26px;flex-shrink:0;}
  .switch input{opacity:0;width:0;height:0;}
  .switch-track{position:absolute;inset:0;background:var(--bg-2);border:1px solid var(--line);border-radius:999px;cursor:pointer;transition:background .2s ease;}
  .switch-track::before{content:"";position:absolute;width:18px;height:18px;left:3px;top:3px;background:var(--tan);border-radius:50%;transition:transform .2s ease, background .2s ease;}
  .switch input:checked + .switch-track{background:var(--blue-dim);}
  .switch input:checked + .switch-track::before{transform:translateX(22px);background:var(--blue);}

  body.reduce-motion .gift-card .ico{animation:none !important;}
  body.reduce-motion .reel-frame.spinning{box-shadow:none;}
  body.reduce-motion .balance, body.reduce-motion .xp-bar-fill{transition:none;}

  footer{padding:26px 28px 40px;font-size:12px;color:var(--tan);border-top:1px solid var(--line);}


  @media (max-width:600px){
    .reel-item{width:110px;flex-basis:110px;}
    .reel-item .ico{font-size:40px;}
    .spin-buttons{flex-direction:column;}
  }
  @media (max-width:420px){
    .nav{padding:14px 16px;gap:8px;}
    .balance, .coin-balance{padding:7px 12px;font-size:13px;}
    .level-badge{padding:7px 12px;font-size:11px;}
    .bank-nav-btn{padding:9px 14px;font-size:12px;}
    .settings-btn{width:36px;height:36px;font-size:15px;}
  }
</style>
</head>
<body>

<header class="nav">
  <div class="brand">TBF<span>PUMBA</span> · GIFT BATTLE</div>
  <div class="nav-right">
    <div class="level-badge">УР. <b id="level-val">1</b></div>
    <div class="balance">★ <span id="balance-val">500</span></div>
    <div class="coin-balance">🪙 <span id="coins-val">0</span></div>
    <button class="bank-nav-btn" id="go-bank-btn">🏦 Банк</button>
    <div id="tg-profile-chip" class="tg-chip">
      <button class="tg-login-btn" id="tg-login-btn">Войти через Telegram</button>
    </div>
    <button class="settings-btn" id="settings-btn" title="Настройки" aria-label="Настройки">⚙️</button>
  </div>
</header>

<div class="wrap" id="main-view">
  <div class="intro">
    <h1>Выбивай <em>гифты</em></h1>
    <p>Крути рулетку за звёзды, собирай гифты в профиль, храни их в банке, покупай новые или продавай. Звёзды и монетки не настоящие — это только внутриигровая валюта.</p>
  </div>
  <div class="xp-bar-wrap">
    <div class="xp-bar-track"><div class="xp-bar-fill" id="xp-fill"></div></div>
    <div class="xp-label" id="xp-label">0 / 150 XP до след. уровня</div>
  </div>

  <section class="roulette">
    <div class="reel-frame">
      <div class="reel-viewport">
        <div class="fade-l"></div>
        <div class="fade-r"></div>
        <div class="pointer"></div>
        <div class="reel-track" id="reel-track"></div>
      </div>
    </div>
    <div class="spin-row">
      <div class="currency-toggle" id="currency-toggle">
        <button class="curr-btn active" data-currency="stars">Платить ★ звёздами</button>
        <button class="curr-btn" data-currency="coins">Платить 🪙 монетками</button>
      </div>
      <div class="spin-buttons" id="spin-buttons">
        <button class="btn-primary" data-count="1">×1 · 100 ★</button>
        <button class="btn-primary" data-count="2">×2 · 200 ★</button>
        <button class="btn-primary" data-count="3">×3 · 300 ★</button>
        <button class="btn-primary" data-count="4">×4 · 400 ★</button>
      </div>
      <div class="odds">common · rare · epic · legend · mythic — от частого к редкому</div>
    </div>
  </section>

  <section class="profile">
    <div class="section-head">
      <h2>Профиль</h2>
      <p id="inv-count">гифтов: 0</p>
    </div>
    <div class="ref-block">
      <div class="ref-block-label">Пригласи друга — получи 150★, а он +200★ и 50🪙 за вход по твоей ссылке</div>
      <div class="redeem-row">
        <input type="text" id="ref-link-input" readonly>
        <button class="btn-secondary" id="ref-copy-btn">Скопировать ссылку</button>
      </div>
      <div class="ref-status" id="ref-status"></div>
    </div>
    <div class="redeem-row">
      <input type="text" id="redeem-code-input" placeholder="Вставь код подарка или реферальный код">
      <button class="btn-secondary gold" id="redeem-code-btn">Принять код</button>
    </div>
    <div id="inv-empty" class="empty-state">Пока пусто — крути рулетку выше</div>
    <div class="inv-grid" id="inv-grid"></div>
    <div id="sell-all-row" style="margin-top:18px; display:none;">
      <button class="btn-secondary gold" id="sell-all-btn">Продать все гифты за <span id="sell-all-val">0</span> ★</button>
    </div>
  </section>
</div>

<section class="bank-section wrap" id="bank-section">
  <a class="bank-back" id="back-to-roulette">← К рулетке</a>
  <div class="section-head">
    <h2>Банк TBFPUMBA</h2>
    <p>Проценты, кредиты, магазин и промокоды</p>
  </div>

  <div class="bank-block">
    <h3>Улучшения · действуют 1 час</h3>
    <div class="shop-grid" id="boost-grid"></div>
  </div>

  <div class="bank-block">
    <h3>Обмен валют · курс 1 🪙 = 2 ★</h3>
    <div class="bank-stars-row"><div>Монет у тебя: <span class="bank-stars-amt" id="coins-bank-val">0</span> 🪙</div></div>
    <div class="bank-input-row">
      <input type="number" id="coin-buy-amt" placeholder="кол-во монет" min="1">
      <button class="btn-secondary gold" id="coin-buy-btn">Купить монеты за звёзды</button>
    </div>
    <div class="bank-input-row">
      <input type="number" id="coin-exchange-amt" placeholder="кол-во монет" min="1">
      <button class="btn-secondary gold" id="coin-exchange-btn">Обменять на звёзды</button>
    </div>
  </div>

  <div class="bank-block">
    <h3>Хранилище звёзд</h3>
    <div class="bank-stars-row"><div>В банке: <span class="bank-stars-amt" id="bank-stars-val">0</span> ★</div></div>
    <div class="bank-input-row">
      <input type="number" id="bank-star-amt" placeholder="кол-во" min="1">
      <button class="btn-secondary gold" id="bank-deposit-star">Положить</button>
      <button class="btn-secondary gold" id="bank-withdraw-star">Забрать</button>
    </div>
  </div>

  <div class="bank-block">
    <h3>Кредит</h3>
    <div class="bank-row" id="loan-active" style="display:none;">
      <div class="bank-row-left"><div class="ico">💳</div><div>
        <div class="bank-row-name" id="loan-info-name">Кредит: 0 ★</div>
        <div class="bank-row-meta" id="loan-info-meta">—</div>
      </div></div>
      <button class="btn-secondary gold" id="loan-repay-btn">Погасить</button>
    </div>
    <div class="shop-grid" id="loan-options"></div>
  </div>

  <div class="bank-block">
    <h3>Хранилище гифтов · 2 ★/день комиссия · проценты банка начисляются тоже</h3>
    <div id="bank-gifts-empty" class="empty-state">В хранилище пусто</div>
    <div class="bank-list" id="bank-gifts-list"></div>
  </div>

  <div class="bank-block">
    <h3>Сдать гифты на хранение</h3>
    <div id="deposit-empty" class="empty-state">Нет гифтов в профиле</div>
    <div class="bank-list" id="deposit-list"></div>
  </div>

  <div class="bank-block">
    <h3>Продать гифты банку</h3>
    <div id="sellbank-empty" class="empty-state">Нечего продавать</div>
    <div class="bank-list" id="sellbank-list"></div>
  </div>

  <div class="bank-block">
    <h3>Магазин гифтов</h3>
    <div class="shop-grid" id="shop-grid"></div>
  </div>

  <div class="bank-block">
    <h3>Промокод</h3>
    <div class="promo-row">
      <input type="text" id="promo-input" placeholder="Введи промокод">
      <button class="btn-secondary gold" id="promo-btn">Активировать</button>
    </div>
  </div>
</section>

<footer class="wrap">TBFPUMBA © 2026 · игровая валюта, не имеет реальной стоимости</footer>

<div class="modal-overlay hidden" id="modal">
  <div class="modal-card" id="modal-card">
    <button class="modal-close" id="modal-close">✕</button>
    <div class="modal-rar" id="modal-rar">RARE</div>
    <div class="modal-ico" id="modal-ico">🎁</div>
    <canvas id="special-canvas"></canvas>
    <div class="modal-name" id="modal-name">Гифт</div>
    <div class="modal-desc" id="modal-desc">Описание</div>
    <div class="modal-actions">
      <button class="btn-secondary" id="modal-sell">Продать за <span id="modal-sell-val">0</span> ★</button>
      <button class="btn-secondary gold" id="modal-sell-coin">Продать за <span id="modal-sell-coin-val">0</span> 🪙</button>
      <button class="btn-secondary" id="modal-gift">🎁 Подарить</button>
      <button class="btn-secondary" id="modal-keep">Оставить</button>
    </div>
  </div>
</div>

<div class="batch-overlay hidden" id="batch-modal">
  <div class="batch-card">
    <h3 id="batch-title">Результаты</h3>
    <div class="batch-sub" id="batch-sub"></div>
    <div class="batch-grid" id="batch-grid"></div>
    <div class="batch-actions">
      <button class="btn-secondary" id="batch-sell">Продать гифты за <span id="batch-sell-val">0</span> ★</button>
      <button class="btn-secondary gold" id="batch-close">Забрать всё</button>
    </div>
  </div>
</div>

<div class="modal-overlay hidden" id="settings-modal">
  <div class="modal-card" id="settings-card" style="max-width:380px;">
    <button class="modal-close" id="settings-close">✕</button>
    <div class="modal-name" style="margin-top:0;">Настройки</div>
    <div class="settings-row" style="margin-top:24px;">
      <h4>Цветовая тема</h4>
      <div class="swatch-row" id="theme-swatches"></div>
    </div>
    <div class="settings-row">
      <div class="toggle-row">
        <span>Меньше анимаций</span>
        <label class="switch">
          <input type="checkbox" id="reduce-motion-toggle">
          <span class="switch-track"></span>
        </label>
      </div>
    </div>
  </div>
</div>

<div class="modal-overlay hidden" id="gift-code-modal">
  <div class="modal-card" style="max-width:420px;">
    <button class="modal-close" id="gift-code-close">✕</button>
    <div class="modal-name" style="margin-top:0;">🎁 Подарок готов</div>
    <div class="modal-desc" id="gift-code-desc"></div>
    <textarea id="gift-code-text" readonly rows="3" style="width:100%;margin-top:14px;background:var(--bg-2);border:1px solid var(--line);border-radius:12px;color:var(--bone);padding:12px;font-size:12px;font-family:'IBM Plex Mono',monospace;resize:none;"></textarea>
    <div class="modal-actions">
      <button class="btn-secondary gold" id="gift-code-copy">Скопировать код</button>
    </div>
  </div>
</div>

<div class="transition-overlay" id="transition-overlay"></div>
<div class="toast" id="toast"></div>

<script src="https://cdn.jsdelivr.net/npm/three@0.158.0/build/three.min.js"></script>
<script>
(function(){
  // ---------- gift catalog ----------
  var GIFTS = [
    {id:'rose',    name:'Роза',            ico:'🌹', rarity:'common', weight:20,   sell:40,   desc:'Классика. Всегда в моде.'},
    {id:'bear',    name:'Мишка',           ico:'🧸', rarity:'common', weight:18,   sell:50,   desc:'Мягкий и надёжный.'},
    {id:'heart',   name:'Сердце',          ico:'❤️', rarity:'common', weight:17,   sell:45,   desc:'Простое, но приятное.'},
    {id:'donut',   name:'Пончик',          ico:'🍩', rarity:'common', weight:15,   sell:42,   desc:'Всегда поднимает настроение.'},
    {id:'balloon', name:'Шарик',           ico:'🎈', rarity:'common', weight:14,   sell:38,   desc:'Лёгкий и праздничный.'},
    {id:'bone',    name:'Кость',           ico:'🦴', rarity:'common', weight:13,   sell:35,   desc:'Для тех, кто понимает.'},
    {id:'cake',    name:'Торт',            ico:'🎂', rarity:'rare',   weight:16,   sell:130,  desc:'Праздник в любой момент.'},
    {id:'ring',    name:'Кольцо',          ico:'💍', rarity:'rare',   weight:14,   sell:150,  desc:'Блестит издалека.'},
    {id:'bolt',    name:'Молния',          ico:'⚡', rarity:'rare',   weight:12,   sell:140,  desc:'Быстрая и внезапная.'},
    {id:'joystick',name:'Джойстик',        ico:'🎮', rarity:'rare',   weight:10,   sell:160,  desc:'Для настоящих игроков.'},
    {id:'rocket',  name:'Ракета',          ico:'🚀', rarity:'epic',   weight:7,    sell:320,  desc:'Улетает по-настоящему высоко.'},
    {id:'hat',     name:'Цилиндр',         ico:'🎩', rarity:'epic',   weight:5.5,  sell:340,  desc:'Стиль решает всё.'},
    {id:'crown',   name:'Корона',          ico:'👑', rarity:'epic',   weight:4,    sell:400,  desc:'Почувствуй себя королём чата.'},
    {id:'snake',   name:'Змея',            ico:'🐍', rarity:'epic',   weight:4.5,  sell:360,  desc:'Тихая и опасная.'},
    {id:'crystal', name:'Шар судьбы',      ico:'🔮', rarity:'epic',   weight:3.5,  sell:380,  desc:'Знает, что будет дальше.'},
    {id:'anchor',  name:'Якорь',           ico:'⚓', rarity:'epic',   weight:4,    sell:370,  desc:'Держит крепко.'},
    {id:'cup',     name:'Золотой кубок',   ico:'🏆', rarity:'legend', weight:1.8,  sell:900,  desc:'Для лучших из лучших.'},
    {id:'diamond', name:'Бриллиант',       ico:'💎', rarity:'legend', weight:1.2,  sell:1100, desc:'Огранка ручной работы.'},
    {id:'eagle',   name:'Орёл',            ico:'🦅', rarity:'legend', weight:1.5,  sell:950,  desc:'Смотрит на всё свысока.'},
    {id:'amulet',  name:'Оберег',          ico:'🧿', rarity:'legend', weight:1,    sell:1050, desc:'Отводит беду.'},
    {id:'unicorn', name:'Единорог',        ico:'🦄', rarity:'legend', weight:1.3,  sell:1000, desc:'Редкий гость в этих краях.'},
    {id:'statue',  name:'MOGH',            ico:'🗿', rarity:'mythic', weight:0.5,  sell:3000, desc:'Одна из самых редких вещей в игре.'},
    {id:'cactus',  name:'Кактус',          ico:'🌵', rarity:'mythic', weight:0.3,  sell:3200, desc:'Свой 3D-горшок и анимация.'},
    {id:'demon',   name:'Демон',           ico:'👹', rarity:'mythic', weight:0.25, sell:3400, desc:'Появляется реже всех. Лучше не злить.'},
    {id:'phoenix', name:'Феникс',          ico:'🔥', rarity:'mythic', weight:0.22, sell:3600, desc:'Самый редкий и дорогой гифт в игре.'},
    {id:'pizza',      name:'Пицца',           ico:'🍕', rarity:'common', weight:16,  sell:44,   desc:'Кусок счастья с сыром.'},
    {id:'headphones', name:'Наушники',        ico:'🎧', rarity:'common', weight:14,  sell:48,   desc:'Свой звук в любой момент.'},
    {id:'sock',       name:'Носок',           ico:'🧦', rarity:'common', weight:15,  sell:36,   desc:'Тёплый и полосатый.'},
    {id:'lollipop',   name:'Леденец',         ico:'🍭', rarity:'rare',   weight:11,  sell:145,  desc:'Сладкая закрутка.'},
    {id:'sunglasses', name:'Очки',            ico:'🕶️', rarity:'rare',   weight:10,  sell:155,  desc:'Стиль без лишних слов.'},
    {id:'giftbox',    name:'Коробка',         ico:'🎁', rarity:'rare',   weight:9,   sell:165,  desc:'Внутри всегда сюрприз.'},
    {id:'butterfly',  name:'Бабочка',         ico:'🦋', rarity:'epic',   weight:4,   sell:350,  desc:'Лёгкая и почти невесомая.'},
    {id:'trident',    name:'Трезубец',        ico:'🔱', rarity:'epic',   weight:3.5, sell:390,  desc:'Оружие морского владыки.'},
    {id:'ufo',        name:'НЛО',             ico:'🛸', rarity:'legend', weight:1.1, sell:1080, desc:'Прилетело неизвестно откуда.'},
    {id:'dragon',     name:'Дракон',          ico:'🐉', rarity:'mythic', weight:0.2, sell:3700, desc:'Редчайшее существо в игре. Собственная 3D-модель.'}
  ];
  var RARITY_LABEL = {common:'COMMON', rare:'RARE', epic:'EPIC', legend:'LEGENDARY', mythic:'MYTHIC'};
  var STORE_KEY = 'tbfpumba_gift_battle_v3';
  var DAY_MS = 24*60*60*1000;
  var PROMO_CODES = { '6666209752': {cactus:1, statue:1, diamond:1} };
  var LOAN_OPTIONS = [{amount:200,days:6},{amount:300,days:8},{amount:400,days:10}];
  var BOOST_MS = 60*60*1000;
  var BOOSTS = [
    {id:'luck',          name:'Удача',                ico:'🍀', desc:'+60% к шансу редких и выше', priceStars:150, priceCoins:80},
    {id:'coinx2',        name:'Двойные монеты',        ico:'🪙', desc:'Монеты с рулетки х2', priceStars:150, priceCoins:80},
    {id:'xp2',           name:'Двойной опыт',          ico:'⭐', desc:'XP с рулетки х2', priceStars:120, priceCoins:60},
    {id:'shopdiscount',  name:'Скидка в магазине',     ico:'🏷️', desc:'-20% к ценам в магазине', priceStars:130, priceCoins:70},
    {id:'sellboost',     name:'Дороже продажа',        ico:'📈', desc:'+20% к цене продажи гифтов', priceStars:130, priceCoins:70},
    {id:'feefree',       name:'Без комиссии банка',    ico:'🛡️', desc:'Хранение гифтов бесплатно', priceStars:140, priceCoins:75},
    {id:'cheapspins',    name:'Дешёвые спины',         ico:'🎯', desc:'-20% к цене прокрутки рулетки', priceStars:160, priceCoins:85},
    {id:'freespin',      name:'Шанс на бесплатный спин', ico:'🎰', desc:'15% шанс, что спин ничего не стоит', priceStars:170, priceCoins:90},
    {id:'coindrop',      name:'Больше монет',          ico:'💰', desc:'Шанс дропа монет: 20% → 50%', priceStars:140, priceCoins:75},
    {id:'interestboost', name:'Двойные проценты банка', ico:'🏦', desc:'Проценты по хранению х2', priceStars:130, priceCoins:70}
  ];
  function boostById(id){ for (var i=0;i<BOOSTS.length;i++){ if (BOOSTS[i].id===id) return BOOSTS[i]; } return null; }
  function isBoostActive(id){ return !!(state.boosts && state.boosts[id] && state.boosts[id] > Date.now()); }

  var totalWeight = GIFTS.reduce(function(s,g){return s+g.weight;}, 0);
  function pickGift(){
    var luck = isBoostActive('luck');
    if (!luck){
      var r = Math.random()*totalWeight;
      for (var i=0;i<GIFTS.length;i++){ r -= GIFTS[i].weight; if (r<=0) return GIFTS[i]; }
      return GIFTS[GIFTS.length-1];
    }
    var weights = GIFTS.map(function(g){ return g.rarity === 'common' ? g.weight : g.weight*1.6; });
    var tw = weights.reduce(function(a,b){ return a+b; }, 0);
    var r2 = Math.random()*tw;
    for (var j=0;j<GIFTS.length;j++){ r2 -= weights[j]; if (r2<=0) return GIFTS[j]; }
    return GIFTS[GIFTS.length-1];
  }
  function byId(id){ for (var i=0;i<GIFTS.length;i++){ if (GIFTS[i].id===id) return GIFTS[i]; } return null; }
  function sellValue(g){ return isBoostActive('sellboost') ? Math.round(g.sell*1.2) : g.sell; }
  function buyPrice(g){ var p = Math.round(g.sell*2.5); return isBoostActive('shopdiscount') ? Math.round(p*0.8) : p; }
  function buyPriceCoin(g){ return Math.max(1, Math.round(buyPrice(g)/2)); }
  function coinSellPrice(g){ return Math.max(1, Math.round(sellValue(g)/10)); }

  // ---------- state ----------
  var state = loadState();
  function loadState(){
    try{
      var raw = localStorage.getItem(STORE_KEY);
      if (raw){
        var s = JSON.parse(raw);
        s.balance = (s.balance !== undefined) ? s.balance : 500;
        s.bankStars = s.bankStars || 0;
        s.coins = s.coins || 0;
        s.xp = s.xp || 0;
        s.inventory = s.inventory || {};
        s.bankGifts = s.bankGifts || [];
        s.redeemedCodes = s.redeemedCodes || [];
        s.loan = (s.loan !== undefined) ? s.loan : null;
        s.settings = s.settings || {accent:'blue', reduceMotion:false};
        s.boosts = s.boosts || {};
        s.tgProfile = s.tgProfile || null;
        s.redeemedGiftCodes = s.redeemedGiftCodes || [];
        s.myRefCode = s.myRefCode || null;
        s.referredBy = s.referredBy || null;
        return s;
      }
    }catch(e){}
    return {balance:500, bankStars:0, coins:0, xp:0, inventory:{}, bankGifts:[], redeemedCodes:[], loan:null, settings:{accent:'blue', reduceMotion:false}, boosts:{}, tgProfile:null, redeemedGiftCodes:[], myRefCode:null, referredBy:null};
  }
  function saveState(){ try{ localStorage.setItem(STORE_KEY, JSON.stringify(state)); }catch(e){} }

  function levelFromXp(xp){ return Math.floor(xp/150)+1; }
  function addXp(amt){
    var before = levelFromXp(state.xp);
    state.xp += amt;
    var after = levelFromXp(state.xp);
    if (after > before){ showToast('Новый уровень: ' + after + '!'); }
  }

  function chargeBankUpkeep(){
    var now = Date.now();
    var changed = false;
    state.bankGifts.forEach(function(entry){
      var g = byId(entry.id); if (!g) return;
      var days = Math.floor((now - entry.lastChargeAt)/DAY_MS);
      if (days > 0){
        var fee = isBoostActive('feefree') ? 0 : days*2;
        var interestRate = isBoostActive('interestboost') ? 0.06 : 0.03;
        var interest = Math.floor(g.sell*interestRate)*days;
        state.balance += (interest - fee);
        entry.lastChargeAt += days*DAY_MS;
        changed = true;
      }
    });
    if (state.loan && now >= state.loan.dueAt){
      state.balance -= state.loan.amount;
      showToast('Кредит на ' + state.loan.amount + ' ★ списан автоматически' + (state.balance < 0 ? ' — счёт ушёл в минус' : ''));
      state.loan = null;
      changed = true;
    }
    if (changed) saveState();
  }

  // ---------- dom refs ----------
  var balanceWrap = document.querySelector('.balance');
  var balanceEl = document.getElementById('balance-val');
  var coinsEl = document.getElementById('coins-val');
  var levelEl = document.getElementById('level-val');
  var xpFill = document.getElementById('xp-fill');
  var xpLabel = document.getElementById('xp-label');
  var invGrid = document.getElementById('inv-grid');
  var invEmpty = document.getElementById('inv-empty');
  var invCount = document.getElementById('inv-count');
  var toastEl = document.getElementById('toast');
  var spinButtons = document.querySelectorAll('.btn-primary[data-count]');

  function renderTop(){
    balanceEl.textContent = state.balance;
    coinsEl.textContent = state.coins;
    balanceWrap.classList.toggle('negative', state.balance < 0);
    var lvl = levelFromXp(state.xp);
    levelEl.textContent = lvl;
    var base = (lvl-1)*150, next = lvl*150;
    var pct = Math.min(100, Math.round(((state.xp-base)/(next-base))*100));
    xpFill.style.width = pct + '%';
    xpLabel.textContent = (state.xp-base) + ' / ' + (next-base) + ' XP до след. уровня';
    spinButtons.forEach(function(b){
      var count = parseInt(b.getAttribute('data-count'),10);
      var cost = spinCost(count);
      var avail = spinCurrency === 'stars' ? state.balance : state.coins;
      b.disabled = avail < cost || spinning;
    });
  }

  function renderInventory(){
    var ids = Object.keys(state.inventory).filter(function(k){ return state.inventory[k] > 0; });
    var total = ids.reduce(function(s,k){ return s + state.inventory[k]; }, 0);
    invCount.textContent = 'гифтов: ' + total;
    invGrid.innerHTML = '';
    var sellAllRow = document.getElementById('sell-all-row');
    var sellAllVal = document.getElementById('sell-all-val');
    if (ids.length === 0){
      invEmpty.style.display = 'block'; invGrid.style.display = 'none';
      sellAllRow.style.display = 'none';
    }
    else{
      invEmpty.style.display = 'none'; invGrid.style.display = 'grid';
      var sumSell = 0;
      ids.forEach(function(id){
        var g = byId(id); if (!g) return;
        sumSell += sellValue(g) * state.inventory[id];
        var card = document.createElement('div');
        card.className = 'gift-card rar-' + g.rarity;
        card.innerHTML = '<div class="count">x' + state.inventory[id] + '</div><div class="ico">' + g.ico + '</div><div class="name">' + g.name + '</div>';
        card.addEventListener('click', function(){ openModal(g); });
        invGrid.appendChild(card);
      });
      sellAllVal.textContent = sumSell;
      sellAllRow.style.display = 'block';
    }
  }

  document.getElementById('sell-all-btn').addEventListener('click', function(){
    var ids = Object.keys(state.inventory).filter(function(k){ return state.inventory[k] > 0; });
    if (ids.length === 0) return;
    var total = 0;
    ids.forEach(function(id){
      var g = byId(id); if (!g) return;
      total += sellValue(g) * state.inventory[id];
    });
    if (!window.confirm('Продать все гифты за ' + total + ' ★? Это нельзя отменить.')) return;
    ids.forEach(function(id){ state.inventory[id] = 0; });
    state.balance += total;
    saveState(); renderTop(); renderInventory();
    showToast('Продано всё за ' + total + ' ★');
  });

  function showToast(msg){
    toastEl.textContent = msg;
    toastEl.classList.add('show');
    clearTimeout(showToast._t);
    showToast._t = setTimeout(function(){ toastEl.classList.remove('show'); }, 2400);
  }

  // ---------- reel ----------
  var track = document.getElementById('reel-track');
  var viewport = track.parentElement;
  var reelFrame = document.querySelector('.reel-frame');
  var ITEM_W = window.innerWidth < 600 ? 110 : 140;
  window.addEventListener('resize', function(){ ITEM_W = window.innerWidth < 600 ? 110 : 140; });
  var spinning = false;
  var spinCurrency = 'stars';

  function spinCost(count){
    var base = spinCurrency === 'stars' ? count*100 : count*50;
    return isBoostActive('cheapspins') ? Math.round(base*0.8) : base;
  }
  function updateSpinButtonLabels(){
    spinButtons.forEach(function(b){
      var count = parseInt(b.getAttribute('data-count'),10);
      var cost = spinCost(count);
      b.textContent = '×' + count + ' · ' + cost + ' ' + (spinCurrency === 'stars' ? '★' : '🪙');
    });
  }
  document.querySelectorAll('.curr-btn').forEach(function(btn){
    btn.addEventListener('click', function(){
      spinCurrency = btn.getAttribute('data-currency');
      document.querySelectorAll('.curr-btn').forEach(function(b){ b.classList.toggle('active', b===btn); });
      updateSpinButtonLabels();
      renderTop();
    });
  });

  function renderReelItem(g){
    var el = document.createElement('div');
    el.className = 'reel-item rar-' + g.rarity;
    el.innerHTML = '<div class="ico">' + g.ico + '</div><div class="rn">' + g.name + '</div>';
    return el;
  }
  function fillTrackStatic(){
    track.innerHTML = '';
    track.style.transition = 'none';
    track.style.transform = 'translateX(0px)';
    for (var i=0;i<12;i++){ track.appendChild(renderReelItem(pickGift())); }
  }
  fillTrackStatic();

  function doSpin(count){
    if (spinning) return;
    var cost = spinCost(count);
    var isFreeSpin = isBoostActive('freespin') && Math.random() < 0.15;
    if (!isFreeSpin){
      if (spinCurrency === 'stars' && state.balance < cost){ showToast('Не хватает звёзд'); return; }
      if (spinCurrency === 'coins' && state.coins < cost){ showToast('Не хватает монет'); return; }
    }
    spinning = true;
    reelFrame.classList.add('spinning');
    spinButtons.forEach(function(b){ b.disabled = true; });

    if (!isFreeSpin){
      if (spinCurrency === 'stars'){ state.balance -= cost; } else { state.coins -= cost; }
    } else {
      showToast('🎰 Бесплатный спин!');
    }
    renderTop();

    var results = [];
    for (var i=0;i<count;i++){ results.push(pickGift()); }

    var ITEMS = 36;
    var landIndex = ITEMS - 6;
    var won = results[0];

    track.innerHTML = '';
    track.style.transition = 'none';
    track.style.transform = 'translateX(0px)';
    for (var j=0;j<ITEMS;j++){
      var g = (j === landIndex) ? won : pickGift();
      track.appendChild(renderReelItem(g));
    }
    void track.offsetWidth;

    var vpWidth = viewport.clientWidth;
    var jitter = (Math.random()-0.5)*ITEM_W*0.5;
    var target = -(landIndex*ITEM_W + ITEM_W/2 - vpWidth/2) + jitter;

    requestAnimationFrame(function(){
      track.style.transition = 'transform 4.4s cubic-bezier(0.1,0.68,0.15,1)';
      track.style.transform = 'translateX(' + target + 'px)';
    });

    setTimeout(function(){
      spinning = false;
      reelFrame.classList.remove('spinning');
      results.forEach(function(r){ state.inventory[r.id] = (state.inventory[r.id] || 0) + 1; });
      var coinsGained = 0;
      var coinChance = isBoostActive('coindrop') ? 0.5 : 0.2;
      for (var ci=0; ci<count; ci++){
        if (Math.random() < coinChance){
          var base = 1 + Math.floor(Math.random()*2);
          coinsGained += isBoostActive('coinx2') ? base*2 : base;
        }
      }
      if (coinsGained > 0){ state.coins += coinsGained; }
      addXp(10*count*(isBoostActive('xp2') ? 2 : 1));
      saveState();
      renderTop();
      renderInventory();
      if (coinsGained > 0){ showToast('+' + coinsGained + ' 🪙 монет'); }
      if (count === 1){ openModal(won, true); }
      else{ openBatchModal(results); }
    }, 4500);
  }
  spinButtons.forEach(function(btn){
    btn.addEventListener('click', function(){ doSpin(parseInt(btn.getAttribute('data-count'),10)); });
  });

  // ---------- single modal ----------
  var modal = document.getElementById('modal');
  var modalCard = document.getElementById('modal-card');
  var modalRar = document.getElementById('modal-rar');
  var modalIco = document.getElementById('modal-ico');
  var modalName = document.getElementById('modal-name');
  var modalDesc = document.getElementById('modal-desc');
  var modalSell = document.getElementById('modal-sell');
  var modalSellVal = document.getElementById('modal-sell-val');
  var modalSellCoin = document.getElementById('modal-sell-coin');
  var modalSellCoinVal = document.getElementById('modal-sell-coin-val');
  var modalKeep = document.getElementById('modal-keep');
  var modalGift = document.getElementById('modal-gift');
  var modalClose = document.getElementById('modal-close');
  var currentGift = null;

  function openModal(g, justWon){
    currentGift = g;
    modalCard.className = 'modal-card rar-' + g.rarity;
    modalRar.textContent = (justWon ? 'НОВЫЙ ГИФТ · ' : '') + RARITY_LABEL[g.rarity];
    modalIco.textContent = g.ico;
    modalName.textContent = g.name;
    modalDesc.textContent = g.desc;
    modalSellVal.textContent = sellValue(g);
    modalSellCoinVal.textContent = coinSellPrice(g);
    modal.classList.remove('hidden');
    requestAnimationFrame(function(){ modal.classList.add('visible'); });
    startSpecial(g.id);
  }
  function closeModal(){
    modal.classList.remove('visible');
    stopSpecial();
    setTimeout(function(){ modal.classList.add('hidden'); }, 200);
  }
  modalClose.addEventListener('click', closeModal);
  modalKeep.addEventListener('click', closeModal);
  modalGift.addEventListener('click', function(){
    if (!currentGift) return;
    var g = currentGift;
    closeModal();
    setTimeout(function(){ sendGiftCode(g); }, 210);
  });
  modal.addEventListener('click', function(e){ if (e.target === modal) closeModal(); });
  modalSell.addEventListener('click', function(){
    if (!currentGift) return;
    var id = currentGift.id;
    if (!state.inventory[id] || state.inventory[id] <= 0){ closeModal(); return; }
    state.inventory[id] -= 1;
    var val = sellValue(currentGift);
    state.balance += val;
    saveState(); renderTop(); renderInventory();
    showToast('Продано за ' + val + ' ★');
    closeModal();
  });
  modalSellCoin.addEventListener('click', function(){
    if (!currentGift) return;
    var id = currentGift.id;
    if (!state.inventory[id] || state.inventory[id] <= 0){ closeModal(); return; }
    var coinVal = coinSellPrice(currentGift);
    state.inventory[id] -= 1;
    state.coins += coinVal;
    saveState(); renderTop(); renderInventory();
    showToast('Продано за ' + coinVal + ' 🪙');
    closeModal();
  });

  // ---------- batch modal ----------
  var batchModal = document.getElementById('batch-modal');
  var batchGrid = document.getElementById('batch-grid');
  var batchSub = document.getElementById('batch-sub');
  var batchClose = document.getElementById('batch-close');
  var batchSell = document.getElementById('batch-sell');
  var batchSellVal = document.getElementById('batch-sell-val');
  var currentBatch = null;

  function openBatchModal(results){
    currentBatch = results;
    batchGrid.innerHTML = '';
    var total = 0;
    results.forEach(function(r, idx){
      total += sellValue(r);
      var el = document.createElement('div');
      el.className = 'batch-item rar-' + r.rarity;
      el.style.animationDelay = (idx*0.08) + 's';
      el.innerHTML = '<div class="ico">' + r.ico + '</div><div class="name">' + r.name + '</div>';
      batchGrid.appendChild(el);
    });
    batchSub.textContent = 'Выбито предметов: ' + results.length + ' · суммарная цена продажи: ' + total + ' ★';
    batchSellVal.textContent = total;
    batchModal.classList.remove('hidden');
    requestAnimationFrame(function(){ batchModal.classList.add('visible'); });
  }
  function closeBatchModal(){
    batchModal.classList.remove('visible');
    setTimeout(function(){ batchModal.classList.add('hidden'); }, 200);
  }
  batchClose.addEventListener('click', closeBatchModal);
  batchModal.addEventListener('click', function(e){ if (e.target === batchModal) closeBatchModal(); });
  batchSell.addEventListener('click', function(){
    if (!currentBatch) { closeBatchModal(); return; }
    var total = 0;
    currentBatch.forEach(function(r){
      var have = state.inventory[r.id] || 0;
      if (have <= 0) return;
      state.inventory[r.id] = have - 1;
      total += sellValue(r);
    });
    state.balance += total;
    saveState(); renderTop(); renderInventory();
    showToast('Продано за ' + total + ' ★');
    closeBatchModal();
  });

  // ---------- 3D models for every gift ----------
  var specialCanvas = document.getElementById('special-canvas');
  var specialRenderer = new THREE.WebGLRenderer({canvas:specialCanvas, antialias:true, alpha:true});
  specialRenderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));
  specialRenderer.toneMapping = THREE.ACESFilmicToneMapping;
  specialRenderer.toneMappingExposure = 1.15;
  if (THREE.SRGBColorSpace) specialRenderer.outputColorSpace = THREE.SRGBColorSpace;
  var specialScene = new THREE.Scene();
  var specialCamera = new THREE.PerspectiveCamera(38, 1, 0.1, 30);
  specialCamera.position.set(0, 0.55, 6.4);

  function mkMat(color, opts){
    opts = opts || {};
    return new THREE.MeshPhysicalMaterial(Object.assign({
      color:color, metalness:0.5, roughness:0.32,
      clearcoat:0.65, clearcoatRoughness:0.22, reflectivity:0.6
    }, opts));
  }

  // -- bespoke: statue (MOGH)
  function buildStatueGroup(){
    var group = new THREE.Group();
    var goldMat = mkMat(0xe0b020, {metalness:1, roughness:0.28});
    var darkMat = mkMat(0x1a2338, {metalness:0.6, roughness:0.5});
    var pedestal = new THREE.Mesh(new THREE.CylinderGeometry(1.1, 1.3, 0.5, 24), darkMat);
    pedestal.position.y = -1.5; group.add(pedestal);
    var pedestalTop = new THREE.Mesh(new THREE.CylinderGeometry(0.9, 0.9, 0.12, 24), goldMat);
    pedestalTop.position.y = -1.22; group.add(pedestalTop);
    var torso = new THREE.Mesh(new THREE.ConeGeometry(0.75, 1.5, 20), goldMat);
    torso.position.y = -0.4; group.add(torso);
    var neck = new THREE.Mesh(new THREE.CylinderGeometry(0.22, 0.28, 0.3, 16), goldMat);
    neck.position.y = 0.5; group.add(neck);
    var head = new THREE.Mesh(new THREE.SphereGeometry(0.42, 24, 24), goldMat);
    head.position.y = 0.95; group.add(head);
    var ring = new THREE.Mesh(new THREE.TorusGeometry(1.15, 0.03, 8, 40), goldMat);
    ring.rotation.x = Math.PI/2; ring.position.y = -1.2; group.add(ring);
    return group;
  }

  // -- bespoke: cactus
  function buildCactusGroup(){
    var group = new THREE.Group();
    var greenMat = mkMat(0x3f8f4a, {roughness:0.55, flatShading:true});
    var greenMatDark = mkMat(0x2e6b38, {roughness:0.55, flatShading:true});
    var potMat = mkMat(0xb05a2c, {roughness:0.7});
    var flowerMat = mkMat(0xd1507a, {emissive:0x3a0f1e, roughness:0.4});
    var pot = new THREE.Mesh(new THREE.CylinderGeometry(0.5, 0.65, 0.55, 12), potMat);
    pot.position.y = -1.35; group.add(pot);
    var potRim = new THREE.Mesh(new THREE.TorusGeometry(0.5, 0.05, 8, 20), mkMat(0x8a3f1c, {roughness:0.6}));
    potRim.rotation.x = Math.PI/2; potRim.position.y = -1.08; group.add(potRim);
    var body = new THREE.Mesh(new THREE.CylinderGeometry(0.32, 0.42, 1.6, 10), greenMat);
    body.position.y = -0.25; group.add(body);
    var topCap = new THREE.Mesh(new THREE.SphereGeometry(0.32, 10, 10), greenMat);
    topCap.position.y = 0.55; group.add(topCap);
    function arm(x, rotZ){
      var g = new THREE.Group();
      var seg = new THREE.Mesh(new THREE.CylinderGeometry(0.13, 0.16, 0.7, 8), greenMatDark);
      seg.position.set(0, 0.35, 0); g.add(seg);
      var cap = new THREE.Mesh(new THREE.SphereGeometry(0.13, 8, 8), greenMatDark);
      cap.position.set(0, 0.7, 0); g.add(cap);
      g.position.set(x, -0.1, 0); g.rotation.z = rotZ;
      return g;
    }
    group.add(arm(-0.45, Math.PI*0.18));
    group.add(arm(0.45, -Math.PI*0.18));
    var flower = new THREE.Mesh(new THREE.SphereGeometry(0.12, 10, 10), flowerMat);
    flower.position.y = 0.92; group.add(flower);
    return group;
  }

  // -- bespoke: demon
  function buildDemonGroup(){
    var group = new THREE.Group();
    var skinMat = mkMat(0x8a1230, {roughness:0.5});
    var hornMat = mkMat(0x14181f, {roughness:0.4});
    var baseMat = mkMat(0x12101c, {roughness:0.6});
    var eyeMat = mkMat(0xff2a2a, {emissive:0xff2a2a, emissiveIntensity:1});
    var pedestal = new THREE.Mesh(new THREE.CylinderGeometry(0.9, 1.05, 0.35, 20), baseMat);
    pedestal.position.y = -1.4; group.add(pedestal);
    var torso = new THREE.Mesh(new THREE.ConeGeometry(0.55, 1.3, 16), skinMat);
    torso.position.y = -0.4; group.add(torso);
    var head = new THREE.Mesh(new THREE.SphereGeometry(0.36, 20, 20), skinMat);
    head.position.y = 0.55; group.add(head);
    function horn(x){
      var h = new THREE.Mesh(new THREE.ConeGeometry(0.08, 0.4, 8), hornMat);
      h.position.set(x, 0.85, 0.05);
      h.rotation.z = x > 0 ? -0.5 : 0.5;
      return h;
    }
    group.add(horn(-0.18), horn(0.18));
    function eye(x){
      var e = new THREE.Mesh(new THREE.SphereGeometry(0.05, 8, 8), eyeMat);
      e.position.set(x, 0.58, 0.32);
      return e;
    }
    group.add(eye(-0.13), eye(0.13));
    var tail = new THREE.Mesh(new THREE.ConeGeometry(0.1, 0.55, 8), skinMat);
    tail.position.set(0, -1.05, -0.35);
    tail.rotation.x = Math.PI*0.35;
    group.add(tail);
    return group;
  }

  // -- bespoke: phoenix
  var phoenixBodyMat = mkMat(0xff6a1a, {emissive:0xff3d00, emissiveIntensity:0.4, roughness:0.4});
  function buildPhoenixGroup(){
    var group = new THREE.Group();
    var headMat = mkMat(0xffb347, {emissive:0xff8a1a, emissiveIntensity:0.3});
    var wingMat = mkMat(0xff3d1a, {emissive:0xcc2400, emissiveIntensity:0.35, roughness:0.5});
    var tailMat = mkMat(0xffcf4d, {emissive:0xff9500, emissiveIntensity:0.4});
    var body = new THREE.Mesh(new THREE.SphereGeometry(0.4, 16, 16), phoenixBodyMat);
    body.scale.set(0.7, 1, 1.3);
    group.add(body);
    var head = new THREE.Mesh(new THREE.SphereGeometry(0.22, 14, 14), headMat);
    head.position.set(0, 0.6, 0.25); group.add(head);
    var beak = new THREE.Mesh(new THREE.ConeGeometry(0.07, 0.22, 8), mkMat(0xffd27a));
    beak.position.set(0, 0.58, 0.5);
    beak.rotation.x = Math.PI/2; group.add(beak);
    function wing(x, rotZ){
      var w = new THREE.Mesh(new THREE.BoxGeometry(0.85, 0.1, 0.5), wingMat);
      w.position.set(x, 0.05, -0.05);
      w.rotation.z = rotZ; w.rotation.y = 0.15*(x>0?1:-1);
      return w;
    }
    group.add(wing(0.6, -0.5), wing(-0.6, 0.5));
    function tailF(rot){
      var t = new THREE.Mesh(new THREE.ConeGeometry(0.06, 0.75, 6), tailMat);
      t.position.set(0, -0.35, -0.55);
      t.rotation.x = Math.PI*0.55 + rot;
      return t;
    }
    group.add(tailF(-0.18), tailF(0), tailF(0.18));
    return group;
  }

  // -- dedicated builders: each gift gets its own recognizable shape
  function pedestal(){
    return new THREE.Mesh(new THREE.CylinderGeometry(0.55,0.68,0.22,24), mkMat(0x0f1830,{metalness:0.5, roughness:0.55}));
  }
  function addBase(group, y){
    var p = pedestal(); p.position.y = (y!==undefined? y : -1.3); group.add(p); return group;
  }

  function buildRose(){
    var g = new THREE.Group();
    var stemMat = mkMat(0x2f8f4a, {roughness:0.5});
    var petalMat = mkMat(0xc23a5e, {roughness:0.4});
    var stem = new THREE.Mesh(new THREE.CylinderGeometry(0.05,0.06,1.5,10), stemMat);
    stem.position.y = -0.55; g.add(stem);
    for (var i=0;i<2;i++){
      var leaf = new THREE.Mesh(new THREE.SphereGeometry(0.16,10,8), stemMat);
      leaf.scale.set(1,0.3,1.7);
      leaf.position.set(i===0?-0.18:0.18, -0.7, 0);
      leaf.rotation.z = i===0? 0.6 : -0.6;
      g.add(leaf);
    }
    var bud = new THREE.Mesh(new THREE.SphereGeometry(0.32,14,14), petalMat);
    bud.scale.set(1,1.2,1); bud.position.y = 0.55; g.add(bud);
    for (var p=0;p<5;p++){
      var petal = new THREE.Mesh(new THREE.SphereGeometry(0.22,10,10), petalMat);
      var ang = (p/5)*Math.PI*2;
      petal.scale.set(0.5,0.8,0.9);
      petal.position.set(Math.cos(ang)*0.2, 0.5+Math.sin(ang*2)*0.06, Math.sin(ang)*0.2);
      petal.rotation.y = ang;
      g.add(petal);
    }
    return addBase(g, -1.35);
  }

  function buildBear(){
    var g = new THREE.Group();
    var m = mkMat(0x8a5a3a, {roughness:0.6});
    var mLight = mkMat(0xd9b48f, {roughness:0.6});
    var body = new THREE.Mesh(new THREE.SphereGeometry(0.55,18,18), m); body.position.y=-0.35; g.add(body);
    var head = new THREE.Mesh(new THREE.SphereGeometry(0.4,18,18), m); head.position.y=0.5; g.add(head);
    var snout = new THREE.Mesh(new THREE.SphereGeometry(0.16,12,12), mLight); snout.position.set(0,0.42,0.34); g.add(snout);
    var nose = new THREE.Mesh(new THREE.SphereGeometry(0.05,8,8), mkMat(0x1a120c)); nose.position.set(0,0.46,0.48); g.add(nose);
    [-0.28,0.28].forEach(function(x){
      var ear = new THREE.Mesh(new THREE.SphereGeometry(0.14,10,10), m);
      ear.position.set(x,0.85,0.05); g.add(ear);
      var arm = new THREE.Mesh(new THREE.SphereGeometry(0.18,10,10), m);
      arm.position.set(x*1.8,-0.25,0.1); g.add(arm);
      var leg = new THREE.Mesh(new THREE.SphereGeometry(0.2,10,10), m);
      leg.position.set(x*0.9,-0.85,0.05); g.add(leg);
    });
    return addBase(g, -1.35);
  }

  function buildHeart(){
    var g = new THREE.Group();
    var m = mkMat(0xc11f3d, {roughness:0.35, emissive:0x4a0a14, emissiveIntensity:0.25});
    [-0.22,0.22].forEach(function(x){
      var lobe = new THREE.Mesh(new THREE.SphereGeometry(0.34,16,16), m);
      lobe.position.set(x,0.25,0); g.add(lobe);
    });
    var bottom = new THREE.Mesh(new THREE.ConeGeometry(0.42,0.8,16), m);
    bottom.rotation.x = Math.PI; bottom.position.set(0,-0.25,0); g.add(bottom);
    return addBase(g, -1.25);
  }

  function buildDonut(){
    var g = new THREE.Group();
    var base = new THREE.Mesh(new THREE.TorusGeometry(0.55,0.28,16,32), mkMat(0xd9a066,{roughness:0.6}));
    g.add(base);
    var glaze = new THREE.Mesh(new THREE.TorusGeometry(0.55,0.3,16,32,Math.PI*1.6), mkMat(0xff8fc0,{roughness:0.35}));
    glaze.position.z = 0.06; g.add(glaze);
    for (var i=0;i<10;i++){
      var spr = new THREE.Mesh(new THREE.BoxGeometry(0.06,0.02,0.02), mkMat([0xffe38a,0x8affc4,0x8ac4ff][i%3]));
      var a = Math.random()*Math.PI*2, r = 0.35+Math.random()*0.4;
      spr.position.set(Math.cos(a)*r, Math.sin(a)*r, 0.12);
      spr.rotation.z = Math.random()*Math.PI;
      g.add(spr);
    }
    return addBase(g, -1.15);
  }

  function buildBalloon(){
    var g = new THREE.Group();
    var m = mkMat(0xe23b3b, {roughness:0.3, metalness:0.1});
    var body = new THREE.Mesh(new THREE.SphereGeometry(0.55,20,20), m);
    body.scale.set(0.9,1.15,0.9); body.position.y = 0.5; g.add(body);
    var knot = new THREE.Mesh(new THREE.ConeGeometry(0.08,0.14,8), m);
    knot.position.y = -0.15; knot.rotation.x = Math.PI; g.add(knot);
    var pts = [];
    for (var i=0;i<8;i++){ pts.push(new THREE.Vector3(Math.sin(i*0.7)*0.05, -0.25-i*0.13, 0)); }
    var curve = new THREE.CatmullRomCurve3(pts);
    var tube = new THREE.Mesh(new THREE.TubeGeometry(curve,20,0.02,6,false), mkMat(0xeaf1fb));
    g.add(tube);
    return addBase(g, -1.55);
  }

  function buildBone(){
    var g = new THREE.Group();
    var m = mkMat(0xf2ead9, {roughness:0.5});
    var shaft = new THREE.Mesh(new THREE.CylinderGeometry(0.14,0.14,1.3,12), m);
    shaft.rotation.z = Math.PI/2; g.add(shaft);
    [-0.65,0.65].forEach(function(x){
      [-0.14,0.14].forEach(function(y){
        var knob = new THREE.Mesh(new THREE.SphereGeometry(0.2,12,12), m);
        knob.position.set(x,y,0); g.add(knob);
      });
    });
    return addBase(g, -0.85);
  }

  function buildCake(){
    var g = new THREE.Group();
    var creamMat = mkMat(0xf7e2c0, {roughness:0.5});
    var pinkMat = mkMat(0xff8fc0, {roughness:0.4});
    var tier1 = new THREE.Mesh(new THREE.CylinderGeometry(0.6,0.65,0.55,24), creamMat);
    tier1.position.y = -0.7; g.add(tier1);
    var drip1 = new THREE.Mesh(new THREE.TorusGeometry(0.6,0.06,8,24), pinkMat);
    drip1.rotation.x = Math.PI/2; drip1.position.y = -0.42; g.add(drip1);
    var tier2 = new THREE.Mesh(new THREE.CylinderGeometry(0.42,0.46,0.5,24), creamMat);
    tier2.position.y = -0.05; g.add(tier2);
    var drip2 = new THREE.Mesh(new THREE.TorusGeometry(0.42,0.05,8,24), pinkMat);
    drip2.rotation.x = Math.PI/2; drip2.position.y = 0.2; g.add(drip2);
    var candle = new THREE.Mesh(new THREE.CylinderGeometry(0.05,0.05,0.4,8), mkMat(0x5fd4ff));
    candle.position.y = 0.45; g.add(candle);
    var flame = new THREE.Mesh(new THREE.ConeGeometry(0.07,0.18,8), mkMat(0xffb347,{emissive:0xff8a1a, emissiveIntensity:0.8}));
    flame.position.y = 0.72; g.add(flame);
    return addBase(g, -1.35);
  }

  function buildRing(){
    var g = new THREE.Group();
    var band = new THREE.Mesh(new THREE.TorusGeometry(0.5,0.09,14,32), mkMat(0xdba514,{metalness:0.85, roughness:0.25}));
    g.add(band);
    var gem = new THREE.Mesh(new THREE.OctahedronGeometry(0.28,0), mkMat(0xbfe9ff,{metalness:0.3, roughness:0.1, emissive:0xbfe9ff, emissiveIntensity:0.25}));
    gem.position.y = 0.42; g.add(gem);
    [-0.14,0.14].forEach(function(x){
      var prong = new THREE.Mesh(new THREE.ConeGeometry(0.04,0.18,6), mkMat(0xdba514,{metalness:0.85}));
      prong.position.set(x,0.3,0); g.add(prong);
    });
    return addBase(g, -0.75);
  }

  function buildBolt(){
    var g = new THREE.Group();
    var m = mkMat(0xf2d200, {emissive:0xf2d200, emissiveIntensity:0.5, roughness:0.3});
    var seg1 = new THREE.Mesh(new THREE.BoxGeometry(0.22,0.85,0.1), m);
    seg1.position.set(0.1,0.5,0); seg1.rotation.z = -0.35; g.add(seg1);
    var seg2 = new THREE.Mesh(new THREE.BoxGeometry(0.22,0.6,0.1), m);
    seg2.position.set(-0.12,0,0); seg2.rotation.z = 0.5; g.add(seg2);
    var seg3 = new THREE.Mesh(new THREE.BoxGeometry(0.2,0.8,0.1), m);
    seg3.position.set(0.02,-0.55,0); seg3.rotation.z = -0.35; g.add(seg3);
    return addBase(g, -1.3);
  }

  function buildJoystick(){
    var g = new THREE.Group();
    var baseMat = mkMat(0x2e3648, {roughness:0.5});
    var base = new THREE.Mesh(new THREE.CylinderGeometry(0.55,0.6,0.28,20), baseMat);
    base.position.y = -0.55; g.add(base);
    var stick = new THREE.Mesh(new THREE.CylinderGeometry(0.06,0.07,0.75,10), mkMat(0x556077));
    stick.position.y = -0.05; g.add(stick);
    var knob = new THREE.Mesh(new THREE.SphereGeometry(0.16,14,14), mkMat(0xff4d4d,{emissive:0xff4d4d, emissiveIntensity:0.3}));
    knob.position.y = 0.38; g.add(knob);
    [[-0.25,-0.42],[0.05,-0.5]].forEach(function(p){
      var btn = new THREE.Mesh(new THREE.CylinderGeometry(0.08,0.08,0.06,12), mkMat(0xffd166));
      btn.position.set(p[0],-0.32,p[1]); g.add(btn);
    });
    return addBase(g, -1.05);
  }

  function buildRocket(){
    var g = new THREE.Group();
    var body = new THREE.Mesh(new THREE.CylinderGeometry(0.28,0.28,1.2,16), mkMat(0xc7d1dc,{metalness:0.6, roughness:0.3}));
    g.add(body);
    var nose = new THREE.Mesh(new THREE.ConeGeometry(0.28,0.6,16), mkMat(0xff4d4d,{roughness:0.35}));
    nose.position.y = 0.9; g.add(nose);
    var window = new THREE.Mesh(new THREE.SphereGeometry(0.13,14,14), mkMat(0x5fd4ff,{emissive:0x5fd4ff, emissiveIntensity:0.4}));
    window.position.set(0,0.15,0.26); g.add(window);
    [0,120,240].forEach(function(deg){
      var fin = new THREE.Mesh(new THREE.ConeGeometry(0.22,0.5,4), mkMat(0xff4d4d));
      var rad = deg*Math.PI/180;
      fin.position.set(Math.cos(rad)*0.32,-0.65,Math.sin(rad)*0.32);
      fin.rotation.x = Math.PI/2.4; fin.rotation.z = rad;
      g.add(fin);
    });
    var flame = new THREE.Mesh(new THREE.ConeGeometry(0.2,0.5,12), mkMat(0xffb347,{emissive:0xff6a1a, emissiveIntensity:0.7}));
    flame.rotation.x = Math.PI; flame.position.y = -1; g.add(flame);
    return addBase(g, -1.35);
  }

  function buildHat(){
    var g = new THREE.Group();
    var m = mkMat(0x14181f, {roughness:0.4});
    var brim = new THREE.Mesh(new THREE.CylinderGeometry(0.7,0.7,0.08,28), m);
    brim.position.y = -0.55; g.add(brim);
    var crown = new THREE.Mesh(new THREE.CylinderGeometry(0.42,0.46,1.05,28), m);
    crown.position.y = 0.02; g.add(crown);
    var band = new THREE.Mesh(new THREE.TorusGeometry(0.43,0.06,10,28), mkMat(0xdba514,{metalness:0.8}));
    band.rotation.x = Math.PI/2; band.position.y = -0.45; g.add(band);
    return addBase(g, -0.78);
  }

  function buildCrown(){
    var g = new THREE.Group();
    var m = mkMat(0xf2b84b, {metalness:0.9, roughness:0.25});
    var base = new THREE.Mesh(new THREE.CylinderGeometry(0.55,0.6,0.35,20), m);
    g.add(base);
    for (var i=0;i<5;i++){
      var a = (i/5)*Math.PI*2;
      var spike = new THREE.Mesh(new THREE.ConeGeometry(0.14,0.5,10), m);
      spike.position.set(Math.cos(a)*0.45,0.4,Math.sin(a)*0.45); g.add(spike);
      var gem = new THREE.Mesh(new THREE.SphereGeometry(0.06,8,8), mkMat(0x9be8ff,{emissive:0x9be8ff, emissiveIntensity:0.5}));
      gem.position.set(Math.cos(a)*0.45,0.68,Math.sin(a)*0.45); g.add(gem);
    }
    return addBase(g, -0.6);
  }

  function buildSnake(){
    var g = new THREE.Group();
    var m = mkMat(0x2f8f4a, {roughness:0.4});
    var segCount = 9;
    for (var i=0;i<segCount;i++){
      var t = i/(segCount-1);
      var s = new THREE.Mesh(new THREE.SphereGeometry(0.24*(1-t*0.55),10,10), m);
      s.position.set(Math.sin(t*Math.PI*1.6)*0.55, -0.7+t*1.3, Math.cos(t*Math.PI*1.6)*0.2);
      g.add(s);
    }
    var head = new THREE.Mesh(new THREE.ConeGeometry(0.13,0.3,10), mkMat(0x1c5c30));
    head.position.set(Math.sin(1.6*Math.PI*1.6)*0.55,0.62,Math.cos(1.6*Math.PI*1.6)*0.2);
    g.add(head);
    return addBase(g, -1.15);
  }

  function buildCrystal(){
    var g = new THREE.Group();
    var ball = new THREE.Mesh(new THREE.SphereGeometry(0.5,24,24), mkMat(0x7c4fd1,{transparent:true, opacity:0.55, roughness:0.1, metalness:0.1, emissive:0xd7b8ff, emissiveIntensity:0.3}));
    ball.position.y = 0.15; g.add(ball);
    var innerGlow = new THREE.Mesh(new THREE.SphereGeometry(0.2,14,14), mkMat(0xd7b8ff,{emissive:0xd7b8ff, emissiveIntensity:0.8}));
    innerGlow.position.y = 0.15; g.add(innerGlow);
    var stand = new THREE.Mesh(new THREE.CylinderGeometry(0.1,0.35,0.35,16), mkMat(0x2a1f4a,{metalness:0.6}));
    stand.position.y = -0.55; g.add(stand);
    var ring = new THREE.Mesh(new THREE.TorusGeometry(0.32,0.04,8,24), mkMat(0xdba514,{metalness:0.8}));
    ring.rotation.x = Math.PI/2; ring.position.y = -0.4; g.add(ring);
    return addBase(g, -1.05);
  }

  function buildAnchor(){
    var g = new THREE.Group();
    var m = mkMat(0x8fa3bf, {metalness:0.75, roughness:0.3});
    var ring = new THREE.Mesh(new THREE.TorusGeometry(0.2,0.06,10,20), m);
    ring.position.y = 0.85; g.add(ring);
    var shaft = new THREE.Mesh(new THREE.CylinderGeometry(0.07,0.07,1.3,10), m);
    shaft.position.y = 0.15; g.add(shaft);
    var bar = new THREE.Mesh(new THREE.BoxGeometry(0.6,0.08,0.08), m);
    bar.position.y = 0.55; g.add(bar);
    [-1,1].forEach(function(dir){
      var fluke = new THREE.Mesh(new THREE.TorusGeometry(0.32,0.06,8,16,Math.PI*0.6), m);
      fluke.position.set(dir*0.2,-0.55,0);
      fluke.rotation.z = dir>0? -0.4 : Math.PI+0.4;
      g.add(fluke);
    });
    return addBase(g, -1.35);
  }

  function buildCup(){
    var g = new THREE.Group();
    var m = mkMat(0xe0b020, {metalness:0.9, roughness:0.25});
    var bowl = new THREE.Mesh(new THREE.SphereGeometry(0.4,18,18,0,Math.PI*2,0,Math.PI/1.6), m);
    bowl.position.y = 0.35; g.add(bowl);
    var rim = new THREE.Mesh(new THREE.TorusGeometry(0.4,0.03,8,24), m);
    rim.rotation.x = Math.PI/2; rim.position.y = 0.62; g.add(rim);
    var stem = new THREE.Mesh(new THREE.CylinderGeometry(0.06,0.1,0.55,12), m);
    stem.position.y = -0.15; g.add(stem);
    var base = new THREE.Mesh(new THREE.CylinderGeometry(0.35,0.4,0.15,20), m);
    base.position.y = -0.48; g.add(base);
    [-1,1].forEach(function(dir){
      var handle = new THREE.Mesh(new THREE.TorusGeometry(0.18,0.035,8,16,Math.PI*1.3), m);
      handle.position.set(dir*0.42,0.3,0);
      handle.rotation.y = Math.PI/2; handle.rotation.z = dir>0? 0.3:-0.3+Math.PI;
      g.add(handle);
    });
    return addBase(g, -0.7);
  }

  function buildDiamond(){
    var g = new THREE.Group();
    var m = mkMat(0xbfe9ff, {metalness:0.2, roughness:0.05, emissive:0xbfe9ff, emissiveIntensity:0.25});
    var top = new THREE.Mesh(new THREE.OctahedronGeometry(0.55,0), m);
    top.scale.set(1,0.55,1); top.position.y = 0.25; g.add(top);
    var bottom = new THREE.Mesh(new THREE.OctahedronGeometry(0.55,0), m);
    bottom.scale.set(1,0.9,1); bottom.position.y = -0.3; g.add(bottom);
    return addBase(g, -1.1);
  }

  function buildEagle(){
    var g = new THREE.Group();
    var bodyMat = mkMat(0x6b4a2f, {roughness:0.55});
    var headMat = mkMat(0xf5f5f0, {roughness:0.4});
    var body = new THREE.Mesh(new THREE.SphereGeometry(0.4,16,16), bodyMat);
    body.scale.set(0.8,1.2,0.9); g.add(body);
    var head = new THREE.Mesh(new THREE.SphereGeometry(0.2,14,14), headMat);
    head.position.y = 0.62; g.add(head);
    var beak = new THREE.Mesh(new THREE.ConeGeometry(0.07,0.22,8), mkMat(0xf2b84b));
    beak.rotation.x = Math.PI/2; beak.position.set(0,0.6,0.24); g.add(beak);
    [-1,1].forEach(function(dir){
      var wing = new THREE.Mesh(new THREE.BoxGeometry(0.85,0.08,0.4), bodyMat);
      wing.position.set(dir*0.55,0.1,-0.05);
      wing.rotation.z = dir*0.5; wing.rotation.y = -dir*0.2;
      g.add(wing);
    });
    var tail = new THREE.Mesh(new THREE.ConeGeometry(0.2,0.5,10), bodyMat);
    tail.rotation.x = Math.PI*0.55; tail.position.set(0,-0.5,-0.35); g.add(tail);
    return addBase(g, -1.15);
  }

  function buildAmulet(){
    var g = new THREE.Group();
    var band = new THREE.Mesh(new THREE.TorusGeometry(0.42,0.1,14,28), mkMat(0x1e4d8f,{metalness:0.6, roughness:0.3}));
    g.add(band);
    var gem = new THREE.Mesh(new THREE.SphereGeometry(0.22,16,16), mkMat(0x5fd4ff,{emissive:0x5fd4ff, emissiveIntensity:0.5}));
    g.add(gem);
    var bail = new THREE.Mesh(new THREE.TorusGeometry(0.13,0.035,8,16), mkMat(0xdba514,{metalness:0.8}));
    bail.position.y = 0.62; g.add(bail);
    return addBase(g, -0.75);
  }

  function buildUnicorn(){
    var g = new THREE.Group();
    var m = mkMat(0xffffff, {roughness:0.4});
    var body = new THREE.Mesh(new THREE.CylinderGeometry(0.28,0.32,1,12), m);
    body.rotation.z = Math.PI/2; body.position.y = 0.05; g.add(body);
    var neck = new THREE.Mesh(new THREE.CylinderGeometry(0.16,0.2,0.55,10), m);
    neck.position.set(0.5,0.4,0); neck.rotation.z = -0.5; g.add(neck);
    var head = new THREE.Mesh(new THREE.SphereGeometry(0.2,14,14), m);
    head.position.set(0.78,0.68,0); g.add(head);
    var horn = new THREE.Mesh(new THREE.ConeGeometry(0.05,0.4,8), mkMat(0xf2b84b,{metalness:0.7, emissive:0xf2b84b, emissiveIntensity:0.3}));
    horn.position.set(0.85,0.95,0); horn.rotation.z = -0.3; g.add(horn);
    for (var m1=0;m1<5;m1++){
      var mane = new THREE.Mesh(new THREE.ConeGeometry(0.06,0.22,6), mkMat(0xff8fc0));
      mane.position.set(0.6-m1*0.13,0.6-m1*0.02,0.02);
      mane.rotation.z = 1.3; g.add(mane);
    }
    [[-0.4,-0.55],[0,-0.55],[0.4,-0.55]].forEach(function(p){
      var leg = new THREE.Mesh(new THREE.CylinderGeometry(0.06,0.06,0.5,8), m);
      leg.position.set(p[0],p[1],0); g.add(leg);
    });
    var tail = new THREE.Mesh(new THREE.ConeGeometry(0.1,0.5,8), mkMat(0xff8fc0));
    tail.position.set(-0.55,-0.05,0); tail.rotation.z = Math.PI*0.6; g.add(tail);
    return addBase(g, -1.05);
  }

  function buildPizza(){
    var g = new THREE.Group();
    var doughMat = mkMat(0xe8b661, {roughness:0.6});
    var cheeseMat = mkMat(0xffcf5c, {roughness:0.5, emissive:0x8a5a1a, emissiveIntensity:0.1});
    var slice = new THREE.Mesh(new THREE.CylinderGeometry(0.85,0.85,0.16,24,1,false,0,Math.PI/3.2), cheeseMat);
    slice.rotation.x = Math.PI/2; slice.rotation.z = -Math.PI/6.4; g.add(slice);
    var crust = new THREE.Mesh(new THREE.TorusGeometry(0.85,0.09,10,24,Math.PI/3.2), doughMat);
    crust.rotation.x = Math.PI/2; crust.rotation.z = -Math.PI/6.4; crust.position.y = 0.02; g.add(crust);
    var toppingColors = [0xc11f3d, 0x8a1230, 0x3f8f4a];
    for (var i=0;i<6;i++){
      var top = new THREE.Mesh(new THREE.SphereGeometry(0.09,10,10), mkMat(toppingColors[i%3]));
      var ang = (Math.random()-0.5)*0.9;
      var r = 0.25+Math.random()*0.45;
      top.position.set(Math.cos(ang)*r*0.9, 0.12, Math.sin(ang)*r);
      g.add(top);
    }
    return addBase(g, -0.55);
  }

  function buildHeadphones(){
    var g = new THREE.Group();
    var m = mkMat(0x2e3648, {roughness:0.4});
    var accent = mkMat(0x3b82f6, {emissive:0x3b82f6, emissiveIntensity:0.3});
    var band = new THREE.Mesh(new THREE.TorusGeometry(0.55,0.07,10,24,Math.PI), m);
    band.rotation.z = Math.PI; g.add(band);
    [-0.55,0.55].forEach(function(x){
      var cup = new THREE.Mesh(new THREE.CylinderGeometry(0.24,0.24,0.22,20), m);
      cup.rotation.z = Math.PI/2; cup.position.set(x,-0.05,0); g.add(cup);
      var pad = new THREE.Mesh(new THREE.TorusGeometry(0.2,0.04,8,20), accent);
      pad.rotation.y = Math.PI/2; pad.position.set(x + (x>0?0.11:-0.11),-0.05,0); g.add(pad);
    });
    return addBase(g, -0.85);
  }

  function buildSock(){
    var g = new THREE.Group();
    var m = mkMat(0xeaf1fb, {roughness:0.6});
    var stripeMat = mkMat(0x3b82f6, {roughness:0.5});
    var leg = new THREE.Mesh(new THREE.CylinderGeometry(0.28,0.3,1.1,16), m);
    leg.position.y = 0.35; g.add(leg);
    var foot = new THREE.Mesh(new THREE.CapsuleGeometry ? new THREE.CapsuleGeometry(0.28,0.5,4,12) : new THREE.CylinderGeometry(0.28,0.28,0.7,16), m);
    foot.rotation.z = Math.PI/2; foot.position.set(0.32,-0.35,0); g.add(foot);
    [0.55,0.25,-0.05].forEach(function(y){
      var stripe = new THREE.Mesh(new THREE.TorusGeometry(0.29,0.05,8,20), stripeMat);
      stripe.rotation.x = Math.PI/2; stripe.position.y = y; g.add(stripe);
    });
    return addBase(g, -1.05);
  }

  function buildLollipop(){
    var g = new THREE.Group();
    var colors = [0xff3d7a, 0xffffff, 0xffb347];
    for (var i=0;i<4;i++){
      var ring = new THREE.Mesh(new THREE.TorusGeometry(0.5-i*0.12,0.09,10,28), mkMat(colors[i%3], {roughness:0.3}));
      ring.position.z = i*0.05; g.add(ring);
    }
    var stick = new THREE.Mesh(new THREE.CylinderGeometry(0.045,0.045,0.9,10), mkMat(0xf2ead9));
    stick.position.y = -0.85; g.add(stick);
    return addBase(g, -1.35);
  }

  function buildSunglasses(){
    var g = new THREE.Group();
    var m = mkMat(0x14181f, {roughness:0.25, clearcoat:0.9});
    [-0.34,0.34].forEach(function(x){
      var lens = new THREE.Mesh(new THREE.SphereGeometry(0.28,16,16), m);
      lens.scale.set(1,0.85,0.35);
      lens.position.set(x,0,0); g.add(lens);
      var arm = new THREE.Mesh(new THREE.CylinderGeometry(0.025,0.025,0.55,8), m);
      arm.rotation.y = Math.PI/2; arm.rotation.z = 0.15*(x>0?1:-1);
      arm.position.set(x + (x>0?0.5:-0.5), 0, -0.15); g.add(arm);
    });
    var bridge = new THREE.Mesh(new THREE.CylinderGeometry(0.025,0.025,0.2,8), m);
    bridge.rotation.z = Math.PI/2; g.add(bridge);
    return addBase(g, -0.65);
  }

  function buildGiftbox(){
    var g = new THREE.Group();
    var boxMat = mkMat(0xc11f3d, {roughness:0.4});
    var ribbonMat = mkMat(0xf2b84b, {metalness:0.6, roughness:0.3});
    var box = new THREE.Mesh(new THREE.BoxGeometry(1,0.8,1), boxMat);
    g.add(box);
    var r1 = new THREE.Mesh(new THREE.BoxGeometry(1.04,0.16,1.04), ribbonMat); g.add(r1);
    var r2 = new THREE.Mesh(new THREE.BoxGeometry(0.16,0.84,1.04), ribbonMat); g.add(r2);
    [-0.13,0.13].forEach(function(x){
      var loop = new THREE.Mesh(new THREE.TorusGeometry(0.16,0.06,8,16), ribbonMat);
      loop.position.set(x,0.5,0); loop.rotation.y = Math.PI/2;
      loop.rotation.z = x>0 ? -0.6 : 0.6; g.add(loop);
    });
    return addBase(g, -0.85);
  }

  function buildButterfly(){
    var g = new THREE.Group();
    var body = new THREE.Mesh(new THREE.CylinderGeometry(0.04,0.04,0.7,8), mkMat(0x1c1c22));
    g.add(body);
    var wingMat = mkMat(0x8b5cf6, {roughness:0.35, emissive:0x8b5cf6, emissiveIntensity:0.2, transparent:true, opacity:0.9});
    function wing(x,y,scale,rot){
      var w = new THREE.Mesh(new THREE.SphereGeometry(0.32,14,14), wingMat);
      w.scale.set(0.35,1,scale);
      w.position.set(x,y,0); w.rotation.z = rot;
      return w;
    }
    g.add(wing(0.28,0.15,1,-0.3), wing(-0.28,0.15,1,0.3));
    g.add(wing(0.2,-0.2,0.65,-0.5), wing(-0.2,-0.2,0.65,0.5));
    [-0.06,0.06].forEach(function(x){
      var ant = new THREE.Mesh(new THREE.CylinderGeometry(0.012,0.012,0.3,6), mkMat(0x1c1c22));
      ant.position.set(x,0.45,0); ant.rotation.z = x>0?0.3:-0.3; g.add(ant);
    });
    return addBase(g, -0.75);
  }

  function buildTrident(){
    var g = new THREE.Group();
    var m = mkMat(0x8fa3bf, {metalness:0.85, roughness:0.25});
    var shaft = new THREE.Mesh(new THREE.CylinderGeometry(0.06,0.06,1.6,12), m);
    shaft.position.y = -0.2; g.add(shaft);
    var crossbar = new THREE.Mesh(new THREE.CylinderGeometry(0.045,0.045,0.7,10), m);
    crossbar.rotation.z = Math.PI/2; crossbar.position.y = 0.5; g.add(crossbar);
    [-0.35,0,0.35].forEach(function(x){
      var prong = new THREE.Mesh(new THREE.ConeGeometry(0.06,0.55,10), m);
      prong.position.set(x,0.85,0); g.add(prong);
    });
    return addBase(g, -1.3);
  }

  function buildUfo(){
    var g = new THREE.Group();
    var bodyMat = mkMat(0x8fa3bf, {metalness:0.8, roughness:0.2});
    var glassMat = mkMat(0x5fd4ff, {transparent:true, opacity:0.6, emissive:0x5fd4ff, emissiveIntensity:0.4, roughness:0.1});
    var disc = new THREE.Mesh(new THREE.SphereGeometry(0.75,24,12), bodyMat);
    disc.scale.set(1,0.28,1); g.add(disc);
    var dome = new THREE.Mesh(new THREE.SphereGeometry(0.34,20,20,0,Math.PI*2,0,Math.PI/1.9), glassMat);
    dome.position.y = 0.08; g.add(dome);
    for (var i=0;i<8;i++){
      var a = (i/8)*Math.PI*2;
      var light = new THREE.Mesh(new THREE.SphereGeometry(0.06,8,8), mkMat(0xf2b84b,{emissive:0xf2b84b, emissiveIntensity:0.8}));
      light.position.set(Math.cos(a)*0.68,-0.05,Math.sin(a)*0.68);
      g.add(light);
    }
    return addBase(g, -0.65);
  }

  function buildDragon(){
    var g = new THREE.Group();
    var scaleMat = mkMat(0x1c5c30, {roughness:0.45});
    var bellyMat = mkMat(0xd7c98a, {roughness:0.5});
    var wingMat = mkMat(0x2f8f4a, {roughness:0.5, transparent:true, opacity:0.85});
    var body = new THREE.Mesh(new THREE.ConeGeometry(0.45,1.3,16), scaleMat);
    body.rotation.x = Math.PI; body.position.y = -0.1; g.add(body);
    var belly = new THREE.Mesh(new THREE.ConeGeometry(0.25,1.1,12), bellyMat);
    belly.rotation.x = Math.PI; belly.position.set(0,-0.1,0.2); g.add(belly);
    var head = new THREE.Mesh(new THREE.SphereGeometry(0.32,16,16), scaleMat);
    head.position.y = 0.7; g.add(head);
    var snout = new THREE.Mesh(new THREE.ConeGeometry(0.14,0.35,10), scaleMat);
    snout.rotation.x = Math.PI/2; snout.position.set(0,0.65,0.32); g.add(snout);
    [-0.12,0.12].forEach(function(x){
      var horn = new THREE.Mesh(new THREE.ConeGeometry(0.05,0.28,8), mkMat(0xeaf1fb));
      horn.position.set(x,0.98,0.05); horn.rotation.z = x>0?-0.3:0.3; g.add(horn);
      var eye = new THREE.Mesh(new THREE.SphereGeometry(0.045,8,8), mkMat(0xff2a2a,{emissive:0xff2a2a, emissiveIntensity:1}));
      eye.position.set(x*1.4,0.72,0.28); g.add(eye);
    });
    function wing(x, mirror){
      var w = new THREE.Mesh(new THREE.CircleGeometry(0.55,3), wingMat);
      w.position.set(x,0.15,-0.1);
      w.rotation.y = mirror ? Math.PI/2+0.4 : -Math.PI/2-0.4;
      w.rotation.z = mirror ? -0.4 : 0.4;
      return w;
    }
    g.add(wing(0.55,false), wing(-0.55,true));
    var tail = new THREE.Mesh(new THREE.ConeGeometry(0.12,0.9,10), scaleMat);
    tail.rotation.x = Math.PI*0.4; tail.position.set(0,-0.95,-0.5); g.add(tail);
    return addBase(g, -1.35);
  }

  var GIFT_BUILDERS = {
    statue:buildStatueGroup, cactus:buildCactusGroup, demon:buildDemonGroup, phoenix:buildPhoenixGroup, dragon:buildDragon,
    rose:buildRose, bear:buildBear, heart:buildHeart, donut:buildDonut, balloon:buildBalloon, bone:buildBone,
    cake:buildCake, ring:buildRing, bolt:buildBolt, joystick:buildJoystick,
    rocket:buildRocket, hat:buildHat, crown:buildCrown, snake:buildSnake, crystal:buildCrystal, anchor:buildAnchor,
    cup:buildCup, diamond:buildDiamond, eagle:buildEagle, amulet:buildAmulet, unicorn:buildUnicorn,
    pizza:buildPizza, headphones:buildHeadphones, sock:buildSock, lollipop:buildLollipop, sunglasses:buildSunglasses,
    giftbox:buildGiftbox, butterfly:buildButterfly, trident:buildTrident, ufo:buildUfo
  };

  var modelGroups = {};
  function getModelGroup(id){
    if (modelGroups[id]) return modelGroups[id];
    var builder = GIFT_BUILDERS[id];
    var grp = builder ? builder() : buildRing();
    grp.visible = false;
    specialScene.add(grp);
    modelGroups[id] = grp;
    return grp;
  }
  specialScene.add(new THREE.AmbientLight(0x3a4a6e, 0.9));
  var sKey = new THREE.DirectionalLight(0xffffff, 2.4); sKey.position.set(3.2,3.6,4.2); specialScene.add(sKey);
  var sFill = new THREE.PointLight(0x3b82f6, 1.4, 22); sFill.position.set(-3.4,0.5,2.6); specialScene.add(sFill);
  var sRim = new THREE.PointLight(0x0ea5e9, 3.2, 20); sRim.position.set(0,1.6,-4.2); specialScene.add(sRim);
  var sBelow = new THREE.PointLight(0x8b5cf6, 0.6, 12); sBelow.position.set(0,-1.6,1.5); specialScene.add(sBelow);

  var shadowCanvasT = document.createElement('canvas');
  shadowCanvasT.width = 256; shadowCanvasT.height = 256;
  var shCtx = shadowCanvasT.getContext('2d');
  var shGrad = shCtx.createRadialGradient(128,128,8,128,128,120);
  shGrad.addColorStop(0, 'rgba(0,0,0,0.55)');
  shGrad.addColorStop(1, 'rgba(0,0,0,0)');
  shCtx.fillStyle = shGrad; shCtx.fillRect(0,0,256,256);
  var shadowTexT = new THREE.CanvasTexture(shadowCanvasT);
  var shadowMeshT = new THREE.Mesh(
    new THREE.PlaneGeometry(3.4,3.4),
    new THREE.MeshBasicMaterial({map:shadowTexT, transparent:true, depthWrite:false})
  );
  shadowMeshT.rotation.x = -Math.PI/2;
  shadowMeshT.position.y = -1.75;
  specialScene.add(shadowMeshT);

  var sparkCount = 60;
  var sparkGeo = new THREE.BufferGeometry();
  var sparkPos = new Float32Array(sparkCount*3);
  for (var i=0;i<sparkCount;i++){
    var a = Math.random()*Math.PI*2, r = 1.6 + Math.random()*0.8, y = (Math.random()-0.5)*3;
    sparkPos[i*3] = Math.cos(a)*r; sparkPos[i*3+1] = y; sparkPos[i*3+2] = Math.sin(a)*r;
  }
  sparkGeo.setAttribute('position', new THREE.BufferAttribute(sparkPos, 3));
  var sparkMat = new THREE.PointsMaterial({color:0x3b82f6, size:0.05, transparent:true, opacity:0.75, blending:THREE.AdditiveBlending, depthWrite:false});
  var sparks = new THREE.Points(sparkGeo, sparkMat);
  specialScene.add(sparks);

  var specialRAF = null;
  var specialClock = new THREE.Clock();
  var activeGroupId = null;
  function resizeSpecial(){
    var w = specialCanvas.clientWidth || 380, h = specialCanvas.clientHeight || 220;
    specialRenderer.setSize(w, h, false);
    specialCamera.aspect = w/h; specialCamera.updateProjectionMatrix();
  }
  function specialLoop(){
    specialRAF = requestAnimationFrame(specialLoop);
    if (specialCanvas.clientWidth !== specialCanvas.width || specialCanvas.clientHeight !== specialCanvas.height){ resizeSpecial(); }
    var t = specialClock.getElapsedTime();
    var reduced = state.settings && state.settings.reduceMotion;
    var g = modelGroups[activeGroupId];
    if (g){
      g.rotation.y = t*(reduced?0.35:0.75);
      g.rotation.x = reduced ? 0 : Math.sin(t*0.7)*0.05;
      g.position.y = reduced ? 0 : Math.sin(t*1.15)*0.05;
    }
    if (activeGroupId === 'phoenix'){ phoenixBodyMat.emissiveIntensity = 0.4 + Math.sin(t*8)*0.18; }
    sparks.rotation.y = reduced ? 0 : -t*0.25;
    specialRenderer.render(specialScene, specialCamera);
  }
  function startSpecial(id){
    Object.keys(modelGroups).forEach(function(k){ modelGroups[k].visible = false; });
    var grp = getModelGroup(id);
    grp.visible = true;
    grp.position.y = 0;
    activeGroupId = id;
    resizeSpecial();
    if (!specialRAF) specialLoop();
  }
  function stopSpecial(){ if (specialRAF){ cancelAnimationFrame(specialRAF); specialRAF = null; } }

  // ---------- bank transition ----------
  var overlay = document.getElementById('transition-overlay');
  var mainView = document.getElementById('main-view');
  var bankSection = document.getElementById('bank-section');
  document.getElementById('go-bank-btn').addEventListener('click', function(){
    overlay.classList.add('active');
    setTimeout(function(){
      chargeBankUpkeep();
      renderTop();
      renderBank();
      mainView.style.display = 'none';
      bankSection.classList.add('active');
      window.scrollTo({top:0, behavior:'instant'});
    }, 480);
    setTimeout(function(){ overlay.classList.remove('active'); }, 900);
  });
  document.getElementById('back-to-roulette').addEventListener('click', function(){
    overlay.classList.add('active');
    setTimeout(function(){
      bankSection.classList.remove('active');
      mainView.style.display = '';
      window.scrollTo({top:0, behavior:'instant'});
    }, 480);
    setTimeout(function(){ overlay.classList.remove('active'); }, 900);
  });

  // ---------- bank rendering ----------
  var bankStarsVal = document.getElementById('bank-stars-val');
  var bankStarAmt = document.getElementById('bank-star-amt');
  var coinsBankVal = document.getElementById('coins-bank-val');

  document.getElementById('coin-buy-btn').addEventListener('click', function(){
    var amtInput = document.getElementById('coin-buy-amt');
    var amt = Math.floor(Number(amtInput.value));
    if (!amt || amt <= 0){ showToast('Укажи количество монет'); return; }
    var cost = amt * 2;
    if (cost > state.balance){ showToast('Недостаточно звёзд'); return; }
    state.balance -= cost; state.coins += amt;
    saveState(); renderTop(); renderBank();
    amtInput.value = '';
    showToast('Куплено ' + amt + ' 🪙 за ' + cost + ' ★');
  });
  document.getElementById('coin-exchange-btn').addEventListener('click', function(){
    var amtInput = document.getElementById('coin-exchange-amt');
    var amt = Math.floor(Number(amtInput.value));
    if (!amt || amt <= 0){ showToast('Укажи количество монет'); return; }
    if (amt > state.coins){ showToast('Недостаточно монет'); return; }
    var starsGained = amt * 2;
    state.coins -= amt; state.balance += starsGained;
    saveState(); renderTop(); renderBank();
    amtInput.value = '';
    showToast('Обменяно ' + amt + ' 🪙 на ' + starsGained + ' ★');
  });
  document.getElementById('bank-deposit-star').addEventListener('click', function(){
    var amt = Math.floor(Number(bankStarAmt.value));
    if (!amt || amt <= 0){ showToast('Укажи количество'); return; }
    if (amt > state.balance){ showToast('Недостаточно звёзд'); return; }
    state.balance -= amt; state.bankStars += amt;
    saveState(); renderTop(); renderBank();
    showToast('Положено ' + amt + ' ★ в банк');
  });
  document.getElementById('bank-withdraw-star').addEventListener('click', function(){
    var amt = Math.floor(Number(bankStarAmt.value));
    if (!amt || amt <= 0){ showToast('Укажи количество'); return; }
    if (amt > state.bankStars){ showToast('В банке столько нет'); return; }
    state.bankStars -= amt; state.balance += amt;
    saveState(); renderTop(); renderBank();
    showToast('Забрано ' + amt + ' ★ из банка');
  });

  document.getElementById('loan-repay-btn').addEventListener('click', function(){
    if (!state.loan) return;
    state.balance -= state.loan.amount;
    state.loan = null;
    saveState(); renderTop(); renderBank();
    showToast('Кредит погашен');
  });

  function renderLoan(){
    var activeEl = document.getElementById('loan-active');
    var optsEl = document.getElementById('loan-options');
    if (state.loan){
      activeEl.style.display = 'flex';
      document.getElementById('loan-info-name').textContent = 'Кредит: ' + state.loan.amount + ' ★';
      var msLeft = state.loan.dueAt - Date.now();
      var daysLeft = Math.ceil(msLeft/DAY_MS);
      document.getElementById('loan-info-meta').textContent = msLeft > 0 ? ('вернуть через ~' + daysLeft + ' дн.') : 'просрочен — спишется автоматически';
      optsEl.innerHTML = '';
    } else {
      activeEl.style.display = 'none';
      optsEl.innerHTML = '';
      LOAN_OPTIONS.forEach(function(opt){
        var card = document.createElement('div');
        card.className = 'shop-card';
        card.innerHTML = '<div class="ico">💳</div><div class="name">' + opt.amount + ' ★</div><div class="price">на ' + opt.days + ' дн.</div>';
        var btn = document.createElement('button');
        btn.className = 'btn-secondary gold'; btn.style.marginTop = '10px'; btn.style.width = '100%';
        btn.textContent = 'Взять кредит';
        btn.addEventListener('click', function(){
          state.loan = {amount:opt.amount, takenAt:Date.now(), dueAt:Date.now()+opt.days*DAY_MS};
          state.balance += opt.amount;
          saveState(); renderTop(); renderBank();
          showToast('Кредит на ' + opt.amount + ' ★ выдан, вернуть за ' + opt.days + ' дн.');
        });
        card.appendChild(btn);
        optsEl.appendChild(card);
      });
    }
  }

  var bankOffers = {};
  var bankCoinOffers = {};
  function renderBoosts(){
    var grid = document.getElementById('boost-grid');
    grid.innerHTML = '';
    BOOSTS.forEach(function(b){
      var active = isBoostActive(b.id);
      var card = document.createElement('div');
      card.className = 'shop-card';
      var statusHtml = active
        ? '<div class="price" style="color:var(--blue);">активен · ' + Math.max(1, Math.ceil((state.boosts[b.id]-Date.now())/60000)) + ' мин</div>'
        : '<div class="price">' + b.priceStars + ' ★ · ' + b.priceCoins + ' 🪙</div>';
      card.innerHTML = '<div class="ico">'+b.ico+'</div><div class="name">'+b.name+'</div><div class="bank-row-meta" style="margin-top:4px;">'+b.desc+'</div>'+statusHtml;
      if (!active){
        var btnWrap = document.createElement('div');
        btnWrap.style.display = 'flex'; btnWrap.style.gap = '6px'; btnWrap.style.marginTop = '10px';
        var btnS = document.createElement('button');
        btnS.className = 'btn-secondary'; btnS.style.flex = '1'; btnS.textContent = 'За ★';
        btnS.addEventListener('click', function(){
          if (state.balance < b.priceStars){ showToast('Не хватает звёзд'); return; }
          state.balance -= b.priceStars;
          activateBoost(b.id);
        });
        var btnC = document.createElement('button');
        btnC.className = 'btn-secondary gold'; btnC.style.flex = '1'; btnC.textContent = 'За 🪙';
        btnC.addEventListener('click', function(){
          if (state.coins < b.priceCoins){ showToast('Не хватает монет'); return; }
          state.coins -= b.priceCoins;
          activateBoost(b.id);
        });
        btnWrap.appendChild(btnS); btnWrap.appendChild(btnC);
        card.appendChild(btnWrap);
      }
      grid.appendChild(card);
    });
  }
  function activateBoost(id){
    var now = Date.now();
    var current = (state.boosts[id] && state.boosts[id] > now) ? state.boosts[id] : now;
    state.boosts[id] = current + BOOST_MS;
    saveState(); renderTop(); renderBank();
    showToast('Улучшение активировано на 1 час: ' + boostById(id).name);
  }
  function renderBank(){
    bankStarsVal.textContent = state.bankStars;
    coinsBankVal.textContent = state.coins;
    renderLoan();
    renderBoosts();

    var giftsListEl = document.getElementById('bank-gifts-list');
    var giftsEmptyEl = document.getElementById('bank-gifts-empty');
    giftsListEl.innerHTML = '';
    if (state.bankGifts.length === 0){ giftsEmptyEl.style.display='block'; giftsListEl.style.display='none'; }
    else{
      giftsEmptyEl.style.display='none'; giftsListEl.style.display='flex';
      state.bankGifts.forEach(function(entry){
        var g = byId(entry.id); if (!g) return;
        var days = Math.floor((Date.now()-entry.storedAt)/DAY_MS);
        var dailyInterest = Math.floor(g.sell*0.03);
        var row = document.createElement('div');
        row.className = 'bank-row';
        row.innerHTML =
          '<div class="bank-row-left"><div class="ico">'+g.ico+'</div><div><div class="bank-row-name">'+g.name+'</div>'+
          '<div class="bank-row-meta">хранится '+days+' дн. · -2★/день, +'+dailyInterest+'★/день процентов</div></div></div>';
        var btn = document.createElement('button');
        btn.className = 'btn-secondary';
        btn.textContent = 'Забрать';
        btn.addEventListener('click', function(){
          state.bankGifts = state.bankGifts.filter(function(e){ return e.uid !== entry.uid; });
          state.inventory[g.id] = (state.inventory[g.id]||0)+1;
          saveState(); renderInventory(); renderBank();
          showToast(g.name + ' возвращён в профиль');
        });
        row.appendChild(btn);
        giftsListEl.appendChild(row);
      });
    }

    var depoListEl = document.getElementById('deposit-list');
    var depoEmptyEl = document.getElementById('deposit-empty');
    var invIds = Object.keys(state.inventory).filter(function(k){ return state.inventory[k] > 0; });
    depoListEl.innerHTML = '';
    if (invIds.length === 0){ depoEmptyEl.style.display='block'; depoListEl.style.display='none'; }
    else{
      depoEmptyEl.style.display='none'; depoListEl.style.display='flex';
      invIds.forEach(function(id){
        var g = byId(id); if (!g) return;
        var row = document.createElement('div');
        row.className = 'bank-row';
        row.innerHTML = '<div class="bank-row-left"><div class="ico">'+g.ico+'</div><div><div class="bank-row-name">'+g.name+'</div><div class="bank-row-meta">у тебя: x'+state.inventory[id]+'</div></div></div>';
        var btn = document.createElement('button');
        btn.className = 'btn-secondary';
        btn.textContent = 'Сдать на хранение';
        btn.addEventListener('click', function(){
          if (!state.inventory[id] || state.inventory[id] <= 0) return;
          state.inventory[id] -= 1;
          state.bankGifts.push({uid: 'b'+Date.now()+Math.random().toString(36).slice(2), id:id, storedAt:Date.now(), lastChargeAt:Date.now()});
          saveState(); renderInventory(); renderBank();
          showToast(g.name + ' сдан на хранение');
        });
        row.appendChild(btn);
        depoListEl.appendChild(row);
      });
    }

    var sellListEl = document.getElementById('sellbank-list');
    var sellEmptyEl = document.getElementById('sellbank-empty');
    sellListEl.innerHTML = '';
    if (invIds.length === 0){ sellEmptyEl.style.display='block'; sellListEl.style.display='none'; }
    else{
      sellEmptyEl.style.display='none'; sellListEl.style.display='flex';
      invIds.forEach(function(id){
        var g = byId(id); if (!g) return;
        if (bankOffers[id] === undefined){
          bankOffers[id] = Math.max(1, Math.round(sellValue(g)*(0.7+Math.random()*0.4)));
        }
        if (bankCoinOffers[id] === undefined){
          bankCoinOffers[id] = Math.max(1, Math.round(coinSellPrice(g)*(0.7+Math.random()*0.4)));
        }
        var offer = bankOffers[id], coinOffer = bankCoinOffers[id];
        var row = document.createElement('div');
        row.className = 'bank-row';
        row.innerHTML = '<div class="bank-row-left"><div class="ico">'+g.ico+'</div><div><div class="bank-row-name">'+g.name+'</div><div class="bank-row-meta">предложение: '+offer+' ★ или '+coinOffer+' 🪙</div></div></div>';
        var btnWrap = document.createElement('div');
        btnWrap.style.display = 'flex'; btnWrap.style.gap = '8px';
        var btn = document.createElement('button');
        btn.className = 'btn-secondary gold'; btn.textContent = 'За ★';
        btn.addEventListener('click', function(){
          if (!state.inventory[id] || state.inventory[id] <= 0) return;
          state.inventory[id] -= 1; state.balance += bankOffers[id];
          delete bankOffers[id]; delete bankCoinOffers[id];
          saveState(); renderTop(); renderInventory(); renderBank();
          showToast('Банк купил гифт за ' + offer + ' ★');
        });
        var btnCoin = document.createElement('button');
        btnCoin.className = 'btn-secondary'; btnCoin.textContent = 'За 🪙';
        btnCoin.addEventListener('click', function(){
          if (!state.inventory[id] || state.inventory[id] <= 0) return;
          state.inventory[id] -= 1; state.coins += bankCoinOffers[id];
          delete bankOffers[id]; delete bankCoinOffers[id];
          saveState(); renderTop(); renderInventory(); renderBank();
          showToast('Банк купил гифт за ' + coinOffer + ' 🪙');
        });
        btnWrap.appendChild(btn); btnWrap.appendChild(btnCoin);
        row.appendChild(btnWrap);
        sellListEl.appendChild(row);
      });
    }

    var shopGrid = document.getElementById('shop-grid');
    shopGrid.innerHTML = '';
    GIFTS.forEach(function(g){
      var card = document.createElement('div');
      card.className = 'shop-card';
      card.innerHTML = '<div class="ico">'+g.ico+'</div><div class="name">'+g.name+'</div><div class="price">'+buyPrice(g)+' ★ · '+buyPriceCoin(g)+' 🪙</div>';
      var btnWrap = document.createElement('div');
      btnWrap.style.display = 'flex'; btnWrap.style.gap = '6px'; btnWrap.style.marginTop = '10px';
      var btn = document.createElement('button');
      btn.className = 'btn-secondary'; btn.style.flex = '1';
      btn.textContent = 'За ★';
      btn.addEventListener('click', function(){
        var price = buyPrice(g);
        if (state.balance < price){ showToast('Не хватает звёзд'); return; }
        state.balance -= price;
        state.inventory[g.id] = (state.inventory[g.id]||0)+1;
        saveState(); renderTop(); renderInventory(); renderBank();
        showToast('Куплено: ' + g.name);
      });
      var btnCoin = document.createElement('button');
      btnCoin.className = 'btn-secondary gold'; btnCoin.style.flex = '1';
      btnCoin.textContent = 'За 🪙';
      btnCoin.addEventListener('click', function(){
        var priceCoin = buyPriceCoin(g);
        if (state.coins < priceCoin){ showToast('Не хватает монет'); return; }
        state.coins -= priceCoin;
        state.inventory[g.id] = (state.inventory[g.id]||0)+1;
        saveState(); renderTop(); renderInventory(); renderBank();
        showToast('Куплено: ' + g.name);
      });
      btnWrap.appendChild(btn); btnWrap.appendChild(btnCoin);
      card.appendChild(btnWrap);
      shopGrid.appendChild(card);
    });
  }

  document.getElementById('promo-btn').addEventListener('click', function(){
    var input = document.getElementById('promo-input');
    var code = input.value.trim();
    if (!code){ showToast('Введи промокод'); return; }
    var reward = PROMO_CODES[code];
    if (!reward){ showToast('Промокод не найден'); return; }
    Object.keys(reward).forEach(function(id){
      state.inventory[id] = (state.inventory[id]||0) + reward[id];
    });
    saveState(); renderInventory(); renderBank();
    input.value = '';
    showToast('Промокод активирован! Получены редкие гифты 🎉');
  });

  // ---------- telegram login ----------
  // Юзернейм твоего бота (без @). В @BotFather команда /setdomain уже настроена на этот бот —
  // просто пришли туда домен, на котором будет висеть сайт (например: username.github.io).
  var TG_BOT_USERNAME = 'gametbf_bot';

  window.onTelegramAuth = function(user){
    state.tgProfile = user;
    saveState();
    renderTgProfile();
    showToast('Привет, ' + user.first_name + '!');
  };

  function renderTgProfile(){
    var chip = document.getElementById('tg-profile-chip');
    if (state.tgProfile){
      var p = state.tgProfile;
      var name = p.first_name + (p.last_name ? ' ' + p.last_name : '');
      chip.innerHTML =
        '<div class="tg-profile">' +
        (p.photo_url ? '<img src="'+p.photo_url+'" alt="">' : '') +
        '<span class="tg-name">'+name+'</span>' +
        '<button class="tg-logout" id="tg-logout-btn" title="Выйти">✕</button>' +
        '</div>';
      document.getElementById('tg-logout-btn').addEventListener('click', function(){
        state.tgProfile = null; saveState(); renderTgProfile();
      });
    } else {
      chip.innerHTML = '';
      var s = document.createElement('script');
      s.async = true;
      s.src = 'https://telegram.org/js/telegram-widget.js?22';
      s.setAttribute('data-telegram-login', TG_BOT_USERNAME);
      s.setAttribute('data-size', 'medium');
      s.setAttribute('data-radius', '20');
      s.setAttribute('data-onauth', 'onTelegramAuth(user)');
      s.setAttribute('data-request-access', 'write');
      chip.appendChild(s);
    }
  }

  function tgDisplayName(){
    if (state.tgProfile){ return state.tgProfile.first_name || state.tgProfile.username || 'Игрок'; }
    return 'Игрок';
  }

  // ---------- gifting between players (serverless gift codes) ----------
  function encodeGiftCode(payload){
    return btoa(unescape(encodeURIComponent(JSON.stringify(payload))));
  }
  function decodeGiftCode(code){
    try{ return JSON.parse(decodeURIComponent(escape(atob(code.trim())))); }catch(e){ return null; }
  }
  function sendGiftCode(g){
    if (!state.inventory[g.id] || state.inventory[g.id] <= 0){ showToast('Нет такого гифта'); return; }
    state.inventory[g.id] -= 1;
    var payload = {v:1, gid:g.id, from:tgDisplayName(), code: 'g'+Date.now()+Math.random().toString(36).slice(2)};
    var code = encodeGiftCode(payload);
    saveState(); renderInventory();
    openCodeModal(code, 'Гифт «' + g.name + '» отправлен из твоего профиля. Перешли этот код другу — он вставит его в поле «Принять код» в профиле.');
  }
  function redeemCode(codeStr){
    var payload = decodeGiftCode(codeStr);
    if (!payload || !payload.code){ showToast('Код не распознан'); return; }
    state.redeemedGiftCodes = state.redeemedGiftCodes || [];
    if (state.redeemedGiftCodes.indexOf(payload.code) !== -1){ showToast('Этот код уже использован на этом устройстве'); return; }
    if (payload.gid){
      var g = byId(payload.gid);
      if (!g){ showToast('Гифт в коде не распознан'); return; }
      state.redeemedGiftCodes.push(payload.code);
      state.inventory[g.id] = (state.inventory[g.id]||0) + 1;
      saveState(); renderInventory();
      showToast('Подарок от ' + (payload.from||'друга') + ': ' + g.ico + ' ' + g.name + '!');
    } else if (payload.ref){
      if (payload.ref !== myReferralCode()){ showToast('Этот реферальный код не для тебя'); return; }
      state.redeemedGiftCodes.push(payload.code);
      state.balance += 150;
      saveState(); renderTop();
      showToast('Реферальная награда от ' + (payload.from||'друга') + ': +150 ★');
    } else {
      showToast('Код не распознан');
    }
  }

  var giftCodeModal = document.getElementById('gift-code-modal');
  function openCodeModal(code, desc){
    document.getElementById('gift-code-desc').textContent = desc;
    document.getElementById('gift-code-text').value = code;
    giftCodeModal.classList.remove('hidden');
    requestAnimationFrame(function(){ giftCodeModal.classList.add('visible'); });
  }
  function closeGiftCodeModal(){
    giftCodeModal.classList.remove('visible');
    setTimeout(function(){ giftCodeModal.classList.add('hidden'); }, 200);
  }
  document.getElementById('gift-code-close').addEventListener('click', closeGiftCodeModal);
  giftCodeModal.addEventListener('click', function(e){ if (e.target === giftCodeModal) closeGiftCodeModal(); });
  document.getElementById('gift-code-copy').addEventListener('click', function(){
    var ta = document.getElementById('gift-code-text');
    ta.select();
    try{ document.execCommand('copy'); showToast('Код скопирован'); }catch(e){ showToast('Скопируй код вручную'); }
  });
  document.getElementById('redeem-code-btn').addEventListener('click', function(){
    var input = document.getElementById('redeem-code-input');
    if (!input.value.trim()){ showToast('Вставь код'); return; }
    redeemCode(input.value);
    input.value = '';
  });

  // ---------- referral system ----------
  function myReferralCode(){
    if (!state.myRefCode){
      state.myRefCode = (state.tgProfile && state.tgProfile.username) ? state.tgProfile.username : ('p'+Math.random().toString(36).slice(2,8));
      saveState();
    }
    return state.myRefCode;
  }
  function referralLink(){
    return window.location.origin + window.location.pathname + '?ref=' + encodeURIComponent(myReferralCode());
  }
  function renderReferral(){
    var input = document.getElementById('ref-link-input');
    if (input) input.value = referralLink();
    var status = document.getElementById('ref-status');
    if (status){
      status.textContent = state.referredBy ? ('Ты пришёл по приглашению: ' + state.referredBy) : 'Пока никто тебя не приглашал';
    }
  }
  function checkReferralParam(){
    try{
      var params = new URLSearchParams(window.location.search);
      var ref = params.get('ref');
      if (ref && !state.referredBy && ref !== myReferralCode()){
        state.referredBy = ref;
        state.balance += 200;
        state.coins += 50;
        saveState(); renderTop();
        showToast('Бонус за приглашение: +200 ★ +50 🪙');
        var payload = {v:1, ref: ref, from: tgDisplayName(), code: 'r'+Date.now()+Math.random().toString(36).slice(2)};
        var code = encodeGiftCode(payload);
        setTimeout(function(){
          openCodeModal(code, 'Ты получил бонус за приглашение! Отправь этот код тому, кто тебя позвал — он получит награду за реферала.');
        }, 300);
      }
    }catch(e){}
  }
  document.getElementById('ref-copy-btn').addEventListener('click', function(){
    var input = document.getElementById('ref-link-input');
    input.select();
    try{ document.execCommand('copy'); showToast('Ссылка скопирована'); }catch(e){ showToast('Скопируй ссылку вручную'); }
  });

  // ---------- settings ----------
  var ACCENT_THEMES = {
    blue:   {blue:'#3b82f6', cta:'#0ea5e9', dim:'#1e4d8f'},
    purple: {blue:'#8b5cf6', cta:'#a78bfa', dim:'#4c2d99'},
    green:  {blue:'#22c55e', cta:'#34d399', dim:'#166534'},
    red:    {blue:'#ef4444', cta:'#f97316', dim:'#7f1d1d'},
    gold:   {blue:'#f2b84b', cta:'#facc15', dim:'#8a5a12'}
  };
  function applyTheme(name){
    var t = ACCENT_THEMES[name] || ACCENT_THEMES.blue;
    var root = document.documentElement.style;
    root.setProperty('--blue', t.blue);
    root.setProperty('--cta', t.cta);
    root.setProperty('--blue-dim', t.dim);
  }
  function applySettings(){
    applyTheme(state.settings.accent);
    document.body.classList.toggle('reduce-motion', !!state.settings.reduceMotion);
    document.getElementById('reduce-motion-toggle').checked = !!state.settings.reduceMotion;
    var swatchWrap = document.getElementById('theme-swatches');
    swatchWrap.querySelectorAll('.swatch').forEach(function(sw){
      sw.classList.toggle('active', sw.getAttribute('data-theme') === state.settings.accent);
    });
  }
  var swatchWrap = document.getElementById('theme-swatches');
  Object.keys(ACCENT_THEMES).forEach(function(name){
    var sw = document.createElement('div');
    sw.className = 'swatch';
    sw.setAttribute('data-theme', name);
    sw.style.background = ACCENT_THEMES[name].blue;
    sw.addEventListener('click', function(){
      state.settings.accent = name;
      saveState();
      applySettings();
    });
    swatchWrap.appendChild(sw);
  });
  document.getElementById('reduce-motion-toggle').addEventListener('change', function(e){
    state.settings.reduceMotion = e.target.checked;
    saveState();
    applySettings();
  });

  var settingsModal = document.getElementById('settings-modal');
  document.getElementById('settings-btn').addEventListener('click', function(){
    applySettings();
    settingsModal.classList.remove('hidden');
    requestAnimationFrame(function(){ settingsModal.classList.add('visible'); });
  });
  function closeSettings(){
    settingsModal.classList.remove('visible');
    setTimeout(function(){ settingsModal.classList.add('hidden'); }, 200);
  }
  document.getElementById('settings-close').addEventListener('click', closeSettings);
  settingsModal.addEventListener('click', function(e){ if (e.target === settingsModal) closeSettings(); });

  document.addEventListener('keydown', function(e){
    if (e.key !== 'Escape') return;
    if (!settingsModal.classList.contains('hidden')){ closeSettings(); return; }
    if (!batchModal.classList.contains('hidden')){ closeBatchModal(); return; }
    if (!modal.classList.contains('hidden')){ closeModal(); return; }
  });

  // ---------- init ----------
  applySettings();
  renderTgProfile();
  checkReferralParam();
  renderReferral();
  updateSpinButtonLabels();
  chargeBankUpkeep();
  renderTop();
  renderInventory();
  renderBank();
  setInterval(function(){ chargeBankUpkeep(); renderTop(); if (bankSection.classList.contains('active')){ renderBank(); } }, 60*1000);
})();
</script>
</body>
</html>
