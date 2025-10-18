<!doctype html>
<html lang="ru">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Чат-бот — Визитка</title>
  <style>
    /* Reset + base */
    *{box-sizing:border-box;margin:0;padding:0}
    html,body,#root{height:100%}
    body{font-family:Inter,ui-sans-serif,system-ui,-apple-system,'Segoe UI',Roboto,'Helvetica Neue',Arial; background:linear-gradient(180deg,#f8fafc,#ffffff 40%,#f1f5f9); color:#0f172a; -webkit-font-smoothing:antialiased; overflow-x:hidden}
    .container{max-width:1100px;margin:0 auto;padding:0 20px}

    /* Header */
    header{padding:22px 0; position:relative; z-index:10}
    .brand{display:flex;align-items:center;gap:14px}
    .logo{width:48px;height:48px;border-radius:999px;background:linear-gradient(135deg,#6366f1,#ec4899);display:flex;align-items:center;justify-content:center;color:#fff;font-weight:700;box-shadow:0 10px 30px rgba(99,102,241,0.12);backdrop-filter:blur(6px)}
    nav{display:flex;gap:18px;align-items:center}
    nav a{color:inherit;text-decoration:none;font-size:14px;opacity:0.9}
    .menu-btn{display:none}

    /* Hero */
    .hero{display:flex;gap:40px;align-items:center;padding:48px 0;position:relative;z-index:10}
    .col{flex:1}
    h1{font-size:34px;line-height:1.02;margin-bottom:12px}
    p.lead{color:#475569;margin-top:8px}
    ul.points{margin-top:18px;list-style:none;display:block}
    ul.points li{display:flex;gap:10px;align-items:flex-start;margin-bottom:10px;color:#334155}
    .dot{color:#6366f1;font-weight:700;margin-top:2px}

    /* Buttons - iPhone style */
    .btn{display:inline-flex;align-items:center;justify-content:center;gap:8px;padding:12px 18px;border-radius:18px;font-weight:700;cursor:pointer;text-decoration:none}
    .btn-primary{background:linear-gradient(90deg,#6366f1,#ec4899);color:white;box-shadow:0 8px 30px rgba(99,102,241,0.15)}
    .btn-outline{background:transparent;border:1px solid rgba(15,23,42,0.08);padding:10px 16px;font-weight:600;border-radius:18px}
    .btn-secondary{background:linear-gradient(90deg,#ff8a00,#ff5e7a);color:#fff;box-shadow:0 8px 20px rgba(254,120,26,0.08)}

    /* Glass card */
    .glass-wrap{max-width:420px;margin:0 auto;position:relative}
    .glass{
      position:relative;
      background:rgba(255,255,255,0.14);
      border:1px solid rgba(255,255,255,0.12);
      backdrop-filter:blur(10px);
      padding:20px;border-radius:18px;box-shadow:0 12px 40px rgba(2,6,23,0.06);color:#fff;
    }
    .glass .meta{display:flex;gap:12px;align-items:center;margin-bottom:12px}
    .avatar{width:48px;height:48px;border-radius:999px;background:rgba(255,255,255,0.6);display:flex;align-items:center;justify-content:center;color:#0f172a;font-weight:700}

    /* small text inside */
    .muted{color:rgba(255,255,255,0.85);font-size:13px}
    .chat-bubble{background:rgba(255,255,255,0.06);padding:10px;border-radius:12px;color:rgba(255,255,255,0.95);font-size:14px}
    .chat-bubble.primary{background:linear-gradient(90deg,#4f46e5,#ec4899);color:#fff;display:inline-block}

    /* Footer */
    footer{padding:28px 0;position:relative;z-index:10}
    .footer-box{background:rgba(255,255,255,0.14);border-radius:12px;padding:16px;border:1px solid rgba(255,255,255,0.12);backdrop-filter:blur(8px);display:flex;justify-content:space-between;align-items:center;gap:20px}

    /* Stickers (background) */
    .stickers{position:absolute;inset:0;pointer-events:none;z-index:0}
    .sticker{position:absolute;font-size:36px;opacity:0.95;filter:drop-shadow(0 10px 30px rgba(2,6,23,0.06))}
    .s1{left:5%;top:8%;animation:float 8s ease-in-out infinite}
    .s2{right:8%;top:16%;animation:floatReverse 10s ease-in-out infinite}
    .s3{left:18%;bottom:14%;animation:float 12s ease-in-out infinite}
    .s4{right:18%;bottom:22%;animation:floatReverse 9s ease-in-out infinite}
    .s5{left:50%;top:6%;transform:translateX(-50%);animation:float 11s ease-in-out infinite}
    .s6{left:10%;top:50%;animation:spinFloat 14s linear infinite}
    .s7{right:6%;top:50%;animation:floatReverse 13s ease-in-out infinite}

    @keyframes float{
      0%{transform:translateY(0) translateX(0) rotate(0deg)}
      50%{transform:translateY(-20px) translateX(6px) rotate(6deg)}
      100%{transform:translateY(0) translateX(0) rotate(0deg)}
    }
    @keyframes floatReverse{
      0%{transform:translateY(0) translateX(0) rotate(0deg)}
      50%{transform:translateY(-18px) translateX(-6px) rotate(-6deg)}
      100%{transform:translateY(0) translateX(0) rotate(0deg)}
    }
    @keyframes spinFloat{
      0%{transform:translateY(0) rotate(0deg)}
      50%{transform:translateY(-16px) rotate(180deg)}
      100%{transform:translateY(0) rotate(360deg)}
    }

    /* Responsive */
    @media (max-width:900px){
      .hero{flex-direction:column-reverse;padding:30px 0}
      nav{display:none}
      .menu-btn{display:inline-flex}
      .stickers{display:none}
      h1{font-size:28px}
    }
  </style>
</head>
<body>
  <div class="stickers" aria-hidden="true">
    <div class="sticker s1">💳</div>
    <div class="sticker s2">📇</div>
    <div class="sticker s3">💼</div>
    <div class="sticker s4">📈</div>
    <div class="sticker s5">💬</div>
    <div class="sticker s6">💵</div>
    <div class="sticker s7">📞</div>
  </div>

  <header class="container">
    <div style="display:flex;align-items:center;justify-content:space-between">
      <div class="brand">
        <div class="logo">CB</div>
        <div>
          <div style="font-weight:600">Чат-бот — Визитка</div>
          <div style="font-size:12px;color:#64748b">Быстро. Просто. Работает как положено.</div>
        </div>
      </div>

      <nav>
        <a href="#features">Фичи</a>
        <a href="#pricing">Тарифы</a>
        <a href="#demo">Демо</a>
        <a class="btn" href="https://t.me/ramazanvizbot" target="_blank" rel="noopener noreferrer">Связаться</a>
      </nav>
    </div>
  </header>

  <main class="container hero">
    <div class="col">
      <h1>Чат-бот-визитка для бизнеса и людей — 24/7</h1>
      <p class="lead">У тебя есть контакты, услуги или товары — бот покажет их, ответит на вопросы, соберёт лиды и даже примет оплату (если надо). Работает в Telegram, WhatsApp и на сайте.</p>

      <ul class="points">
        <li><span class="dot">●</span><span>Быстрый старт — настройка за 1–3 дня.</span></li>
        <li><span class="dot">●</span><span>Сбор лидов, автосообщения, витрина услуг.</span></li>
        <li><span class="dot">●</span><span>Интеграции: CRM, платежи, Google/Яндекс.</span></li>
      </ul>

      <div style="margin-top:18px;display:flex;gap:12px;flex-wrap:wrap">
        <a class="btn btn-primary" href="https://t.me/ramazanvizbot" target="_blank" rel="noopener noreferrer">Заказать бот</a>
        <a class="btn btn-outline" href="https://t.me/ramazanvizbot" target="_blank" rel="noopener noreferrer">Посмотреть демо</a>
        <a class="btn btn-secondary" href="https://t.me/ramazanvizbot" target="_blank" rel="noopener noreferrer">Ознакомиться с шаблонами</a>
      </div>

      <p style="margin-top:14px;color:#64748b;font-size:13px">Цена от 15 000 ₽/мес — без генеральской болтовни. Индивидуально — договоримся.</p>
    </div>

    <div class="col glass-wrap">
      <div style="position:absolute;inset:-6px;border-radius:20px;filter:blur(18px);background:linear-gradient(90deg,rgba(255,255,255,0.16),rgba(255,255,255,0.04));z-index:0"></div>
      <div class="glass" role="region" aria-label="Демо чат-бот">
        <div class="meta">
          <div class="avatar">🤖</div>
          <div>
            <div style="font-weight:600">Bot-Vizitka</div>
            <div class="muted" style="font-size:12px;margin-top:2px">Онлайн — отвечает за секунды</div>
          </div>
        </div>

        <div style="display:flex;flex-direction:column;gap:10px">
          <div class="chat-bubble muted">Привет! Я бот-визитка. Чем могу помочь?</div>
          <div class="chat-bubble primary">Хочу прайс на услугу</div>
          <div class="chat-bubble muted">Отлично — выбери раздел: Услуги / Контакты / Записаться</div>
        </div>

        <div style="display:flex;gap:8px;margin-top:12px">
          <a class="btn" style="flex:1;background:rgba(255,255,255,0.08);border-radius:12px;border:1px solid rgba(255,255,255,0.08);color:#fff;text-align:center" href="https://t.me/ramazanvizbot" target="_blank" rel="noopener noreferrer">Услуги</a>
          <a class="btn" style="flex:1;background:rgba(255,255,255,0.08);border-radius:12px;border:1px solid rgba(255,255,255,0.08);color:#fff;text-align:center" href="https://t.me/ramazanvizbot" target="_blank" rel="noopener noreferrer">Контакты</a>
        </div>

        <div style="margin-top:10px;font-size:12px;color:rgba(255,255,255,0.9)">Ознакомиться с шаблонами: <a href="https://t.me/ramazanvizbot" target="_blank" rel="noopener noreferrer" style="color:#fff;text-decoration:underline">@ramazanvizbot</a></div>
      </div>
    </div>
  </main>

  <section id="features" class="container" style="padding:30px 0 10px 0">
    <h2 style="font-size:20px;margin-bottom:10px">Что умеет бот</h2>
    <div style="display:grid;grid-template-columns:repeat(3,1fr);gap:12px">
      <div style="background:#fff;border-radius:10px;padding:14px;box-shadow:0 6px 18px rgba(2,6,23,0.04)">Витрина услуг — покажи товары и цены</div>
      <div style="background:#fff;border-radius:10px;padding:14px;box-shadow:0 6px 18px rgba(2,6,23,0.04)">Сбор лидов — CRM / почта / Google Sheets</div>
      <div style="background:#fff;border-radius:10px;padding:14px;box-shadow:0 6px 18px rgba(2,6,23,0.04)">Автоответы и сценарии под продажи</div>
    </div>
  </section>

  <footer class="container" style="padding-top:20px;padding-bottom:60px">
    <div class="footer-box">
      <div>© <span id="year"></span> Чат-бот Визитка — Сделано быстро и по делу.</div>
      <div>Telegram: <a href="https://t.me/ramazanvizbot" target="_blank" rel="noopener noreferrer" style="color:#0ea5e9;text-decoration:underline">@ramazanvizbot</a></div>
    </div>
  </footer>

  <script>
    // make sure year shows current
    document.getElementById('year').textContent = new Date().getFullYear();

    // All anchor buttons already point to t.me link.
    // Extra: open link in new window on click for buttons (if user clicks)
    // (Not needed, anchors use target="_blank", but left here in case you want JS)
    (function(){
      // noop for future hooks
    })();
  </script>
</body>
</html>
