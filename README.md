<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0">
<title>RD Vivaha Jewellers • Erode • Bridal Luxury</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;1,300;1,400&family=Cinzel:wght@400;500;600;700&family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/Swiper/11.0.5/swiper-bundle.min.css">
<style>
:root{
  --g:#C9A84C;--g2:#E8C96A;--g3:#F5E0A0;--g4:#A07820;
  --bk:#060504;--bk2:#0C0A08;--bk3:#141210;
  --cr:#F2EDE3;--cr2:#C8BBA2;--cr3:#8A7D65;
  --mr:#5C0F0F;--mr2:#7A1515;
  --ease:cubic-bezier(0.23,1,0.32,1);
}
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box}
html{scroll-behavior:smooth}
body{background:var(--bk);color:var(--cr);font-family:'Cormorant Garamond',serif;
  font-weight:300;line-height:1.65;overflow-x:hidden;cursor:none}

/* ═══ CURSOR ═══ */
#cur{position:fixed;width:8px;height:8px;background:var(--g2);border-radius:50%;
  pointer-events:none;z-index:999999;transform:translate(-50%,-50%);
  transition:width .15s,height .15s,background .2s;mix-blend-mode:screen}
#cur-r{position:fixed;width:34px;height:34px;border:1px solid rgba(201,168,76,.55);
  border-radius:50%;pointer-events:none;z-index:999998;transform:translate(-50%,-50%);
  transition:all .1s linear}
body.hv #cur{width:18px;height:18px;background:var(--g);mix-blend-mode:normal}
body.hv #cur-r{width:52px;height:52px;border-color:var(--g);opacity:.8}

/* ═══ PRELOADER ═══ */
#pl{position:fixed;inset:0;background:var(--bk);z-index:100000;
  display:flex;flex-direction:column;align-items:center;justify-content:center;gap:28px;
  transition:opacity 1.2s var(--ease),visibility 1.2s}
#pl.out{opacity:0;visibility:hidden}
.pl-mandala{width:160px;height:160px;animation:spin 10s linear infinite}
.pl-mandala svg{width:100%;height:100%}
.pl-name{font-family:'Cinzel',serif;font-size:clamp(1.4rem,4vw,2.2rem);color:var(--g);
  letter-spacing:10px;text-align:center;animation:breathe 2s ease-in-out infinite}
.pl-sub{font-size:.55rem;letter-spacing:8px;color:var(--cr3);text-align:center;font-family:'Cinzel',serif}
.pl-tamil{font-style:italic;color:rgba(201,168,76,.6);font-size:1rem;letter-spacing:4px}
.pl-bar{width:220px;height:1px;background:rgba(201,168,76,.1);overflow:hidden;position:relative}
.pl-fill{position:absolute;left:-100%;top:0;width:100%;height:100%;
  background:linear-gradient(90deg,transparent,var(--g),var(--g2),var(--g),transparent);
  animation:barslide 1.6s ease-in-out infinite}
@keyframes spin{to{transform:rotate(360deg)}}
@keyframes breathe{0%,100%{opacity:1}50%{opacity:.45}}
@keyframes barslide{0%{left:-100%}100%{left:100%}}

/* ═══ PARTICLES ═══ */
#pc{position:fixed;inset:0;pointer-events:none;z-index:2}

/* ═══ NAV ═══ */
#nav{position:fixed;top:0;left:0;right:0;z-index:5000;
  padding:20px 56px;display:flex;align-items:center;justify-content:space-between;
  transition:all .5s var(--ease)}
#nav.scrolled{padding:12px 56px;background:rgba(6,5,4,.94);
  backdrop-filter:blur(28px) saturate(160%);
  border-bottom:1px solid rgba(201,168,76,.12)}
.n-logo{font-family:'Cinzel',serif;font-size:1.15rem;letter-spacing:5px;color:var(--g);
  text-decoration:none;display:flex;flex-direction:column;line-height:1.2}
.n-logo small{font-size:.42rem;letter-spacing:6px;color:var(--cr3)}
.n-links{display:flex;gap:40px;list-style:none}
.n-links a{color:rgba(242,237,227,.6);text-decoration:none;font-family:'Cinzel',serif;
  font-size:.6rem;letter-spacing:3px;text-transform:uppercase;transition:color .3s;
  position:relative;padding:4px 0}
.n-links a::after{content:'';position:absolute;bottom:0;left:0;width:0;height:1px;
  background:var(--g);transition:width .4s var(--ease)}
.n-links a:hover{color:var(--g)}
.n-links a:hover::after{width:100%}
.n-right{display:flex;align-items:center;gap:12px}
.n-ico{background:none;border:1px solid rgba(201,168,76,.28);color:var(--g);
  width:40px;height:40px;border-radius:50%;display:flex;align-items:center;justify-content:center;
  cursor:none;transition:all .3s;font-size:.9rem;position:relative}
.n-ico:hover{background:var(--g);color:var(--bk);border-color:var(--g)}
#wbadge{position:absolute;top:-4px;right:-4px;background:var(--mr2);color:#fff;
  font-size:.5rem;width:16px;height:16px;border-radius:50%;
  display:none;align-items:center;justify-content:center}
#wbadge.on{display:flex}
.n-cta{font-family:'Cinzel',serif;font-size:.6rem;letter-spacing:3px;
  background:var(--g);color:var(--bk);border:none;padding:11px 26px;
  cursor:none;transition:all .3s;clip-path:polygon(8px 0,100% 0,calc(100% - 8px) 100%,0 100%)}
.n-cta:hover{background:var(--g2);box-shadow:0 8px 30px rgba(201,168,76,.35)}
.menu-btn{display:none;background:none;border:1px solid rgba(201,168,76,.3);
  color:var(--g);width:44px;height:44px;cursor:none;align-items:center;
  justify-content:center;font-size:1.1rem;transition:all .3s}
.menu-btn:hover{background:var(--g);color:var(--bk)}

/* Mobile menu */
.scrim{position:fixed;inset:0;background:rgba(0,0,0,.75);z-index:4999;
  opacity:0;visibility:hidden;transition:all .3s;backdrop-filter:blur(4px)}
.scrim.open{opacity:1;visibility:visible}
.mob{position:fixed;top:0;right:-110%;width:min(380px,100vw);height:100vh;
  background:var(--bk2);z-index:5001;padding:80px 36px;
  transition:right .55s var(--ease);border-left:1px solid rgba(201,168,76,.12);
  overflow-y:auto}
.mob.open{right:0}
.mob-x{position:absolute;top:20px;right:20px;background:none;
  border:1px solid rgba(201,168,76,.3);color:var(--g);width:40px;height:40px;
  border-radius:50%;cursor:none;display:flex;align-items:center;justify-content:center;
  font-size:1.1rem;transition:all .3s}
.mob-x:hover{background:var(--g);color:var(--bk);transform:rotate(90deg)}
.mob-links a{display:block;color:var(--cr2);text-decoration:none;font-family:'Playfair Display',serif;
  font-size:1.7rem;font-weight:300;padding:15px 0;border-bottom:1px solid rgba(201,168,76,.07);
  transition:all .3s}
.mob-links a:hover{color:var(--g);padding-left:18px}

/* ═══ HERO ═══ */
#hero{min-height:100vh;position:relative;display:flex;align-items:center;
  justify-content:center;overflow:hidden}
.h-vid{position:absolute;inset:0;width:100%;height:100%;object-fit:cover;
  filter:brightness(.42) saturate(1.15);z-index:0;
  transform:scale(1.08);transition:transform 20s ease-out}
.h-vid.on{transform:scale(1)}
.h-grad{position:absolute;inset:0;z-index:1;
  background:
    radial-gradient(ellipse 110% 70% at 50% 115%,var(--bk) 0%,transparent 55%),
    radial-gradient(ellipse 70% 50% at 50% -10%,rgba(201,168,76,.07) 0%,transparent 50%),
    linear-gradient(to bottom,rgba(6,5,4,.35) 0%,transparent 45%,rgba(6,5,4,.55) 100%)}
.h-pattern{position:absolute;inset:0;z-index:1;
  background-image:repeating-linear-gradient(45deg,rgba(201,168,76,.015) 0,rgba(201,168,76,.015) 1px,transparent 1px,transparent 10px)}
.h-mandala{position:absolute;top:50%;left:50%;transform:translate(-50%,-50%);
  width:min(950px,130vw);opacity:.038;animation:spin 70s linear infinite;z-index:1;pointer-events:none}
/* Floating jewels hero */
.h-jewel{position:absolute;z-index:2;pointer-events:none;
  animation:jewelfloat ease-in-out infinite}
@keyframes jewelfloat{0%,100%{transform:translateY(0) rotate(0deg)}50%{transform:translateY(-22px) rotate(8deg)}}
.h-content{position:relative;z-index:4;text-align:center;max-width:1080px;padding:0 24px}
.h-label{font-family:'Cinzel',serif;font-size:.62rem;letter-spacing:12px;color:var(--g);
  margin-bottom:24px;opacity:0;animation:riseUp .8s var(--ease) .3s forwards;
  display:flex;align-items:center;justify-content:center;gap:14px}
.h-label::before,.h-label::after{content:'';width:44px;height:1px;
  background:linear-gradient(90deg,transparent,rgba(201,168,76,.6))}
.h-label::after{transform:scaleX(-1)}
.h-tamil{font-style:italic;font-size:1.15rem;letter-spacing:6px;color:rgba(201,168,76,.8);
  margin-bottom:24px;opacity:0;animation:riseUp .8s var(--ease) .48s forwards}
.h-h1{font-family:'Playfair Display',serif;font-weight:900;
  font-size:clamp(4rem,13vw,9rem);line-height:.9;margin-bottom:30px;
  opacity:0;animation:riseUp .9s var(--ease) .62s forwards}
.h-h1 .t1{display:block;font-size:.38em;letter-spacing:16px;color:var(--cr3);
  text-transform:uppercase;margin-bottom:8px;font-weight:400}
.h-h1 .t2{display:block;
  background:linear-gradient(135deg,var(--cr3) 0%,var(--g2) 22%,var(--g) 42%,var(--g3) 52%,var(--g) 68%,var(--cr) 100%);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  background-size:200%;animation:shimmer 4s ease infinite}
.h-h1 .t3{display:block;font-style:italic;font-size:.5em;color:var(--cr2);margin-top:10px;font-weight:400}
@keyframes shimmer{0%{background-position:0%}50%{background-position:100%}100%{background-position:0%}}
.h-desc{font-size:1.2rem;color:var(--cr2);max-width:580px;margin:0 auto 44px;
  line-height:1.85;opacity:0;animation:riseUp .8s var(--ease) .85s forwards}
.h-btns{display:flex;gap:18px;justify-content:center;flex-wrap:wrap;
  opacity:0;animation:riseUp .8s var(--ease) 1s forwards}
.h-scroll{position:absolute;bottom:38px;left:50%;transform:translateX(-50%);z-index:4;
  display:flex;flex-direction:column;align-items:center;gap:10px;
  opacity:0;animation:fadeIn 1.2s 1.6s forwards}
.h-sline{width:1px;height:56px;background:linear-gradient(to bottom,var(--g),transparent);
  animation:spulse 2.2s ease-in-out infinite}
.h-stxt{font-family:'Cinzel',serif;font-size:.48rem;letter-spacing:6px;color:var(--cr3)}
@keyframes riseUp{from{opacity:0;transform:translateY(50px)}to{opacity:1;transform:translateY(0)}}
@keyframes fadeIn{from{opacity:0}to{opacity:1}}
@keyframes spulse{0%,100%{transform:scaleY(.5);opacity:.3}50%{transform:scaleY(1);opacity:1}}

/* ═══ BUTTONS ═══ */
.btn{display:inline-flex;align-items:center;gap:10px;padding:16px 38px;
  font-family:'Cinzel',serif;font-size:.62rem;text-transform:uppercase;letter-spacing:4px;
  text-decoration:none;cursor:none;border:none;
  position:relative;overflow:hidden;transition:all .45s var(--ease)}
.btn-g{background:var(--g);color:var(--bk)}
.btn-g::after{content:'';position:absolute;inset:0;
  background:linear-gradient(120deg,transparent,rgba(255,255,255,.3),transparent);
  transform:translateX(-100%);transition:transform .55s var(--ease)}
.btn-g:hover{background:var(--g2);transform:translateY(-4px);box-shadow:0 18px 40px rgba(201,168,76,.3)}
.btn-g:hover::after{transform:translateX(100%)}
.btn-o{background:transparent;color:var(--g);border:1px solid rgba(201,168,76,.55)}
.btn-o::before{content:'';position:absolute;inset:0;background:var(--g);
  transform:scaleX(0);transform-origin:left;transition:transform .4s var(--ease);z-index:-1}
.btn-o:hover{color:var(--bk);transform:translateY(-4px);box-shadow:0 14px 30px rgba(201,168,76,.2)}
.btn-o:hover::before{transform:scaleX(1)}
.btn-r{background:var(--mr);color:var(--cr);border:none}
.btn-r:hover{background:var(--mr2);transform:translateY(-3px)}

/* ═══ MARQUEE ═══ */
.mq-wrap{background:var(--bk2);border-top:1px solid rgba(201,168,76,.1);
  border-bottom:1px solid rgba(201,168,76,.1);padding:16px 0;overflow:hidden;
  position:relative;z-index:5}
.mq-inner{display:inline-flex;animation:mq 32s linear infinite}
.mq-inner:hover{animation-play-state:paused}
.mq-set{display:flex;white-space:nowrap}
.mq-set span{font-family:'Cinzel',serif;font-size:.58rem;letter-spacing:5px;color:var(--cr3);
  padding:0 26px;transition:color .3s}
.mq-set span:hover{color:var(--g)}
.mq-set i{color:rgba(201,168,76,.4);font-size:.38rem}
@keyframes mq{from{transform:translateX(0)}to{transform:translateX(-50%)}}

/* ═══ SECTIONS ═══ */
section{padding:110px 0;position:relative;z-index:5}
.wrap{max-width:1400px;margin:0 auto;padding:0 56px}
.s-tag{font-family:'Cinzel',serif;font-size:.58rem;letter-spacing:8px;color:var(--g);
  text-transform:uppercase;margin-bottom:16px;
  display:flex;align-items:center;justify-content:center;gap:12px}
.s-tag::before,.s-tag::after{content:'';width:32px;height:1px;
  background:linear-gradient(90deg,transparent,rgba(201,168,76,.5),transparent)}
.s-tag.lft{justify-content:flex-start}.s-tag.lft::before{display:none}
.s-h2{font-family:'Playfair Display',serif;font-size:clamp(2.6rem,5.5vw,4.8rem);
  font-weight:900;line-height:1.1;margin-bottom:18px}
.s-h2 em{font-style:italic;
  background:linear-gradient(135deg,var(--g4),var(--g),var(--g2));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text}
.divider{width:70px;height:1px;background:linear-gradient(90deg,transparent,var(--g),transparent);
  margin:0 auto 60px}
.divider.lft{margin:0 0 60px}
.sec-head{text-align:center;margin-bottom:70px}

/* ═══ COLLECTIONS SWIPER ═══ */
.colSwiper{padding:0 56px 50px!important;overflow:visible!important}
.colSwiper .swiper-slide{width:320px}
.cc{position:relative;aspect-ratio:3/4;overflow:hidden;cursor:none;
  border:1px solid rgba(201,168,76,.08)}
.cc:hover{border-color:rgba(201,168,76,.45)}
.cc img{width:100%;height:100%;object-fit:cover;transition:transform 1.1s var(--ease)}
.cc:hover img{transform:scale(1.12)}
.cc-ov{position:absolute;inset:0;
  background:linear-gradient(to top,rgba(6,5,4,.96) 0%,rgba(6,5,4,.15) 55%,transparent 100%);
  display:flex;flex-direction:column;justify-content:flex-end;padding:30px;
  transition:background .5s}
.cc:hover .cc-ov{background:linear-gradient(to top,rgba(201,168,76,.38) 0%,rgba(6,5,4,.1) 55%,transparent 100%)}
.cc-cat{font-family:'Cinzel',serif;font-size:.55rem;letter-spacing:4px;color:var(--g);margin-bottom:6px}
.cc-name{font-family:'Playfair Display',serif;font-size:2.1rem;font-weight:700;
  margin-bottom:10px;transform:translateY(0);transition:transform .4s var(--ease)}
