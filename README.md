<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Academia Godoi Jiu-Jitsu | Rolim de Moura - RO</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Oswald:wght@500;600;700&family=Work+Sans:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root{
    --ink:#0c0c0c;
    --ink-2:#171212;
    --ink-3:#1f1717;
    --bone:#f1ece1;
    --bone-dim:#c7bfb2;
    --red:#c81e2c;
    --red-dim:#6e1017;
    --red-bright:#e2293a;
    --gold:#d9a441;
    --line:rgba(241,236,225,0.12);
    --radius:2px;
  }
  *{margin:0;padding:0;box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  body{
    background:var(--ink);
    color:var(--bone);
    font-family:'Work Sans',sans-serif;
    line-height:1.55;
    -webkit-font-smoothing:antialiased;
    overflow-x:hidden;
  }
  h1,h2,h3,.display{
    font-family:'Oswald',sans-serif;
    text-transform:uppercase;
    letter-spacing:0.01em;
    font-weight:700;
    line-height:1.05;
  }
  .mono{font-family:'JetBrains Mono',monospace; letter-spacing:0.03em;}
  a{color:inherit;text-decoration:none;}
  img{display:block;max-width:100%;}
  .wrap{max-width:1120px;margin:0 auto;padding:0 24px;}
  ::selection{background:var(--red);color:var(--bone);}

  .tatame{
    position:absolute;inset:0;
    background-image:
      linear-gradient(rgba(241,236,225,0.035) 1px, transparent 1px),
      linear-gradient(90deg, rgba(241,236,225,0.035) 1px, transparent 1px);
    background-size:44px 44px;
    pointer-events:none;
  }

  /* signature: claw-stripe progress rail */
  #rail{
    position:fixed;left:0;top:0;bottom:0;width:10px;z-index:50;
    background:repeating-linear-gradient(180deg, var(--ink-3) 0 26px, var(--ink-3) 26px 30px);
  }
  #rail .fill{
    position:absolute;left:0;top:0;width:100%;height:0%;
    background:repeating-linear-gradient(180deg, var(--red) 0 26px, var(--red-dim) 26px 30px);
    transition:height .08s linear;
  }
  @media (max-width:860px){ #rail{display:none;} }

  header{
    position:sticky;top:0;z-index:40;
    background:rgba(12,12,12,0.9);
    backdrop-filter:blur(8px);
    border-bottom:1px solid var(--line);
  }
  header .wrap{
    display:flex;align-items:center;justify-content:space-between;
    padding-top:12px;padding-bottom:12px;
    margin-left:10px;
  }
  .brand{display:flex;align-items:center;gap:12px;}
  .brand img{height:44px;width:44px;object-fit:cover;border-radius:50%;border:2px solid var(--red);}
  .brand .name{
    font-family:'Oswald',sans-serif;font-weight:700;
    font-size:1.05rem;letter-spacing:0.03em;text-transform:uppercase;
  }
  .brand .name span{display:block;font-family:'JetBrains Mono',monospace;font-size:0.62rem;color:var(--bone-dim);letter-spacing:0.1em;text-transform:none;font-weight:400;}
  nav{display:flex;gap:32px;align-items:center;}
  nav a{font-size:0.85rem;text-transform:uppercase;letter-spacing:0.06em;color:var(--bone-dim);transition:color .2s;}
  nav a:hover{color:var(--bone);}
  @media (max-width:760px){ nav .navlinks{display:none;} }

  .btn{
    display:inline-flex;align-items:center;gap:8px;
    padding:13px 22px;
    font-family:'Oswald',sans-serif;font-weight:600;
    text-transform:uppercase;letter-spacing:0.04em;font-size:0.85rem;
    border-radius:var(--radius);
    transition:transform .18s ease, box-shadow .18s ease;
    white-space:nowrap;
  }
  .btn-primary{background:var(--red);color:var(--bone);box-shadow:0 0 0 1px var(--red-dim);}
  .btn-primary:hover{transform:translateY(-2px);box-shadow:0 8px 22px rgba(200,30,44,0.4);}
  .btn-ghost{border:1px solid var(--line);color:var(--bone);}
  .btn-ghost:hover{border-color:var(--bone-dim);}

  .hero{
    position:relative;
    padding:110px 10px 100px 34px;
    overflow:hidden;
    border-bottom:1px solid var(--line);
    background:radial-gradient(circle at 82% 30%, rgba(200,30,44,0.16), transparent 55%);
  }
  .hero-inner{max-width:1120px;margin:0 auto;padding:0 24px;position:relative;z-index:2;}
  .eyebrow{
    font-family:'JetBrains Mono',monospace;
    font-size:0.78rem;color:var(--red-bright);letter-spacing:0.12em;
    display:flex;align-items:center;gap:10px;margin-bottom:22px;
  }
  .eyebrow::before{content:'';width:26px;height:1px;background:var(--red-bright);}
  .hero h1{
    font-size:clamp(2.4rem, 6.4vw, 5.2rem);
    max-width:14ch;
    margin-bottom:26px;
  }
  .hero h1 em{font-style:normal;color:var(--red-bright);}
  .hero p.lead{
    font-size:1.15rem;color:var(--bone-dim);max-width:46ch;margin-bottom:38px;
  }
  .hero .ctas{display:flex;gap:16px;flex-wrap:wrap;margin-bottom:34px;}
  .trust-row{display:flex;gap:26px;flex-wrap:wrap;align-items:center;font-size:0.85rem;color:var(--bone-dim);}
  .trust-row .stars{color:var(--gold);letter-spacing:2px;}
  .trust-row b{color:var(--bone);}

  .hero-logo{
    position:absolute;right:-30px;top:50%;transform:translateY(-50%);
    width:420px;height:420px;opacity:0.16;
    filter:grayscale(1) contrast(1.2);
    z-index:1;
  }
  @media (max-width:900px){ .hero-logo{display:none;} }
  @media (max-width:860px){ .hero{padding-left:24px;} }

  section{padding:96px 0;position:relative;}
  .section-alt{background:var(--ink-2);}
  .kicker{
    font-family:'JetBrains Mono',monospace;font-size:0.78rem;color:var(--red-bright);
    letter-spacing:0.12em;margin-bottom:14px;display:block;
  }
  .h2{font-size:clamp(1.8rem,3.6vw,2.6rem);max-width:20ch;margin-bottom:18px;}
  .section-lead{color:var(--bone-dim);max-width:56ch;font-size:1.02rem;margin-bottom:56px;}

  .grid-4{display:grid;grid-template-columns:repeat(4,1fr);gap:1px;background:var(--line);border:1px solid var(--line);}
  .grid-4 .card{background:var(--ink);padding:34px 26px;}
  @media (max-width:900px){ .grid-4{grid-template-columns:repeat(2,1fr);} }
  @media (max-width:540px){ .grid-4{grid-template-columns:1fr;} }
  .card .num{font-family:'JetBrains Mono',monospace;color:var(--red-dim);font-size:0.8rem;margin-bottom:16px;}
  .card h3{font-size:1.15rem;margin-bottom:10px;text-transform:none;letter-spacing:0;}
  .card p{color:var(--bone-dim);font-size:0.94rem;}

  /* schedule */
  .schedule{display:grid;grid-template-columns:repeat(2,1fr);gap:22px;}
  @media (max-width:760px){ .schedule{grid-template-columns:1fr;} }
  .day-card{
    background:var(--ink);border:1px solid var(--line);
    overflow:hidden;
  }
  .day-card .day-head{
    background:var(--red);color:var(--bone);
    padding:16px 24px;
    font-family:'Oswald',sans-serif;font-weight:600;
    text-transform:uppercase;letter-spacing:0.03em;font-size:1.02rem;
  }
  .day-card .day-body{padding:22px 24px;}
  .day-card .slot{
    display:flex;align-items:center;justify-content:space-between;
    padding:12px 0;border-bottom:1px solid var(--line);
  }
  .day-card .slot:last-child{border-bottom:none;}
  .day-card .slot .time{font-family:'JetBrains Mono',monospace;font-size:0.95rem;color:var(--bone);min-width:64px;}
  .day-card .slot .tag{
    font-family:'JetBrains Mono',monospace;font-size:0.68rem;letter-spacing:0.08em;
    padding:4px 10px;border-radius:20px;text-transform:uppercase;
  }
  .tag.gi{background:rgba(200,30,44,0.15);color:var(--red-bright);border:1px solid var(--red-dim);}
  .tag.nogi{background:rgba(241,236,225,0.08);color:var(--bone-dim);border:1px solid var(--line);}
  .tag.kids{background:rgba(217,164,65,0.15);color:var(--gold);border:1px solid rgba(217,164,65,0.4);}

  .proof{display:grid;grid-template-columns:0.9fr 1.3fr;gap:60px;align-items:center;}
  @media (max-width:860px){ .proof{grid-template-columns:1fr;gap:36px;} }
  .rating-block{
    border:1px solid var(--line);padding:36px;text-align:center;background:var(--ink);
  }
  .rating-block .big{font-family:'Oswald',sans-serif;font-size:4rem;font-weight:700;color:var(--red-bright);line-height:1;}
  .rating-block .stars{color:var(--gold);font-size:1.3rem;letter-spacing:3px;margin:12px 0 8px;}
  .rating-block .cap{color:var(--bone-dim);font-size:0.85rem;}
  blockquote{
    font-family:'Oswald',sans-serif;font-weight:500;text-transform:none;
    font-size:1.5rem;line-height:1.4;color:var(--bone);
    border-left:3px solid var(--red);padding-left:26px;
  }
  blockquote cite{
    display:block;margin-top:18px;font-family:'JetBrains Mono',monospace;
    font-size:0.8rem;color:var(--bone-dim);font-style:normal;
  }

  .offer{
    position:relative;
    background:linear-gradient(135deg,var(--red-dim),var(--ink));
    border:1px solid var(--line);
    padding:64px 46px;text-align:center;
  }
  .offer h2{font-size:clamp(1.8rem,4vw,2.8rem);margin-bottom:16px;}
  .offer p{color:var(--bone-dim);max-width:52ch;margin:0 auto 30px;}
  .offer .btn-primary{font-size:0.95rem;padding:16px 30px;}
  .offer .fine{margin-top:18px;font-family:'JetBrains Mono',monospace;font-size:0.75rem;color:var(--bone-dim);}

  .loc{display:grid;grid-template-columns:1fr 1fr;gap:1px;background:var(--line);border:1px solid var(--line);}
  @media (max-width:860px){ .loc{grid-template-columns:1fr;} }
  .loc-info{background:var(--ink);padding:44px;}
  .loc-info .row{display:flex;gap:16px;margin-bottom:26px;align-items:flex-start;}
  .loc-info .row .k{font-family:'JetBrains Mono',monospace;font-size:0.72rem;color:var(--red-bright);letter-spacing:0.1em;min-width:88px;padding-top:3px;}
  .loc-info .row .v{color:var(--bone);font-size:0.98rem;}
  .loc-info .row .v small{display:block;color:var(--bone-dim);margin-top:4px;}
  .loc-map{background:var(--ink-3);min-height:360px;}
  .loc-map iframe{width:100%;height:100%;min-height:360px;border:0;filter:grayscale(0.5) contrast(1.05);}

  footer{border-top:1px solid var(--line);padding:44px 0;background:var(--ink-2);}
  footer .wrap{display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:16px;}
  footer .fbrand{display:flex;align-items:center;gap:12px;}
  footer .fbrand img{height:34px;width:34px;border-radius:50%;object-fit:cover;border:2px solid var(--red);}
  footer .fname{font-family:'Oswald',sans-serif;text-transform:uppercase;font-weight:700;letter-spacing:0.04em;}
  footer .fmeta{color:var(--bone-dim);font-size:0.82rem;}

  .sticky-cta{
    position:fixed;bottom:0;left:0;right:0;z-index:60;
    background:var(--ink);border-top:1px solid var(--line);
    padding:12px 16px;display:none;
    align-items:center;justify-content:center;
  }
  .sticky-cta .btn{width:100%;justify-content:center;}
  @media (max-width:640px){ .sticky-cta{display:flex;} body{padding-bottom:64px;} }

  .reveal{opacity:0;transform:translateY(18px);transition:opacity .6s ease, transform .6s ease;}
  .reveal.in{opacity:1;transform:translateY(0);}
  @media (prefers-reduced-motion: reduce){
    .reveal{opacity:1;transform:none;transition:none;}
    html{scroll-behavior:auto;}
  }
</style>
</head>
<body>

<div id="rail"><div class="fill" id="rail-fill"></div></div>

<header>
  <div class="wrap">
    <div class="brand">
      <img src="data:image/jpeg;base64,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
