<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>TBFPUMBA — Gift Battle</title>
<meta name="description" content="Крути рулетку, выбивай гифты, копи звёзды, храни всё в банке.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Anton&family=IBM+Plex+Mono:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --bg-0:#100b07; --bg-1:#1c140d; --bg-2:#241a10;
    --rust:#d15a22; --rust-dim:#8a3f1c; --blood:#c11f3d; --gold:#e0b020;
    --bone:#ede2cf; --tan:#9c8064; --line:rgba(237,226,207,0.14);
    --c-common:#9c8064; --c-rare:#4f8fd1; --c-epic:#a04fd1; --c-legend:#e0b020; --c-mythic:#f2efe6;
  }
  *{box-sizing:border-box;margin:0;padding:0;}
  body{background:var(--bg-0);color:var(--bone);font-family:'IBM Plex Mono',monospace;line-height:1.6;}
  a{color:inherit;text-decoration:none;}
  h1,h2,h3{font-family:'Anton',sans-serif;font-weight:400;letter-spacing:0.01em;line-height:0.95;}
  button{font-family:'IBM Plex Mono',monospace;cursor:pointer;}
  input{font-family:'IBM Plex Mono',monospace;}

  .nav{display:flex;align-items:center;justify-content:space-between;padding:18px 28px;border-bottom:1px solid var(--line);flex-wrap:wrap;gap:12px;}
  .brand{font-family:'Anton',sans-serif;font-size:20px;}
  .brand span{color:var(--rust);}
  .nav-right{display:flex;align-items:center;gap:10px;flex-wrap:wrap;}
  .balance{
    display:flex;align-items:center;gap:8px;
    background:var(--bg-1);border:1px solid var(--line);
    padding:9px 16px;font-size:15px;font-weight:600;color:var(--gold);
  }
  .coin-balance{
    display:flex;align-items:center;gap:8px;
    background:var(--bg-1);border:1px solid var(--line);
    padding:9px 16px;font-size:15px;font-weight:600;color:#c98a3a;
  }
  .level-badge{
    display:flex;align-items:center;gap:8px;
    background:var(--bg-1);border:1px solid var(--line);
    padding:9px 14px;font-size:12px;color:var(--tan);
  }
  .level-badge b{color:var(--bone);}
  .bank-nav-btn{
    background:var(--bg-2);border:1px solid var(--gold);color:var(--gold);
    padding:10px 18px;font-size:13px;font-weight:600;
    transition:background .18s ease, color .18s ease, transform .18s ease, box-shadow .18s ease;
  }
  .bank-nav-btn:hover{background:var(--gold);color:var(--bg-0);transform:translateY(-2px);box-shadow:0 8px 18px rgba(224,176,32,0.35);}
  .bank-nav-btn:active{transform:translateY(0);}

  .wrap{max-width:1080px;margin:0 auto;padding:0 28px;}

  .intro{padding:28px 0 14px;max-width:620px;}
  .intro h1{font-size:clamp(28px,5vw,44px);text-transform:uppercase;}
  .intro h1 em{font-style:normal;color:var(--rust);}
  .intro p{margin-top:10px;color:var(--tan);font-size:14px;}

  .xp-bar-wrap{max-width:620px;margin:14px 0 6px;}
  .xp-bar-track{background:var(--bg-2);border:1px solid var(--line);height:8px;overflow:hidden;}
  .xp-bar-fill{background:linear-gradient(90deg, var(--rust), var(--gold));height:100%;width:0%;transition:width .3s ease;}
  .xp-label{font-size:11px;color:var(--tan);margin-top:6px;}

  /* ROULETTE */
  .roulette{padding:20px 0 50px;}
  .reel-frame{position:relative;background:var(--bg-1);border:1px solid var(--line);overflow:hidden;padding:20px 0;transition:box-shadow .3s ease, border-color .3s ease;}
  .reel-frame.spinning{box-shadow:0 0 34px rgba(209,90,34,0.35), inset 0 0 20px rgba(209,90,34,0.08);border-color:var(--rust);}
  .reel-viewport{position:relative;height:150px;overflow:hidden;}
  .reel-track{position:absolute;top:0;left:0;display:flex;will-change:transform;}
  .reel-item{width:140px;height:150px;flex:0 0 140px;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:8px;border-right:1px solid var(--line);}
  .reel-item .ico{font-size:52px;filter:drop-shadow(0 0 6px rgba(0,0,0,0.4));}
  .reel-item .rn{font-size:10px;text-transform:uppercase;color:var(--tan);}
  .rar-common .ico{color:var(--c-common);}
  .rar-rare .ico{color:var(--c-rare);}
  .rar-epic .ico{color:var(--c-epic);}
  .rar-legend .ico{color:var(--c-legend); text-shadow:0 0 18px rgba(224,176,32,0.6);}
  .rar-mythic .ico{
    color:var(--c-mythic);
    text-shadow:0 0 10px rgba(224,176,32,0.7), 0 0 22px rgba(193,31,61,0.5), 0 0 32px rgba(209,90,34,0.5);
    animation:mythicpulse 2.2s ease-in-out infinite;
  }
  @keyframes mythicpulse{0%,100%{filter:brightness(1);}50%{filter:brightness(1.35);}}

  .pointer{position:absolute;top:0;bottom:0;left:50%;width:2px;background:var(--blood);transform:translateX(-1px);z-index:3;}
  .pointer::before, .pointer::after{content:"";position:absolute;left:50%;transform:translateX(-50%);border:8px solid transparent;}
  .pointer::before{top:-2px;border-top-color:var(--blood);border-bottom:0;}
  .pointer::after{bottom:-2px;border-bottom-color:var(--blood);border-top:0;}

  .fade-l, .fade-r{position:absolute;top:0;bottom:0;width:80px;z-index:2;pointer-events:none;}
  .fade-l{left:0;background:linear-gradient(90deg, var(--bg-1), transparent);}
  .fade-r{right:0;background:linear-gradient(-90deg, var(--bg-1), transparent);}

  .spin-row{margin-top:18px;}
  .spin-buttons{display:flex;gap:10px;flex-wrap:wrap;}
  .btn-primary{
    background:linear-gradient(135deg, var(--blood), #9c1730);
    color:var(--bone);border:none;
    padding:15px 24px;font-weight:600;font-size:14px;
    clip-path:polygon(0 0,100% 0,100% 70%,94% 100%,0 100%);
    transition:transform .18s ease, box-shadow .18s ease, background .18s ease;
    flex:1;min-width:130px;
    box-shadow:0 4px 14px rgba(193,31,61,0.25);
  }
  .btn-primary:hover{background:linear-gradient(135deg, #e2264a, var(--blood));transform:translateY(-3px);box-shadow:0 10px 22px rgba(193,31,61,0.4);}
  .btn-primary:active{transform:translateY(0);box-shadow:0 4px 10px rgba(193,31,61,0.3);}
  .btn-primary:disabled{background:var(--bg-2);color:var(--tan);cursor:not-allowed;box-shadow:none;transform:none;}
  .odds{font-size:12px;color:var(--tan);margin-top:12px;}
  .odds b{color:var(--bone);}

  /* PROFILE */
  .profile{padding:20px 0 60px;}
  .section-head{display:flex;align-items:baseline;justify-content:space-between;margin-bottom:22px;flex-wrap:wrap;gap:10px;}
  .section-head h2{font-size:clamp(26px,4vw,36px);text-transform:uppercase;}
  .section-head p{font-size:13px;color:var(--tan);}
  .empty-state{border:1px dashed var(--line);padding:40px;text-align:center;color:var(--tan);font-size:14px;}
  .inv-grid{display:grid;grid-template-columns:repeat(auto-fill, minmax(150px, 1fr));gap:14px;}
  .gift-card{background:var(--bg-1);border:1px solid var(--line);padding:20px 14px;text-align:center;cursor:pointer;transition:transform .18s ease, border-color .18s ease, box-shadow .18s ease;position:relative;}
  .gift-card:hover{transform:translateY(-6px);border-color:var(--rust);box-shadow:0 12px 24px rgba(0,0,0,0.35);}
  .gift-card .ico{font-size:44px;display:inline-block;animation:bob 3s ease-in-out infinite;}
  .gift-card.rar-legend .ico{animation:spin3d 3.5s linear infinite;}
  .gift-card.rar-mythic .ico{animation:spin3d 3.5s linear infinite, mythicpulse 2.2s ease-in-out infinite;}
  .gift-card.rar-mythic{border-color:var(--c-mythic);}
  .gift-card .name{margin-top:10px;font-size:12px;color:var(--bone);}
  .gift-card .count{position:absolute;top:8px;right:8px;background:var(--bg-2);border:1px solid var(--line);font-size:11px;padding:2px 7px;color:var(--tan);}
  @keyframes bob{0%,100%{transform:translateY(0);}50%{transform:translateY(-6px);}}
  @keyframes spin3d{from{transform:rotateY(0deg);}to{transform:rotateY(360deg);}}

  /* BANK */
  .bank-section{padding:30px 0 80px;border-top:1px solid var(--line);}
  .bank-back{font-size:12px;color:var(--tan);border:1px solid var(--line);padding:8px 14px;display:inline-block;margin-bottom:22px;transition:border-color .15s ease,color .15s ease;}
  .bank-back:hover{border-color:var(--gold);color:var(--gold);}
  .bank-block{background:var(--bg-1);border:1px solid var(--line);padding:24px;margin-bottom:20px;}
  .bank-block h3{font-size:13px;text-transform:uppercase;color:var(--tan);margin-bottom:16px;letter-spacing:0.05em;}
  .bank-stars-row{display:flex;align-items:center;gap:14px;flex-wrap:wrap;}
  .bank-stars-amt{font-family:'Anton',sans-serif;font-size:26px;color:var(--gold);}
  .bank-input-row{display:flex;gap:10px;flex-wrap:wrap;align-items:center;margin-top:14px;}
  .bank-input-row input[type="number"]{
    width:110px;background:var(--bg-2);border:1px solid var(--line);color:var(--bone);padding:9px 10px;font-size:13px;
  }
  .bank-list{display:flex;flex-direction:column;gap:10px;}
  .bank-row{
    display:flex;align-items:center;justify-content:space-between;gap:10px;flex-wrap:wrap;
    background:var(--bg-2);border:1px solid var(--line);padding:12px 14px;
    transition:border-color .18s ease, transform .18s ease;
  }
  .bank-row:hover{border-color:var(--rust-dim);transform:translateX(2px);}
  .bank-row-left{display:flex;align-items:center;gap:12px;}
  .bank-row-left .ico{font-size:26px;}
  .bank-row-meta{font-size:11px;color:var(--tan);}
  .bank-row-name{font-size:13px;color:var(--bone);}

  .shop-grid{display:grid;grid-template-columns:repeat(auto-fill, minmax(180px,1fr));gap:12px;}
  .shop-card{background:var(--bg-2);border:1px solid var(--line);padding:16px;text-align:center;transition:transform .18s ease, border-color .18s ease, box-shadow .18s ease;}
  .shop-card:hover{transform:translateY(-4px);border-color:var(--gold);box-shadow:0 10px 20px rgba(0,0,0,0.3);}
  .shop-card .ico{font-size:34px;}
  .shop-card .name{font-size:12px;margin-top:6px;color:var(--bone);}
  .shop-card .price{font-size:12px;color:var(--gold);margin-top:6px;}

  .promo-row{display:flex;gap:10px;flex-wrap:wrap;}
  .promo-row input[type="text"]{
    flex:1;min-width:200px;background:var(--bg-2);border:1px solid var(--line);color:var(--bone);padding:11px 12px;font-size:13px;
  }

  .btn-secondary{border:1px solid var(--rust);background:transparent;color:var(--bone);padding:10px 16px;font-size:12px;transition:background .18s ease,color .18s ease,transform .18s ease,box-shadow .18s ease;white-space:nowrap;}
  .btn-secondary:hover{background:var(--rust);color:var(--bg-0);transform:translateY(-2px);box-shadow:0 6px 14px rgba(209,90,34,0.25);}
  .btn-secondary:active{transform:translateY(0);}
  .btn-secondary.gold{border-color:var(--gold);color:var(--gold);}
  .btn-secondary.gold:hover{background:var(--gold);color:var(--bg-0);box-shadow:0 6px 14px rgba(224,176,32,0.3);}

  /* MODAL (single gift) */
  .modal-overlay{position:fixed;inset:0;background:rgba(16,11,7,0.86);display:flex;align-items:center;justify-content:center;z-index:50;padding:20px;
    opacity:0;transition:opacity .22s ease;}
  .modal-overlay.hidden{display:none;opacity:0;}
  .modal-overlay.visible{opacity:1;}
  .modal-card{background:var(--bg-1);border:1px solid var(--line);max-width:420px;width:100%;padding:34px 30px;text-align:center;position:relative;
    transform:scale(0.9) translateY(14px);transition:transform .22s cubic-bezier(0.2,0.9,0.3,1.3);box-shadow:0 20px 50px rgba(0,0,0,0.45);}
  .modal-overlay.visible .modal-card{transform:scale(1) translateY(0);}
  .modal-close{position:absolute;top:14px;right:14px;background:transparent;border:1px solid var(--line);color:var(--bone);width:30px;height:30px;font-size:16px;line-height:1;}
  .modal-rar{font-size:11px;text-transform:uppercase;letter-spacing:0.08em;}
  .modal-ico{font-size:88px;margin:18px 0;animation:bob 3s ease-in-out infinite;}
  .modal-card.has-special .modal-ico{display:none;}
  #special-canvas{width:100%;height:220px;display:none;}
  .modal-card.has-special #special-canvas{display:block;}
  .modal-name{font-family:'Anton',sans-serif;font-size:26px;text-transform:uppercase;margin-top:8px;}
  .modal-desc{font-size:13px;color:var(--tan);margin-top:8px;}
  .modal-actions{display:flex;gap:12px;justify-content:center;margin-top:24px;flex-wrap:wrap;}

  /* BATCH MODAL */
  .batch-overlay{position:fixed;inset:0;background:rgba(16,11,7,0.9);display:flex;align-items:center;justify-content:center;z-index:55;padding:20px;
    opacity:0;transition:opacity .22s ease;}
  .batch-overlay.hidden{display:none;opacity:0;}
  .batch-overlay.visible{opacity:1;}
  .batch-card{background:var(--bg-1);border:1px solid var(--line);max-width:640px;width:100%;padding:30px;max-height:82vh;overflow:auto;
    transform:scale(0.92) translateY(14px);transition:transform .22s cubic-bezier(0.2,0.9,0.3,1.3);box-shadow:0 20px 50px rgba(0,0,0,0.45);}
  .batch-overlay.visible .batch-card{transform:scale(1) translateY(0);}
  .batch-card h3{font-size:22px;text-transform:uppercase;margin-bottom:6px;}
  .batch-sub{font-size:12px;color:var(--tan);margin-bottom:18px;}
  .batch-grid{display:grid;grid-template-columns:repeat(auto-fill, minmax(120px,1fr));gap:10px;}
  .batch-item{background:var(--bg-2);border:1px solid var(--line);padding:14px 8px;text-align:center;animation:popin .35s ease both;}
  .batch-item .ico{font-size:34px;}
  .batch-item .name{font-size:11px;margin-top:6px;color:var(--bone);}
  @keyframes popin{from{opacity:0;transform:scale(0.7);}to{opacity:1;transform:scale(1);}}
  .batch-actions{margin-top:20px;text-align:right;}

  /* TRANSITION */
  .transition-overlay{
    position:fixed;inset:0;z-index:100;pointer-events:none;
    background:radial-gradient(circle, var(--gold) 0%, var(--rust-dim) 45%, var(--bg-0) 75%);
    clip-path:circle(0% at 50% 40%);
    transition:clip-path .55s cubic-bezier(0.6,0,0.3,1);
  }
  .transition-overlay.active{clip-path:circle(150% at 50% 40%);}

  .toast{
    position:fixed;bottom:24px;left:50%;transform:translateX(-50%);
    background:var(--bg-2);border:1px solid var(--rust);color:var(--bone);
    padding:12px 22px;font-size:13px;z-index:60;opacity:0;
    transition:opacity .25s ease, transform .25s ease;pointer-events:none;text-align:center;max-width:88vw;
  }
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
    <p>Крути рулетку за звёзды, собирай гифты в профиль, храни их в банке, покупай новые или продавай. Звёзды не настоящие — это только внутриигровая валюта.</p>
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
      <div class="odds">common <b>~52%</b> · rare <b>~28%</b> · epic <b>~16%</b> · legend <b>~3%</b> · mythic <b>~0.8%</b></div>
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
    <p>Храни, покупай, продавай, активируй промокоды</p>
  </div>

  <div class="bank-block">
    <h3>Обмен валют · курс 1 🪙 = 2 ★</h3>
    <div class="bank-stars-row">
      <div>Монет у тебя: <span class="bank-stars-amt" id="coins-bank-val">0</span> 🪙</div>
    </div>
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
    <div class="bank-stars-row">
      <div>В банке: <span class="bank-stars-amt" id="bank-stars-val">0</span> ★</div>
    </div>
    <div class="bank-input-row">
      <input type="number" id="bank-star-amt" placeholder="кол-во" min="1">
      <button class="btn-secondary gold" id="bank-deposit-star">Положить</button>
      <button class="btn-secondary gold" id="bank-withdraw-star">Забрать</button>
    </div>
  </div>

  <div class="bank-block">
    <h3>Хранилище гифтов · 2 ★ / день за штуку</h3>
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
    {id:'cup',     name:'Золотой кубок',   ico:'🏆', rarity:'legend', weight:1.8,  sell:900,  desc:'Для лучших из лучших.'},
    {id:'diamond', name:'Бриллиант',       ico:'💎', rarity:'legend', weight:1.2,  sell:1100, desc:'Огранка ручной работы.'},
    {id:'eagle',   name:'Орёл',            ico:'🦅', rarity:'legend', weight:1.5,  sell:950,  desc:'Смотрит на всё свысока.'},
    {id:'amulet',  name:'Оберег',          ico:'🧿', rarity:'legend', weight:1,    sell:1050, desc:'Отводит беду.'},
    {id:'statue',  name:'MOGH',            ico:'🗿', rarity:'mythic', weight:0.5,  sell:3000, desc:'Одна из самых редких вещей в игре. 3D-модель на постаменте.'},
    {id:'cactus',  name:'Кактус',          ico:'🌵', rarity:'mythic', weight:0.3,  sell:3200, desc:'Один из самых редких предметов в игре. Свой 3D-горшок и анимация.'},
    {id:'demon',   name:'Демон',           ico:'👹', rarity:'mythic', weight:0.25, sell:3400, desc:'Появляется реже всех. Лучше не злить.'}
  ];
  var RARITY_LABEL = {common:'COMMON', rare:'RARE', epic:'EPIC', legend:'LEGENDARY', mythic:'MYTHIC'};
  var SPECIAL_MODELS = {statue:true, cactus:true};
  var STORE_KEY = 'tbfpumba_gift_battle_v2';
  var DAY_MS = 24*60*60*1000;
  var PROMO_CODES = {
    '6666209752': {cactus:1, statue:1, diamond:1}
  };

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
        s.balance = s.balance || 0;
        s.bankStars = s.bankStars || 0;
        s.coins = s.coins || 0;
        s.xp = s.xp || 0;
        s.inventory = s.inventory || {};
        s.bankGifts = s.bankGifts || [];
        s.redeemedCodes = s.redeemedCodes || [];
        return s;
      }
    }catch(e){}
    return {balance:500, bankStars:0, coins:0, xp:0, inventory:{}, bankGifts:[], redeemedCodes:[]};
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
      var days = Math.floor((now - entry.lastChargeAt)/DAY_MS);
      if (days > 0){
        var cost = days*2;
        var deduct = Math.min(state.balance, cost);
        state.balance -= deduct;
        entry.lastChargeAt += days*DAY_MS;
        changed = true;
      }
    });
    if (changed) saveState();
  }

  // ---------- dom refs ----------
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
    modalCard.className = 'modal-card rar-' + g.rarity + (SPECIAL_MODELS[g.id] ? ' has-special' : '');
    modalRar.textContent = (justWon ? 'НОВЫЙ ГИФТ · ' : '') + RARITY_LABEL[g.rarity];
    modalIco.textContent = g.ico;
    modalName.textContent = g.name;
    modalDesc.textContent = g.desc;
    modalSellVal.textContent = g.sell;
    modalSellCoinVal.textContent = coinSellPrice(g);
    modal.classList.remove('hidden');
    requestAnimationFrame(function(){ modal.classList.add('visible'); });
    if (SPECIAL_MODELS[g.id]){ startSpecial(g.id); } else { stopSpecial(); }
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

  // ---------- 3D special models (statue / cactus) ----------
  var specialCanvas = document.getElementById('special-canvas');
  var specialRenderer = new THREE.WebGLRenderer({canvas:specialCanvas, antialias:true, alpha:true});
  specialRenderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));
  var specialScene = new THREE.Scene();
  var specialCamera = new THREE.PerspectiveCamera(40, 1, 0.1, 30);
  specialCamera.position.set(0, 0.6, 6);

  var goldMat = new THREE.MeshStandardMaterial({color:0xe0b020, metalness:1, roughness:0.28});
  var darkMat = new THREE.MeshStandardMaterial({color:0x3a2a12, metalness:0.6, roughness:0.5});
  var greenMat = new THREE.MeshStandardMaterial({color:0x3f8f4a, roughness:0.55, flatShading:true});
  var greenMatDark = new THREE.MeshStandardMaterial({color:0x2e6b38, roughness:0.55, flatShading:true});
  var potMat = new THREE.MeshStandardMaterial({color:0xb05a2c, roughness:0.7});
  var flowerMat = new THREE.MeshStandardMaterial({color:0xd1507a, emissive:0x3a0f1e, roughness:0.4});

  function buildStatueGroup(){
    var group = new THREE.Group();
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

  function buildCactusGroup(){
    var group = new THREE.Group();
    var pot = new THREE.Mesh(new THREE.CylinderGeometry(0.5, 0.65, 0.55, 12), potMat);
    pot.position.y = -1.35; group.add(pot);
    var potRim = new THREE.Mesh(new THREE.TorusGeometry(0.5, 0.05, 8, 20), new THREE.MeshStandardMaterial({color:0x8a3f1c, roughness:0.6}));
    potRim.rotation.x = Math.PI/2; potRim.position.y = -1.08; group.add(potRim);
    var body = new THREE.Mesh(new THREE.CylinderGeometry(0.32, 0.42, 1.6, 10), greenMat);
    body.position.y = -0.25; group.add(body);
    var topCap = new THREE.Mesh(new THREE.SphereGeometry(0.32, 10, 10), greenMat);
    topCap.position.y = 0.55; group.add(topCap);

    function arm(x, rotZ){
      var g = new THREE.Group();
      var seg = new THREE.Mesh(new THREE.CylinderGeometry(0.13, 0.16, 0.7, 8), greenMatDark);
      seg.position.set(0, 0.35, 0);
      g.add(seg);
      var cap = new THREE.Mesh(new THREE.SphereGeometry(0.13, 8, 8), greenMatDark);
      cap.position.set(0, 0.7, 0);
      g.add(cap);
      g.position.set(x, -0.1, 0);
      g.rotation.z = rotZ;
      return g;
    }
    group.add(arm(-0.45, Math.PI*0.18));
    group.add(arm(0.45, -Math.PI*0.18));

    var flower = new THREE.Mesh(new THREE.SphereGeometry(0.12, 10, 10), flowerMat);
    flower.position.y = 0.92; group.add(flower);
    return group;
  }

  var statueGroup = buildStatueGroup();
  var cactusGroup = buildCactusGroup();
  specialScene.add(statueGroup, cactusGroup);
  cactusGroup.visible = false;

  specialScene.add(new THREE.AmbientLight(0x3a2a1a, 1.2));
  var sLight1 = new THREE.PointLight(0xffe8cf, 3, 20); sLight1.position.set(3,3,4); specialScene.add(sLight1);
  var sLight2 = new THREE.PointLight(0xc11f3d, 2.4, 18); sLight2.position.set(-3,-1,-2); specialScene.add(sLight2);
  var sLight3 = new THREE.PointLight(0xd15a22, 2.2, 18); sLight3.position.set(0,2,-4); specialScene.add(sLight3);

  var sparkCount = 60;
  var sparkGeo = new THREE.BufferGeometry();
  var sparkPos = new Float32Array(sparkCount*3);
  for (var i=0;i<sparkCount;i++){
    var a = Math.random()*Math.PI*2, r = 1.6 + Math.random()*0.8, y = (Math.random()-0.5)*3;
    sparkPos[i*3] = Math.cos(a)*r; sparkPos[i*3+1] = y; sparkPos[i*3+2] = Math.sin(a)*r;
  }
  sparkGeo.setAttribute('position', new THREE.BufferAttribute(sparkPos, 3));
  var sparkMat = new THREE.PointsMaterial({color:0xe0b020, size:0.05, transparent:true, opacity:0.8, blending:THREE.AdditiveBlending, depthWrite:false});
  var sparks = new THREE.Points(sparkGeo, sparkMat);
  specialScene.add(sparks);

  var specialRAF = null;
  var specialClock = new THREE.Clock();
  function resizeSpecial(){
    var w = specialCanvas.clientWidth || 380, h = specialCanvas.clientHeight || 220;
    specialRenderer.setSize(w, h, false);
    specialCamera.aspect = w/h; specialCamera.updateProjectionMatrix();
  }
  function specialLoop(){
    specialRAF = requestAnimationFrame(specialLoop);
    if (specialCanvas.clientWidth !== specialCanvas.width || specialCanvas.clientHeight !== specialCanvas.height){ resizeSpecial(); }
    var t = specialClock.getElapsedTime();
    statueGroup.rotation.y = t*0.9;
    cactusGroup.rotation.y = t*0.9;
    sparks.rotation.y = -t*0.3;
    specialRenderer.render(specialScene, specialCamera);
  }
  function startSpecial(id){
    statueGroup.visible = (id === 'statue');
    cactusGroup.visible = (id === 'cactus');
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
    state.balance -= cost;
    state.coins += amt;
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
    state.coins -= amt;
    state.balance += starsGained;
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

  var bankOffers = {};
  var bankCoinOffers = {};
  function renderBank(){
    bankStarsVal.textContent = state.bankStars;
    coinsBankVal.textContent = state.coins;

    // stored gifts
    var giftsListEl = document.getElementById('bank-gifts-list');
    var giftsEmptyEl = document.getElementById('bank-gifts-empty');
    giftsListEl.innerHTML = '';
    if (state.bankGifts.length === 0){ giftsEmptyEl.style.display='block'; giftsListEl.style.display='none'; }
    else{
      giftsEmptyEl.style.display='none'; giftsListEl.style.display='flex';
      state.bankGifts.forEach(function(entry){
        var g = byId(entry.id); if (!g) return;
        var days = Math.floor((Date.now()-entry.storedAt)/DAY_MS);
        var row = document.createElement('div');
        row.className = 'bank-row';
        row.innerHTML =
          '<div class="bank-row-left"><div class="ico">'+g.ico+'</div><div><div class="bank-row-name">'+g.name+'</div>'+
          '<div class="bank-row-meta">хранится '+days+' дн. · 2★/день</div></div></div>';
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

    // deposit from inventory
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

    // sell to bank
    var sellListEl = document.getElementById('sellbank-list');
    var sellEmptyEl = document.getElementById('sellbank-empty');
    sellListEl.innerHTML = '';
    if (invIds.length === 0){ sellEmptyEl.style.display='block'; sellListEl.style.display='none'; }
    else{
      sellEmptyEl.style.display='none'; sellListEl.style.display='flex';
      invIds.forEach(function(id){
        var g = byId(id); if (!g) return;
        if (bankOffers[id] === undefined){
          var factor = 0.7 + Math.random()*0.4;
          bankOffers[id] = Math.max(1, Math.round(g.sell*factor));
        }
        if (bankCoinOffers[id] === undefined){
          var coinFactor = 0.7 + Math.random()*0.4;
          bankCoinOffers[id] = Math.max(1, Math.round(coinSellPrice(g)*coinFactor));
        }
        var offer = bankOffers[id];
        var coinOffer = bankCoinOffers[id];
        var row = document.createElement('div');
        row.className = 'bank-row';
        row.innerHTML = '<div class="bank-row-left"><div class="ico">'+g.ico+'</div><div><div class="bank-row-name">'+g.name+'</div><div class="bank-row-meta">предложение: '+offer+' ★ или '+coinOffer+' 🪙</div></div></div>';
        var btnWrap = document.createElement('div');
        btnWrap.style.display = 'flex';
        btnWrap.style.gap = '8px';
        var btn = document.createElement('button');
        btn.className = 'btn-secondary gold';
        btn.textContent = 'За ★';
        btn.addEventListener('click', function(){
          if (!state.inventory[id] || state.inventory[id] <= 0) return;
          state.inventory[id] -= 1;
          state.balance += bankOffers[id];
          delete bankOffers[id]; delete bankCoinOffers[id];
          saveState(); renderTop(); renderInventory(); renderBank();
          showToast('Банк купил гифт за ' + offer + ' ★');
        });
        var btnCoin = document.createElement('button');
        btnCoin.className = 'btn-secondary';
        btnCoin.textContent = 'За 🪙';
        btnCoin.addEventListener('click', function(){
          if (!state.inventory[id] || state.inventory[id] <= 0) return;
          state.inventory[id] -= 1;
          state.coins += bankCoinOffers[id];
          delete bankOffers[id]; delete bankCoinOffers[id];
          saveState(); renderTop(); renderInventory(); renderBank();
          showToast('Банк купил гифт за ' + coinOffer + ' 🪙');
        });
        btnWrap.appendChild(btn);
        btnWrap.appendChild(btnCoin);
        row.appendChild(btnWrap);
        sellListEl.appendChild(row);
      });
    }

    // shop
    var shopGrid = document.getElementById('shop-grid');
    shopGrid.innerHTML = '';
    GIFTS.forEach(function(g){
      var card = document.createElement('div');
      card.className = 'shop-card';
      card.innerHTML = '<div class="ico">'+g.ico+'</div><div class="name">'+g.name+'</div><div class="price">'+buyPrice(g)+' ★</div>';
      var btn = document.createElement('button');
      btn.className = 'btn-secondary';
      btn.style.marginTop = '10px';
      btn.style.width = '100%';
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

  // ---------- promo codes ----------
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
  setInterval(function(){ chargeBankUpkeep(); renderTop(); }, 5*60*1000);
})();
</script>
</body>
</html>