.cc:hover .cc-name{transform:translateY(-10px)}
.cc-tamil{font-style:italic;color:rgba(242,237,227,.45);font-size:.9rem;margin-bottom:8px}
.cc-cta{font-family:'Cinzel',serif;font-size:.55rem;letter-spacing:3px;color:var(--g2);
  opacity:0;transform:translateY(12px);transition:all .4s var(--ease) .06s;
  display:flex;align-items:center;gap:8px}
.cc:hover .cc-cta{opacity:1;transform:translateY(0)}
.cc-shine{position:absolute;inset:0;
  background:linear-gradient(135deg,transparent 38%,rgba(255,255,255,.05) 50%,transparent 62%);
  transform:translateX(-100%);transition:transform .9s var(--ease);z-index:1}
.cc:hover .cc-shine{transform:translateX(100%)}
.swiper-pagination-bullet{background:rgba(201,168,76,.35)!important}
.swiper-pagination-bullet-active{background:var(--g)!important}

/* ═══ 50-IMAGE MOSAIC GRID ═══ */
.gallery-section{background:var(--bk2)}
.gal-grid{display:grid;gap:5px;
  grid-template-columns:repeat(5,1fr);
  grid-auto-rows:200px}
.gi{overflow:hidden;position:relative;cursor:none}
.gi.tall{grid-row:span 2}
.gi.wide{grid-column:span 2}
.gi.large{grid-column:span 2;grid-row:span 2}
.gi img{width:100%;height:100%;object-fit:cover;transition:transform .9s var(--ease),filter .5s}
.gi:hover img{transform:scale(1.14);filter:brightness(1.1) saturate(1.2)}
.gi-ov{position:absolute;inset:0;
  background:linear-gradient(135deg,rgba(201,168,76,.55),rgba(92,15,15,.4));
  display:flex;align-items:center;justify-content:center;
  opacity:0;transition:opacity .4s}
.gi:hover .gi-ov{opacity:1}
.gi-ov i{color:#fff;font-size:2rem;transform:scale(0);transition:transform .4s var(--ease)}
.gi:hover .gi-ov i{transform:scale(1)}
.gi-cap{position:absolute;bottom:0;left:0;right:0;
  background:linear-gradient(to top,rgba(6,5,4,.9),transparent);
  padding:16px 14px 12px;
  transform:translateY(100%);transition:transform .4s var(--ease)}
.gi:hover .gi-cap{transform:translateY(0)}
.gi-cap span{font-family:'Cinzel',serif;font-size:.52rem;letter-spacing:3px;color:var(--g);display:block}
.gi-cap p{font-size:.78rem;color:var(--cr2)}

/* ═══ VIDEO SECTIONS ═══ */
.vs{position:relative;min-height:700px;display:flex;align-items:center;overflow:hidden}
.vs-vid{position:absolute;inset:0;width:100%;height:100%;object-fit:cover}
.vs-dark{position:absolute;inset:0;
  background:linear-gradient(100deg,rgba(6,5,4,.97) 0%,rgba(6,5,4,.65) 42%,rgba(6,5,4,.2) 70%)}
.vs-content{position:relative;z-index:2;max-width:600px}
.vs-content p{color:var(--cr2);line-height:1.9;font-size:1.05rem;margin-bottom:32px}
.vs-stats{display:flex;gap:44px;margin:32px 0;flex-wrap:wrap}
.vss-n{font-family:'Playfair Display',serif;font-size:3.5rem;font-weight:900;color:var(--g);line-height:1}
.vss-l{font-family:'Cinzel',serif;font-size:.56rem;letter-spacing:3px;color:var(--cr3);margin-top:4px}
.vs-line{width:1px;height:56px;background:rgba(201,168,76,.2);align-self:center}
/* orbs */
.orb{position:absolute;border-radius:50%;pointer-events:none;animation:orbF 9s ease-in-out infinite}
.orb1{width:450px;height:450px;top:-80px;right:-80px;
  background:radial-gradient(circle,rgba(201,168,76,.055) 0%,transparent 70%);animation-delay:-3s}
.orb2{width:280px;height:280px;bottom:60px;right:240px;
  background:radial-gradient(circle,rgba(201,168,76,.04) 0%,transparent 70%);animation-delay:-6s}
@keyframes orbF{0%,100%{transform:translateY(0) scale(1)}50%{transform:translateY(-28px) scale(1.08)}}

/* ═══ PRODUCTS ═══ */
.prod-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(280px,1fr));gap:22px}
.pc{background:linear-gradient(145deg,var(--bk3),var(--bk2));
  border:1px solid rgba(201,168,76,.06);overflow:hidden;
  transition:all .6s var(--ease);position:relative}
.pc:hover{transform:translateY(-14px);border-color:rgba(201,168,76,.38);
  box-shadow:0 36px 60px rgba(0,0,0,.6)}
.pi{aspect-ratio:1;overflow:hidden;position:relative}
.pi img{width:100%;height:100%;object-fit:cover;transition:transform .95s var(--ease)}
.pc:hover .pi img{transform:scale(1.18)}
.pbadge{position:absolute;top:14px;left:14px;z-index:2;background:linear-gradient(135deg,var(--g4),var(--g));
  color:var(--bk);padding:5px 12px;font-family:'Cinzel',serif;font-size:.52rem;letter-spacing:2px;
  clip-path:polygon(6px 0,100% 0,calc(100% - 6px) 100%,0 100%)}
.pbadge.red{background:linear-gradient(135deg,var(--mr),var(--mr2))}
.p-acts{position:absolute;top:14px;right:14px;display:flex;flex-direction:column;
  gap:8px;z-index:2;opacity:0;transform:translateX(10px);transition:all .4s}
.pc:hover .p-acts{opacity:1;transform:translateX(0)}
.p-act{width:36px;height:36px;background:rgba(6,5,4,.85);
  border:1px solid rgba(201,168,76,.22);border-radius:50%;
  display:flex;align-items:center;justify-content:center;color:var(--g);
  cursor:none;transition:all .3s;font-size:.82rem;backdrop-filter:blur(4px)}
.p-act:hover,.p-act.wd{background:var(--g);color:var(--bk);border-color:var(--g)}
.p-act.wh{background:var(--mr2);color:#fff;border-color:var(--mr2)}
.pinfo{padding:22px 20px}
.pname{font-family:'Playfair Display',serif;font-size:1.5rem;font-weight:700;margin-bottom:4px}
.pcat{color:var(--cr3);font-size:.75rem;margin-bottom:16px}
.pfoot{display:flex;align-items:center;justify-content:space-between}
.pprice{font-family:'Playfair Display',serif;font-size:1.35rem;font-weight:700;
  background:linear-gradient(135deg,var(--g),var(--g2));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text}
.pqv{background:none;border:1px solid rgba(201,168,76,.22);color:var(--g);
  padding:8px 16px;font-family:'Cinzel',serif;font-size:.55rem;letter-spacing:2px;
  cursor:none;transition:all .3s}
.pqv:hover{background:var(--g);color:var(--bk)}

/* ═══ HERITAGE NUMBERS ═══ */
.h-grid{display:grid;grid-template-columns:repeat(4,1fr);
  border-left:1px solid rgba(201,168,76,.08)}
.hcell{padding:56px 36px;text-align:center;border-right:1px solid rgba(201,168,76,.08);
  position:relative;overflow:hidden;transition:background .4s}
.hcell::before{content:'';position:absolute;inset:0;
  background:radial-gradient(circle at 50% 50%,rgba(201,168,76,.06) 0%,transparent 70%);
  opacity:0;transition:opacity .5s}
.hcell:hover::before{opacity:1}
.hn{font-family:'Playfair Display',serif;font-size:4.2rem;font-weight:900;line-height:1;
  margin-bottom:8px;
  background:linear-gradient(135deg,var(--g4),var(--g),var(--g2));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  transition:transform .4s var(--ease)}
.hcell:hover .hn{transform:scale(1.06)}
.hl{font-family:'Cinzel',serif;font-size:.58rem;letter-spacing:4px;color:var(--cr3)}

/* ═══ BRIDAL STORY SPLIT ═══ */
.bs{display:grid;grid-template-columns:1fr 1fr;min-height:640px;overflow:hidden}
.bs-l{position:relative;overflow:hidden}
.bs-l img{width:100%;height:100%;object-fit:cover;display:block;transition:transform 9s var(--ease)}
.bs-l:hover img{transform:scale(1.06)}
.bs-l-ov{position:absolute;inset:0;background:linear-gradient(to right,transparent 55%,var(--bk) 100%)}
.bs-r{background:var(--bk);display:flex;align-items:center;padding:72px 60px 72px 68px;
  position:relative;overflow:hidden}
.bs-r::before{content:'';position:absolute;top:-80px;right:-80px;width:380px;height:380px;
  border-radius:50%;background:radial-gradient(circle,rgba(201,168,76,.05) 0%,transparent 70%)}
.bs-r p{color:var(--cr2);line-height:1.95;margin-bottom:24px;font-size:1rem}

/* ═══ TESTIMONIALS ═══ */
.t-sec{background:var(--bk2)}
.testiSwiper .swiper-slide{height:auto;padding:8px}
.tc{background:linear-gradient(145deg,var(--bk3),var(--bk2));
  border:1px solid rgba(201,168,76,.09);padding:40px 36px;
  transition:all .4s var(--ease);height:100%;position:relative;overflow:hidden}
.tc::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;
  background:linear-gradient(90deg,transparent,var(--g),transparent);
  transform:scaleX(0);transition:transform .5s var(--ease);transform-origin:center}
.tc:hover::before{transform:scaleX(1)}
.tc:hover{border-color:rgba(201,168,76,.25);transform:translateY(-8px)}
.tc-q{font-family:'Playfair Display',serif;font-size:5rem;font-weight:900;
  color:var(--g);opacity:.18;line-height:1;margin-bottom:14px}
.tc-t{font-style:italic;font-size:1.1rem;line-height:1.95;margin-bottom:24px;color:var(--cr)}
.tc-auth{display:flex;align-items:center;gap:12px}
.tc-av{width:48px;height:48px;border-radius:50%;
  background:linear-gradient(135deg,var(--g4),var(--g2));
  display:flex;align-items:center;justify-content:center;color:var(--bk);
  font-weight:700;font-size:.95rem;border:1.5px solid var(--g);flex-shrink:0}
.tc-name{font-family:'Cinzel',serif;font-size:.7rem;letter-spacing:2px;margin-bottom:3px}
.tc-loc{font-size:.75rem;color:var(--cr3)}
.tc-stars{color:var(--g);font-size:.75rem;margin-top:4px;letter-spacing:2px}

/* ═══ INSTAGRAM MOSAIC ═══ */
.ig-grid{display:grid;grid-template-columns:repeat(4,1fr);
  grid-template-rows:repeat(2,220px);gap:5px}
.ig-item{overflow:hidden;cursor:none;position:relative}
.ig-item:first-child{grid-row:1/3;grid-column:1/2}
.ig-item img{width:100%;height:100%;object-fit:cover;transition:transform 1s var(--ease)}
.ig-item:hover img{transform:scale(1.12)}
.ig-ov{position:absolute;inset:0;
  background:linear-gradient(135deg,rgba(201,168,76,.55),rgba(92,15,15,.45));
  display:flex;align-items:center;justify-content:center;opacity:0;transition:opacity .4s}
.ig-item:hover .ig-ov{opacity:1}
.ig-ov i{color:#fff;font-size:2rem;transform:scale(0);transition:transform .4s var(--ease)}
.ig-item:hover .ig-ov i{transform:scale(1)}

/* ═══ ABOUT ═══ */
.ab-grid{display:grid;grid-template-columns:1fr 1fr;gap:88px;align-items:center}
.ab-text{color:var(--cr2);line-height:1.95;margin-bottom:32px;font-size:1rem}
.ab-feats{display:grid;grid-template-columns:1fr 1fr;gap:18px;margin-bottom:36px}
.af{display:flex;align-items:flex-start;gap:14px;padding:17px;
  border:1px solid rgba(201,168,76,.08);transition:all .35s}
.af:hover{border-color:rgba(201,168,76,.35);background:rgba(201,168,76,.04)}
.af-ico{width:42px;height:42px;flex-shrink:0;background:rgba(201,168,76,.07);
  border:1px solid rgba(201,168,76,.14);display:flex;align-items:center;justify-content:center;
  color:var(--g);font-size:1.05rem;transition:all .4s}
.af:hover .af-ico{background:var(--g);color:var(--bk);transform:rotateY(180deg)}
.af-t{font-family:'Playfair Display',serif;font-size:1.05rem;margin-bottom:3px}
.af-d{font-size:.72rem;color:var(--cr3)}
.ab-img{position:relative}
.ab-img img{width:100%;display:block;border:1px solid rgba(201,168,76,.14)}
.ab-corner{position:absolute;width:52px;height:52px;border-color:var(--g);border-style:solid}
.ab-corner.tl{top:-16px;left:-16px;border-width:1px 0 0 1px}
.ab-corner.br{bottom:-16px;right:-16px;border-width:0 1px 1px 0}
.ab-tag{position:absolute;bottom:-20px;right:-20px;
  background:var(--g);color:var(--bk);padding:14px 22px;
  font-family:'Cinzel',serif;font-size:.58rem;letter-spacing:3px;font-weight:700}
.ab-tag span{display:block;font-family:'Playfair Display',serif;font-size:2rem;
  font-weight:900;letter-spacing:0;line-height:1}

/* ═══ AI TRY-ON — SNAPCHAT STYLE ═══ */
#tryon{background:var(--bk);overflow:hidden;position:relative}
#tryon::before,#tryon::after{content:'';position:absolute;top:50%;left:50%;
  border-radius:50%;border:1px solid rgba(201,168,76,.05);animation:ringPulse 5s ease-in-out infinite}
#tryon::before{width:700px;height:700px;transform:translate(-50%,-50%)}
#tryon::after{width:500px;height:500px;transform:translate(-50%,-50%);animation-delay:1.2s}
@keyframes ringPulse{0%,100%{transform:translate(-50%,-50%) scale(1);opacity:.5}
  50%{transform:translate(-50%,-50%) scale(1.07);opacity:1}}
.ai-badge{display:inline-block;background:linear-gradient(135deg,var(--g4),var(--g));
  color:var(--bk);padding:8px 22px;font-family:'Cinzel',serif;font-size:.6rem;
  letter-spacing:5px;margin-bottom:28px;font-weight:700;
  clip-path:polygon(10px 0,100% 0,calc(100% - 10px) 100%,0 100%);
  animation:badgeGlow 2.2s ease-in-out infinite}
@keyframes badgeGlow{0%,100%{box-shadow:0 0 0 rgba(201,168,76,0)}50%{box-shadow:0 0 32px rgba(201,168,76,.35)}}

/* TRY-ON MAIN UI */
.tryon-ui{display:grid;grid-template-columns:1fr 1.4fr;gap:50px;align-items:start;margin-top:44px}
.tryon-cam-box{
  position:relative;aspect-ratio:9/16;background:var(--bk2);
  border:2px solid rgba(201,168,76,.25);overflow:hidden;max-height:580px}
#camFeed{width:100%;height:100%;object-fit:cover;display:block;
  transform:scaleX(-1)} /* mirror */
#camCanvas{position:absolute;inset:0;width:100%;height:100%;pointer-events:none}
#photoPreview{width:100%;height:100%;object-fit:cover;display:none;position:absolute;inset:0}
.cam-corner{position:absolute;width:22px;height:22px;border-color:var(--g);border-style:solid;z-index:3}
.cam-corner.tl{top:10px;left:10px;border-width:2px 0 0 2px}
.cam-corner.tr{top:10px;right:10px;border-width:2px 2px 0 0}
.cam-corner.bl{bottom:10px;left:10px;border-width:0 0 2px 2px}
.cam-corner.br{bottom:10px;right:10px;border-width:0 2px 2px 0}
.cam-scan{position:absolute;left:0;right:0;height:2px;
  background:linear-gradient(90deg,transparent,rgba(201,168,76,.8),transparent);
  top:0;z-index:3;animation:camScan 3s ease-in-out infinite;opacity:0}
