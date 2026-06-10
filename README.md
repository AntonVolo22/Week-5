<!DOCTYPE html>
<html lang="et">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>404 — Cafe 89°</title>
<link rel="icon" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><text y='.9em' font-size='90'>☕</text></svg>"/>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=DM+Sans:opsz,wght@9..40,300;9..40,400;9..40,500&display=swap" rel="stylesheet"/>
<style>
:root{
  --cream:#F5F0E8;--espresso:#1A0F08;--coffee:#3D2314;--coffee-mid:#4A2A18;
  --gold:#C9A96E;--gold-hover:#D4B07D;--gold-light:#E8D5B0;
  --bark:#7A4F2F;--mist:#9E9189;
  --serif:'Cormorant Garamond',Georgia,serif;
  --sans:'DM Sans',system-ui,sans-serif;
  --ease:cubic-bezier(.22,1,.36,1);
}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html,body{height:100%;-webkit-font-smoothing:antialiased}

body{
  font-family:var(--sans);
  background:var(--espresso);
  color:var(--cream);
  display:flex;
  flex-direction:column;
  align-items:center;
  justify-content:center;
  min-height:100svh;
  overflow:hidden;
  position:relative;
  padding:2rem;
}

/* ── BACKGROUND ── */
.bg{
  position:fixed;inset:0;
  background:radial-gradient(ellipse 80% 65% at 50% 55%, #3D2314 0%, #1A0F08 68%);
  z-index:0;
}
.noise{
  position:fixed;inset:0;opacity:.035;z-index:0;
  background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 300 300' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='f'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23f)'/%3E%3C/svg%3E");
  background-size:220px;
}

/* ── RINGS ── */
.rings{position:fixed;inset:0;display:flex;align-items:center;justify-content:center;pointer-events:none;z-index:0}
.ring{position:absolute;border-radius:50%;border:1px solid rgba(201,169,110,.09);animation:pulse 7s ease-in-out infinite}
.ring:nth-child(1){width:360px;height:360px;animation-delay:0s}
.ring:nth-child(2){width:560px;height:560px;border-color:rgba(201,169,110,.055);animation-delay:1.5s}
.ring:nth-child(3){width:800px;height:800px;border-color:rgba(201,169,110,.03);animation-delay:3s}
@keyframes pulse{0%,100%{transform:scale(1);opacity:.7}50%{transform:scale(1.02);opacity:1}}

/* ── STEAM ── */
.steam-wrap{position:relative;z-index:1;margin-bottom:-1rem}
.cup{font-size:5rem;display:block;animation:float 4s ease-in-out infinite}
@keyframes float{0%,100%{transform:translateY(0)}50%{transform:translateY(-10px)}}
.steam{display:flex;gap:.9rem;justify-content:center;margin-bottom:.5rem;height:36px}
.s{
  width:3px;border-radius:4px;
  background:linear-gradient(to top, rgba(201,169,110,.5), transparent);
  animation:steamRise 2.4s ease-in-out infinite;
  transform-origin:bottom;
}
.s:nth-child(1){height:28px;animation-delay:0s}
.s:nth-child(2){height:36px;animation-delay:.4s}
.s:nth-child(3){height:22px;animation-delay:.8s}
@keyframes steamRise{
  0%{transform:scaleY(0) translateY(0);opacity:0}
  40%{opacity:1}
  100%{transform:scaleY(1) translateY(-12px);opacity:0}
}

/* ── CONTENT ── */
.content{
  position:relative;z-index:1;
  text-align:center;
  max-width:580px;
  animation:fadeUp .9s var(--ease) forwards;
  opacity:0;
}
@keyframes fadeUp{from{opacity:0;transform:translateY(24px)}to{opacity:1;transform:none}}

.tag{
  font-size:.65rem;letter-spacing:.24em;text-transform:uppercase;
  color:var(--gold);margin-bottom:1.8rem;display:block;
}
.tag::before,.tag::after{
  content:'';display:inline-block;width:20px;height:1px;
  background:var(--gold);opacity:.5;vertical-align:middle;margin:0 .7rem;
}

.num{
  font-family:var(--serif);
  font-size:clamp(7rem,18vw,13rem);
  font-weight:300;
  line-height:.85;
  color:var(--gold);
  letter-spacing:-.02em;
  display:block;
  margin-bottom:.4rem;
  text-shadow:0 0 80px rgba(201,169,110,.15);
}

.title{
  font-family:var(--serif);
  font-size:clamp(1.6rem,3.5vw,2.4rem);
  font-weight:300;
  color:var(--cream);
  line-height:1.2;
  margin-bottom:1rem;
}
.title em{font-style:italic;color:var(--gold)}

.sub{
  font-size:.9rem;
  color:rgba(245,240,232,.48);
  line-height:1.85;
  letter-spacing:.03em;
  margin-bottom:3rem;
}

/* ── BUTTONS ── */
.btns{display:flex;gap:1rem;justify-content:center;flex-wrap:wrap;margin-bottom:3.5rem}
.btn-g{
  font-family:var(--sans);font-size:.73rem;letter-spacing:.13em;
  text-transform:uppercase;font-weight:500;
  background:var(--gold);color:var(--espresso);
  border:none;padding:.95rem 2.4rem;
  cursor:pointer;text-decoration:none;display:inline-block;
  transition:background .2s,transform .15s;
}
.btn-g:hover{background:var(--gold-hover);transform:translateY(-2px)}
.btn-o{
  font-family:var(--sans);font-size:.73rem;letter-spacing:.13em;
  text-transform:uppercase;
  background:transparent;color:var(--cream);
  border:1px solid rgba(245,240,232,.22);
  padding:.95rem 2.4rem;
  cursor:pointer;text-decoration:none;display:inline-block;
  transition:border-color .2s,color .2s;
}
.btn-o:hover{border-color:var(--gold);color:var(--gold)}

/* ── DIVIDER ── */
.div-line{
  width:1px;height:40px;
  background:linear-gradient(to bottom,transparent,rgba(201,169,110,.3),transparent);
  margin:0 auto 2rem;
}

/* ── QUICK LINKS ── */
.links{display:flex;gap:2rem;justify-content:center;flex-wrap:wrap}
.links a{
  font-size:.68rem;letter-spacing:.14em;text-transform:uppercase;
  color:rgba(245,240,232,.3);text-decoration:none;
  transition:color .2s;
}
.links a:hover{color:var(--gold)}

/* ── LOGO ── */
.logo{
  position:fixed;top:1.8rem;left:50%;transform:translateX(-50%);
  font-family:var(--serif);font-size:1.4rem;font-weight:400;
  color:var(--gold);text-decoration:none;letter-spacing:.04em;z-index:10;
}
.logo span{font-style:italic}

/* ── LANG ── */
.lang-row{
  position:fixed;top:1.6rem;right:2rem;
  display:flex;border:1px solid rgba(201,169,110,.22);overflow:hidden;z-index:10;
}
.lb{
  font-family:var(--sans);font-size:.6rem;font-weight:500;letter-spacing:.1em;
  text-transform:uppercase;padding:.36rem .6rem;
  background:transparent;color:rgba(201,169,110,.4);
  border:none;border-right:1px solid rgba(201,169,110,.14);
  cursor:pointer;transition:background .15s,color .15s;
}
.lb:last-child{border-right:none}
.lb.on,.lb:hover{background:var(--gold);color:var(--espresso)}

/* ── FOOTER NOTE ── */
.foot-note{
  position:fixed;bottom:1.6rem;left:50%;transform:translateX(-50%);
  font-size:.65rem;letter-spacing:.1em;color:rgba(245,240,232,.18);
  white-space:nowrap;z-index:1;
}

@media(max-width:480px){
  .links{gap:1.2rem}
  .btns{flex-direction:column;align-items:center}
  .btn-g,.btn-o{width:100%;max-width:260px;text-align:center}
}
</style>
</head>
<body>

<a href="index.html" class="logo">Cafe <span>89°</span></a>

<div class="lang-row">
  <button class="lb on" onclick="L('et')">ET</button>
  <button class="lb" onclick="L('en')">EN</button>
  <button class="lb" onclick="L('ru')">RU</button>
  <button class="lb" onclick="L('uk')">UK</button>
</div>

<div class="bg"></div>
<div class="noise"></div>
<div class="rings">
  <div class="ring"></div>
  <div class="ring"></div>
  <div class="ring"></div>
</div>

<div class="steam-wrap">
  <div class="steam">
    <div class="s"></div>
    <div class="s"></div>
    <div class="s"></div>
  </div>
  <span class="cup">☕</span>
</div>

<div class="content">
  <span class="tag" data-t="tag">Lehte ei leitud</span>
  <span class="num">404</span>
  <h1 class="title" data-t="title">See leht on <em>kadunud</em></h1>
  <p class="sub" data-t="sub">Aga meie kohv on alati olemas.<br>Tulge külla Madara 33, Tallinn.</p>

  <div class="btns">
    <a href="index.html" class="btn-g" data-t="btn_home">← Tagasi avalehele</a>
    <a href="index.html#menu" class="btn-o" data-t="btn_menu">Vaata menüüd</a>
  </div>

  <div class="div-line"></div>

  <div class="links">
    <a href="index.html#story" data-t="l_story">Meie lugu</a>
    <a href="index.html#menu" data-t="l_menu">Menüü</a>
    <a href="index.html#services" data-t="l_srv">Üritused</a>
    <a href="index.html#visit" data-t="l_visit">Külasta</a>
  </div>
</div>

<p class="foot-note">© 2025 Cafe 89° · Madara 33, Tallinn</p>

<script>
const T = {
  et:{
    tag:"Lehte ei leitud",
    title:"See leht on <em>kadunud</em>",
    sub:"Aga meie kohv on alati olemas.<br>Tulge külla Madara 33, Tallinn.",
    btn_home:"← Tagasi avalehele",
    btn_menu:"Vaata menüüd",
    l_story:"Meie lugu",l_menu:"Menüü",l_srv:"Üritused",l_visit:"Külasta"
  },
  en:{
    tag:"Page not found",
    title:"This page has <em>vanished</em>",
    sub:"But our coffee is always here.<br>Come visit us at Madara 33, Tallinn.",
    btn_home:"← Back to home",
    btn_menu:"View menu",
    l_story:"Our Story",l_menu:"Menu",l_srv:"Events",l_visit:"Visit"
  },
  ru:{
    tag:"Страница не найдена",
    title:"Эта страница <em>исчезла</em>",
    sub:"Но наш кофе всегда на месте.<br>Приходите на Madara 33, Таллин.",
    btn_home:"← На главную",
    btn_menu:"Смотреть меню",
    l_story:"Наша история",l_menu:"Меню",l_srv:"Мероприятия",l_visit:"Посетить"
  },
  uk:{
    tag:"Сторінку не знайдено",
    title:"Ця сторінка <em>зникла</em>",
    sub:"Але наша кава завжди тут.<br>Приходьте на Madara 33, Таллінн.",
    btn_home:"← На головну",
    btn_menu:"Переглянути меню",
    l_story:"Наша історія",l_menu:"Меню",l_srv:"Заходи",l_visit:"Відвідати"
  }
};

function L(lang){
  const t = T[lang];
  if(!t) return;
  document.querySelectorAll('[data-t]').forEach(el => {
    const k = el.getAttribute('data-t');
    if(t[k] !== undefined) el.innerHTML = t[k];
  });
  document.querySelectorAll('.lb').forEach(b => {
    b.classList.toggle('on', b.textContent.trim().toLowerCase() === lang);
  });
  document.documentElement.lang = lang;
}

// Auto-detect browser language
const browserLang = navigator.language?.slice(0,2);
const supported = ['et','en','ru','uk'];
L(supported.includes(browserLang) ? browserLang : 'et');
</script>
</body>
</html>
