<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Tettou Preto INK — Estúdio de Tatuagem · Florianópolis</title>
<meta name="description" content="Tettou Preto INK — estúdio de tatuagem em Florianópolis/SC. Realismo preto & cinza, blackwork, fechamentos e tatuagens 100% personalizadas. Aberto 24h. Agende pelo WhatsApp.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Caveat:wght@500;600;700&family=Space+Grotesk:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#0d0b0a; --bg2:#14110f; --panel:#1a1613; --panel2:#211b17;
    --line:rgba(236,230,221,.12); --line-2:rgba(236,230,221,.22);
    --bone:#ece6dd; --bone-dim:#b7aea2; --muted:#857b70;
    --ember:#d98a4e; --ember-2:#eaa869; --blood:#8a2f22; --ok:#5fb878;
    --maxw:1280px;
    --disp:'Bebas Neue',sans-serif; --body:'Space Grotesk',sans-serif; --hand:'Caveat',cursive;
    --pad:clamp(1.25rem,4vw,4rem);
  }
  *{box-sizing:border-box;margin:0;padding:0}
  html{scroll-behavior:smooth;scroll-padding-top:90px}
  body{background:var(--bg);color:var(--bone);font-family:var(--body);font-weight:400;line-height:1.6;-webkit-font-smoothing:antialiased;overflow-x:hidden}
  a{color:inherit;text-decoration:none}
  img{max-width:100%;display:block}
  ::selection{background:var(--ember);color:#160f0a}
  h1,h2,h3{font-family:var(--disp);font-weight:400;line-height:.92;letter-spacing:.01em}

  .grain{position:fixed;inset:0;z-index:9998;pointer-events:none;opacity:.42;mix-blend-mode:overlay;
    background-image:url("data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='180' height='180'><filter id='n'><feTurbulence type='fractalNoise' baseFrequency='0.85' numOctaves='2' stitchTiles='stitch'/></filter><rect width='100%25' height='100%25' filter='url(%23n)' opacity='0.55'/></svg>");}

  .cursor,.cursor-ring{position:fixed;top:0;left:0;z-index:9999;pointer-events:none;border-radius:50%;transform:translate(-50%,-50%);will-change:transform}
  .cursor{width:7px;height:7px;background:var(--ember)}
  .cursor-ring{width:34px;height:34px;border:1px solid var(--ember);opacity:.5;transition:width .25s,height .25s,opacity .25s,border-color .25s}
  body.cur-big .cursor-ring{width:62px;height:62px;opacity:.9;border-color:var(--ember-2)}
  body.cur-big .cursor{opacity:0}
  @media (hover:none){.cursor,.cursor-ring{display:none}}

  .nav{position:fixed;top:0;left:0;right:0;z-index:100;display:flex;align-items:center;justify-content:space-between;
    padding:1rem var(--pad);transition:background .4s,border-color .4s,padding .4s;border-bottom:1px solid transparent}
  .nav.scrolled{background:rgba(13,11,10,.82);backdrop-filter:blur(12px);border-color:var(--line);padding:.7rem var(--pad)}
  .brand{display:flex;align-items:center;gap:.65rem}
  .brand .mark{width:34px;height:34px;flex:none}
  .brand .wm{font-family:var(--disp);font-size:1.5rem;letter-spacing:.06em;line-height:1}
  .brand .wm b{color:var(--ember);font-weight:400}
  .nav-links{display:flex;align-items:center;gap:2rem}
  .nav-links a{font-size:.82rem;letter-spacing:.16em;text-transform:uppercase;color:var(--bone-dim);position:relative;padding:.3rem 0;transition:color .3s}
  .nav-links a::after{content:"";position:absolute;left:0;bottom:0;height:1px;width:0;background:var(--ember);transition:width .35s}
  .nav-links a:hover{color:var(--bone)}
  .nav-links a:hover::after{width:100%}
  .btn{display:inline-flex;align-items:center;gap:.55rem;font-family:var(--body);font-weight:600;font-size:.82rem;
    letter-spacing:.12em;text-transform:uppercase;padding:.85rem 1.5rem;border:1px solid var(--line-2);color:var(--bone);
    background:transparent;cursor:pointer;position:relative;overflow:hidden;transition:color .35s,border-color .35s}
  .btn span{position:relative;z-index:2;display:inline-flex;align-items:center;gap:.55rem}
  .btn svg{width:16px;height:16px}
  .btn::before{content:"";position:absolute;inset:0;background:var(--ember);transform:translateY(101%);transition:transform .4s cubic-bezier(.7,0,.2,1);z-index:1}
  .btn:hover{color:#160f0a;border-color:var(--ember)}
  .btn:hover::before{transform:translateY(0)}
  .btn.solid{background:var(--ember);color:#160f0a;border-color:var(--ember)}
  .btn.solid::before{background:var(--bone)}
  .btn.solid:hover{color:#160f0a}
  .btn.lg{padding:1.05rem 1.9rem;font-size:.9rem}
  .burger{display:none;background:none;border:1px solid var(--line-2);width:46px;height:42px;cursor:pointer;position:relative;z-index:200}
  .burger span{position:absolute;left:12px;right:12px;height:2px;background:var(--bone);transition:.35s}
  .burger span:nth-child(1){top:15px}.burger span:nth-child(2){top:20px}.burger span:nth-child(3){top:25px}
  .burger.open span:nth-child(1){top:20px;transform:rotate(45deg)}
  .burger.open span:nth-child(2){opacity:0}
  .burger.open span:nth-child(3){top:20px;transform:rotate(-45deg)}

  .mobile-menu{position:fixed;inset:0;z-index:150;background:var(--bg);display:flex;flex-direction:column;justify-content:center;
    padding:2rem var(--pad);gap:1rem;transform:translateY(-100%);transition:transform .5s cubic-bezier(.7,0,.2,1)}
  .mobile-menu.open{transform:translateY(0)}
  .mobile-menu a{font-family:var(--disp);font-size:clamp(2.5rem,12vw,4.5rem);line-height:1;color:var(--bone-dim);transition:color .3s,transform .3s}
  .mobile-menu a:hover{color:var(--ember);transform:translateX(10px)}
  .mobile-menu .mm-foot{margin-top:2rem;font-family:var(--hand);font-size:1.5rem;color:var(--muted)}

  .hero{position:relative;min-height:100vh;display:grid;grid-template-columns:1.15fr .85fr;gap:2rem;
    padding:8rem var(--pad) 3rem;align-items:center}
  .hero::before{content:"";position:absolute;inset:0;z-index:-1;
    background:radial-gradient(120% 90% at 85% 15%,rgba(217,138,78,.10),transparent 55%),
               radial-gradient(80% 60% at 10% 90%,rgba(138,47,34,.10),transparent 60%)}
  .hero-l{max-width:640px}
  .eyebrow{font-family:var(--hand);font-size:clamp(1.4rem,3vw,1.9rem);color:var(--ember);display:inline-block;margin-bottom:1rem;transform:rotate(-2deg)}
  .hero h1{font-size:clamp(4.5rem,15vw,12rem);letter-spacing:.01em}
  .hero h1 .l2{color:transparent;-webkit-text-stroke:1.5px var(--bone-dim)}
  .hero h1 .l3{color:var(--ember)}
  .hero p.lead{font-size:clamp(1rem,1.6vw,1.2rem);color:var(--bone-dim);max-width:46ch;margin:1.4rem 0 1.8rem}
  .hero-chips{display:flex;flex-wrap:wrap;gap:.6rem;margin-bottom:2rem}
  .chip{display:inline-flex;align-items:center;gap:.5rem;font-size:.78rem;letter-spacing:.08em;text-transform:uppercase;
    color:var(--bone-dim);border:1px solid var(--line);padding:.5rem .85rem}
  .chip .dot{width:6px;height:6px;border-radius:50%;background:var(--ember)}
  .chip.live{border-color:rgba(95,184,120,.4);color:var(--bone)}
  .chip.live .dot{background:var(--ok);box-shadow:0 0 0 0 rgba(95,184,120,.6);animation:pulse 2s infinite}
  @keyframes pulse{0%{box-shadow:0 0 0 0 rgba(95,184,120,.5)}70%{box-shadow:0 0 0 7px rgba(95,184,120,0)}100%{box-shadow:0 0 0 0 rgba(95,184,120,0)}}
  .hero-cta{display:flex;flex-wrap:wrap;gap:.9rem}
  .scroll-cue{position:absolute;bottom:1.6rem;left:var(--pad);display:flex;align-items:center;gap:.7rem;
    font-size:.72rem;letter-spacing:.22em;text-transform:uppercase;color:var(--muted)}
  .scroll-cue .bar{width:46px;height:1px;background:var(--line-2);position:relative;overflow:hidden}
  .scroll-cue .bar::after{content:"";position:absolute;inset:0;background:var(--ember);transform:translateX(-100%);animation:cue 2.2s infinite}
  @keyframes cue{0%{transform:translateX(-100%)}60%,100%{transform:translateX(100%)}}

  .wall{position:relative;min-height:min(70vh,560px);background:linear-gradient(160deg,#0a0908,#161210);
    border:1px solid var(--line);overflow:hidden;display:flex;align-items:center;justify-content:center}
  .wall::before{content:"";position:absolute;inset:0;
    background:radial-gradient(60% 55% at 50% 42%,rgba(217,138,78,.16),transparent 70%);
    animation:glow 6s ease-in-out infinite alternate}
  @keyframes glow{from{opacity:.5}to{opacity:1}}
  .wall .mark{position:absolute;width:150px;opacity:.10}
  .wall .script{position:relative;z-index:2;text-align:center;padding:1rem}
  .wall .script .big{font-family:var(--hand);font-weight:700;font-size:clamp(3rem,8vw,5.5rem);line-height:.9;color:var(--bone);text-shadow:0 0 40px rgba(217,138,78,.25)}
  .wall .script .big em{color:var(--ember);font-style:normal}
  .wall .script .sub{font-family:var(--hand);font-size:1.4rem;color:var(--muted);margin-top:.4rem;transform:rotate(-3deg)}
  .wall .frame{position:absolute;inset:14px;border:1px solid var(--line);pointer-events:none}

  .marquee{border-top:1px solid var(--line);border-bottom:1px solid var(--line);overflow:hidden;padding:1.1rem 0;background:var(--bg2)}
  .marquee-track{display:flex;gap:2.5rem;white-space:nowrap;width:max-content;animation:scroll 32s linear infinite}
  .marquee-track span{font-family:var(--disp);font-size:1.7rem;letter-spacing:.08em;color:var(--bone-dim);display:flex;align-items:center;gap:2.5rem}
  .marquee-track span::after{content:"✦";color:var(--ember);font-size:1rem}
  @keyframes scroll{to{transform:translateX(-50%)}}

  section{padding:clamp(4rem,9vw,8rem) var(--pad)}
  .wrap{max-width:var(--maxw);margin:0 auto}
  .sec-head{display:flex;align-items:flex-end;justify-content:space-between;gap:1.5rem;flex-wrap:wrap;margin-bottom:2.6rem}
  .sec-head .k{font-family:var(--hand);font-size:1.5rem;color:var(--ember);transform:rotate(-2deg);display:block;margin-bottom:.3rem}
  .sec-head h2{font-size:clamp(2.6rem,7vw,5.5rem)}
  .sec-head .note{max-width:34ch;color:var(--muted);font-size:.92rem}
  .sec-head .note a{color:var(--ember);border-bottom:1px solid var(--line-2)}

  .featured{display:grid;grid-template-columns:1fr 1fr;gap:0;border:1px solid var(--line);margin-bottom:14px;background:var(--panel)}
  .featured .plate{min-height:340px}
  .featured .f-body{padding:clamp(1.5rem,3vw,2.6rem);display:flex;flex-direction:column;justify-content:center}
  .featured .f-body .tag{font-size:.72rem;letter-spacing:.2em;text-transform:uppercase;color:var(--ember)}
  .featured .f-body h3{font-size:clamp(2rem,4vw,3.2rem);margin:.6rem 0 .8rem}
  .featured .f-body p{color:var(--bone-dim);max-width:42ch;margin-bottom:1.2rem}
  .meta{display:flex;flex-wrap:wrap;gap:1.4rem;margin-bottom:1.4rem}
  .meta div{font-size:.8rem;color:var(--muted)}
  .meta b{display:block;font-family:var(--disp);font-size:1.5rem;letter-spacing:.04em;color:var(--bone)}

  .masonry{columns:3 320px;column-gap:14px}
  .card{break-inside:avoid;margin-bottom:14px;border:1px solid var(--line);background:var(--panel);position:relative;overflow:hidden;
    transition:transform .4s cubic-bezier(.2,.7,.2,1),border-color .4s}
  .card:hover{transform:translateY(-5px);border-color:var(--line-2)}
  .plate{position:relative;overflow:hidden;background:
    radial-gradient(120% 120% at 50% 0%,var(--panel2),var(--panel) 70%);
    background-image:radial-gradient(rgba(236,230,221,.07) 1px,transparent 1.5px);background-size:13px 13px}
  .plate::after{content:"";position:absolute;inset:0;background:radial-gradient(80% 80% at 50% 50%,transparent 40%,rgba(0,0,0,.55))}
  .plate .num{position:absolute;top:.4rem;right:.8rem;font-family:var(--disp);font-size:3.4rem;color:rgba(236,230,221,.10);z-index:1;transition:color .4s}
  .card:hover .plate .num{color:rgba(217,138,78,.4)}
  .plate .motif{position:absolute;inset:0;display:flex;align-items:center;justify-content:center;z-index:2;opacity:.5;transition:opacity .4s,transform .6s}
  .card:hover .plate .motif{opacity:.95;transform:scale(1.06) rotate(-2deg)}
  .plate .motif svg{width:62%;height:auto;stroke:var(--bone);fill:none;stroke-width:2.4;stroke-linecap:round;stroke-linejoin:round}
  .plate .ig{position:absolute;left:.7rem;bottom:.7rem;z-index:3;display:inline-flex;align-items:center;gap:.4rem;
    font-size:.68rem;letter-spacing:.12em;text-transform:uppercase;color:var(--bone-dim);background:rgba(13,11,10,.6);
    border:1px solid var(--line);padding:.35rem .6rem;opacity:0;transform:translateY(6px);transition:.35s}
  .card:hover .plate .ig{opacity:1;transform:translateY(0)}
  .plate .ig svg{width:13px;height:13px}
  .card .c-body{padding:1rem 1.1rem 1.2rem;border-top:1px solid var(--line)}
  .card .c-body .tag{font-size:.68rem;letter-spacing:.18em;text-transform:uppercase;color:var(--ember)}
  .card .c-body h3{font-size:1.7rem;margin:.35rem 0 .3rem}
  .card .c-body p{font-size:.85rem;color:var(--muted)}
  .h-tall{min-height:420px}.h-mid{min-height:300px}.h-short{min-height:230px}

  .stats{display:grid;grid-template-columns:repeat(4,1fr);gap:1px;background:var(--line);border:1px solid var(--line)}
  .stat{background:var(--bg);padding:1.6rem 1.4rem}
  .stat b{font-family:var(--disp);font-size:clamp(2rem,4vw,3rem);color:var(--bone);display:block;line-height:1}
  .stat b em{color:var(--ember);font-style:normal}
  .stat span{font-size:.78rem;letter-spacing:.1em;text-transform:uppercase;color:var(--muted)}

  .about{display:grid;grid-template-columns:1fr 1fr;gap:clamp(2rem,5vw,5rem);align-items:start}
  .about .lead{font-size:clamp(1.1rem,1.8vw,1.35rem);color:var(--bone-dim)}
  .about .lead strong{color:var(--bone);font-weight:600}
  .about .hand{font-family:var(--hand);font-size:1.7rem;color:var(--ember);margin-top:1.4rem;transform:rotate(-2deg)}
  .steps{display:flex;flex-direction:column;gap:1px;background:var(--line);border:1px solid var(--line)}
  .step{background:var(--bg);padding:1.4rem 1.5rem;display:grid;grid-template-columns:auto 1fr;gap:1.2rem;align-items:baseline;transition:background .3s}
  .step:hover{background:var(--panel)}
  .step .n{font-family:var(--disp);font-size:2rem;color:var(--ember)}
  .step h4{font-family:var(--body);font-weight:600;font-size:1.05rem;letter-spacing:.02em}
  .step p{font-size:.88rem;color:var(--muted);margin-top:.2rem}

  .styles{border-top:1px solid var(--line)}
  .style-row{display:grid;grid-template-columns:auto 1fr auto;gap:1.5rem;align-items:center;padding:1.6rem 0;border-bottom:1px solid var(--line);
    transition:padding .35s,background .35s;cursor:default}
  .style-row:hover{padding-left:1.2rem;background:linear-gradient(90deg,rgba(217,138,78,.06),transparent)}
  .style-row .n{font-family:var(--disp);font-size:1.4rem;color:var(--muted);width:2.5rem}
  .style-row h3{font-size:clamp(1.8rem,4vw,3rem)}
  .style-row p{color:var(--muted);font-size:.9rem;max-width:30ch;text-align:right}

  .vaga{border:1px solid var(--line);background:linear-gradient(120deg,var(--panel),var(--bg2));padding:clamp(1.8rem,4vw,3rem);
    display:flex;align-items:center;justify-content:space-between;gap:1.5rem;flex-wrap:wrap;position:relative;overflow:hidden}
  .vaga::before{content:"";position:absolute;right:-40px;top:-40px;width:200px;height:200px;border:1px solid var(--line);border-radius:50%;opacity:.5}
  .vaga .k{font-family:var(--hand);font-size:1.5rem;color:var(--blood);transform:rotate(-2deg)}
  .vaga h3{font-size:clamp(2rem,5vw,3.4rem)}
  .vaga p{color:var(--bone-dim);max-width:40ch}

  .contact{position:relative}
  .contact::before{content:"";position:absolute;inset:0;z-index:-1;background:radial-gradient(70% 60% at 50% 100%,rgba(217,138,78,.10),transparent 60%)}
  .contact .big{font-size:clamp(3rem,12vw,9rem);text-align:center;line-height:.9}
  .contact .big em{color:var(--ember);font-style:normal}
  .contact .sub{text-align:center;font-family:var(--hand);font-size:1.7rem;color:var(--bone-dim);margin:.6rem 0 2.4rem}
  .contact-cta{display:flex;flex-wrap:wrap;gap:.9rem;justify-content:center}
  .contact-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:1px;background:var(--line);border:1px solid var(--line);margin-top:2.5rem}
  .c-box{background:var(--bg);padding:1.6rem;display:flex;flex-direction:column;gap:.35rem}
  .c-box .k{font-size:.72rem;letter-spacing:.18em;text-transform:uppercase;color:var(--muted);display:flex;align-items:center;gap:.5rem;margin-bottom:.4rem}
  .c-box .k svg{width:15px;height:15px;color:var(--ember)}
  .c-box a,.c-box .val{font-family:var(--disp);font-size:1.45rem;letter-spacing:.03em;color:var(--bone);transition:color .3s;line-height:1.1}
  .c-box a:hover{color:var(--ember)}
  .c-box small{color:var(--muted);font-size:.82rem}
  .c-box .open{color:var(--ok)}
  .c-box .socials{display:flex;flex-direction:column;gap:.5rem}
  .c-box .socials a{font-family:var(--body);font-weight:500;font-size:.95rem;color:var(--bone-dim);display:flex;align-items:center;gap:.5rem;transition:color .3s,transform .3s}
  .c-box .socials a:hover{color:var(--ember);transform:translateX(4px)}
  .c-box .socials a svg{width:16px;height:16px;color:var(--ember)}

  footer{border-top:1px solid var(--line);padding:2.5rem var(--pad);display:flex;align-items:center;justify-content:space-between;gap:1.5rem;flex-wrap:wrap}
  footer .f-brand{display:flex;align-items:center;gap:.6rem;font-family:var(--disp);font-size:1.3rem;letter-spacing:.05em}
  footer .f-brand b{color:var(--ember);font-weight:400}
  footer .f-brand .mark{width:28px;height:28px}
  footer .f-mid{font-size:.82rem;color:var(--muted);text-align:center}
  footer .f-mid a{color:var(--bone-dim)}
  footer .f-mid a:hover{color:var(--ember)}
  footer .f-hand{font-family:var(--hand);font-size:1.4rem;color:var(--ember)}

  [data-reveal]{opacity:0;transform:translateY(26px);transition:opacity .8s ease,transform .8s cubic-bezier(.2,.7,.2,1)}
  [data-reveal].in{opacity:1;transform:none}

  @media(max-width:900px){
    .hero{grid-template-columns:1fr;padding-top:7rem;min-height:auto}
    .wall{min-height:340px;order:-1}
    .about{grid-template-columns:1fr}
    .featured{grid-template-columns:1fr}
    .featured .plate{min-height:260px}
    .stats{grid-template-columns:repeat(2,1fr)}
    .contact-grid{grid-template-columns:repeat(2,1fr)}
    .style-row p{text-align:left}
    .style-row{grid-template-columns:auto 1fr}
    .style-row p{grid-column:2}
  }
  @media(max-width:720px){
    .nav-links{display:none}
    .burger{display:block}
    .masonry{columns:2 160px}
  }
  @media(max-width:480px){
    .masonry{columns:1}
    .contact-grid{grid-template-columns:1fr}
  }

  @media (prefers-reduced-motion:reduce){
    html{scroll-behavior:auto}
    *{animation:none!important;transition:none!important}
    [data-reveal]{opacity:1;transform:none}
    .marquee-track{transform:none}
    .cursor,.cursor-ring{display:none}
  }
</style>
</head>
<body>

<svg width="0" height="0" style="position:absolute" aria-hidden="true">
  <symbol id="mark" viewBox="0 0 64 64">
    <path d="M10 42 L32 18 L54 42" fill="none" stroke="currentColor" stroke-width="9" stroke-linecap="square"/>
    <line x1="40" y1="14" x2="47" y2="5" stroke="currentColor" stroke-width="2.5"/>
    <circle cx="40" cy="20" r="2.4" fill="var(--ember)"/>
  </symbol>
  <symbol id="m-crown" viewBox="0 0 100 100"><ellipse cx="50" cy="52" rx="34" ry="22"/><line x1="20" y1="40" x2="12" y2="30"/><line x1="34" y1="33" x2="30" y2="20"/><line x1="50" y1="30" x2="50" y2="16"/><line x1="66" y1="33" x2="70" y2="20"/><line x1="80" y1="40" x2="88" y2="30"/><line x1="50" y1="74" x2="50" y2="88"/></symbol>
  <symbol id="m-cross" viewBox="0 0 100 100"><line x1="50" y1="14" x2="50" y2="86"/><line x1="28" y1="42" x2="72" y2="42"/><path d="M50 14 l-6 10 M50 14 l6 10"/></symbol>
  <symbol id="m-snake" viewBox="0 0 100 100"><path d="M28 80 C28 58 72 62 72 42 C72 28 46 28 46 42 C46 52 60 52 60 44"/><circle cx="60" cy="42" r="3"/><path d="M60 42 l8 -4"/></symbol>
  <symbol id="m-lion" viewBox="0 0 100 100"><circle cx="50" cy="52" r="15"/><line x1="50" y1="30" x2="50" y2="16"/><line x1="33" y1="37" x2="24" y2="26"/><line x1="67" y1="37" x2="76" y2="26"/><line x1="26" y1="52" x2="12" y2="52"/><line x1="74" y1="52" x2="88" y2="52"/><line x1="33" y1="67" x2="24" y2="78"/><line x1="67" y1="67" x2="76" y2="78"/><line x1="50" y1="74" x2="50" y2="88"/></symbol>
  <symbol id="m-wave" viewBox="0 0 100 100"><path d="M14 40 q16 -12 32 0 t32 0"/><path d="M14 55 q16 -12 32 0 t32 0"/><path d="M14 70 q16 -12 32 0 t32 0"/></symbol>
  <symbol id="m-moth" viewBox="0 0 100 100"><path d="M50 50 C30 24 14 40 24 66 C34 78 48 62 50 50 Z"/><path d="M50 50 C70 24 86 40 76 66 C66 78 52 62 50 50 Z"/><line x1="50" y1="30" x2="50" y2="74"/><path d="M50 30 l-8 -10 M50 30 l8 -10"/></symbol>
  <symbol id="m-rose" viewBox="0 0 100 100"><path d="M50 40 a8 8 0 1 1 -8 -8 a5 5 0 1 0 5 5"/><path d="M50 40 C34 30 24 44 34 56 C44 66 58 60 58 48 C58 40 52 38 50 40"/><line x1="50" y1="58" x2="50" y2="86"/><path d="M50 70 l-10 -6 M50 76 l10 -6"/></symbol>
  <symbol id="m-face" viewBox="0 0 100 100"><path d="M44 22 C32 34 32 54 42 68 C47 78 58 80 62 70"/><line x1="40" y1="46" x2="52" y2="46"/><path d="M50 58 l6 4"/></symbol>
  <symbol id="m-poly" viewBox="0 0 100 100"><path d="M50 16 L78 33 L78 67 L50 84 L22 67 L22 33 Z"/><path d="M50 16 L50 50 L78 67 M50 50 L22 67 M50 50 L50 84"/></symbol>
  <symbol id="ig" viewBox="0 0 24 24"><rect x="3" y="3" width="18" height="18" rx="5" fill="none" stroke="currentColor" stroke-width="2"/><circle cx="12" cy="12" r="4" fill="none" stroke="currentColor" stroke-width="2"/><circle cx="17.5" cy="6.5" r="1.2" fill="currentColor"/></symbol>
  <symbol id="wa" viewBox="0 0 24 24"><path d="M12 2a10 10 0 0 0-8.6 15l-1.3 4.7 4.8-1.3A10 10 0 1 0 12 2Zm5.3 14.2c-.2.6-1.3 1.2-1.8 1.2-.5.1-1 .1-1.7-.1-.4-.1-.9-.3-1.6-.6-2.8-1.2-4.6-4-4.7-4.2-.1-.2-1.1-1.4-1.1-2.7s.7-1.9.9-2.2c.2-.2.5-.3.7-.3h.5c.2 0 .4 0 .6.5l.8 1.9c.1.2.1.4 0 .5l-.4.6c-.2.2-.3.4-.1.7.2.3.9 1.4 1.9 2.3 1.3 1.1 2.3 1.5 2.6 1.6.2.1.4.1.6-.1l.7-.9c.2-.2.4-.2.6-.1l1.8.9c.3.1.5.2.5.3.1.1.1.6-.1 1.2Z" fill="currentColor"/></symbol>
  <symbol id="phone" viewBox="0 0 24 24"><path d="M6.6 10.8c1.4 2.8 3.8 5.1 6.6 6.6l2.2-2.2c.3-.3.7-.4 1-.2 1.1.4 2.3.6 3.6.6.6 0 1 .4 1 1V20c0 .6-.4 1-1 1C10.6 21 3 13.4 3 4c0-.6.4-1 1-1h3.5c.6 0 1 .4 1 1 0 1.2.2 2.4.6 3.6.1.4 0 .8-.3 1l-2.2 2.2Z" fill="currentColor"/></symbol>
  <symbol id="pin" viewBox="0 0 24 24"><path d="M12 2a7 7 0 0 0-7 7c0 5 7 13 7 13s7-8 7-13a7 7 0 0 0-7-7Zm0 9.5A2.5 2.5 0 1 1 12 6.5a2.5 2.5 0 0 1 0 5Z" fill="currentColor"/></symbol>
  <symbol id="clock" viewBox="0 0 24 24"><circle cx="12" cy="12" r="9" fill="none" stroke="currentColor" stroke-width="2"/><path d="M12 7v5l3.5 2" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"/></symbol>
  <symbol id="fb" viewBox="0 0 24 24"><path d="M14 8.5V7c0-.8.2-1 1-1h1.5V3H14c-2.5 0-4 1.6-4 4v1.5H8V12h2v9h4v-9h2.2l.3-3.5H14Z" fill="currentColor"/></symbol>
</svg>

<div class="grain" aria-hidden="true"></div>
<div class="cursor" aria-hidden="true"></div>
<div class="cursor-ring" aria-hidden="true"></div>

<header class="nav" id="nav">
  <a class="brand" href="#top" aria-label="Tettou Preto INK">
    <svg class="mark" style="color:var(--bone)"><use href="#mark"/></svg>
    <span class="wm">TETTOO PRETO <b>INK</b></span>
  </a>
  <nav class="nav-links" aria-label="Principal">
    <a href="#galeria">Galeria</a>
    <a href="#estudio">Estúdio</a>
    <a href="#estilos">Estilos</a>
    <a href="#contato">Contato</a>
    <a class="btn solid" href="https://wa.me/554831976757" target="_blank" rel="noopener"><span>Agendar</span></a>
  </nav>
  <button class="burger" id="burger" aria-label="Abrir menu" aria-expanded="false"><span></span><span></span><span></span></button>
</header>

<div class="mobile-menu" id="mobileMenu">
  <a href="#galeria">Galeria</a>
  <a href="#estudio">Estúdio</a>
  <a href="#estilos">Estilos</a>
  <a href="#contato">Contato</a>
  <a href="https://wa.me/554831976757" target="_blank" rel="noopener" style="color:var(--ember)">Agendar no WhatsApp</a>
  <div class="mm-foot">Rua Conselheiro Mafra, 590 · Centro, Floripa<br>Aberto 24 horas · (48) 3197-6757</div>
</div>

<main id="top">
<section class="hero">
  <div class="hero-l">
    <span class="eyebrow" data-reveal>estúdio de tatuagem — florianópolis</span>
    <h1 data-reveal>TETTOO<br><span class="l2">PRETO</span> <span class="l3">INK</span></h1>
    <p class="lead" data-reveal>Tatuagens <strong style="color:var(--bone)">100% personalizadas</strong> — realismo preto & cinza, blackwork e fechamentos feitos em múltiplas sessões, no coração de Floripa.</p>
    <div class="hero-chips" data-reveal>
      <span class="chip live"><span class="dot"></span>Aberto 24 horas</span>
      <span class="chip"><span class="dot"></span>Centro · Florianópolis/SC</span>
      <span class="chip"><span class="dot"></span>Fechamentos em 3 sessões</span>
    </div>
    <div class="hero-cta" data-reveal>
      <a class="btn solid" href="https://wa.me/554831976757" target="_blank" rel="noopener"><span><svg><use href="#wa"/></svg>Agendar no WhatsApp</span></a>
      <a class="btn" href="#galeria"><span>Ver trabalhos</span></a>
    </div>
  </div>

  <div class="wall" data-reveal>
    <div class="frame"></div>
    <svg class="mark" style="color:var(--bone)"><use href="#mark"/></svg>
    <div class="script">
      <div class="big">Tettou Preto <em>INK</em></div>
      <div class="sub">est. florianópolis · aberto 24h</div>
    </div>
  </div>

  <div class="scroll-cue"><span>role</span><span class="bar"></span></div>
</section>

<div class="marquee" aria-hidden="true">
  <div class="marquee-track">
    <span>Realismo Preto & Cinza</span><span>Blackwork</span><span>Fechamentos</span><span>Dotwork</span><span>Fine Line</span><span>Tradicional</span><span>Personalizado</span>
    <span>Realismo Preto & Cinza</span><span>Blackwork</span><span>Fechamentos</span><span>Dotwork</span><span>Fine Line</span><span>Tradicional</span><span>Personalizado</span>
  </div>
</div>

<section id="galeria">
  <div class="wrap">
    <div class="sec-head" data-reveal>
      <div>
        <span class="k">o que sai da máquina</span>
        <h2>Galeria</h2>
      </div>
      <p class="note">Cada peça é única. As fotos originais em alta estão no <a href="https://www.instagram.com/tettoopreto.ink" target="_blank" rel="noopener">@tettoopreto.ink</a>.</p>
    </div>

    <article class="featured" data-reveal>
      <div class="plate h-tall">
        <span class="num">01</span>
        <div class="motif"><svg><use href="#m-crown"/></svg></div>
        <a class="ig" href="https://www.instagram.com/tettoopreto.ink" target="_blank" rel="noopener"><svg><use href="#ig"/></svg>ver no instagram</a>
      </div>
      <div class="f-body">
        <span class="tag">Realismo · Blackwork</span>
        <h3>Fechamento Religioso</h3>
        <p>Braço completo em preto: Cristo com coroa de espinhos, figura de manto e cruz de madeira amarrada com corda. Trabalho apresentado em 3 sessões com o artista residente.</p>
        <div class="meta">
          <div><b>Braço</b>localização</div>
          <div><b>3</b>sessões</div>
          <div><b>100%</b>preto</div>
        </div>
        <a class="btn" href="https://www.instagram.com/tettoopreto.ink" target="_blank" rel="noopener"><span>Ver no Instagram</span></a>
      </div>
    </article>

    <div class="masonry" data-reveal-group>
      <article class="card" data-reveal>
        <div class="plate h-mid"><span class="num">02</span><div class="motif"><svg><use href="#m-lion"/></svg></div>
          <a class="ig" href="https://www.instagram.com/tettoopreto.ink" target="_blank" rel="noopener"><svg><use href="#ig"/></svg>IG</a></div>
        <div class="c-body"><span class="tag">Realismo</span><h3>Leão</h3><p>Peito · traço fino e sombreado profundo.</p></div>
      </article>
      <article class="card" data-reveal>
        <div class="plate h-short"><span class="num">03</span><div class="motif"><svg><use href="#m-face"/></svg></div>
          <a class="ig" href="https://www.instagram.com/tettoopreto.ink" target="_blank" rel="noopener"><svg><use href="#ig"/></svg>IG</a></div>
        <div class="c-body"><span class="tag">Blackwork</span><h3>Rosto</h3><p>Pescoço · linhas densas e alto contraste.</p></div>
      </article>
      <article class="card" data-reveal>
        <div class="plate h-tall"><span class="num">04</span><div class="motif"><svg><use href="#m-wave"/></svg></div>
          <a class="ig" href="https://www.instagram.com/tettoopreto.ink" target="_blank" rel="noopener"><svg><use href="#ig"/></svg>IG</a></div>
        <div class="c-body"><span class="tag">Fechamento</span><h3>Costas</h3><p>Fechamento de costas em linework.</p></div>
      </article>
      <article class="card" data-reveal>
        <div class="plate h-short"><span class="num">05</span><div class="motif"><svg><use href="#m-poly"/></svg></div>
          <a class="ig" href="https://www.instagram.com/tettoopreto.ink" target="_blank" rel="noopener"><svg><use href="#ig"/></svg>IG</a></div>
        <div class="c-body"><span class="tag">Dotwork</span><h3>Poligonal</h3><p>Braço · pontilhismo e geometria.</p></div>
      </article>
      <article class="card" data-reveal>
        <div class="plate h-mid"><span class="num">06</span><div class="motif"><svg><use href="#m-rose"/></svg></div>
          <a class="ig" href="https://www.instagram.com/tettoopreto.ink" target="_blank" rel="noopener"><svg><use href="#ig"/></svg>IG</a></div>
        <div class="c-body"><span class="tag">Realismo</span><h3>Retrato</h3><p>Portre em preto e cinza.</p></div>
      </article>
      <article class="card" data-reveal>
        <div class="plate h-mid"><span class="num">07</span><div class="motif"><svg><use href="#m-moth"/></svg></div>
          <a class="ig" href="https://www.instagram.com/tettoopreto.ink" target="_blank" rel="noopener"><svg><use href="#ig"/></svg>IG</a></div>
        <div class="c-body"><span class="tag">Blackwork</span><h3>Ombro</h3><p>Fechamento de ombro em andamento.</p></div>
      </article>
      <article class="card" data-reveal>
        <div class="plate h-short"><span class="num">08</span><div class="motif"><svg><use href="#m-snake"/></svg></div>
          <a class="ig" href="https://www.instagram.com/tettoopreto.ink" target="_blank" rel="noopener"><svg><use href="#ig"/></svg>IG</a></div>
        <div class="c-body"><span class="tag">Sessão</span><h3>Na máquina</h3><p>Por trás do balcão, dia de agulha.</p></div>
      </article>
      <article class="card" data-reveal>
        <div class="plate h-mid"><span class="num">09</span><div class="motif"><svg><use href="#m-cross"/></svg></div>
          <a class="ig" href="https://www.instagram.com/tettoopreto.ink" target="_blank" rel="noopener"><svg><use href="#ig"/></svg>IG</a></div>
        <div class="c-body"><span class="tag">Religioso</span><h3>Cruz</h3><p>Detalhe em blackwork fino.</p></div>
      </article>
    </div>
  </div>
</section>

<section style="padding-top:0">
  <div class="wrap">
    <div class="stats" data-reveal>
      <div class="stat"><b>24<em>h</em></b><span>aberto todos os dias</span></div>
      <div class="stat"><b><em>3</em></b><span>sessões p/ fechamento</span></div>
      <div class="stat"><b>100<em>%</em></b><span>personalizado</span></div>
      <div class="stat"><b>Floripa</b><span>Centro · SC</span></div>
    </div>
  </div>
</section>

<section id="estudio">
  <div class="wrap about">
    <div data-reveal>
      <span class="k" style="font-family:var(--hand);font-size:1.5rem;color:var(--ember);display:block;margin-bottom:.4rem">o espaço</span>
      <h2 style="font-size:clamp(2.6rem,7vw,5rem);margin-bottom:1.4rem">Estúdio no<br>centro de Floripa</h2>
      <p class="lead">O <strong>Tettou Preto INK</strong> é especializado em tatuagens personalizadas, com foco em <strong>realismo preto & cinza</strong>, blackwork e fechamentos. Cada projeto é desenhado sob medida e executado em sessões, até o acabamento final.</p>
      <p class="lead" style="margin-top:1rem">Espaço limpo, agulha nova por cliente e atendimento direto com o artista — do rascunho à última passada. <strong>Aberto 24 horas</strong>, por agendamento.</p>
      <div class="hand">Rua Conselheiro Mafra, 590 — Centro, Florianópolis/SC</div>
    </div>

    <div class="steps" data-reveal>
      <div class="step"><span class="n">01</span><div><h4>Fale com a gente</h4><p>Manda sua ideia pelo WhatsApp ou DM. A gente conversa sobre tamanho, local e estilo.</p></div></div>
      <div class="step"><span class="n">02</span><div><h4>Design & primeira sessão</h4><p>Montamos o projeto e começamos o traço. Fechamentos grandes são divididos em sessões.</p></div></div>
      <div class="step"><span class="n">03</span><div><h4>Fechamento</h4><p>Sessões até o acabamento final, com orientação de cuidado pós-tatuagem.</p></div></div>
    </div>
  </div>
</section>

<section id="estilos" style="padding-top:0">
  <div class="wrap">
    <div class="sec-head" data-reveal>
      <div><span class="k">especialidades</span><h2>Estilos</h2></div>
      <p class="note">Do traço fino ao fechamento pesado — tudo em preto e cinza, feito pra durar.</p>
    </div>
    <div class="styles" data-reveal-group>
      <div class="style-row" data-reveal><span class="n">01</span><h3>Realismo P&amp;C</h3><p>Retratos e figuras em preto e cinza.</p></div>
      <div class="style-row" data-reveal><span class="n">02</span><h3>Blackwork</h3><p>Linhas sólidas, alto contraste e peso.</p></div>
      <div class="style-row" data-reveal><span class="n">03</span><h3>Fechamentos</h3><p>Braço, costas e corpo em sessões.</p></div>
      <div class="style-row" data-reveal><span class="n">04</span><h3>Dotwork</h3><p>Pontilhismo, mandalas e geometria.</p></div>
      <div class="style-row" data-reveal><span class="n">05</span><h3>Fine Line</h3><p>Traço delicado e minimalista.</p></div>
      <div class="style-row" data-reveal><span class="n">06</span><h3>Tradicional</h3><p>Clássicos com contorno marcante.</p></div>
    </div>
  </div>
</section>

<section style="padding-top:0">
  <div class="wrap">
    <div class="vaga" data-reveal>
      <div>
        <span class="k">trabalhe conosco</span>
        <h3>Vaga: Tatuador Residente</h3>
        <p>Procurando um espaço pra tatuar em Floripa? Manda seu portfólio no WhatsApp e a gente conversa.</p>
      </div>
      <a class="btn solid" href="https://wa.me/554831976757" target="_blank" rel="noopener"><span><svg><use href="#wa"/></svg>Enviar portfólio</span></a>
    </div>
  </div>
</section>

<section id="contato" class="contact">
  <div class="wrap">
    <div class="big" data-reveal>Vamos <em>tatuar?</em></div>
    <div class="sub" data-reveal>agende direto pelo whatsapp — aberto 24 horas</div>
    <div class="contact-cta" data-reveal>
      <a class="btn solid lg" href="https://wa.me/554831976757" target="_blank" rel="noopener"><span><svg><use href="#wa"/></svg>(48) 3197-6757</span></a>
      <a class="btn lg" href="tel:+554831976757"><span><svg><use href="#phone"/></svg>Ligar agora</span></a>
    </div>

    <div class="contact-grid" data-reveal>
      <div class="c-box">
        <span class="k"><svg><use href="#phone"/></svg>Telefone / WhatsApp</span>
        <a href="https://wa.me/554831976757" target="_blank" rel="noopener">(48) 3197-6757</a>
        <small>chamar no WhatsApp ou ligar</small>
      </div>
      <div class="c-box">
        <span class="k"><svg><use href="#pin"/></svg>Endereço</span>
        <a href="https://www.google.com/maps/search/?api=1&query=Rua+Conselheiro+Mafra+590+Centro+Florian%C3%B3polis+SC+88010-102" target="_blank" rel="noopener">R. Conselheiro Mafra, 590</a>
        <small>Centro · Florianópolis/SC<br>CEP 88010-102 · <a href="https://www.google.com/maps/search/?api=1&query=Rua+Conselheiro+Mafra+590+Florian%C3%B3polis+SC" target="_blank" rel="noopener" style="color:var(--ember)">ver no mapa</a></small>
      </div>
      <div class="c-box">
        <span class="k"><svg><use href="#clock"/></svg>Horário</span>
        <span class="val open">Aberto 24 horas</span>
        <small>atendimento por agendamento</small>
      </div>
      <div class="c-box">
        <span class="k"><svg><use href="#ig"/></svg>Redes sociais</span>
        <div class="socials">
          <a href="https://www.instagram.com/tettoopreto.ink" target="_blank" rel="noopener"><svg><use href="#ig"/></svg>@tettoopreto.ink · estúdio</a>
          <a href="https://www.instagram.com/2p.ink" target="_blank" rel="noopener"><svg><use href="#ig"/></svg>@2p.ink · Pedro</a>
          <a href="https://www.facebook.com/" target="_blank" rel="noopener"><svg><use href="#fb"/></svg>Pedro Cardoso INK</a>
        </div>
      </div>
    </div>
  </div>
</section>
</main>

<footer>
  <div class="f-brand"><svg class="mark" style="color:var(--bone)"><use href="#mark"/></svg>TETTOO PRETO <b>INK</b></div>
  <div class="f-mid">
    R. Conselheiro Mafra, 590 · Centro, Florianópolis/SC · 88010-102<br>
    <a href="tel:+554831976757">(48) 3197-6757</a> · Aberto 24h · © <span id="yr"></span>
  </div>
  <div class="f-hand">feito à mão em Floripa</div>
</footer>

<script>
(function(){
  var reduce = window.matchMedia('(prefers-reduced-motion: reduce)').matches;
  document.getElementById('yr').textContent = new Date().getFullYear();

  var nav = document.getElementById('nav');
  var onScroll = function(){ nav.classList.toggle('scrolled', window.scrollY > 40); };
  onScroll(); window.addEventListener('scroll', onScroll, {passive:true});

  var burger = document.getElementById('burger'), menu = document.getElementById('mobileMenu');
  burger.addEventListener('click', function(){
    var open = menu.classList.toggle('open');
    burger.classList.toggle('open', open);
    burger.setAttribute('aria-expanded', open);
    document.body.style.overflow = open ? 'hidden' : '';
  });
  menu.querySelectorAll('a').forEach(function(a){
    a.addEventListener('click', function(){
      menu.classList.remove('open'); burger.classList.remove('open');
      burger.setAttribute('aria-expanded','false'); document.body.style.overflow='';
    });
  });

  document.querySelectorAll('[data-reveal-group]').forEach(function(g){
    Array.prototype.forEach.call(g.querySelectorAll('[data-reveal]'), function(el,i){ el.style.transitionDelay = (i*70)+'ms'; });
  });
  if(reduce){
    document.querySelectorAll('[data-reveal]').forEach(function(el){ el.classList.add('in'); });
  } else {
    var io = new IntersectionObserver(function(entries){
      entries.forEach(function(e){ if(e.isIntersecting){ e.target.classList.add('in'); io.unobserve(e.target); } });
    }, {threshold:.12, rootMargin:'0px 0px -8% 0px'});
    document.querySelectorAll('[data-reveal]').forEach(function(el){ io.observe(el); });
  }

  if(!reduce && window.matchMedia('(hover:hover)').matches){
    var dot = document.querySelector('.cursor'), ring = document.querySelector('.cursor-ring');
    var x=innerWidth/2,y=innerHeight/2,rx=x,ry=y;
    window.addEventListener('mousemove', function(e){ x=e.clientX; y=e.clientY; }, {passive:true});
    (function loop(){
      rx += (x-rx)*0.2; ry += (y-ry)*0.2;
      dot.style.transform = 'translate('+x+'px,'+y+'px) translate(-50%,-50%)';
      ring.style.transform = 'translate('+rx+'px,'+ry+'px) translate(-50%,-50%)';
      requestAnimationFrame(loop);
    })();
    document.querySelectorAll('a,button').forEach(function(el){
      el.addEventListener('mouseenter', function(){ document.body.classList.add('cur-big'); });
      el.addEventListener('mouseleave', function(){ document.body.classList.remove('cur-big'); });
    });
  }
})();
</script>
</body>
</html>