.cam-scan.on{opacity:1}
@keyframes camScan{0%{top:0;opacity:0}5%{opacity:1}95%{opacity:1}100%{top:100%;opacity:0}}
.cam-label{position:absolute;bottom:12px;left:50%;transform:translateX(-50%);
  font-family:'Cinzel',serif;font-size:.5rem;letter-spacing:4px;color:rgba(201,168,76,.7);
  background:rgba(6,5,4,.6);padding:5px 14px;backdrop-filter:blur(4px);z-index:5}
.cam-btns{display:flex;gap:10px;margin-top:14px;flex-wrap:wrap}
.cam-btn{flex:1;font-family:'Cinzel',serif;font-size:.58rem;letter-spacing:3px;
  border:1px solid rgba(201,168,76,.3);background:rgba(201,168,76,.04);
  color:var(--g);padding:12px;cursor:none;transition:all .3s;
  display:flex;align-items:center;justify-content:center;gap:8px;min-width:120px}
.cam-btn:hover{background:var(--g);color:var(--bk);border-color:var(--g)}
.cam-btn.active{background:var(--g);color:var(--bk);border-color:var(--g)}

/* Jewellery picker */
.j-picker{display:flex;flex-direction:column;gap:24px}
.j-category{font-family:'Cinzel',serif;font-size:.58rem;letter-spacing:4px;color:var(--g);margin-bottom:10px}
.j-items{display:grid;grid-template-columns:repeat(3,1fr);gap:10px}
.j-item{aspect-ratio:1;border:1.5px solid rgba(201,168,76,.12);cursor:none;
  position:relative;overflow:hidden;transition:all .4s;background:var(--bk3)}
.j-item img{width:100%;height:100%;object-fit:cover;transition:transform .5s}
.j-item:hover{border-color:rgba(201,168,76,.5);transform:scale(1.05)}
.j-item:hover img{transform:scale(1.1)}
.j-item.sel{border-color:var(--g);box-shadow:0 0 20px rgba(201,168,76,.3)}
.j-item.sel::after{content:'✓';position:absolute;top:5px;right:5px;
  background:var(--g);color:var(--bk);width:18px;height:18px;border-radius:50%;
  display:flex;align-items:center;justify-content:center;font-size:.65rem}
.j-item-name{position:absolute;bottom:0;left:0;right:0;
  background:rgba(6,5,4,.85);padding:5px 6px;
  font-family:'Cinzel',serif;font-size:.45rem;letter-spacing:2px;color:var(--g);
  transform:translateY(100%);transition:transform .3s}
.j-item:hover .j-item-name{transform:translateY(0)}
.tryon-note{font-style:italic;color:var(--cr3);font-size:.88rem;
  margin-top:16px;text-align:center;line-height:1.6}
.tryon-mode-btns{display:flex;gap:12px;margin-bottom:20px;flex-wrap:wrap}
.mode-btn{font-family:'Cinzel',serif;font-size:.55rem;letter-spacing:3px;
  padding:10px 18px;border:1px solid rgba(201,168,76,.25);
  color:var(--cr3);background:none;cursor:none;transition:all .3s}
.mode-btn.active,.mode-btn:hover{border-color:var(--g);color:var(--g);background:rgba(201,168,76,.06)}
.ai-progress{height:2px;background:rgba(201,168,76,.1);margin-top:12px;display:none}
.ai-prog-fill{height:100%;background:var(--g);width:0;transition:width .1s linear}
.ai-hint{color:var(--cr3);font-style:italic;font-size:.85rem;margin-top:10px;min-height:20px}
/* Floating jewel overlays on canvas */
.jewel-overlay{position:absolute;pointer-events:none;z-index:5;
  filter:drop-shadow(0 4px 16px rgba(201,168,76,.6));
  transition:all .3s;animation:jglow 2s ease-in-out infinite}
@keyframes jglow{0%,100%{filter:drop-shadow(0 4px 16px rgba(201,168,76,.5))}
  50%{filter:drop-shadow(0 4px 28px rgba(201,168,76,.9))}}

/* ═══ CONTACT ═══ */
.con-section{background:var(--bk2)}
.con-grid{display:grid;grid-template-columns:1fr 1.5fr;gap:48px}
.con-card{background:linear-gradient(145deg,var(--bk3),var(--bk2));
  border:1px solid rgba(201,168,76,.1);padding:46px 38px}
.ci{display:flex;gap:18px;margin-bottom:32px}
.ci-ico{width:48px;height:48px;background:rgba(201,168,76,.06);
  border:1px solid rgba(201,168,76,.14);display:flex;align-items:center;
  justify-content:center;color:var(--g);font-size:1.05rem;flex-shrink:0;transition:all .3s}
.ci:hover .ci-ico{background:var(--g);color:var(--bk)}
.ci-lbl{font-family:'Cinzel',serif;font-size:.56rem;letter-spacing:4px;color:var(--g);margin-bottom:7px}
.ci-val{color:var(--cr2);line-height:1.8;font-size:.9rem}
.ci-val a{color:var(--cr2);text-decoration:none;transition:color .3s}
.ci-val a:hover{color:var(--g)}
.map-box{border:1px solid rgba(201,168,76,.2);overflow:hidden;min-height:460px;position:relative}
.map-box iframe{width:100%;height:100%;min-height:460px;border:0;
  filter:grayscale(60%) contrast(1.1) brightness(.72) sepia(.15)}
.map-pin{position:absolute;bottom:22px;left:22px;
  background:rgba(6,5,4,.95);backdrop-filter:blur(8px);
  padding:12px 20px;border:1px solid rgba(201,168,76,.3);z-index:5}
.map-pin p{color:var(--g);font-family:'Cinzel',serif;font-size:.62rem;letter-spacing:3px}

/* ═══ WISHLIST PANEL ═══ */
#wp{position:fixed;top:0;right:-420px;width:min(400px,100%);height:100vh;
  background:var(--bk2);border-left:1px solid rgba(201,168,76,.18);
  z-index:9000;transition:right .55s var(--ease);
  display:flex;flex-direction:column;box-shadow:-24px 0 60px rgba(0,0,0,.5)}
#wp.open{right:0}
.wp-head{padding:24px 22px;border-bottom:1px solid rgba(201,168,76,.1);
  display:flex;justify-content:space-between;align-items:center}
.wp-title{font-family:'Cinzel',serif;font-size:.85rem;letter-spacing:4px;color:var(--g)}
.wp-x{background:none;border:none;color:var(--cr3);font-size:1rem;cursor:none;transition:color .3s}
.wp-x:hover{color:var(--g)}
.wp-body{flex:1;overflow-y:auto;padding:16px}
.wi{display:flex;gap:12px;align-items:center;padding:12px;
  border-bottom:1px solid rgba(201,168,76,.07)}
.wi img{width:52px;height:52px;object-fit:cover;flex-shrink:0;border:1px solid rgba(201,168,76,.15)}
.wi-name{font-family:'Playfair Display',serif;font-size:1.05rem;color:var(--cr)}
.wi-price{font-family:'Cinzel',serif;color:var(--g);font-size:.72rem}
.wi-rm{background:none;border:none;color:var(--cr3);cursor:none;font-size:.8rem;
  transition:color .3s;margin-left:auto;flex-shrink:0}
.wi-rm:hover{color:var(--mr2)}
.wp-empty{text-align:center;padding:48px 20px;color:var(--cr3);font-style:italic}
.wp-foot{padding:18px 22px;border-top:1px solid rgba(201,168,76,.1)}
.wp-ov{position:fixed;inset:0;z-index:8999;background:rgba(0,0,0,.6);
  backdrop-filter:blur(3px);display:none}
.wp-ov.show{display:block}

/* ═══ MODAL ═══ */
#modal{position:fixed;inset:0;background:rgba(6,5,4,.97);backdrop-filter:blur(14px);
  z-index:80000;display:none;align-items:center;justify-content:center}
#modal.open{display:flex}
.md-box{background:linear-gradient(145deg,var(--bk2),var(--bk3));
  border:1px solid rgba(201,168,76,.28);max-width:520px;width:90%;
  padding:52px 44px;text-align:center;position:relative;
  animation:mdIn .45s var(--ease)}
@keyframes mdIn{from{opacity:0;transform:scale(.88) translateY(28px)}to{opacity:1;transform:scale(1)translateY(0)}}
.md-bar{position:absolute;top:0;left:0;right:0;height:2px;
  background:linear-gradient(90deg,transparent,var(--g),transparent)}
.md-x{position:absolute;top:16px;right:18px;background:none;
  border:none;color:var(--cr3);font-size:1rem;cursor:none;transition:color .3s}
.md-x:hover{color:var(--g)}
.md-img{width:160px;height:160px;object-fit:cover;margin:0 auto 20px;display:block;
  border:1px solid rgba(201,168,76,.2)}
.md-name{font-family:'Playfair Display',serif;font-size:2.4rem;font-weight:900;margin-bottom:8px}
.md-price{font-family:'Playfair Display',serif;font-size:1.7rem;font-weight:700;margin:10px 0;
  background:linear-gradient(135deg,var(--g),var(--g2));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text}
.md-tags{display:flex;gap:8px;justify-content:center;flex-wrap:wrap;margin-bottom:22px}
.md-tag{background:rgba(201,168,76,.08);border:1px solid rgba(201,168,76,.18);
  color:var(--g2);padding:4px 12px;font-family:'Cinzel',serif;font-size:.52rem;letter-spacing:2px}
.md-desc{color:var(--cr2);line-height:1.8;font-size:.9rem;margin-bottom:28px}
.md-acts{display:flex;gap:12px;justify-content:center;flex-wrap:wrap}

/* ═══ TOAST ═══ */
.toast{position:fixed;bottom:32px;right:32px;z-index:999999;
  background:var(--bk2);border:1px solid var(--g);border-left:3px solid var(--g);
  padding:15px 28px;display:flex;align-items:center;gap:12px;
  animation:toastIn .4s var(--ease);box-shadow:0 18px 40px rgba(0,0,0,.5)}
@keyframes toastIn{from{opacity:0;transform:translateX(80px)}to{opacity:1;transform:translateX(0)}}
.toast i{color:var(--g)}
.toast p{font-family:'Cinzel',serif;font-size:.65rem;letter-spacing:2px;color:var(--cr)}

/* ═══ FOOTER ═══ */
footer{background:var(--bk);border-top:1px solid rgba(201,168,76,.1);padding:76px 0 28px}
.foot-grid{display:grid;grid-template-columns:2fr 1fr 1fr 1.4fr;gap:46px;margin-bottom:56px}
.fl{font-family:'Cinzel',serif;font-size:1.4rem;letter-spacing:5px;color:var(--g);margin-bottom:14px}
.fd{color:var(--cr3);font-size:.88rem;line-height:1.85;max-width:280px;margin-bottom:22px}
.ft{font-style:italic;color:rgba(201,168,76,.5);font-size:.95rem;margin-bottom:20px}
.fsoc{display:flex;gap:10px}
.fs{width:38px;height:38px;border:1px solid rgba(201,168,76,.18);
  display:flex;align-items:center;justify-content:center;color:var(--g);
  text-decoration:none;font-size:.9rem;transition:all .3s;cursor:none}
.fs:hover{background:var(--g);color:var(--bk);border-color:var(--g);transform:translateY(-4px)}
.fh{font-family:'Cinzel',serif;font-size:.6rem;letter-spacing:4px;color:var(--g);margin-bottom:20px}
.fu{list-style:none;display:flex;flex-direction:column;gap:9px}
.fu a{color:var(--cr3);text-decoration:none;font-size:.85rem;transition:all .3s;cursor:none;display:inline-block}
.fu a:hover{color:var(--cr);transform:translateX(5px)}
.nl-f{display:flex;gap:8px;margin-top:14px}
.nl-i{flex:1;background:rgba(255,255,255,.02);border:1px solid rgba(201,168,76,.18);
  padding:11px 14px;color:var(--cr);font-size:.82rem;outline:none;
  transition:border-color .3s;font-family:'Cormorant Garamond',serif}
.nl-i:focus{border-color:var(--g)}
.nl-b{background:var(--g);color:var(--bk);border:none;padding:0 18px;
  cursor:none;transition:all .3s;font-family:'Cinzel',serif;font-size:.62rem;letter-spacing:2px}
.nl-b:hover{background:var(--g2)}
.foot-bot{border-top:1px solid rgba(201,168,76,.07);padding-top:28px;
  display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:14px}
.foot-copy{color:var(--cr3);font-size:.72rem;letter-spacing:1px}
.foot-motto{font-family:'Cinzel',serif;font-size:.62rem;letter-spacing:5px;color:var(--g)}
.foot-cert{display:flex;gap:8px;flex-wrap:wrap}
.cert{background:rgba(201,168,76,.07);border:1px solid rgba(201,168,76,.18);
  padding:4px 12px;font-family:'Cinzel',serif;font-size:.52rem;letter-spacing:2px;color:var(--g)}

/* ═══ SCROLL REVEAL ═══ */
.rv{opacity:0;transform:translateY(44px);transition:opacity .8s var(--ease),transform .8s var(--ease)}
.rv.up{opacity:1;transform:translateY(0)}
.rvl{opacity:0;transform:translateX(-44px);transition:opacity .8s var(--ease),transform .8s var(--ease)}
.rvl.up{opacity:1;transform:translateX(0)}
.rvr{opacity:0;transform:translateX(44px);transition:opacity .8s var(--ease),transform .8s var(--ease)}
.rvr.up{opacity:1;transform:translateX(0)}
.d1{transition-delay:.1s}.d2{transition-delay:.18s}.d3{transition-delay:.26s}
.d4{transition-delay:.34s}.d5{transition-delay:.42s}.d6{transition-delay:.5s}

/* ═══ RESPONSIVE ═══ */
@media(max-width:1100px){
  .wrap{padding:0 36px}
  #nav{padding:18px 36px}
  #nav.scrolled{padding:11px 36px}
  .foot-grid{grid-template-columns:1fr 1fr}
  .gal-grid{grid-template-columns:repeat(4,1fr)}
  .h-grid{grid-template-columns:repeat(2,1fr)}
}
@media(max-width:880px){
  .n-links,.n-cta{display:none}
  .menu-btn{display:flex}
  .ab-grid,.bs,.con-grid,.tryon-ui{grid-template-columns:1fr}
  .bs-l{height:380px}
  .bs-l-ov{background:linear-gradient(to bottom,transparent 55%,var(--bk) 100%)}
  .ig-grid{grid-template-columns:repeat(3,1fr);grid-template-rows:auto}
  .ig-item:first-child{grid-row:auto;grid-column:auto}
  .gal-grid{grid-template-columns:repeat(3,1fr)}
  .gi.large,.gi.wide,.gi.tall{grid-column:auto;grid-row:auto}
  .tryon-cam-box{max-height:400px}
}
@media(max-width:640px){
  section{padding:72px 0}
  .wrap{padding:0 20px}
  #nav{padding:14px 20px}
  .h-h1{font-size:3.2rem;letter-spacing:-1px}
  .h-btns{flex-direction:column;align-items:center}
  .btn{width:100%;max-width:300px;justify-content:center}
  .h-grid{grid-template-columns:1fr 1fr}
  .gal-grid{grid-template-columns:repeat(2,1fr)}
  .prod-grid{grid-template-columns:1fr 1fr}
  .ig-grid{grid-template-columns:repeat(2,1fr)}
  .ab-feats{grid-template-columns:1fr}
  .j-items{grid-template-columns:repeat(3,1fr)}
  .foot-grid{grid-template-columns:1fr}
  .foot-bot{flex-direction:column;text-align:center}
  #wp{width:100%}
  .colSwiper{padding:0 20px 40px!important}
  .vs-stats{gap:22px}
  .vss-n{font-size:2.6rem}
  .vs-line{display:none}
}
@media(max-width:400px){
  .prod-grid{grid-template-columns:1fr}
  .gal-grid{grid-template-columns:repeat(2,1fr)}
  .j-items{grid-template-columns:repeat(2,1fr)}
}
</style>
</head>
<body>

<div id="cur"></div><div id="cur-r"></div>
<canvas id="pc"></canvas>

