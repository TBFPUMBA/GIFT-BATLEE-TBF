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
  .bank-section{padding:30px 0 80px;border-top:1px solid var(--line);}
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
  #special-canvas{width:100%;height:220px;display:block;}
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
  .batch-actions{margin-top:20px;text-align:right;}

  .transition-overlay{position:fixed;inset:0;z-index:100;pointer-events:none;background:radial-gradient(circle, var(--cta) 0%, var(--blue-dim) 45%, var(--bg-0) 75%);clip-path:circle(0% at 50% 40%);transition:clip-path .55s cubic-bezier(0.6,0,0.3,1);}
  .transition-overlay.active{clip-path:circle(150% at 50% 40%);}

  .toast{position:fixed;bottom:24px;left:50%;transform:translateX(-50%);background:var(--bg-2);border:1px solid var(--blue);color:var(--bone);border-radius:999px;padding:12px 24px;font-size:13px;z-index:60;opacity:0;transition:opacity .25s ease, transform .25s ease;pointer-events:none;text-align:center;max-width:88vw;}
  .toast.show{opacity:1;transform:translateX(-50%) translateY(-6px);}

  footer{padding:26px 28px 40px;font-size:12px;color:var(--tan);border-top:1px solid var(--line);}

  @media (max-width:600px){
    .reel-item{width:110px;flex-basis:110px;}
    .reel-item .ico{font-size:40px;}
    .spin-buttons{flex-direction:column;}
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
  </div>
</header>

<div class="wrap">
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
      <div class="spin-buttons">
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
    <div id="inv-empty" class="empty-state">Пока пусто — крути рулетку выше</div>
    <div class="inv-grid" id="inv-grid"></div>
  </section>
</div>

<section class="bank-section wrap" id="bank-section">
  <a class="bank-back" id="back-to-roulette">← К рулетке</a>
  <div class="section-head">
    <h2>Банк TBFPUMBA</h2>
    <p>Проценты, кредиты, магазин и промокоды</p>
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
      <button class="btn-secondary gold" id="modal-sell-coin">Продать за <span id="modal-sell-coin-val">0</span> 🪙</button>
      <button class="btn-secondary" id="modal-keep">Оставить</button>
    </div>
  </div>
</div>

<div class="batch-overlay hidden" id="batch-modal">
  <div class="batch-card">
    <h3 id="batch-title">Результаты</h3>
    <div class="batch-sub" id="batch-sub"></div>
    <div class="batch-grid" id="batch-grid"></div>
    <div class="batch-actions"><button class="btn-secondary gold" id="batch-close">Забрать всё</button></div>
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
    {id:'phoenix', name:'Феникс',          ico:'🔥', rarity:'mythic', weight:0.22, sell:3600, desc:'Самый редкий и дорогой гифт в игре.'}
  ];
  var RARITY_LABEL = {common:'COMMON', rare:'RARE', epic:'EPIC', legend:'LEGENDARY', mythic:'MYTHIC'};
  var STORE_KEY = 'tbfpumba_gift_battle_v3';
  var DAY_MS = 24*60*60*1000;
  var PROMO_CODES = { '6666209752': {cactus:1, statue:1, diamond:1} };
  var LOAN_OPTIONS = [{amount:200,days:6},{amount:300,days:8},{amount:400,days:10}];

  var totalWeight = GIFTS.reduce(function(s,g){return s+g.weight;}, 0);
  function pickGift(){
    var r = Math.random()*totalWeight;
    for (var i=0;i<GIFTS.length;i++){ r -= GIFTS[i].weight; if (r<=0) return GIFTS[i]; }
    return GIFTS[GIFTS.length-1];
  }
  function byId(id){ for (var i=0;i<GIFTS.length;i++){ if (GIFTS[i].id===id) return GIFTS[i]; } return null; }
  function buyPrice(g){ return Math.round(g.sell*2.5); }
  function coinSellPrice(g){ return Math.max(1, Math.round(g.sell/10)); }

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
        return s;
      }
    }catch(e){}
    return {balance:500, bankStars:0, coins:0, xp:0, inventory:{}, bankGifts:[], redeemedCodes:[], loan:null};
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
        var fee = days*2;
        var interest = Math.floor(g.sell*0.03)*days;
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
      var cost = parseInt(b.getAttribute('data-count'),10)*100;
      b.disabled = state.balance < cost || spinning;
    });
  }

  function renderInventory(){
    var ids = Object.keys(state.inventory).filter(function(k){ return state.inventory[k] > 0; });
    var total = ids.reduce(function(s,k){ return s + state.inventory[k]; }, 0);
    invCount.textContent = 'гифтов: ' + total;
    invGrid.innerHTML = '';
    if (ids.length === 0){ invEmpty.style.display = 'block'; invGrid.style.display = 'none'; }
    else{
      invEmpty.style.display = 'none'; invGrid.style.display = 'grid';
      ids.forEach(function(id){
        var g = byId(id); if (!g) return;
        var card = document.createElement('div');
        card.className = 'gift-card rar-' + g.rarity;
        card.innerHTML = '<div class="count">x' + state.inventory[id] + '</div><div class="ico">' + g.ico + '</div><div class="name">' + g.name + '</div>';
        card.addEventListener('click', function(){ openModal(g); });
        invGrid.appendChild(card);
      });
    }
  }

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
  var spinning = false;

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
    var cost = count*100;
    if (state.balance < cost){ showToast('Не хватает звёзд'); return; }
    spinning = true;
    reelFrame.classList.add('spinning');
    spinButtons.forEach(function(b){ b.disabled = true; });

    state.balance -= cost;
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
      for (var ci=0; ci<count; ci++){
        if (Math.random() < 0.2){ coinsGained += 1 + Math.floor(Math.random()*2); }
      }
      if (coinsGained > 0){ state.coins += coinsGained; }
      addXp(10*count);
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
  var modalClose = document.getElementById('modal-close');
  var currentGift = null;

  function openModal(g, justWon){
    currentGift = g;
    modalCard.className = 'modal-card rar-' + g.rarity;
    modalRar.textContent = (justWon ? 'НОВЫЙ ГИФТ · ' : '') + RARITY_LABEL[g.rarity];
    modalIco.textContent = g.ico;
    modalName.textContent = g.name;
    modalDesc.textContent = g.desc;
    modalSellVal.textContent = g.sell;
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
  modal.addEventListener('click', function(e){ if (e.target === modal) closeModal(); });
  modalSell.addEventListener('click', function(){
    if (!currentGift) return;
    var id = currentGift.id;
    if (!state.inventory[id] || state.inventory[id] <= 0){ closeModal(); return; }
    state.inventory[id] -= 1;
    state.balance += currentGift.sell;
    saveState(); renderTop(); renderInventory();
    showToast('Продано за ' + currentGift.sell + ' ★');
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

  function openBatchModal(results){
    batchGrid.innerHTML = '';
    var total = 0;
    results.forEach(function(r, idx){
      total += r.sell;
      var el = document.createElement('div');
      el.className = 'batch-item rar-' + r.rarity;
      el.style.animationDelay = (idx*0.08) + 's';
      el.innerHTML = '<div class="ico">' + r.ico + '</div><div class="name">' + r.name + '</div>';
      batchGrid.appendChild(el);
    });
    batchSub.textContent = 'Выбито предметов: ' + results.length + ' · суммарная цена продажи: ' + total + ' ★';
    batchModal.classList.remove('hidden');
    requestAnimationFrame(function(){ batchModal.classList.add('visible'); });
  }
  function closeBatchModal(){
    batchModal.classList.remove('visible');
    setTimeout(function(){ batchModal.classList.add('hidden'); }, 200);
  }
  batchClose.addEventListener('click', closeBatchModal);
  batchModal.addEventListener('click', function(e){ if (e.target === batchModal) closeBatchModal(); });

  // ---------- 3D models for every gift ----------
  var specialCanvas = document.getElementById('special-canvas');
  var specialRenderer = new THREE.WebGLRenderer({canvas:specialCanvas, antialias:true, alpha:true});
  specialRenderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));
  var specialScene = new THREE.Scene();
  var specialCamera = new THREE.PerspectiveCamera(40, 1, 0.1, 30);
  specialCamera.position.set(0, 0.5, 6);

  function mkMat(color, opts){
    opts = opts || {};
    return new THREE.MeshStandardMaterial(Object.assign({color:color, metalness:0.45, roughness:0.4}, opts));
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

  // -- generic medallion builder for the rest
  function buildMedallion(discColor, accentType, accentColor){
    var group = new THREE.Group();
    var rim = new THREE.Mesh(new THREE.CylinderGeometry(1.05,1.05,0.22,32), mkMat(0x1e4d8f, {metalness:0.7, roughness:0.35}));
    rim.rotation.x = Math.PI/2; group.add(rim);
    var disc = new THREE.Mesh(new THREE.CylinderGeometry(0.92,0.92,0.14,32), mkMat(discColor, {metalness:0.55, roughness:0.35}));
    disc.rotation.x = Math.PI/2; disc.position.z = 0.02; group.add(disc);
    var accentMat = mkMat(accentColor, {metalness:0.4, roughness:0.3, emissive:accentColor, emissiveIntensity:0.15});
    var accentMesh;
    if (accentType==='sphere') accentMesh = new THREE.Mesh(new THREE.SphereGeometry(0.32,16,16), accentMat);
    else if (accentType==='cone') accentMesh = new THREE.Mesh(new THREE.ConeGeometry(0.3,0.55,16), accentMat);
    else if (accentType==='torus') accentMesh = new THREE.Mesh(new THREE.TorusGeometry(0.3,0.1,10,24), accentMat);
    else if (accentType==='box') accentMesh = new THREE.Mesh(new THREE.BoxGeometry(0.42,0.42,0.42), accentMat);
    else accentMesh = new THREE.Mesh(new THREE.OctahedronGeometry(0.34,0), accentMat);
    accentMesh.position.z = 0.32; group.add(accentMesh);
    var base = new THREE.Mesh(new THREE.CylinderGeometry(0.5,0.6,0.3,20), mkMat(0x0f1830, {metalness:0.5, roughness:0.5}));
    base.position.y = -1.35; group.add(base);
    return group;
  }

  var BESPOKE_BUILDERS = {statue:buildStatueGroup, cactus:buildCactusGroup, demon:buildDemonGroup, phoenix:buildPhoenixGroup};
  var GENERIC_MODELS = {
    rose:{color:0xc23a5e, accent:'sphere', accentColor:0xff6b9c},
    bear:{color:0x8a5a3a, accent:'sphere', accentColor:0xd9b48f},
    heart:{color:0xc11f3d, accent:'sphere', accentColor:0xff3b5c},
    donut:{color:0xd9a066, accent:'torus', accentColor:0xff8fc0},
    balloon:{color:0xe23b3b, accent:'sphere', accentColor:0xff7a7a},
    bone:{color:0xf2ead9, accent:'box', accentColor:0xffffff},
    cake:{color:0xf7e2c0, accent:'cone', accentColor:0xffb347},
    ring:{color:0xdba514, accent:'diamond', accentColor:0xbfe9ff},
    bolt:{color:0xf2d200, accent:'cone', accentColor:0xfff7cc},
    joystick:{color:0x2e3648, accent:'sphere', accentColor:0xff4d4d},
    rocket:{color:0xc7d1dc, accent:'cone', accentColor:0xff4d4d},
    hat:{color:0x14181f, accent:'torus', accentColor:0xdba514},
    crown:{color:0xf2b84b, accent:'diamond', accentColor:0x9be8ff},
    snake:{color:0x2f8f4a, accent:'torus', accentColor:0x1c5c30},
    crystal:{color:0x7c4fd1, accent:'sphere', accentColor:0xd7b8ff},
    anchor:{color:0x334155, accent:'cone', accentColor:0xcbd5e1},
    cup:{color:0xe0b020, accent:'torus', accentColor:0xf2d27a},
    diamond:{color:0xbfe9ff, accent:'diamond', accentColor:0xffffff},
    eagle:{color:0x6b4a2f, accent:'cone', accentColor:0xf5f5f0},
    amulet:{color:0x1e4d8f, accent:'sphere', accentColor:0x5fd4ff},
    unicorn:{color:0xffffff, accent:'cone', accentColor:0xf2b84b}
  };

  var modelGroups = {};
  GIFTS.forEach(function(g){
    var grp;
    if (BESPOKE_BUILDERS[g.id]) grp = BESPOKE_BUILDERS[g.id]();
    else {
      var m = GENERIC_MODELS[g.id] || {color:0x7d92b8, accent:'sphere', accentColor:0xbfe9ff};
      grp = buildMedallion(m.color, m.accent, m.accentColor);
    }
    grp.visible = false;
    specialScene.add(grp);
    modelGroups[g.id] = grp;
  });

  specialScene.add(new THREE.AmbientLight(0x2a3550, 1.2));
  var sLight1 = new THREE.PointLight(0xeaf1fb, 3, 20); sLight1.position.set(3,3,4); specialScene.add(sLight1);
  var sLight2 = new THREE.PointLight(0x3b82f6, 2.6, 18); sLight2.position.set(-3,-1,-2); specialScene.add(sLight2);
  var sLight3 = new THREE.PointLight(0x0ea5e9, 2.2, 18); sLight3.position.set(0,2,-4); specialScene.add(sLight3);

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
    var g = modelGroups[activeGroupId];
    if (g){ g.rotation.y = t*0.9; }
    if (activeGroupId === 'phoenix'){ phoenixBodyMat.emissiveIntensity = 0.4 + Math.sin(t*8)*0.18; }
    sparks.rotation.y = -t*0.3;
    specialRenderer.render(specialScene, specialCamera);
  }
  function startSpecial(id){
    Object.keys(modelGroups).forEach(function(k){ modelGroups[k].visible = (k === id); });
    activeGroupId = id;
    resizeSpecial();
    if (!specialRAF) specialLoop();
  }
  function stopSpecial(){ if (specialRAF){ cancelAnimationFrame(specialRAF); specialRAF = null; } }

  // ---------- bank transition ----------
  var overlay = document.getElementById('transition-overlay');
  document.getElementById('go-bank-btn').addEventListener('click', function(){
    overlay.classList.add('active');
    setTimeout(function(){
      chargeBankUpkeep();
      renderTop();
      renderBank();
      document.getElementById('bank-section').scrollIntoView({behavior:'instant', block:'start'});
    }, 480);
    setTimeout(function(){ overlay.classList.remove('active'); }, 900);
  });
  document.getElementById('back-to-roulette').addEventListener('click', function(){
    overlay.classList.add('active');
    setTimeout(function(){
      document.querySelector('.roulette').scrollIntoView({behavior:'instant', block:'start'});
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
  function renderBank(){
    bankStarsVal.textContent = state.bankStars;
    coinsBankVal.textContent = state.coins;
    renderLoan();

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
          bankOffers[id] = Math.max(1, Math.round(g.sell*(0.7+Math.random()*0.4)));
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
      card.innerHTML = '<div class="ico">'+g.ico+'</div><div class="name">'+g.name+'</div><div class="price">'+buyPrice(g)+' ★</div>';
      var btn = document.createElement('button');
      btn.className = 'btn-secondary'; btn.style.marginTop = '10px'; btn.style.width = '100%';
      btn.textContent = 'Купить';
      btn.addEventListener('click', function(){
        var price = buyPrice(g);
        if (state.balance < price){ showToast('Не хватает звёзд'); return; }
        state.balance -= price;
        state.inventory[g.id] = (state.inventory[g.id]||0)+1;
        saveState(); renderTop(); renderInventory(); renderBank();
        showToast('Куплено: ' + g.name);
      });
      card.appendChild(btn);
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

  // ---------- init ----------
  chargeBankUpkeep();
  renderTop();
  renderInventory();
  renderBank();
  setInterval(function(){ chargeBankUpkeep(); renderTop(); if (document.getElementById('bank-section').getBoundingClientRect().top < window.innerHeight){ renderBank(); } }, 60*1000);
})();
</script>
</body>
</html>