<!-- ═══════════ PRELOADER ═══════════ -->
<div id="pl">
  <div class="pl-mandala">
    <svg viewBox="0 0 200 200" fill="none">
      <circle cx="100" cy="100" r="96" stroke="rgba(201,168,76,.15)" stroke-width="1"/>
      <circle cx="100" cy="100" r="82" stroke="rgba(201,168,76,.1)" stroke-width="1" stroke-dasharray="4 7"/>
      <circle cx="100" cy="100" r="68" stroke="rgba(201,168,76,.2)" stroke-width="1"/>
      <circle cx="100" cy="100" r="54" stroke="rgba(201,168,76,.12)" stroke-width="1" stroke-dasharray="2 5"/>
      <circle cx="100" cy="100" r="38" stroke="rgba(201,168,76,.3)" stroke-width="1"/>
      <circle cx="100" cy="100" r="22" stroke="rgba(201,168,76,.18)" stroke-width="1" stroke-dasharray="2 3"/>
      <circle cx="100" cy="100" r="7" fill="rgba(201,168,76,.8)"/>
      <g stroke="rgba(201,168,76,.48)" stroke-width=".7" fill="none">
        <path d="M100 18 Q110 59 100 100 Q90 59 100 18Z"/>
        <path d="M100 18 Q110 59 100 100 Q90 59 100 18Z" transform="rotate(45 100 100)"/>
        <path d="M100 18 Q110 59 100 100 Q90 59 100 18Z" transform="rotate(90 100 100)"/>
        <path d="M100 18 Q110 59 100 100 Q90 59 100 18Z" transform="rotate(135 100 100)"/>
        <path d="M100 18 Q110 59 100 100 Q90 59 100 18Z" transform="rotate(180 100 100)"/>
        <path d="M100 18 Q110 59 100 100 Q90 59 100 18Z" transform="rotate(225 100 100)"/>
        <path d="M100 18 Q110 59 100 100 Q90 59 100 18Z" transform="rotate(270 100 100)"/>
        <path d="M100 18 Q110 59 100 100 Q90 59 100 18Z" transform="rotate(315 100 100)"/>
      </g>
      <line x1="100" y1="4" x2="100" y2="196" stroke="rgba(201,168,76,.12)" stroke-width=".5"/>
      <line x1="4" y1="100" x2="196" y2="100" stroke="rgba(201,168,76,.12)" stroke-width=".5"/>
      <path d="M100 8L104 14L100 20L96 14Z" fill="rgba(201,168,76,.7)"/>
      <path d="M100 180L104 186L100 192L96 186Z" fill="rgba(201,168,76,.7)"/>
      <path d="M8 100L14 96L20 100L14 104Z" fill="rgba(201,168,76,.7)"/>
      <path d="M180 100L186 96L192 100L186 104Z" fill="rgba(201,168,76,.7)"/>
    </svg>
  </div>
  <div class="pl-name">RD VIVAHA JEWELLERS</div>
  <div class="pl-sub">ERODE • TAMIL NADU • EST. 1982</div>
  <div class="pl-tamil">மங்களம் · பாரம்பரியம் · அழகு</div>
  <div class="pl-bar"><div class="pl-fill"></div></div>
</div>

<!-- ═══════════ NAV ═══════════ -->
<nav id="nav">
  <a href="#hero" class="n-logo">RD VIVAHA JEWELLERS<small>EST. 1982 · ERODE, TAMIL NADU</small></a>
  <ul class="n-links">
    <li><a href="#collections">Collections</a></li>
    <li><a href="#gallery">Gallery</a></li>
    <li><a href="#products">Pieces</a></li>
    <li><a href="#tryon">Try-On</a></li>
    <li><a href="#about">Heritage</a></li>
    <li><a href="#contact">Visit</a></li>
  </ul>
  <div class="n-right">
    <button class="n-ico" id="openWP"><i class="far fa-heart"></i><span id="wbadge">0</span></button>
    <button class="n-cta" onclick="toast('Appointment request sent! We\'ll reach you soon.')">Book Appointment</button>
    <button class="menu-btn" id="menuBtn"><i class="fas fa-bars"></i></button>
  </div>
</nav>

<div class="scrim" id="scrim"></div>
<div class="mob" id="mob">
  <button class="mob-x" id="mobX"><i class="fas fa-times"></i></button>
  <div class="mob-links">
    <a href="#collections" onclick="cmob()">Collections</a>
    <a href="#gallery" onclick="cmob()">Gallery</a>
    <a href="#products" onclick="cmob()">Pieces</a>
    <a href="#tryon" onclick="cmob()">AI Try-On</a>
    <a href="#about" onclick="cmob()">Heritage</a>
    <a href="#contact" onclick="cmob()">Visit Us</a>
    <a href="#contact" onclick="cmob()">Book Appointment</a>
  </div>
</div>

<!-- ═══════════ HERO ═══════════ -->
<section id="hero" style="padding:0">
  <video class="h-vid" id="hv" autoplay muted loop playsinline
    poster="https://images.unsplash.com/photo-1605100804763-247f67b3557e?w=1920&q=80">
    <source src="https://videos.pexels.com/video-files/854182/854182-hd_1920_1080_30fps.mp4" type="video/mp4">
  </video>
  <div class="h-grad"></div><div class="h-pattern"></div>
  <!-- Big mandala bg -->
  <svg class="h-mandala" viewBox="0 0 800 800" fill="none">
    <circle cx="400" cy="400" r="392" stroke="#C9A84C" stroke-width=".4"/>
    <circle cx="400" cy="400" r="340" stroke="#C9A84C" stroke-width=".3" stroke-dasharray="3 8"/>
    <circle cx="400" cy="400" r="290" stroke="#C9A84C" stroke-width=".4"/>
    <circle cx="400" cy="400" r="240" stroke="#C9A84C" stroke-width=".3" stroke-dasharray="2 6"/>
    <circle cx="400" cy="400" r="190" stroke="#C9A84C" stroke-width=".4"/>
    <circle cx="400" cy="400" r="140" stroke="#C9A84C" stroke-width=".3"/>
    <circle cx="400" cy="400" r="60" stroke="#C9A84C" stroke-width=".4"/>
    <line x1="400" y1="8" x2="400" y2="792" stroke="#C9A84C" stroke-width=".3" opacity=".6"/>
    <line x1="8" y1="400" x2="792" y2="400" stroke="#C9A84C" stroke-width=".3" opacity=".6"/>
    <line x1="8" y1="400" x2="792" y2="400" stroke="#C9A84C" stroke-width=".3" opacity=".4" transform="rotate(45 400 400)"/>
    <line x1="8" y1="400" x2="792" y2="400" stroke="#C9A84C" stroke-width=".25" opacity=".3" transform="rotate(22.5 400 400)"/>
    <line x1="8" y1="400" x2="792" y2="400" stroke="#C9A84C" stroke-width=".25" opacity=".3" transform="rotate(67.5 400 400)"/>
    <g fill="none" stroke="#C9A84C" stroke-width=".5">
      <path d="M400 210 Q416 305 400 400 Q384 305 400 210Z"/>
      <path d="M400 210 Q416 305 400 400 Q384 305 400 210Z" transform="rotate(22.5 400 400)"/>
      <path d="M400 210 Q416 305 400 400 Q384 305 400 210Z" transform="rotate(45 400 400)"/>
      <path d="M400 210 Q416 305 400 400 Q384 305 400 210Z" transform="rotate(67.5 400 400)"/>
      <path d="M400 210 Q416 305 400 400 Q384 305 400 210Z" transform="rotate(90 400 400)"/>
      <path d="M400 210 Q416 305 400 400 Q384 305 400 210Z" transform="rotate(112.5 400 400)"/>
      <path d="M400 210 Q416 305 400 400 Q384 305 400 210Z" transform="rotate(135 400 400)"/>
      <path d="M400 210 Q416 305 400 400 Q384 305 400 210Z" transform="rotate(157.5 400 400)"/>
      <path d="M400 210 Q416 305 400 400 Q384 305 400 210Z" transform="rotate(180 400 400)"/>
      <path d="M400 210 Q416 305 400 400 Q384 305 400 210Z" transform="rotate(202.5 400 400)"/>
      <path d="M400 210 Q416 305 400 400 Q384 305 400 210Z" transform="rotate(225 400 400)"/>
      <path d="M400 210 Q416 305 400 400 Q384 305 400 210Z" transform="rotate(247.5 400 400)"/>
      <path d="M400 210 Q416 305 400 400 Q384 305 400 210Z" transform="rotate(270 400 400)"/>
      <path d="M400 210 Q416 305 400 400 Q384 305 400 210Z" transform="rotate(292.5 400 400)"/>
      <path d="M400 210 Q416 305 400 400 Q384 305 400 210Z" transform="rotate(315 400 400)"/>
      <path d="M400 210 Q416 305 400 400 Q384 305 400 210Z" transform="rotate(337.5 400 400)"/>
    </g>
    <g fill="#C9A84C">
      <path d="M400 20L403 28L400 36L397 28Z" opacity=".7"/>
      <path d="M400 764L403 772L400 780L397 772Z" opacity=".7"/>
      <path d="M20 400L28 397L36 400L28 403Z" opacity=".7"/>
      <path d="M764 400L772 397L780 400L772 403Z" opacity=".7"/>
    </g>
    <circle cx="400" cy="400" r="16" stroke="#C9A84C" stroke-width=".7"/>
    <circle cx="400" cy="400" r="7" fill="#C9A84C" opacity=".7"/>
  </svg>

  <div class="h-content">
    <p class="h-label">✦ Erode's Finest Bridal Jeweller Since 1982 ✦</p>
    <p class="h-tamil">மங்களம் · பாரம்பரியம் · அழகு</p>
    <h1 class="h-h1">
      <span class="t1">Timeless Elegance</span>
      <span class="t2">Where Gold</span>
      <span class="t3">Meets Grace</span>
    </h1>
    <p class="h-desc">Handcrafted heirlooms for Tamil Nadu's most cherished weddings. Every piece tells a story of devotion, artistry, and uncompromising purity.</p>
    <div class="h-btns">
      <button class="btn btn-g" onclick="document.getElementById('tryon').scrollIntoView({behavior:'smooth'})">
        <i class="fas fa-camera"></i> Try On Live
      </button>
      <a href="#collections" class="btn btn-o"><i class="fas fa-gem"></i> Explore Bridal</a>
    </div>
  </div>
  <div class="h-scroll"><span class="h-stxt">Scroll</span><div class="h-sline"></div></div>
</section>

<!-- ═══════════ MARQUEE ═══════════ -->
<div class="mq-wrap" aria-hidden="true">
  <div class="mq-inner">
    <div class="mq-set">
      <span>22k Hallmarked Gold</span><i class="fas fa-diamond"></i>
      <span>Temple Jewellery</span><i class="fas fa-diamond"></i>
      <span>Bridal Collections</span><i class="fas fa-diamond"></i>
      <span>Polki & Kundan</span><i class="fas fa-diamond"></i>
      <span>Lifetime Buyback</span><i class="fas fa-diamond"></i>
      <span>BIS Certified Purity</span><i class="fas fa-diamond"></i>
      <span>Custom Design</span><i class="fas fa-diamond"></i>
      <span>Free Bridal Consultation</span><i class="fas fa-diamond"></i>
      <span>Jadau Work</span><i class="fas fa-diamond"></i>
      <span>South Indian Craft</span><i class="fas fa-diamond"></i>
      <span>Three Generations of Trust</span><i class="fas fa-diamond"></i>
    </div>
    <div class="mq-set" aria-hidden="true">
      <span>22k Hallmarked Gold</span><i class="fas fa-diamond"></i>
      <span>Temple Jewellery</span><i class="fas fa-diamond"></i>
      <span>Bridal Collections</span><i class="fas fa-diamond"></i>
      <span>Polki & Kundan</span><i class="fas fa-diamond"></i>
      <span>Lifetime Buyback</span><i class="fas fa-diamond"></i>
      <span>BIS Certified Purity</span><i class="fas fa-diamond"></i>
      <span>Custom Design</span><i class="fas fa-diamond"></i>
      <span>Free Bridal Consultation</span><i class="fas fa-diamond"></i>
      <span>Jadau Work</span><i class="fas fa-diamond"></i>
      <span>South Indian Craft</span><i class="fas fa-diamond"></i>
      <span>Three Generations of Trust</span><i class="fas fa-diamond"></i>
    </div>
  </div>
</div>

<!-- ═══════════ COLLECTIONS ═══════════ -->
<section id="collections">
  <div class="wrap">
    <div class="sec-head rv">
      <p class="s-tag">The Bridal Trousseau</p>
      <h2 class="s-h2">Our <em>Collections</em></h2>
      <div class="divider"></div>
    </div>
  </div>
  <div class="swiper colSwiper">
    <div class="swiper-wrapper">
      <!-- 1 -->
      <div class="swiper-slide"><div class="cc">
        <img src="https://images.unsplash.com/photo-1605100804763-247f67b3557e?w=700&q=90" alt="Necklaces" loading="lazy">
        <div class="cc-ov"><span class="cc-cat">Statement Pieces</span><h3 class="cc-name">Necklaces</h3><p class="cc-tamil">மாலைகள்</p><span class="cc-cta">Discover <i class="fas fa-arrow-right"></i></span></div>
        <div class="cc-shine"></div>
      </div></div>
      <!-- 2 -->
      <div class="swiper-slide"><div class="cc">
        <img src="https://images.unsplash.com/photo-1535632066927-ab7c9ab60908?w=700&q=90" alt="Earrings" loading="lazy">
        <div class="cc-ov"><span class="cc-cat">Temple Drops</span><h3 class="cc-name">Jhumkas</h3><p class="cc-tamil">ஜுக்கா</p><span class="cc-cta">Explore <i class="fas fa-arrow-right"></i></span></div>
        <div class="cc-shine"></div>
      </div></div>
      <!-- 3 -->
      <div class="swiper-slide"><div class="cc">
        <img src="https://images.unsplash.com/photo-1515562141207-7c627e9583e7?w=700&q=90" alt="Bridal Sets" loading="lazy">
        <div class="cc-ov"><span class="cc-cat">Complete Trousseau</span><h3 class="cc-name">Bridal Sets</h3><p class="cc-tamil">மணமகள் செட்</p><span class="cc-cta">View <i class="fas fa-arrow-right"></i></span></div>
        <div class="cc-shine"></div>
      </div></div>
      <!-- 4 -->
      <div class="swiper-slide"><div class="cc">
        <img src="https://images.unsplash.com/photo-1599643478518-a784e190ba6e?w=700&q=90" alt="Bangles" loading="lazy">
        <div class="cc-ov"><span class="cc-cat">Wrist Adornments</span><h3 class="cc-name">Bangles</h3><p class="cc-tamil">வளையல்</p><span class="cc-cta">View <i class="fas fa-arrow-right"></i></span></div>
        <div class="cc-shine"></div>
      </div></div>
      <!-- 5 -->
      <div class="swiper-slide"><div class="cc">
        <img src="https://images.unsplash.com/photo-1602173574767-37ac01994b2a?w=700&q=90" alt="Temple Jewellery" loading="lazy">
        <div class="cc-ov"><span class="cc-cat">Divine Craft</span><h3 class="cc-name">Temple Jewellery</h3><p class="cc-tamil">கோவில் நகைகள்</p><span class="cc-cta">Discover <i class="fas fa-arrow-right"></i></span></div>
        <div class="cc-shine"></div>
      </div></div>
      <!-- 6 -->
      <div class="swiper-slide"><div class="cc">
        <img src="https://images.unsplash.com/photo-1611085583191-a3b181a88401?w=700&q=90" alt="Rings" loading="lazy">
        <div class="cc-ov"><span class="cc-cat">Eternal Bonds</span><h3 class="cc-name">Rings</h3><p class="cc-tamil">மோதிரம்</p><span class="cc-cta">Explore <i class="fas fa-arrow-right"></i></span></div>
        <div class="cc-shine"></div>
      </div></div>
      <!-- 7 -->
      <div class="swiper-slide"><div class="cc">
        <img src="https://images.unsplash.com/photo-1506630448388-4e683c67ddb0?w=700&q=90" alt="Ottiyanam" loading="lazy">
        <div class="cc-ov"><span class="cc-cat">Bridal Exclusive</span><h3 class="cc-name">Ottiyanam</h3><p class="cc-tamil">ஒட்டியாணம்</p><span class="cc-cta">View <i class="fas fa-arrow-right"></i></span></div>
        <div class="cc-shine"></div>
      </div></div>
      <!-- 8 -->
      <div class="swiper-slide"><div class="cc">
        <img src="https://images.unsplash.com/photo-1633810543430-721b9bcef5db?w=700&q=90" alt="Anklets" loading="lazy">
        <div class="cc-ov"><span class="cc-cat">Foot Adornments</span><h3 class="cc-name">Kolusu</h3><p class="cc-tamil">கொலுசு</p><span class="cc-cta">View <i class="fas fa-arrow-right"></i></span></div>
        <div class="cc-shine"></div>
      </div></div>
    </div>
    <div class="swiper-pagination" style="bottom:0"></div>
  </div>
</section>

<!-- ═══════════ VIDEO SHOWCASE 1 ═══════════ -->
<div class="vs">
  <video class="vs-vid" autoplay muted loop playsinline>
    <source src="https://videos.pexels.com/video-files/3195394/3195394-uhd_2560_1440_25fps.mp4" type="video/mp4">
    <source src="https://videos.pexels.com/video-files/854182/854182-hd_1920_1080_30fps.mp4" type="video/mp4">
  </video>
  <div class="vs-dark"></div>
  <div class="orb orb1"></div><div class="orb orb2"></div>
  <div class="wrap" style="position:relative;z-index:3">
    <div class="vs-content rvl">
      <p class="s-tag lft">The Art of Craftsmanship</p>
      <h2 class="s-h2">Forged in Fire<br><em>&amp; Tradition</em></h2>
      <p>Our master craftsmen breathe life into 22k gold using centuries-old techniques passed down through generations of Tamil artisans. Every piece is a devotion to perfection.</p>
      <div class="vs-stats">
        <div><div class="vss-n" id="sn1">0</div><div class="vss-l">Years Legacy</div></div>
        <div class="vs-line"></div>
        <div><div class="vss-n" id="sn2">0</div><div class="vss-l">Happy Brides</div></div>
        <div class="vs-line"></div>
        <div><div class="vss-n" id="sn3">0</div><div class="vss-l">Unique Designs</div></div>
      </div>
      <a href="#about" class="btn btn-o">Discover Our Heritage</a>
    </div>
  </div>
</div>

<!-- ═══════════ 50-IMAGE GALLERY MOSAIC ═══════════ -->
<section id="gallery" class="gallery-section">
  <div class="wrap">
    <div class="sec-head rv">
      <p class="s-tag">50+ Curated Pieces</p>
      <h2 class="s-h2">Bridal <em>Gallery</em></h2>
      <div class="divider"></div>
    </div>
  </div>
  <div class="gal-grid rv" style="padding:0 56px">
    <!-- Row of 50+ images using Unsplash jewellery photos -->
    <div class="gi large"><img src="https://images.unsplash.com/photo-1605100804763-247f67b3557e?w=700&q=85" alt="Gold Necklace" loading="lazy"><div class="gi-ov"><i class="fas fa-search-plus"></i></div><div class="gi-cap"><span>Bestseller</span><p>Rani Haar</p></div></div>
    <div class="gi"><img src="https://images.unsplash.com/photo-1535632066927-ab7c9ab60908?w=500&q=85" alt="Earrings" loading="lazy"><div class="gi-ov"><i class="fas fa-search-plus"></i></div><div class="gi-cap"><span>Classic</span><p>Jhumka</p></div></div>
    <div class="gi"><img src="https://images.unsplash.com/photo-1515562141207-7c627e9583e7?w=500&q=85" alt="Bridal" loading="lazy"><div class="gi-ov"><i class="fas fa-search-plus"></i></div><div class="gi-cap"><span>New</span><p>Bridal Set</p></div></div>
    <div class="gi tall"><img src="https://images.unsplash.com/photo-1599643478518-a784e190ba6e?w=500&q=85" alt="Bangles" loading="lazy"><div class="gi-ov"><i class="fas fa-search-plus"></i></div><div class="gi-cap"><span>Traditional</span><p>Valayal</p></div></div>
    <div class="gi"><img src="https://images.unsplash.com/photo-1602173574767-37ac01994b2a?w=500&q=85" alt="Temple" loading="lazy"><div class="gi-ov"><i class="fas fa-search-plus"></i></div><div class="gi-cap"><span>Heritage</span><p>Temple</p></div></div>
    <div class="gi"><img src="https://images.unsplash.com/photo-1611085583191-a3b181a88401?w=500&q=85" alt="Rings" loading="lazy"><div class="gi-ov"><i class="fas fa-search-plus"></i></div><div class="gi-cap"><span>Eternal</span><p>Rings</p></div></div>
    <div class="gi"><img src="https://images.unsplash.com/photo-1589128777073-263566ae5e4d?w=500&q=85" alt="Craft" loading="lazy"><div class="gi-ov"><i class="fas fa-search-plus"></i></div><div class="gi-cap"><span>Handmade</span><p>Artisan</p></div></div>
    <div class="gi wide"><img src="https://images.unsplash.com/photo-1506630448388-4e683c67ddb0?w=700&q=85" alt="Ottiyanam" loading="lazy"><div class="gi-ov"><i class="fas fa-search-plus"></i></div><div class="gi-cap"><span>Bridal</span><p>Ottiyanam</p></div></div>
    <div class="gi"><img src="https://images.unsplash.com/photo-1618403088890-3d9ff6f4c8b1?w=500&q=85" alt="Tikka" loading="lazy"><div class="gi-ov"><i class="fas fa-search-plus"></i></div><div class="gi-cap"><span>Headpiece</span><p>Nethi Chutti</p></div></div>
    <div class="gi"><img src="https://images.unsplash.com/photo-1617038220319-276d3cfab638?w=500&q=85" alt="Gold" loading="lazy"><div class="gi-ov"><i class="fas fa-search-plus"></i></div><div class="gi-cap"><span>22K</span><p>Gold Set</p></div></div>
    <div class="gi tall"><img src="https://images.unsplash.com/photo-1571945150007-bb5a77cbfda2?w=500&q=85" alt="Necklace" loading="lazy"><div class="gi-ov"><i class="fas fa-search-plus"></i></div><div class="gi-cap"><span>Exclusive</span><p>Choker</p></div></div>
    <div class="gi"><img src="https://images.unsplash.com/photo-1630398072856-1893a8b17c37?w=500&q=85" alt="Diamond" loading="lazy"><div class="gi-ov"><i class="fas fa-search-plus"></i></div><div class="gi-cap"><span>Polki</span><p>Diamond</p></div></div>
    <div class="gi"><img src="https://images.unsplash.com/photo-1633810543430-721b9bcef5db?w=500&q=85" alt="Anklets" loading="lazy"><div class="gi-ov"><i class="fas fa-search-plus"></i></div><div class="gi-cap"><span>Foot</span><p>Kolusu</p></div></div>
    <div class="gi large"><img src="https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=700&q=85" alt="Bridal Look" loading="lazy"><div class="gi-ov"><i class="fas fa-search-plus"></i></div><div class="gi-cap"><span>Full Look</span><p>Bridal Set</p></div></div>
    <div class="gi"><img src="https://images.unsplash.com/photo-1505373877841-8d25f7d46678?w=500&q=85" alt="Wedding" loading="lazy"><div class="gi-ov"><i class="fas fa-search-plus"></i></div><div class="gi-cap"><span>Wedding</span><p>Thali</p></div></div>
    <div class="gi"><img src="https://images.unsplash.com/photo-1565193566173-7a0ee3dbe261?w=500&q=85" alt="Gold Chain" loading="lazy"><div class="gi-ov"><i class="fas fa-search-plus"></i></div><div class="gi-cap"><span>Gold</span><p>Chain</p></div></div>
    <div class="gi"><img src="https://images.unsplash.com/photo-1535632787350-4e68ef0ac584?w=500&q=85" alt="Kundan" loading="lazy"><div class="gi-ov"><i class="fas fa-search-plus"></i></div><div class="gi-cap"><span>Kundan</span><p>Choker</p></div></div>
    <div class="gi"><img src="https://images.unsplash.com/photo-1610714429003-5a99c67cd54a?w=500&q=85" alt="Ring" loading="lazy"><div class="gi-ov"><i class="fas fa-search-plus"></i></div><div class="gi-cap"><span>Solitaire</span><p>Ring</p></div></div>
    <div class="gi wide"><img src="https://images.unsplash.com/photo-1553361371-9b22f78e8b1d?w=700&q=85" alt="Bracelet" loading="lazy"><div class="gi-ov"><i class="fas fa-search-plus"></i></div><div class="gi-cap"><span>Wrist</span><p>Bracelet</p></div></div>
    <div class="gi"><img src="https://images.unsplash.com/photo-1618042164219-62c820f10329?w=500&q=85" alt="Pendant" loading="lazy"><div class="gi-ov"><i class="fas fa-search-plus"></i></div><div class="gi-cap"><span>Gold</span><p>Pendant</p></div></div>
  </div>
</section>

<!-- ═══════════ PRODUCTS ═══════════ -->
<section id="products" style="background:var(--bk2)">
  <div class="wrap">
    <div class="sec-head rv">
      <p class="s-tag">Signature Pieces</p>
      <h2 class="s-h2">Featured <em>Creations</em></h2>
      <div class="divider"></div>
    </div>
    <div class="prod-grid">
      <!-- P1 -->
      <div class="pc rv d1" data-name="Rani Haar" data-price="₹ 4,85,000" data-desc="22K Hallmarked Gold • Temple Motifs • South Indian Craft" data-img="https://images.unsplash.com/photo-1605100804763-247f67b3557e?w=500&q=90">
        <div class="pi"><img src="https://images.unsplash.com/photo-1605100804763-247f67b3557e?w=600&q=85" alt="Rani Haar" loading="lazy"><span class="pbadge">Bestseller</span>
        <div class="p-acts"><button class="p-act wbtn"><i class="far fa-heart"></i></button><button class="p-act qvbtn"><i class="fas fa-eye"></i></button></div></div>
        <div class="pinfo"><h3 class="pname">Rani Haar</h3><p class="pcat">22K Gold • Temple Motifs</p><div class="pfoot"><span class="pprice">₹ 4,85,000</span><button class="pqv qvbtn">Quick View</button></div></div>
      </div>
      <!-- P2 -->
      <div class="pc rv d2" data-name="Vivaha Bridal Set" data-price="₹ 7,99,000" data-desc="Complete Trousseau • Necklace + Jhumkas + Bangles" data-img="https://images.unsplash.com/photo-1515562141207-7c627e9583e7?w=500&q=90">
        <div class="pi"><img src="https://images.unsplash.com/photo-1515562141207-7c627e9583e7?w=600&q=85" alt="Bridal Set" loading="lazy"><span class="pbadge red">Exclusive</span>
        <div class="p-acts"><button class="p-act wbtn"><i class="far fa-heart"></i></button><button class="p-act qvbtn"><i class="fas fa-eye"></i></button></div></div>
        <div class="pinfo"><h3 class="pname">Vivaha Bridal Set</h3><p class="pcat">Complete Trousseau</p><div class="pfoot"><span class="pprice">₹ 7,99,000</span><button class="pqv qvbtn">Quick View</button></div></div>
      </div>
      <!-- P3 -->
      <div class="pc rv d3" data-name="Temple Jhumka" data-price="₹ 1,72,000" data-desc="22K Gold • South Indian Temple • Meenakari finish" data-img="https://images.unsplash.com/photo-1535632066927-ab7c9ab60908?w=500&q=90">
        <div class="pi"><img src="https://images.unsplash.com/photo-1535632066927-ab7c9ab60908?w=600&q=85" alt="Jhumka" loading="lazy">
        <div class="p-acts"><button class="p-act wbtn"><i class="far fa-heart"></i></button><button class="p-act qvbtn"><i class="fas fa-eye"></i></button></div></div>
        <div class="pinfo"><h3 class="pname">Temple Jhumka</h3><p class="pcat">22K Gold • South Indian</p><div class="pfoot"><span class="pprice">₹ 1,72,000</span><button class="pqv qvbtn">Quick View</button></div></div>
      </div>
      <!-- P4 -->
      <div class="pc rv d4" data-name="Polki Choker" data-price="₹ 3,25,000" data-desc="Uncut Diamonds • Jadau Work • Royal Rajasthani Art" data-img="https://images.unsplash.com/photo-1602173574767-37ac01994b2a?w=500&q=90">
        <div class="pi"><img src="https://images.unsplash.com/photo-1602173574767-37ac01994b2a?w=600&q=85" alt="Polki" loading="lazy">
        <div class="p-acts"><button class="p-act wbtn"><i class="far fa-heart"></i></button><button class="p-act qvbtn"><i class="fas fa-eye"></i></button></div></div>
        <div class="pinfo"><h3 class="pname">Polki Choker</h3><p class="pcat">Uncut Diamonds • Gold</p><div class="pfoot"><span class="pprice">₹ 3,25,000</span><button class="pqv qvbtn">Quick View</button></div></div>
      </div>
      <!-- P5 -->
      <div class="pc rv d1" data-name="Ottiyanam Waist Belt" data-price="₹ 2,48,000" data-desc="22K Gold • Peacock Motifs • Bridal Exclusive" data-img="https://images.unsplash.com/photo-1506630448388-4e683c67ddb0?w=500&q=90">
        <div class="pi"><img src="https://images.unsplash.com/photo-1506630448388-4e683c67ddb0?w=600&q=85" alt="Ottiyanam" loading="lazy"><span class="pbadge">Heritage</span>
        <div class="p-acts"><button class="p-act wbtn"><i class="far fa-heart"></i></button><button class="p-act qvbtn"><i class="fas fa-eye"></i></button></div></div>
        <div class="pinfo"><h3 class="pname">Ottiyanam</h3><p class="pcat">22K Gold Waist Belt</p><div class="pfoot"><span class="pprice">₹ 2,48,000</span><button class="pqv qvbtn">Quick View</button></div></div>
      </div>
      <!-- P6 -->
      <div class="pc rv d2" data-name="Kundan Maang Tikka" data-price="₹ 95,000" data-desc="Kundan Stones • 22K Gold Setting • Meenakari Back" data-img="https://images.unsplash.com/photo-1618403088890-3d9ff6f4c8b1?w=500&q=90">
        <div class="pi"><img src="https://images.unsplash.com/photo-1618403088890-3d9ff6f4c8b1?w=600&q=85" alt="Tikka" loading="lazy">
        <div class="p-acts"><button class="p-act wbtn"><i class="far fa-heart"></i></button><button class="p-act qvbtn"><i class="fas fa-eye"></i></button></div></div>
        <div class="pinfo"><h3 class="pname">Kundan Maang Tikka</h3><p class="pcat">Kundan • 22K Gold</p><div class="pfoot"><span class="pprice">₹ 95,000</span><button class="pqv qvbtn">Quick View</button></div></div>
      </div>
      <!-- P7 -->
      <div class="pc rv d3" data-name="Valayal Bangles" data-price="₹ 1,08,000" data-desc="22K Gold • Set of 6 • South Indian Bridal Classic" data-img="https://images.unsplash.com/photo-1599643478518-a784e190ba6e?w=500&q=90">
        <div class="pi"><img src="https://images.unsplash.com/photo-1599643478518-a784e190ba6e?w=600&q=85" alt="Bangles" loading="lazy">
        <div class="p-acts"><button class="p-act wbtn"><i class="far fa-heart"></i></button><button class="p-act qvbtn"><i class="fas fa-eye"></i></button></div></div>
        <div class="pinfo"><h3 class="pname">Valayal Set</h3><p class="pcat">Gold Bangles • Set of 6</p><div class="pfoot"><span class="pprice">₹ 1,08,000</span><button class="pqv qvbtn">Quick View</button></div></div>
      </div>
      <!-- P8 -->
      <div class="pc rv d4" data-name="Vanki Arm Band" data-price="₹ 1,24,000" data-desc="22K Gold • Peacock Arm Band • Traditional South Indian" data-img="https://images.unsplash.com/photo-1617038220319-276d3cfab638?w=500&q=90">
        <div class="pi"><img src="https://images.unsplash.com/photo-1617038220319-276d3cfab638?w=600&q=85" alt="Vanki" loading="lazy">
        <div class="p-acts"><button class="p-act wbtn"><i class="far fa-heart"></i></button><button class="p-act qvbtn"><i class="fas fa-eye"></i></button></div></div>
        <div class="pinfo"><h3 class="pname">Vanki Arm Band</h3><p class="pcat">22K Gold • Traditional</p><div class="pfoot"><span class="pprice">₹ 1,24,000</span><button class="pqv qvbtn">Quick View</button></div></div>
      </div>
    </div>
  </div>
</section>

<!-- ═══════════ VIDEO 2 — AMBIENT ═══════════ -->
<div style="position:relative;height:480px;overflow:hidden">
  <video style="width:100%;height:100%;object-fit:cover;filter:brightness(.38) saturate(1.2)" autoplay muted loop playsinline>
    <source src="https://videos.pexels.com/video-files/7218359/7218359-hd_1280_720_30fps.mp4" type="video/mp4">
    <source src="https://videos.pexels.com/video-files/3195394/3195394-uhd_2560_1440_25fps.mp4" type="video/mp4">
  </video>
  <div style="position:absolute;inset:0;display:flex;align-items:center;justify-content:center;flex-direction:column;gap:18px;z-index:2;background:linear-gradient(90deg,rgba(6,5,4,.65) 0%,rgba(6,5,4,.2) 50%,rgba(6,5,4,.65) 100%)">
    <p style="font-family:'Cinzel',serif;font-size:.68rem;letter-spacing:10px;color:var(--g)" class="rv">The Craft</p>
    <h2 style="font-family:'Playfair Display',serif;font-size:clamp(2.4rem,8vw,6rem);font-weight:900;text-align:center;line-height:1.05" class="rv d1">
      Handcrafted with<br><em style="font-style:italic;background:linear-gradient(135deg,var(--g4),var(--g2));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text">Devotion &amp; Fire</em>
    </h2>
    <a href="#contact" class="btn btn-o rv d2">Begin Your Bridal Journey</a>
  </div>
</div>

<!-- ═══════════ HERITAGE NUMBERS ═══════════ -->
<div style="background:var(--bk);border-top:1px solid rgba(201,168,76,.08);border-bottom:1px solid rgba(201,168,76,.08)" class="rv">
  <div class="wrap" style="padding:0 56px">
    <div class="h-grid">
      <div class="hcell"><div class="hn" id="hn1">0</div><div class="hl">Years in Erode</div></div>
      <div class="hcell"><div class="hn" id="hn2">0</div><div class="hl">Families Adorned</div></div>
      <div class="hcell"><div class="hn" id="hn3">0</div><div class="hl">Master Artisans</div></div>
      <div class="hcell"><div class="hn" id="hn4">0</div><div class="hl">Designs Created</div></div>
    </div>
  </div>
</div>

<!-- ═══════════ BRIDAL STORY SPLIT ═══════════ -->
<div class="bs" id="story">
  <div class="bs-l">
    <img src="https://images.unsplash.com/photo-1589128777073-263566ae5e4d?w=1000&q=90" alt="Craftsmanship" loading="lazy">
    <div class="bs-l-ov"></div>
  </div>
  <div class="bs-r">
    <div class="rvr">
      <p class="s-tag lft">The Vivaha Promise</p>
      <h2 class="s-h2" style="text-align:left">Every Bride<br>Deserves to <em>Shine</em></h2>
      <p style="height:1px;background:linear-gradient(to right,rgba(201,168,76,.4),transparent);margin:18px 0"></p>
      <p>At RD Vivaha, we believe a bride's jewellery is not mere adornment — it is memory made tangible. Each piece is crafted with devotion, blessed by tradition, and designed to outlast generations.</p>
      <p>From the first consultation to the moment you step into your wedding mandap, our family walks every step of the journey with you.</p>
      <div style="display:flex;gap:14px;flex-wrap:wrap;margin-top:28px">
        <a href="#contact" class="btn btn-g" style="flex:1;justify-content:center;min-width:160px">Book Consultation</a>
        <a href="#products" class="btn btn-o" style="flex:1;justify-content:center;min-width:160px">View Products</a>
      </div>
    </div>
  </div>
</div>

<!-- ═══════════ AI TRY-ON (SNAPCHAT STYLE) ═══════════ -->
<section id="tryon">
  <div class="wrap">
    <div class="sec-head rv">
      <span class="ai-badge">✦ AI Innovation</span>
      <h2 class="s-h2" style="margin-top:8px">Live Virtual <em>Try-On</em></h2>
      <p style="color:var(--cr2);max-width:560px;margin:0 auto 12px;font-size:1.05rem;line-height:1.8">
        Snapchat-style live jewellery try-on — use your camera in real-time or upload a photo. Choose any piece from our collection and see it on you instantly.
      </p>
      <div class="divider"></div>
    </div>

    <div class="tryon-ui rv">
      <!-- LEFT: Camera / Photo -->
      <div>
        <div class="tryon-mode-btns">
          <button class="mode-btn active" id="modeCam" onclick="switchMode('cam')"><i class="fas fa-video"></i> Live Camera</button>
          <button class="mode-btn" id="modePhoto" onclick="switchMode('photo')"><i class="fas fa-image"></i> Upload Photo</button>
        </div>

        <div class="tryon-cam-box" id="camBox">
          <video id="camFeed" autoplay playsinline></video>
          <canvas id="camCanvas"></canvas>
          <img id="photoPreview" alt="Preview">
          <!-- Corner brackets -->
          <div class="cam-corner tl"></div><div class="cam-corner tr"></div>
          <div class="cam-corner bl"></div><div class="cam-corner br"></div>
          <div class="cam-scan" id="camScan"></div>
          <div class="cam-label" id="camLabel">LIVE CAMERA</div>
        </div>

        <div class="cam-btns">
          <button class="cam-btn active" id="camStartBtn" onclick="startCam()"><i class="fas fa-camera"></i> Start Camera</button>
          <button class="cam-btn" id="camCapBtn" onclick="captureSnap()" style="display:none"><i class="fas fa-camera-retro"></i> Capture</button>
          <button class="cam-btn" id="uploadBtn" onclick="document.getElementById('pUpload').click()" style="display:none"><i class="fas fa-upload"></i> Upload Photo</button>
          <button class="cam-btn" onclick="resetTryon()"><i class="fas fa-redo"></i> Reset</button>
        </div>
        <input type="file" id="pUpload" accept="image/*" style="display:none" onchange="loadPhoto(this)">

        <div class="ai-progress" id="aiProg"><div class="ai-prog-fill" id="aiProgFill"></div></div>
        <p class="ai-hint" id="aiHint">Start camera or upload a photo to begin your virtual trial</p>

        <p class="tryon-note">🔒 Your camera feed stays on your device — nothing is uploaded. Jewellery overlays are rendered locally in real-time.</p>
      </div>

      <!-- RIGHT: Jewellery Picker -->
      <div class="j-picker">
        <div>
          <p class="j-category">✦ Necklaces</p>
          <div class="j-items" id="jItems">
            <div class="j-item sel" data-jtype="necklace" data-jname="Rani Haar" data-jpos="neck" onclick="selectJewel(this)">
              <img src="https://images.unsplash.com/photo-1605100804763-247f67b3557e?w=300&q=80" alt="Rani Haar" loading="lazy">
              <div class="j-item-name">Rani Haar</div>
            </div>
            <div class="j-item" data-jtype="necklace" data-jname="Polki Choker" data-jpos="neck" onclick="selectJewel(this)">
              <img src="https://images.unsplash.com/photo-1602173574767-37ac01994b2a?w=300&q=80" alt="Polki Choker" loading="lazy">
              <div class="j-item-name">Polki Choker</div>
            </div>
            <div class="j-item" data-jtype="necklace" data-jname="Temple Necklace" data-jpos="neck" onclick="selectJewel(this)">
              <img src="https://images.unsplash.com/photo-1630398072856-1893a8b17c37?w=300&q=80" alt="Temple" loading="lazy">
              <div class="j-item-name">Temple Necklace</div>
            </div>
          </div>
        </div>
        <div>
          <p class="j-category" style="margin-top:20px">✦ Earrings</p>
          <div class="j-items">
            <div class="j-item" data-jtype="earring" data-jname="Temple Jhumka" data-jpos="ear" onclick="selectJewel(this)">
              <img src="https://images.unsplash.com/photo-1535632066927-ab7c9ab60908?w=300&q=80" alt="Jhumka" loading="lazy">
              <div class="j-item-name">Temple Jhumka</div>
            </div>
            <div class="j-item" data-jtype="earring" data-jname="Chandbali" data-jpos="ear" onclick="selectJewel(this)">
              <img src="https://images.unsplash.com/photo-1535632787350-4e68ef0ac584?w=300&q=80" alt="Chandbali" loading="lazy">
              <div class="j-item-name">Chandbali</div>
            </div>
            <div class="j-item" data-jtype="earring" data-jname="Gold Drops" data-jpos="ear" onclick="selectJewel(this)">
              <img src="https://images.unsplash.com/photo-1617038220319-276d3cfab638?w=300&q=80" alt="Drops" loading="lazy">
              <div class="j-item-name">Gold Drops</div>
            </div>
          </div>
        </div>
        <div>
          <p class="j-category" style="margin-top:20px">✦ Headpiece</p>
          <div class="j-items">
            <div class="j-item" data-jtype="tikka" data-jname="Nethi Chutti" data-jpos="head" onclick="selectJewel(this)">
              <img src="https://images.unsplash.com/photo-1618403088890-3d9ff6f4c8b1?w=300&q=80" alt="Tikka" loading="lazy">
              <div class="j-item-name">Nethi Chutti</div>
            </div>
            <div class="j-item" data-jtype="tikka" data-jname="Kundan Tikka" data-jpos="head" onclick="selectJewel(this)">
              <img src="https://images.unsplash.com/photo-1610714429003-5a99c67cd54a?w=300&q=80" alt="Kundan" loading="lazy">
              <div class="j-item-name">Kundan Tikka</div>
            </div>
            <div class="j-item" data-jtype="full" data-jname="Full Bridal Look" data-jpos="full" onclick="selectJewel(this)">
              <img src="https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=300&q=80" alt="Full" loading="lazy">
              <div class="j-item-name">Full Bridal Set</div>
            </div>
          </div>
        </div>

        <div style="margin-top:24px;text-align:center">
          <button class="btn btn-g" style="width:100%;justify-content:center" onclick="toast('Photo saved! Share your bridal look with us on Instagram @RDVivahaBridal')">
            <i class="fas fa-share-alt"></i> Share My Look
          </button>
          <button class="btn btn-o" style="width:100%;justify-content:center;margin-top:10px" onclick="toast('✦ Added to waitlist! We\'ll notify you when full AI try-on is live.')">
            <i class="fas fa-sparkles"></i> Join AI Waitlist
          </button>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ═══════════ TESTIMONIALS ═══════════ -->
<section class="t-sec" style="padding:110px 0">
  <div class="wrap">
    <div class="sec-head rv">
      <p class="s-tag">Bride Stories</p>
      <h2 class="s-h2">What Our <em>Brides Say</em></h2>
      <div class="divider"></div>
    </div>
  </div>
  <div class="wrap">
    <div class="swiper testiSwiper">
      <div class="swiper-wrapper">
        <div class="swiper-slide" style="height:auto"><div class="tc"><div class="tc-q">"</div><p class="tc-t">My entire bridal set from RD Vivaha was beyond anything I imagined. The Rani Haar was the centrepiece of my wedding. Every guest was in awe. Absolutely breathtaking craftsmanship.</p><div class="tc-auth"><div class="tc-av">PS</div><div><div class="tc-name">Priya Subramaniam</div><div class="tc-loc">Coimbatore</div><div class="tc-stars">★★★★★</div></div></div></div></div>
        <div class="swiper-slide" style="height:auto"><div class="tc"><div class="tc-q">"</div><p class="tc-t">Three generations of my family have trusted RD Vivaha. The quality, personal attention, and lifetime buyback promise are unmatched in all of Tamil Nadu. My Ottiyanam still shines like day one.</p><div class="tc-auth"><div class="tc-av">KR</div><div><div class="tc-name">Kavitha Rajan</div><div class="tc-loc">Erode</div><div class="tc-stars">★★★★★</div></div></div></div></div>
        <div class="swiper-slide" style="height:auto"><div class="tc"><div class="tc-q">"</div><p class="tc-t">The Polki choker they designed for me was exactly as I described — but even more magnificent. Their custom design service is truly exceptional. Worth every rupee and more.</p><div class="tc-auth"><div class="tc-av">AK</div><div><div class="tc-name">Anitha Krishnamurthy</div><div class="tc-loc">Salem</div><div class="tc-stars">★★★★★</div></div></div></div></div>
        <div class="swiper-slide" style="height:auto"><div class="tc"><div class="tc-q">"</div><p class="tc-t">I was nervous about choosing my bridal jewellery but the team at RD Vivaha made me feel so comfortable. They understood exactly what I wanted and created something truly timeless.</p><div class="tc-auth"><div class="tc-av">MS</div><div><div class="tc-name">Meenakshi Selvam</div><div class="tc-loc">Chennai</div><div class="tc-stars">★★★★★</div></div></div></div></div>
        <div class="swiper-slide" style="height:auto"><div class="tc"><div class="tc-q">"</div><p class="tc-t">From the engagement ring to the full wedding set — every piece was perfection. The hallmarking certificate gave my family such peace of mind. RD Vivaha is truly Erode's crown jewel.</p><div class="tc-auth"><div class="tc-av">RP</div><div><div class="tc-name">Revathi Prakash</div><div class="tc-loc">Tiruppur</div><div class="tc-stars">★★★★★</div></div></div></div></div>
      </div>
      <div class="swiper-pagination" style="margin-top:32px;position:relative"></div>
    </div>
  </div>
</section>

<!-- ═══════════ INSTAGRAM MOSAIC ═══════════ -->
<section style="padding-top:0;background:var(--bk2)">
  <div class="wrap">
    <div class="sec-head rv">
      <p class="s-tag">Follow Our Journey</p>
      <h2 class="s-h2">@RDVivaha <em>Bridal</em></h2>
      <div class="divider"></div>
    </div>
    <div class="ig-grid">
      <div class="ig-item rv d1"><img src="https://images.unsplash.com/photo-1605100804763-247f67b3557e?w=600&q=90" alt="" loading="lazy"><div class="ig-ov"><i class="fab fa-instagram"></i></div></div>
      <div class="ig-item rv d1"><img src="https://images.unsplash.com/photo-1535632066927-ab7c9ab60908?w=600&q=90" alt="" loading="lazy"><div class="ig-ov"><i class="fab fa-instagram"></i></div></div>
      <div class="ig-item rv d2"><img src="https://images.unsplash.com/photo-1515562141207-7c627e9583e7?w=600&q=90" alt="" loading="lazy"><div class="ig-ov"><i class="fab fa-instagram"></i></div></div>
      <div class="ig-item rv d2"><img src="https://images.unsplash.com/photo-1599643478518-a784e190ba6e?w=600&q=90" alt="" loading="lazy"><div class="ig-ov"><i class="fab fa-instagram"></i></div></div>
      <div class="ig-item rv d3"><img src="https://images.unsplash.com/photo-1602173574767-37ac01994b2a?w=600&q=90" alt="" loading="lazy"><div class="ig-ov"><i class="fab fa-instagram"></i></div></div>
      <div class="ig-item rv d3"><img src="https://images.unsplash.com/photo-1589128777073-263566ae5e4d?w=600&q=90" alt="" loading="lazy"><div class="ig-ov"><i class="fab fa-instagram"></i></div></div>
      <div class="ig-item rv d4"><img src="https://images.unsplash.com/photo-1611085583191-a3b181a88401?w=600&q=90" alt="" loading="lazy"><div class="ig-ov"><i class="fab fa-instagram"></i></div></div>
    </div>
  </div>
</section>

<!-- ═══════════ ABOUT ═══════════ -->
<section id="about">
  <div class="wrap">
    <div class="ab-grid">
      <div class="rvl">
        <p class="s-tag lft">Heritage &amp; Trust</p>
        <h2 class="s-h2">Three Generations<br>of <em>Artistry</em></h2>
        <div class="divider lft"></div>
        <p class="ab-text">Since 1982, RD Vivaha Jewellers has been Erode's most trusted name in bridal jewellery. Every piece is hallmarked, handpicked, and crafted to honor tradition while embracing timeless elegance. We don't just sell jewellery — we create heirlooms.</p>
        <div class="ab-feats">
          <div class="af"><div class="af-ico"><i class="fas fa-certificate"></i></div><div><div class="af-t">BIS Hallmarked</div><div class="af-d">100% certified purity</div></div></div>
          <div class="af"><div class="af-ico"><i class="fas fa-handshake"></i></div><div><div class="af-t">Lifetime Buyback</div><div class="af-d">Full exchange value</div></div></div>
          <div class="af"><div class="af-ico"><i class="fas fa-palette"></i></div><div><div class="af-t">Custom Design</div><div class="af-d">Bespoke creations</div></div></div>
          <div class="af"><div class="af-ico"><i class="fas fa-gem"></i></div><div><div class="af-t">Expert Consultation</div><div class="af-d">Personal guidance</div></div></div>
        </div>
        <a href="#contact" class="btn btn-o">Visit Our Atelier <i class="fas fa-arrow-right"></i></a>
      </div>
      <div class="ab-img rvr">
        <img src="https://images.unsplash.com/photo-1589128777073-263566ae5e4d?w=900&q=90" alt="Craftsman" loading="lazy">
        <div class="ab-corner tl"></div>
        <div class="ab-corner br"></div>
        <div class="ab-tag">Est.<span>1982</span></div>
      </div>
    </div>
  </div>
</section>

<!-- ═══════════ CONTACT ═══════════ -->
<section id="contact" class="con-section">
  <div class="wrap">
    <div class="sec-head rv">
      <p class="s-tag">Visit Our Flagship</p>
      <h2 class="s-h2">Find Us in <em>Erode</em></h2>
      <div class="divider"></div>
    </div>
    <div class="con-grid">
      <div class="con-card rvl">
        <div class="ci"><div class="ci-ico"><i class="fas fa-map-pin"></i></div><div><div class="ci-lbl">Address</div><div class="ci-val">421, Nethaji Rd, Erode Fort,<br>Erode, Tamil Nadu 638001</div></div></div>
        <div class="ci"><div class="ci-ico"><i class="fas fa-phone"></i></div><div><div class="ci-lbl">Phone</div><div class="ci-val"><a href="tel:04242223444">0424 222 3444</a></div></div></div>
        <div class="ci"><div class="ci-ico"><i class="far fa-clock"></i></div><div><div class="ci-lbl">Hours</div><div class="ci-val">Mon – Sat: 10:30 am – 8:00 pm<br>Sunday: By appointment only</div></div></div>
        <div class="ci"><div class="ci-ico"><i class="fab fa-instagram"></i></div><div><div class="ci-lbl">Social</div><div class="ci-val"><a href="#">@RDVivahaBridal</a> · <a href="#">@RDVivaha</a></div></div></div>
        <div style="display:flex;gap:12px;margin-top:24px;flex-wrap:wrap">
          <button class="btn btn-g" style="flex:1;justify-content:center;min-width:140px" onclick="toast('Appointment request sent! We\'ll contact you within 24 hours.')"><i class="fas fa-calendar-check"></i> Book Appointment</button>
          <a href="https://maps.google.com/?q=421+Nethaji+Rd+Erode" target="_blank" class="btn btn-o" style="flex:1;justify-content:center;min-width:140px"><i class="fas fa-location-arrow"></i> Get Directions</a>
        </div>
      </div>
      <div class="map-box rvr">
        <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3910.6332240735445!2d77.719963075068!3d11.34285338882496!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3ba96f1e5c5b4b0b%3A0x4f7f5c5e8c3b8b8a!2s421%2C%20Nethaji%20Rd%2C%20Erode%20Fort%2C%20Erode%2C%20Tamil%20Nadu%20638001!5e0!3m2!1sen!2sin!4v1712000000000" allowfullscreen loading="lazy"></iframe>
        <div class="map-pin"><p><i class="fas fa-location-dot" style="margin-right:8px"></i>RD Vivaha Jewellers, Erode</p></div>
      </div>
    </div>
  </div>
</section>

<!-- ═══════════ FOOTER ═══════════ -->
<footer>¯
  <div class="wrap">
    <div class="foot-grid">
      <div>
        <div class="fl">RD VIVAHA JEWELLERS</div>
        <p class="fd">Erode's most trusted bridal jeweller since 1982. Adorning brides with timeless artistry, uncompromising purity, and a promise that lasts generations.</p>
        <p class="ft">மங்களம் · பாரம்பரியம் · அழகு</p>
        <div class="fsoc">
        <a href="https://www.instagram.com/rd_vivaha/" class="fs" target="_blank">
        <i class="fab fa-instagram"></i>
        </a>

        <a href="https://www.facebook.com/p/RD-vivaha-jewellery-100076369530035/" class="fs" target="_blank">
       <i class="fab fa-facebook-f"></i>
       </a>

       <a href="https://wa.me/919424222344" class="fs" target="_blank">
       <i class="fab fa-whatsapp"></i>
      </a>
      </div>
      </div>
      <div><p class="fh">Navigate</p><ul class="fu"><li><a href="#hero">Home</a></li><li><a href="#collections">Collections</a></li><li><a href="#gallery">Gallery</a></li><li><a href="#products">Products</a></li><li><a href="#about">Heritage</a></li><li><a href="#contact">Contact</a></li></ul></div>
      <div><p class="fh">Collections</p><ul class="fu"><li><a href="#">Necklaces</a></li><li><a href="#">Earrings</a></li><li><a href="#">Bangles</a></li><li><a href="#">Bridal Sets</a></li><li><a href="#">Temple Jewellery</a></li><li><a href="#">Ottiyanam</a></li></ul></div>
      <div>
        <p class="fh">Newsletter</p>
        <p style="color:var(--cr3);font-size:.82rem;margin-bottom:4px">Exclusive offers &amp; new arrivals</p>
        <div class="nl-f"><input class="nl-i" type="email" placeholder="Your email address"><button class="nl-b" onclick="toast('Subscribed! Welcome to the RD Vivaha family.')">→</button></div>
        <div style="margin-top:26px"><p class="fh">Certifications</p>
        <div class="foot-cert" style="margin-top:12px">
          <span class="cert">BIS</span><span class="cert">22K</span><span class="cert">ISO</span><span class="cert">HALLMARK</span>
        </div></div>
      </div>
    </div>
    <div class="foot-bot">
      <p class="foot-copy">© 2025 RD Vivaha Jewellers. All rights reserved.</p>
      <p class="foot-motto">Elegance for Every Wedding</p>
      <div style="display:flex;gap:12px;color:var(--cr3);font-size:1.4rem">
        <i class="fab fa-cc-visa"></i><i class="fab fa-cc-mastercard"></i><i class="fab fa-cc-amex"></i><i class="fab fa-cc-paypal"></i>
      </div>
    </div>
  </div>
</footer>

<!-- ═══════════ MODAL ═══════════ -->
<div id="modal">
  <div class="md-box">
    <div class="md-bar"></div>
    <button class="md-x" onclick="closeModal()"><i class="fas fa-times"></i></button>
    <img id="mdImg" class="md-img" src="" alt="">
    <h3 class="md-name" id="mdName"></h3>
    <div class="md-price" id="mdPrice"></div>
    <div class="md-tags" id="mdTags"></div>
    <p class="md-desc">22k Hallmarked Gold · Traditional Craftsmanship · Comes with authenticity certificate and lifetime buyback guarantee.</p>
    <div class="md-acts">
      <button class="btn btn-g" onclick="toast('Enquiry sent for '+document.getElementById('mdName').textContent+'!');closeModal()"><i class="fas fa-paper-plane"></i> Enquire Now</button>
      <button class="btn btn-o" onclick="closeModal()">Close</button>
    </div>
  </div>
</div>

<!-- ═══════════ WISHLIST PANEL ═══════════ -->
<div class="wp-ov" id="wpOv" onclick="toggleWP(false)"></div>
<div id="wp">
  <div class="wp-head">
    <p class="wp-title"><i class="far fa-heart" style="margin-right:8px"></i>MY WISHLIST</p>
    <button class="wp-x" onclick="toggleWP(false)"><i class="fas fa-times"></i></button>
  </div>
  <div class="wp-body" id="wpBody"><p class="wp-empty">Your wishlist is empty.<br>Tap ♡ on any piece to save it.</p></div>
  <div class="wp-foot"><button class="btn btn-g" style="width:100%;justify-content:center" onclick="toast('Enquiry for wishlist sent! We\'ll contact you with pricing.')"><i class="fas fa-paper-plane"></i> Enquire About Wishlist</button></div>
</div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/Swiper/11.0.5/swiper-bundle.min.js"></script>
<script>
(function(){
'use strict';

/* ─── PRELOADER ─── */
window.addEventListener('load',()=>setTimeout(()=>document.getElementById('pl').classList.add('out'),2300));

/* ─── CURSOR ─── */
const c=document.getElementById('cur'),cr=document.getElementById('cur-r');
let mx=0,my=0,rx=0,ry=0;
document.addEventListener('mousemove',e=>{mx=e.clientX;my=e.clientY;c.style.left=mx+'px';c.style.top=my+'px'});
(function ra(){rx+=(mx-rx)*.1;ry+=(my-ry)*.1;cr.style.left=rx+'px';cr.style.top=ry+'px';requestAnimationFrame(ra)})();
document.querySelectorAll('a,button,.cc,.pc,.ig-item,.gi,.j-item').forEach(el=>{
  el.addEventListener('mouseenter',()=>document.body.classList.add('hv'));
  el.addEventListener('mouseleave',()=>document.body.classList.remove('hv'));
});

/* ─── SPARKLE TRAIL ─── */
let lastSp=0;
document.addEventListener('mousemove',e=>{
  if(Date.now()-lastSp<65||Math.random()>.55)return;lastSp=Date.now();
  const s=document.createElement('div');
  const a=Math.random()*Math.PI*2,d=Math.random()*28+8;
  s.style.cssText=`position:fixed;left:${e.clientX}px;top:${e.clientY}px;width:4px;height:4px;background:${Math.random()>.5?'#E8C96A':'#C9A84C'};border-radius:50%;pointer-events:none;z-index:99990;transform:translate(-50%,-50%);transition:all .65s ease;`;
  document.body.appendChild(s);
  requestAnimationFrame(()=>{s.style.opacity='0';s.style.transform=`translate(calc(-50% + ${Math.cos(a)*d}px),calc(-50% + ${Math.sin(a)*d-18}px)) scale(0)`});
  setTimeout(()=>s.remove(),720);
});
document.addEventListener('click',e=>{
  for(let i=0;i<8;i++)setTimeout(()=>{
    const s=document.createElement('div');
    const a=Math.random()*Math.PI*2;
    s.style.cssText=`position:fixed;left:${e.clientX}px;top:${e.clientY}px;width:5px;height:5px;background:#E8C96A;border-radius:50%;pointer-events:none;z-index:99990;transform:translate(-50%,-50%);transition:all .75s ease;`;
    document.body.appendChild(s);
    requestAnimationFrame(()=>{s.style.opacity='0';s.style.transform=`translate(calc(-50% + ${Math.cos(a)*44}px),calc(-50% + ${Math.sin(a)*44}px)) scale(0)`});
    setTimeout(()=>s.remove(),850);
  },i*28);
});

/* ─── PARTICLES ─── */
const cv=document.getElementById('pc'),ct=cv.getContext('2d');
let W,H;const r=()=>{W=cv.width=innerWidth;H=cv.height=innerHeight};r();window.addEventListener('resize',r);
const pts=Array.from({length:90},()=>({x:Math.random()*2000,y:Math.random()*2000,vx:(Math.random()-.5)*.12,vy:(Math.random()-.5)*.12,ra:Math.random()*1.5+.3,o:Math.random()*.22+.05}));
(function dp(){ct.clearRect(0,0,W,H);pts.forEach(p=>{p.x+=p.vx;p.y+=p.vy;if(p.x<0)p.x=W;if(p.x>W)p.x=0;if(p.y<0)p.y=H;if(p.y>H)p.y=0;ct.beginPath();ct.arc(p.x,p.y,p.ra,0,Math.PI*2);ct.fillStyle=`rgba(201,168,76,${p.o})`;ct.fill()});requestAnimationFrame(dp)})();

/* ─── NAV ─── */
const nav=document.getElementById('nav');
window.addEventListener('scroll',()=>{nav.classList.toggle('scrolled',scrollY>80);revealCheck()});

/* ─── MOBILE MENU ─── */
const mm=document.getElementById('mob'),sc=document.getElementById('scrim');
document.getElementById('menuBtn').onclick=()=>{mm.classList.add('open');sc.classList.add('open');document.body.style.overflow='hidden'};
document.getElementById('mobX').onclick=sc.onclick=window.cmob=()=>{mm.classList.remove('open');sc.classList.remove('open');document.body.style.overflow=''};

/* ─── HERO VIDEO ─── */
const hv=document.getElementById('hv');
if(hv)hv.addEventListener('canplay',()=>hv.classList.add('on'));

/* ─── SMOOTH SCROLL ─── */
document.querySelectorAll('a[href^="#"]').forEach(a=>{
  a.addEventListener('click',e=>{const t=document.querySelector(a.getAttribute('href'));if(t){e.preventDefault();t.scrollIntoView({behavior:'smooth'})}});
});

/* ─── SCROLL REVEAL ─── */
function revealCheck(){
  document.querySelectorAll('.rv,.rvl,.rvr').forEach(el=>{
    if(el.getBoundingClientRect().top<innerHeight-80)el.classList.add('up');
  });
}
setTimeout(revealCheck,300);

/* ─── SWIPER ─── */
new Swiper('.colSwiper',{
  slidesPerView:'auto',spaceBetween:22,centeredSlides:true,loop:true,
  autoplay:{delay:3400,disableOnInteraction:false},
  pagination:{el:'.swiper-pagination',clickable:true},
  breakpoints:{320:{slidesPerView:1.2,spaceBetween:14},768:{slidesPerView:2.4,spaceBetween:20},1200:{slidesPerView:3.5,spaceBetween:22}}
});
new Swiper('.testiSwiper',{
  slidesPerView:1,spaceBetween:22,loop:true,
  autoplay:{delay:4800,disableOnInteraction:false},
  pagination:{el:'.swiper-pagination',clickable:true},
  breakpoints:{768:{slidesPerView:2},1100:{slidesPerView:3}}
});

/* ─── COUNTER ANIMATION ─── */
let countDone=false,statsDone=false;
function animNum(id,target,suf=''){
  const el=document.getElementById(id);if(!el)return;
  let v=0;const inc=target/55;
  const iv=setInterval(()=>{v+=inc;if(v>=target){v=target;clearInterval(iv)}el.textContent=Math.floor(v).toLocaleString()+suf},28);
}
function checkCounters(){
  const hg=document.querySelector('.h-grid');
  if(hg&&!countDone&&hg.getBoundingClientRect().top<innerHeight-80){
    countDone=true;animNum('hn1',40,'+');animNum('hn2',12000,'+');animNum('hn3',38,'');animNum('hn4',3500,'+');
  }
  const vs=document.querySelector('.vs-stats');
  if(vs&&!statsDone&&vs.getBoundingClientRect().top<innerHeight-80){
    statsDone=true;animNum('sn1',40,'+');animNum('sn2',12000,'+');animNum('sn3',5000,'+');
  }
}
window.addEventListener('scroll',checkCounters);setTimeout(checkCounters,500);

/* ─── MODAL ─── */
const modal=document.getElementById('modal');
function openModal(card){
  document.getElementById('mdImg').src=card.dataset.img||'';
  document.getElementById('mdName').textContent=card.dataset.name;
  document.getElementById('mdPrice').textContent=card.dataset.price;
  const tags=(card.dataset.desc||'').split('·').map(t=>`<span class="md-tag">${t.trim()}</span>`).join('');
  document.getElementById('mdTags').innerHTML=tags;
  modal.classList.add('open');document.body.style.overflow='hidden';
}
window.closeModal=()=>{modal.classList.remove('open');document.body.style.overflow=''};
modal.addEventListener('click',e=>{if(e.target===modal)closeModal()});
document.addEventListener('keydown',e=>{if(e.key==='Escape'){closeModal();toggleWP(false)}});
document.querySelectorAll('.qvbtn').forEach(b=>{
  b.addEventListener('click',e=>{e.stopPropagation();openModal(b.closest('.pc'));});
});

/* ─── WISHLIST ─── */
let wishlist=[];
function renderWL(){
  const badge=document.getElementById('wbadge'),body=document.getElementById('wpBody');
  badge.textContent=wishlist.length;badge.classList.toggle('on',wishlist.length>0);
  if(!wishlist.length){body.innerHTML='<p class="wp-empty">Your wishlist is empty.<br>Tap ♡ on any piece to save it.</p>';return}
  body.innerHTML=wishlist.map((w,i)=>`<div class="wi"><img src="${w.img}" alt="${w.name}"><div style="flex:1"><div class="wi-name">${w.name}</div><div class="wi-price">${w.price}</div></div><button class="wi-rm" onclick="rmWL(${i})"><i class="fas fa-times"></i></button></div>`).join('');
}
window.rmWL=function(i){
  document.querySelectorAll('.pc').forEach(c=>{if(c.dataset.name===wishlist[i].name){const b=c.querySelector('.wbtn');if(b){b.classList.remove('wh');b.querySelector('i').className='far fa-heart'}}});
  wishlist.splice(i,1);renderWL();
};
window.toggleWP=function(open){
  document.getElementById('wp').classList.toggle('open',open);
  document.getElementById('wpOv').classList.toggle('show',open);
};
document.getElementById('openWP').addEventListener('click',()=>toggleWP(true));
document.querySelectorAll('.wbtn').forEach(b=>{
  b.addEventListener('click',e=>{
    e.stopPropagation();
    const c=b.closest('.pc');
    const name=c.dataset.name,price=c.dataset.price,img=c.dataset.img||'';
    const idx=wishlist.findIndex(w=>w.name===name);
    if(idx>-1){wishlist.splice(idx,1);b.classList.remove('wh');b.querySelector('i').className='far fa-heart'}
    else{wishlist.push({name,price,img});b.classList.add('wh');b.querySelector('i').className='fas fa-heart';toast('Added to wishlist ♥')}
    renderWL();
  });
});

/* ─── TOAST ─── */
window.toast=function(msg){
  document.querySelectorAll('.toast').forEach(t=>t.remove());
  const t=document.createElement('div');t.className='toast';
  t.innerHTML=`<i class="fas fa-check-circle"></i><p>${msg}</p>`;
  document.body.appendChild(t);
  setTimeout(()=>{t.style.opacity='0';t.style.transform='translateX(80px)';t.style.transition='all .35s';setTimeout(()=>t.remove(),380)},3600);
};

/* ══════════════════════════════════════════════════
   AI SNAPCHAT-STYLE LIVE TRY-ON
══════════════════════════════════════════════════ */
let stream=null,camActive=false,mode='cam';
let selectedJewel=document.querySelector('.j-item.sel');
let animFrame=null;

const camFeed=document.getElementById('camFeed');
const camCanvas=document.getElementById('camCanvas');
const camCtx=camCanvas.getContext('2d');
const photoPreview=document.getElementById('photoPreview');
const aiHint=document.getElementById('aiHint');
const aiProg=document.getElementById('aiProg');
const aiProgFill=document.getElementById('aiProgFill');
const camScan=document.getElementById('camScan');
const camLabel=document.getElementById('camLabel');

// Jewellery overlays defined — position as fraction of canvas
const OVERLAYS={
  neck:{
    src:null,// we draw decorative gold lines for neck
    draw:function(ctx,W,H,jwl){drawNecklaceOverlay(ctx,W,H,jwl)}
  },
  ear:{
    draw:function(ctx,W,H,jwl){drawEarringOverlay(ctx,W,H,jwl)}
  },
  head:{
    draw:function(ctx,W,H,jwl){drawTikkaOverlay(ctx,W,H,jwl)}
  },
  full:{
    draw:function(ctx,W,H,jwl){drawNecklaceOverlay(ctx,W,H,jwl);drawEarringOverlay(ctx,W,H,jwl);drawTikkaOverlay(ctx,W,H,jwl);drawBangleOverlay(ctx,W,H)}
  }
};

function drawNecklaceOverlay(ctx,W,H,jwl){
  const cx=W/2,cy=H*0.38,rx=W*0.3,ry=H*0.12;
  ctx.save();
  // Necklace chain arc
  ctx.strokeStyle='rgba(201,168,76,0.9)';ctx.lineWidth=3;
  ctx.shadowColor='rgba(201,168,76,0.7)';ctx.shadowBlur=10;
  ctx.beginPath();ctx.ellipse(cx,cy,rx,ry,0,0,Math.PI);ctx.stroke();
  // Pendant
  ctx.fillStyle='rgba(201,168,76,0.85)';
  ctx.shadowBlur=16;
  const py=cy+ry+6;
  ctx.beginPath();ctx.arc(cx,py,10,0,Math.PI*2);ctx.fill();
  ctx.strokeStyle='rgba(245,224,160,0.9)';ctx.lineWidth=2;ctx.shadowBlur=8;
  ctx.stroke();
  // Chain details
  const steps=16;
  for(let i=0;i<=steps;i++){
    const angle=Math.PI*(i/steps);
    const x=cx-rx*Math.cos(angle),y=cy+ry*Math.sin(angle);
    ctx.beginPath();ctx.arc(x,y,3,0,Math.PI*2);
    ctx.fillStyle=i%2===0?'rgba(232,201,106,0.9)':'rgba(160,120,32,0.8)';ctx.fill();
  }
  // Name label
  ctx.shadowBlur=0;
  ctx.fillStyle='rgba(201,168,76,0.85)';
  ctx.font=`bold ${W*.025}px Cinzel, serif`;
  ctx.textAlign='center';
  ctx.fillText(jwl||'RD VIVAHA JEWEL',cx,H*0.55);
  ctx.restore();
}

function drawEarringOverlay(ctx,W,H,jwl){
  ctx.save();
  [[W*0.22,H*0.3],[W*0.78,H*0.3]].forEach(([ex,ey])=>{
    ctx.shadowColor='rgba(201,168,76,.7)';ctx.shadowBlur=12;
    ctx.strokeStyle='rgba(201,168,76,.9)';ctx.lineWidth=2;
    // Earring stud
    ctx.fillStyle='rgba(201,168,76,.9)';
    ctx.beginPath();ctx.arc(ex,ey,6,0,Math.PI*2);ctx.fill();ctx.stroke();
    // Dangle
    ctx.strokeStyle='rgba(201,168,76,.8)';ctx.lineWidth=1.5;
    ctx.beginPath();ctx.moveTo(ex,ey+6);ctx.lineTo(ex,ey+H*0.06);ctx.stroke();
    // Jhumka bell
    ctx.fillStyle='rgba(201,168,76,.8)';
    ctx.shadowBlur=16;
    ctx.beginPath();ctx.ellipse(ex,ey+H*0.06+10,7,10,0,0,Math.PI*2);ctx.fill();ctx.stroke();
    // Bell dots
    ctx.shadowBlur=0;
    for(let i=0;i<6;i++){const a=i/6*Math.PI*2;
      ctx.beginPath();ctx.arc(ex+5*Math.cos(a),ey+H*0.06+10+4*Math.sin(a),1.5,0,Math.PI*2);
      ctx.fillStyle='rgba(245,224,160,.9)';ctx.fill();
    }
  });
  ctx.restore();
}

function drawTikkaOverlay(ctx,W,H,jwl){
  const cx=W/2,cy=H*0.12;
  ctx.save();
  ctx.shadowColor='rgba(201,168,76,.8)';ctx.shadowBlur=14;
  // Chain from centre head
  ctx.strokeStyle='rgba(201,168,76,.8)';ctx.lineWidth=1.5;
  ctx.beginPath();ctx.moveTo(cx,cy);ctx.quadraticCurveTo(cx,cy+H*0.06,cx,cy+H*0.1);ctx.stroke();
  // Maang tikka pendant
  ctx.fillStyle='rgba(201,168,76,.85)';
  ctx.beginPath();ctx.arc(cx,cy+H*0.11,9,0,Math.PI*2);ctx.fill();
  ctx.strokeStyle='rgba(245,224,160,.9)';ctx.lineWidth=2;ctx.stroke();
  // Drop
  ctx.beginPath();ctx.arc(cx,cy+H*0.11+14,5,0,Math.PI*2);
  ctx.fillStyle='rgba(232,201,106,.9)';ctx.fill();
  // Decorative dots on head edge
  for(let i=0;i<9;i++){
    const x=cx-W*0.22+i*(W*0.055),y=cy-2;
    ctx.beginPath();ctx.arc(x,y,2.5,0,Math.PI*2);
    ctx.fillStyle=i%2===0?'rgba(201,168,76,.7)':'rgba(160,120,32,.5)';ctx.fill();
  }
  ctx.restore();
}

function drawBangleOverlay(ctx,W,H){
  ctx.save();
  [[W*.15,H*.72],[W*.85,H*.72]].forEach(([bx,by])=>{
    for(let i=0;i<3;i++){
      ctx.strokeStyle=`rgba(201,168,76,${.8-i*.15})`;
      ctx.lineWidth=4-i;
      ctx.shadowColor='rgba(201,168,76,.5)';ctx.shadowBlur=8;
      ctx.beginPath();ctx.arc(bx,by,14+i*6,0,Math.PI*2);ctx.stroke();
    }
  });
  ctx.restore();
}

/* Render loop for live camera */
function renderLoop(){
  if(!camActive&&mode==='cam')return;
  camCanvas.width=camFeed.videoWidth||camCanvas.offsetWidth;
  camCanvas.height=camFeed.videoHeight||camCanvas.offsetHeight;
  const W=camCanvas.width,H=camCanvas.height;
  camCtx.clearRect(0,0,W,H);
  if(selectedJewel){
    const pos=selectedJewel.dataset.jpos||'neck';
    const name=selectedJewel.dataset.jname||'';
    const ov=OVERLAYS[pos]||OVERLAYS.neck;
    ov.draw(camCtx,W,H,name);
  }
  animFrame=requestAnimationFrame(renderLoop);
}

function renderOnPhoto(){
  const img=photoPreview;
  camCanvas.width=img.naturalWidth||camCanvas.offsetWidth;
  camCanvas.height=img.naturalHeight||camCanvas.offsetHeight;
  const W=camCanvas.width,H=camCanvas.height;
  camCtx.clearRect(0,0,W,H);
  if(selectedJewel){
    const pos=selectedJewel.dataset.jpos||'neck';
    const name=selectedJewel.dataset.jname||'';
    const ov=OVERLAYS[pos]||OVERLAYS.neck;
    ov.draw(camCtx,W,H,name);
  }
}

window.startCam=async function(){
  try{
    if(stream){stream.getTracks().forEach(t=>t.stop());stream=null}
    stream=await navigator.mediaDevices.getUserMedia({video:{facingMode:'user',width:{ideal:1280},height:{ideal:720}}});
    camFeed.srcObject=stream;
    await camFeed.play();
    camActive=true;
    camFeed.style.display='block';
    photoPreview.style.display='none';
    document.getElementById('camStartBtn').style.display='none';
    document.getElementById('camCapBtn').style.display='flex';
    camScan.classList.add('on');
    camLabel.textContent='LIVE · RD VIVAHA TRY-ON';
    aiHint.textContent='Live camera active! Jewellery overlay is shown in real-time.';
    if(animFrame)cancelAnimationFrame(animFrame);
    renderLoop();
    toast('📸 Camera active! Jewellery overlay rendering live.');
  }catch(err){
    aiHint.textContent='Camera not available. Please use the upload photo option instead.';
    toast('Camera access denied. Try uploading a photo instead.');
    document.getElementById('uploadBtn').style.display='flex';
    document.getElementById('camStartBtn').style.display='flex';
  }
};

window.captureSnap=function(){
  const snap=document.createElement('canvas');
  snap.width=camFeed.videoWidth;snap.height=camFeed.videoHeight;
  const sctx=snap.getContext('2d');
  sctx.drawImage(camFeed,0,0);
  const W=snap.width,H=snap.height;
  if(selectedJewel){
    const pos=selectedJewel.dataset.jpos||'neck';
    const name=selectedJewel.dataset.jname||'';
    (OVERLAYS[pos]||OVERLAYS.neck).draw(sctx,W,H,name);
  }
  // Download
  const a=document.createElement('a');
  a.href=snap.toDataURL('image/png');
  a.download='RDVivaha_BridalLook.png';
  a.click();
  toast('✨ Photo saved! Share your look @RDVivahaBridal');
};

window.switchMode=function(m){
  mode=m;
  document.getElementById('modeCam').classList.toggle('active',m==='cam');
  document.getElementById('modePhoto').classList.toggle('active',m==='photo');
  if(m==='cam'){
    document.getElementById('camStartBtn').style.display='flex';
    document.getElementById('uploadBtn').style.display='none';
    document.getElementById('camCapBtn').style.display='none';
    camLabel.textContent='LIVE CAMERA';
    aiHint.textContent='Click "Start Camera" to begin your live try-on.';
    photoPreview.style.display='none';
  } else {
    if(stream){stream.getTracks().forEach(t=>t.stop());stream=null;camActive=false}
    if(animFrame)cancelAnimationFrame(animFrame);
    camScan.classList.remove('on');
    camFeed.style.display='none';
    document.getElementById('camStartBtn').style.display='none';
    document.getElementById('camCapBtn').style.display='none';
    document.getElementById('uploadBtn').style.display='flex';
    camLabel.textContent='PHOTO MODE';
    aiHint.textContent='Upload your photo to see how the jewellery looks on you.';
    camCtx.clearRect(0,0,camCanvas.width,camCanvas.height);
  }
};

window.loadPhoto=function(input){
  if(!input.files[0])return;
  const reader=new FileReader();
  reader.onload=e=>{
    photoPreview.src=e.target.result;
    photoPreview.style.display='block';
    camFeed.style.display='none';
    aiProg.style.display='block';aiProgFill.style.width='0%';
    aiHint.textContent='Analysing your photo…';
    let p=0;
    const iv=setInterval(()=>{
      p+=Math.random()*9+4;aiProgFill.style.width=Math.min(p,95)+'%';
      if(p>55)aiHint.textContent='Mapping features…';
      if(p>80)aiHint.textContent='Overlaying jewellery…';
      if(p>=95){clearInterval(iv);aiProgFill.style.width='100%';
        setTimeout(()=>{
          aiProg.style.display='none';
          photoPreview.onload=renderOnPhoto;
          if(photoPreview.complete)renderOnPhoto();
          aiHint.innerHTML='✨ Done! Your bridal look is ready to share.';
          camScan.classList.add('on');
        },350);
      }
    },100);
  };
  reader.readAsDataURL(input.files[0]);
};

window.selectJewel=function(el){
  document.querySelectorAll('.j-item').forEach(j=>j.classList.remove('sel'));
  el.classList.add('sel');selectedJewel=el;
  toast('Jewellery selected: '+el.dataset.jname);
  if(mode==='photo'&&photoPreview.style.display!=='none')renderOnPhoto();
  if(camActive){if(animFrame)cancelAnimationFrame(animFrame);renderLoop();}
};

window.resetTryon=function(){
  if(stream){stream.getTracks().forEach(t=>t.stop());stream=null;camActive=false}
  if(animFrame)cancelAnimationFrame(animFrame);
  camFeed.style.display='none';camFeed.srcObject=null;
  photoPreview.style.display='none';photoPreview.src='';
  camCtx.clearRect(0,0,camCanvas.width,camCanvas.height);
  aiProg.style.display='none';
  camScan.classList.remove('on');
  document.getElementById('camStartBtn').style.display='flex';
  document.getElementById('camCapBtn').style.display='none';
  document.getElementById('uploadBtn').style.display='none';
  aiHint.textContent='Start camera or upload a photo to begin your virtual trial';
  camLabel.textContent='LIVE CAMERA';mode='cam';
  document.getElementById('modeCam').classList.add('active');
  document.getElementById('modePhoto').classList.remove('active');
};

/* ─── PARALLAX ─── */
let ticking=false;
window.addEventListener('scroll',()=>{
  if(!ticking){requestAnimationFrame(()=>{
    const sy=pageYOffset;
    document.querySelectorAll('.h-vid').forEach(v=>{v.style.transform=`scale(1.08) translateY(${sy*.1}px)`});
    ticking=false;
  });ticking=true;}
});

})();
</script>
</body>
</html>
