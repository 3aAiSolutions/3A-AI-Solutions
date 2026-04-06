# 3A-AI-Solutions
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>3A AI Solutions — AI Training Academy</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
/* ════════════════════════════════════════
   VARIABLES & RESET
════════════════════════════════════════ */
:root {
  --gold:    #C8973A;
  --gold-lt: #E8B85A;
  --navy:    #07090F;
  --navy-md: #0E1220;
  --navy-lt: #16213A;
  --card:    #111A2C;
  --white:   #F2EFE9;
  --muted:   #7B8BAA;
  --accent:  #3AFFD4;
  --green:   #52B788;
  --purple:  #9B8EC4;
  --r:       14px;
}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0;}
html{scroll-behavior:smooth;}
body{background:var(--navy);color:var(--white);font-family:'DM Sans',sans-serif;overflow-x:hidden;line-height:1.6;}

/* ════════════════════════════════════════
   SCROLLBAR
════════════════════════════════════════ */
::-webkit-scrollbar{width:5px;}
::-webkit-scrollbar-track{background:var(--navy-md);}
::-webkit-scrollbar-thumb{background:var(--gold);border-radius:3px;}

/* ════════════════════════════════════════
   NAV
════════════════════════════════════════ */
nav{position:fixed;top:0;left:0;right:0;z-index:1000;display:flex;align-items:center;justify-content:space-between;padding:1rem 5%;background:rgba(7,9,15,.85);backdrop-filter:blur(20px);border-bottom:1px solid rgba(200,151,58,.1);transition:all .3s;}
nav.scrolled{padding:.7rem 5%;background:rgba(7,9,15,.98);}
.nav-logo{display:flex;align-items:center;gap:.7rem;text-decoration:none;cursor:pointer;}
.nav-logo-3a{font-family:'Syne',sans-serif;font-weight:800;font-size:1.4rem;color:var(--gold);}
.nav-logo-text{font-family:'Syne',sans-serif;font-weight:700;font-size:.85rem;color:var(--white);letter-spacing:.04em;}
.nav-links{display:flex;align-items:center;gap:1.8rem;list-style:none;}
.nav-links a{color:var(--muted);text-decoration:none;font-size:.85rem;transition:color .2s;}
.nav-links a:hover{color:var(--white);}
.nav-enroll{background:var(--gold);color:var(--navy)!important;padding:.45rem 1.1rem;border-radius:8px;font-family:'Syne',sans-serif;font-weight:700;font-size:.82rem;transition:all .2s;}
.nav-enroll:hover{background:var(--gold-lt)!important;transform:translateY(-1px);}
.hamburger{display:none;flex-direction:column;gap:5px;cursor:pointer;background:none;border:none;padding:4px;}
.hamburger span{width:24px;height:2px;background:var(--white);border-radius:2px;transition:all .3s;}
@media(max-width:820px){.nav-links{display:none;}.hamburger{display:flex;}}
.mob-menu{display:none;position:fixed;top:0;left:0;right:0;bottom:0;background:var(--navy);z-index:999;flex-direction:column;align-items:center;justify-content:center;gap:2rem;}
.mob-menu.open{display:flex;}
.mob-menu a{font-family:'Syne',sans-serif;font-size:1.4rem;font-weight:700;color:var(--white);text-decoration:none;}
.mob-menu a:hover{color:var(--gold);}
.mob-close{position:absolute;top:1.5rem;right:1.5rem;background:none;border:none;color:var(--white);font-size:1.8rem;cursor:pointer;}

/* ════════════════════════════════════════
   HERO
════════════════════════════════════════ */
.hero{min-height:100vh;display:flex;align-items:center;position:relative;overflow:hidden;padding:8rem 5% 5rem;}
.hero-bg{position:absolute;inset:0;background:radial-gradient(ellipse 70% 60% at 65% 50%,rgba(200,151,58,.08) 0%,transparent 65%),radial-gradient(ellipse 40% 45% at 10% 75%,rgba(58,255,212,.05) 0%,transparent 50%),var(--navy);}
.hero-grid{position:absolute;inset:0;background-image:linear-gradient(rgba(200,151,58,.05) 1px,transparent 1px),linear-gradient(90deg,rgba(200,151,58,.05) 1px,transparent 1px);background-size:52px 52px;animation:gridSlide 50s linear infinite;}
@keyframes gridSlide{from{background-position:0 0}to{background-position:52px 52px}}
.orb{position:absolute;border-radius:50%;filter:blur(85px);pointer-events:none;}
.orb-1{width:500px;height:500px;background:rgba(200,151,58,.06);top:-10%;right:-5%;animation:drift 16s ease-in-out infinite;}
.orb-2{width:280px;height:280px;background:rgba(58,255,212,.05);bottom:5%;left:0;animation:drift 12s ease-in-out infinite 5s;}
@keyframes drift{0%,100%{transform:translate(0,0)}50%{transform:translate(25px,-35px)}}
.kente{position:absolute;pointer-events:none;}
.kente-tl{top:0;left:0;width:160px;height:160px;background:repeating-linear-gradient(45deg,rgba(200,151,58,.06),rgba(200,151,58,.06) 3px,transparent 3px,transparent 16px);}
.kente-br{bottom:0;right:0;width:180px;height:180px;background:repeating-linear-gradient(45deg,rgba(58,255,212,.04),rgba(58,255,212,.04) 3px,transparent 3px,transparent 16px);}
.hero-content{position:relative;z-index:1;max-width:640px;}
.hero-badge{display:inline-flex;align-items:center;gap:.5rem;padding:.38rem 1rem;border-radius:100px;border:1px solid rgba(200,151,58,.3);background:rgba(200,151,58,.08);font-size:.7rem;letter-spacing:.22em;text-transform:uppercase;color:var(--gold);margin-bottom:1.8rem;animation:fadeUp .8s ease both;}
.badge-dot{width:6px;height:6px;border-radius:50%;background:var(--gold);animation:blink 2s ease infinite;}
@keyframes blink{0%,100%{opacity:1;transform:scale(1)}50%{opacity:.4;transform:scale(1.6)}}
.hero h1{font-family:'Syne',sans-serif;font-size:clamp(2.6rem,5vw,4.6rem);font-weight:800;line-height:1.06;letter-spacing:-.025em;animation:fadeUp .8s .1s ease both;}
.hero h1 .gold{background:linear-gradient(135deg,var(--gold-lt),var(--gold));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;display:block;}
.hero-sub{margin-top:1.4rem;font-size:.98rem;color:var(--muted);line-height:1.85;max-width:500px;animation:fadeUp .8s .2s ease both;}
.hero-actions{display:flex;flex-wrap:wrap;gap:1rem;margin-top:2.2rem;animation:fadeUp .8s .3s ease both;}
.btn-gold{display:inline-flex;align-items:center;gap:.4rem;padding:.85rem 1.9rem;border-radius:10px;background:var(--gold);color:var(--navy);font-family:'Syne',sans-serif;font-weight:700;font-size:.9rem;text-decoration:none;cursor:pointer;border:none;transition:all .25s;box-shadow:0 8px 28px rgba(200,151,58,.28);}
.btn-gold:hover{background:var(--gold-lt);transform:translateY(-3px);box-shadow:0 16px 44px rgba(200,151,58,.42);}
.btn-outline{display:inline-flex;align-items:center;gap:.4rem;padding:.85rem 1.9rem;border-radius:10px;border:1.5px solid rgba(255,255,255,.14);color:var(--white);font-family:'Syne',sans-serif;font-weight:600;font-size:.9rem;text-decoration:none;cursor:pointer;background:none;transition:all .25s;}
.btn-outline:hover{border-color:var(--gold);color:var(--gold);transform:translateY(-3px);}
.hero-stats{display:flex;flex-wrap:wrap;gap:1.5rem;margin-top:2.8rem;animation:fadeUp .8s .4s ease both;}
.hero-stat{text-align:center;}
.hero-stat .num{font-family:'Syne',sans-serif;font-weight:800;font-size:1.8rem;background:linear-gradient(135deg,var(--gold-lt),var(--gold));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;line-height:1;}
.hero-stat .lbl{font-size:.7rem;color:var(--muted);letter-spacing:.1em;text-transform:uppercase;margin-top:.25rem;}
@keyframes fadeUp{from{opacity:0;transform:translateY(22px)}to{opacity:1;transform:none}}

/* ════════════════════════════════════════
   SECTIONS SHARED
════════════════════════════════════════ */
section{padding:5.5rem 5%;}
.sec-inner{max-width:1140px;margin:0 auto;}
.sec-tag{display:inline-flex;align-items:center;gap:.6rem;font-size:.65rem;letter-spacing:.42em;text-transform:uppercase;color:var(--gold);margin-bottom:.9rem;}
.sec-tag::before{content:'';width:20px;height:2px;background:var(--gold);border-radius:2px;flex-shrink:0;}
.sec-title{font-family:'Syne',sans-serif;font-size:clamp(1.7rem,3vw,2.5rem);font-weight:800;line-height:1.15;margin-bottom:.8rem;}
.sec-title span{color:var(--gold);}
.sec-body{font-size:.96rem;color:var(--muted);line-height:1.85;max-width:560px;}
.hr{border:none;height:1px;background:linear-gradient(90deg,transparent,rgba(200,151,58,.18),transparent);}
.reveal{opacity:0;transform:translateY(28px);transition:opacity .7s ease,transform .7s ease;}
.revealed{opacity:1;transform:none;}

/* ════════════════════════════════════════
   TRACKS
════════════════════════════════════════ */
.tracks-bg{background:var(--navy-md);}
.tracks-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(300px,1fr));gap:1.4rem;margin-top:3rem;}
.track-card{background:var(--card);border-radius:var(--r);padding:2rem;border:1px solid rgba(255,255,255,.055);transition:all .28s;cursor:pointer;position:relative;overflow:hidden;}
.track-card::before{content:'';position:absolute;top:0;left:0;right:0;height:3px;opacity:0;transition:opacity .28s;}
.track-card:hover{transform:translateY(-6px);box-shadow:0 20px 55px rgba(0,0,0,.35);}
.track-card:hover::before{opacity:1;}
.track-card.gold-track{border-color:rgba(200,151,58,.15);}
.track-card.gold-track::before{background:linear-gradient(90deg,var(--gold),transparent);opacity:0;}
.track-card.gold-track:hover{border-color:rgba(200,151,58,.3);}
.track-card.gold-track:hover::before{opacity:1;}
.track-card.green-track{border-color:rgba(82,183,136,.1);}
.track-card.green-track::before{background:linear-gradient(90deg,var(--green),transparent);}
.track-card.green-track:hover{border-color:rgba(82,183,136,.25);}
.track-card.purple-track::before{background:linear-gradient(90deg,var(--purple),transparent);}
.track-card.purple-track:hover{border-color:rgba(155,142,196,.25);}
.track-icon{font-size:2.2rem;margin-bottom:1rem;}
.track-label{font-size:.65rem;font-family:'Syne',sans-serif;font-weight:700;letter-spacing:.3em;text-transform:uppercase;margin-bottom:.5rem;}
.track-card.gold-track .track-label{color:var(--gold);}
.track-card.green-track .track-label{color:var(--green);}
.track-card.purple-track .track-label{color:var(--purple);}
.track-title{font-family:'Syne',sans-serif;font-weight:800;font-size:1.2rem;color:var(--white);margin-bottom:.7rem;line-height:1.2;}
.track-desc{font-size:.87rem;color:var(--muted);line-height:1.72;margin-bottom:1.2rem;}
.track-meta{display:flex;gap:1rem;flex-wrap:wrap;margin-bottom:1.4rem;}
.track-pill{font-size:.68rem;padding:.28rem .7rem;border-radius:100px;font-family:'Syne',sans-serif;font-weight:700;letter-spacing:.08em;}
.gold-track .track-pill{background:rgba(200,151,58,.1);color:var(--gold);border:1px solid rgba(200,151,58,.2);}
.green-track .track-pill{background:rgba(82,183,136,.1);color:var(--green);border:1px solid rgba(82,183,136,.2);}
.purple-track .track-pill{background:rgba(155,142,196,.1);color:var(--purple);border:1px solid rgba(155,142,196,.2);}
.track-cta{font-family:'Syne',sans-serif;font-weight:700;font-size:.82rem;padding:.6rem 1.2rem;border-radius:8px;border:none;cursor:pointer;transition:all .2s;}
.gold-track .track-cta{background:var(--gold);color:var(--navy);}
.gold-track .track-cta:hover{background:var(--gold-lt);}
.green-track .track-cta{background:var(--green);color:var(--navy);}
.green-track .track-cta:hover{background:#6FCFA0;}
.purple-track .track-cta{background:var(--purple);color:var(--navy);}
.purple-track .track-cta:hover{background:#B5ABDA;}

/* ════════════════════════════════════════
   VIDEO ACADEMY
════════════════════════════════════════ */
.academy-layout{display:grid;grid-template-columns:320px 1fr;gap:2rem;margin-top:2.5rem;}
@media(max-width:900px){.academy-layout{grid-template-columns:1fr;}}

/* Sidebar */
.academy-sidebar{background:var(--card);border-radius:var(--r);overflow:hidden;border:1px solid rgba(255,255,255,.06);}
.sidebar-header{padding:1.2rem 1.4rem;background:var(--navy-lt);border-bottom:1px solid rgba(255,255,255,.06);}
.sidebar-header-title{font-family:'Syne',sans-serif;font-weight:700;font-size:.92rem;color:var(--white);}
.sidebar-header-sub{font-size:.75rem;color:var(--muted);margin-top:.2rem;}
.track-tabs{display:flex;padding:.8rem 1rem .4rem;gap:.5rem;flex-wrap:wrap;}
.track-tab{font-size:.68rem;font-family:'Syne',sans-serif;font-weight:700;padding:.28rem .7rem;border-radius:100px;border:none;cursor:pointer;transition:all .2s;letter-spacing:.08em;}
.track-tab.active-gold{background:var(--gold);color:var(--navy);}
.track-tab.inactive-gold{background:rgba(200,151,58,.1);color:var(--gold);}
.track-tab.active-green{background:var(--green);color:var(--navy);}
.track-tab.inactive-green{background:rgba(82,183,136,.1);color:var(--green);}
.track-tab.active-purple{background:var(--purple);color:var(--navy);}
.track-tab.inactive-purple{background:rgba(155,142,196,.1);color:var(--purple);}
.lesson-list{padding:.5rem .8rem 1rem;display:flex;flex-direction:column;gap:.3rem;max-height:520px;overflow-y:auto;}
.lesson-item{display:flex;align-items:center;gap:.8rem;padding:.8rem .9rem;border-radius:10px;cursor:pointer;transition:all .2s;border:1px solid transparent;}
.lesson-item:hover{background:rgba(255,255,255,.04);}
.lesson-item.active{background:rgba(200,151,58,.1);border-color:rgba(200,151,58,.2);}
.lesson-item.active-green{background:rgba(82,183,136,.1);border-color:rgba(82,183,136,.2);}
.lesson-item.active-purple{background:rgba(155,142,196,.1);border-color:rgba(155,142,196,.2);}
.lesson-num{width:28px;height:28px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-family:'Syne',sans-serif;font-weight:700;font-size:.72rem;flex-shrink:0;}
.lesson-num.gold{background:rgba(200,151,58,.15);color:var(--gold);}
.lesson-num.green{background:rgba(82,183,136,.15);color:var(--green);}
.lesson-num.purple{background:rgba(155,142,196,.15);color:var(--purple);}
.lesson-num.done{background:var(--gold);color:var(--navy);}
.lesson-info{flex:1;min-width:0;}
.lesson-title{font-size:.82rem;color:var(--white);font-weight:500;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;}
.lesson-dur{font-size:.7rem;color:var(--muted);margin-top:.1rem;}
.lesson-lock{font-size:.8rem;color:var(--muted);}

/* Video player */
.video-area{display:flex;flex-direction:column;gap:1.2rem;}
.video-player{background:var(--card);border-radius:var(--r);overflow:hidden;border:1px solid rgba(255,255,255,.06);}
.vp-screen{position:relative;background:#000;aspect-ratio:16/9;display:flex;align-items:center;justify-content:center;overflow:hidden;}
.vp-bg{position:absolute;inset:0;background:linear-gradient(135deg,#0A0F1E 0%,#16213A 100%);}
.vp-grid{position:absolute;inset:0;background-image:linear-gradient(rgba(200,151,58,.04) 1px,transparent 1px),linear-gradient(90deg,rgba(200,151,58,.04) 1px,transparent 1px);background-size:40px 40px;}
.vp-content{position:relative;z-index:1;text-align:center;padding:2rem;}
.vp-lesson-num{font-family:'Syne',sans-serif;font-size:.65rem;font-weight:700;letter-spacing:.4em;text-transform:uppercase;color:var(--gold);margin-bottom:.8rem;}
.vp-title{font-family:'Syne',sans-serif;font-weight:800;font-size:clamp(1.2rem,2.5vw,2rem);color:var(--white);margin-bottom:.6rem;line-height:1.2;}
.vp-sub{font-size:.85rem;color:var(--muted);margin-bottom:1.5rem;max-width:460px;margin-left:auto;margin-right:auto;}
.vp-play-btn{width:72px;height:72px;border-radius:50%;background:var(--gold);display:flex;align-items:center;justify-content:center;margin:0 auto;cursor:pointer;border:none;transition:all .25s;box-shadow:0 8px 32px rgba(200,151,58,.35);}
.vp-play-btn:hover{background:var(--gold-lt);transform:scale(1.08);box-shadow:0 12px 48px rgba(200,151,58,.5);}
.vp-play-btn svg{margin-left:4px;}
.vp-playing{display:none;}
.vp-lesson-body{position:absolute;inset:0;background:var(--navy);padding:2rem;display:flex;flex-direction:column;justify-content:flex-start;overflow-y:auto;}
.vp-lesson-body .lesson-section-title{font-family:'Syne',sans-serif;font-weight:800;font-size:1.1rem;color:var(--gold);margin-bottom:.8rem;}
.vp-lesson-body .lesson-point{display:flex;gap:.7rem;margin-bottom:.6rem;align-items:flex-start;}
.vp-lesson-body .lesson-point-icon{flex-shrink:0;margin-top:.1rem;}
.vp-lesson-body .lesson-point-text{font-size:.88rem;color:var(--white);line-height:1.65;}
.vp-lesson-body .exercise-box{background:var(--card);border:1px solid rgba(200,151,58,.2);border-radius:10px;padding:1rem 1.2rem;margin-top:1rem;}
.vp-lesson-body .exercise-label{font-family:'Syne',sans-serif;font-size:.65rem;font-weight:700;letter-spacing:.3em;text-transform:uppercase;color:var(--gold);margin-bottom:.5rem;}
.vp-lesson-body .exercise-text{font-size:.85rem;color:var(--muted);line-height:1.7;}
.vp-controls{padding:1rem 1.4rem;display:flex;align-items:center;gap:1rem;background:var(--navy-lt);border-top:1px solid rgba(255,255,255,.06);}
.vp-progress-wrap{flex:1;height:4px;background:rgba(255,255,255,.1);border-radius:4px;cursor:pointer;overflow:hidden;}
.vp-progress-fill{height:100%;background:var(--gold);border-radius:4px;transition:width .3s;}
.vp-time{font-size:.75rem;color:var(--muted);white-space:nowrap;font-family:'Syne',sans-serif;}
.vp-btn{background:none;border:none;color:var(--muted);cursor:pointer;font-size:.95rem;transition:color .2s;padding:0 .3rem;}
.vp-btn:hover{color:var(--white);}
.vp-info{padding:1.2rem 1.4rem;}
.vp-info-title{font-family:'Syne',sans-serif;font-weight:800;font-size:1.05rem;color:var(--white);margin-bottom:.35rem;}
.vp-info-desc{font-size:.85rem;color:var(--muted);line-height:1.7;}
.vp-nav-btns{display:flex;gap:.7rem;margin-top:1rem;}
.vp-nav-btn{font-family:'Syne',sans-serif;font-weight:700;font-size:.78rem;padding:.5rem 1rem;border-radius:8px;border:none;cursor:pointer;transition:all .2s;}
.vp-nav-btn.prev{background:rgba(255,255,255,.06);color:var(--muted);}
.vp-nav-btn.prev:hover{color:var(--white);background:rgba(255,255,255,.1);}
.vp-nav-btn.next{background:var(--gold);color:var(--navy);}
.vp-nav-btn.next:hover{background:var(--gold-lt);}
.vp-tabs{display:flex;gap:.5rem;padding:.8rem 1.4rem .4rem;border-top:1px solid rgba(255,255,255,.06);}
.vp-tab{font-size:.75rem;font-family:'Syne',sans-serif;font-weight:600;padding:.35rem .8rem;border-radius:6px;border:none;cursor:pointer;transition:all .2s;background:transparent;color:var(--muted);}
.vp-tab.active{background:rgba(200,151,58,.15);color:var(--gold);}

/* Quiz panel */
.quiz-panel{padding:1.2rem 1.4rem;display:none;}
.quiz-panel.show{display:block;}
.quiz-q{font-family:'Syne',sans-serif;font-weight:700;font-size:.95rem;color:var(--white);margin-bottom:1rem;}
.quiz-opts{display:flex;flex-direction:column;gap:.5rem;}
.quiz-opt{padding:.7rem 1rem;border-radius:8px;border:1.5px solid rgba(255,255,255,.08);background:var(--navy-md);color:var(--muted);font-size:.85rem;cursor:pointer;transition:all .2s;text-align:left;}
.quiz-opt:hover{border-color:rgba(200,151,58,.3);color:var(--white);}
.quiz-opt.correct{border-color:var(--green);background:rgba(82,183,136,.1);color:var(--green);}
.quiz-opt.wrong{border-color:#CC3333;background:rgba(204,51,51,.1);color:#CC3333;}
.quiz-result{margin-top:1rem;padding:.8rem 1rem;border-radius:8px;font-family:'Syne',sans-serif;font-weight:700;font-size:.85rem;display:none;}
.quiz-result.show{display:block;}
.quiz-result.pass{background:rgba(82,183,136,.1);color:var(--green);border:1px solid rgba(82,183,136,.2);}
.quiz-result.fail{background:rgba(204,51,51,.1);color:#CC3333;border:1px solid rgba(204,51,51,.2);}

/* ════════════════════════════════════════
   ENROLL SECTION
════════════════════════════════════════ */
.enroll-bg{background:var(--navy-md);}
.enroll-grid{display:grid;grid-template-columns:1fr 1fr;gap:4rem;align-items:start;}
@media(max-width:768px){.enroll-grid{grid-template-columns:1fr;}}
.enroll-form{background:var(--card);border-radius:18px;padding:2.2rem;border:1px solid rgba(200,151,58,.15);}
.form-title{font-family:'Syne',sans-serif;font-weight:800;font-size:1.2rem;color:var(--white);margin-bottom:.4rem;}
.form-sub{font-size:.85rem;color:var(--muted);margin-bottom:1.6rem;}
.form-group{margin-bottom:1rem;}
.form-label{display:block;font-size:.78rem;font-family:'Syne',sans-serif;font-weight:600;color:var(--muted);letter-spacing:.1em;text-transform:uppercase;margin-bottom:.4rem;}
.form-input,.form-select,.form-textarea{width:100%;padding:.75rem 1rem;background:var(--navy-lt);border:1.5px solid rgba(255,255,255,.08);border-radius:8px;color:var(--white);font-family:'DM Sans',sans-serif;font-size:.9rem;outline:none;transition:border-color .2s;}
.form-input:focus,.form-select:focus,.form-textarea:focus{border-color:var(--gold);}
.form-select option{background:var(--navy-lt);}
.form-textarea{resize:vertical;min-height:90px;line-height:1.6;}
.form-row{display:grid;grid-template-columns:1fr 1fr;gap:.8rem;}
.form-submit{width:100%;padding:.9rem;background:var(--gold);color:var(--navy);font-family:'Syne',sans-serif;font-weight:700;font-size:.9rem;border:none;border-radius:10px;cursor:pointer;transition:all .25s;margin-top:.5rem;}
.form-submit:hover{background:var(--gold-lt);transform:translateY(-2px);}
.form-note{font-size:.72rem;color:var(--muted);text-align:center;margin-top:.8rem;}
.success-msg{display:none;background:rgba(82,183,136,.1);border:1px solid rgba(82,183,136,.3);border-radius:10px;padding:1.2rem;text-align:center;color:var(--green);font-family:'Syne',sans-serif;font-weight:700;}

/* Info side */
.enroll-info{}
.info-card{background:var(--card);border-radius:var(--r);padding:1.5rem;border:1px solid rgba(255,255,255,.05);margin-bottom:1rem;border-left:3px solid var(--gold);}
.info-card h4{font-family:'Syne',sans-serif;font-weight:700;font-size:.9rem;color:var(--white);margin-bottom:.4rem;}
.info-card p{font-size:.83rem;color:var(--muted);line-height:1.7;}
.contact-cards{display:grid;grid-template-columns:1fr 1fr;gap:.8rem;margin-top:1rem;}
.contact-card{background:var(--card);border-radius:var(--r);padding:1.1rem;text-align:center;border:1px solid rgba(255,255,255,.05);transition:all .2s;}
.contact-card:hover{border-color:rgba(200,151,58,.2);}
.contact-card .c-icon{font-size:1.4rem;margin-bottom:.5rem;}
.contact-card .c-label{font-size:.65rem;color:var(--muted);letter-spacing:.15em;text-transform:uppercase;margin-bottom:.3rem;}
.contact-card .c-val{font-family:'Syne',sans-serif;font-weight:700;font-size:.8rem;color:var(--gold);word-break:break-all;}

/* ════════════════════════════════════════
   PRICING
════════════════════════════════════════ */
.pricing-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:1.4rem;margin-top:3rem;}
.price-card{background:var(--card);border-radius:18px;padding:2rem;border:1px solid rgba(255,255,255,.055);transition:all .28s;position:relative;overflow:hidden;}
.price-card:hover{transform:translateY(-5px);box-shadow:0 20px 55px rgba(0,0,0,.35);}
.price-card.featured{border-color:rgba(200,151,58,.3);background:linear-gradient(145deg,var(--card),rgba(200,151,58,.04));}
.featured-badge{position:absolute;top:1rem;right:1rem;background:var(--gold);color:var(--navy);font-family:'Syne',sans-serif;font-weight:700;font-size:.65rem;padding:.25rem .7rem;border-radius:100px;letter-spacing:.08em;}
.price-track{font-size:.65rem;font-family:'Syne',sans-serif;font-weight:700;letter-spacing:.3em;text-transform:uppercase;margin-bottom:.7rem;}
.price-card:nth-child(1) .price-track{color:var(--gold);}
.price-card:nth-child(2) .price-track{color:var(--green);}
.price-card:nth-child(3) .price-track{color:var(--purple);}
.price-name{font-family:'Syne',sans-serif;font-weight:800;font-size:1.05rem;color:var(--white);margin-bottom:.3rem;}
.price-desc{font-size:.82rem;color:var(--muted);margin-bottom:1.2rem;line-height:1.65;}
.price-amount{font-family:'Syne',sans-serif;font-weight:800;font-size:2.2rem;color:var(--gold-lt);line-height:1;}
.price-amount sup{font-size:1rem;vertical-align:super;}
.price-period{font-size:.78rem;color:var(--muted);margin-bottom:1.4rem;}
.price-features{list-style:none;display:flex;flex-direction:column;gap:.55rem;margin-bottom:1.6rem;}
.price-features li{display:flex;align-items:center;gap:.6rem;font-size:.85rem;color:var(--muted);}
.price-features li::before{content:'✓';color:var(--gold);font-weight:700;flex-shrink:0;}
.price-btn{width:100%;padding:.78rem;border-radius:9px;border:none;font-family:'Syne',sans-serif;font-weight:700;font-size:.85rem;cursor:pointer;transition:all .22s;}
.price-card:nth-child(1) .price-btn{background:var(--gold);color:var(--navy);}
.price-card:nth-child(1) .price-btn:hover{background:var(--gold-lt);}
.price-card:nth-child(2) .price-btn{background:var(--green);color:var(--navy);}
.price-card:nth-child(2) .price-btn:hover{background:#6FCFA0;}
.price-card:nth-child(3) .price-btn{background:var(--purple);color:var(--navy);}
.price-card:nth-child(3) .price-btn:hover{background:#B5ABDA;}

/* ════════════════════════════════════════
   TESTIMONIALS
════════════════════════════════════════ */
.testi-bg{background:var(--navy-md);}
.testi-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:1.4rem;margin-top:3rem;}
.testi-card{background:var(--card);border-radius:var(--r);padding:2rem;border:1px solid rgba(255,255,255,.055);transition:all .28s;}
.testi-card:hover{transform:translateY(-4px);border-color:rgba(200,151,58,.2);}
.testi-qmark{font-family:'Syne',sans-serif;font-size:4.5rem;font-weight:800;color:rgba(200,151,58,.1);line-height:.8;margin-bottom:.4rem;}
.testi-stars{color:var(--gold);font-size:.85rem;letter-spacing:.1em;margin-bottom:.9rem;}
.testi-text{font-size:.88rem;color:var(--muted);line-height:1.78;margin-bottom:1.5rem;}
.testi-author{display:flex;align-items:center;gap:.8rem;}
.testi-av{width:42px;height:42px;border-radius:50%;background:linear-gradient(135deg,var(--gold),#9A7020);display:flex;align-items:center;justify-content:center;font-family:'Syne',sans-serif;font-weight:800;font-size:.9rem;color:var(--navy);flex-shrink:0;}
.testi-name{font-family:'Syne',sans-serif;font-weight:700;font-size:.88rem;color:var(--white);}
.testi-role{font-size:.73rem;color:var(--muted);margin-top:.1rem;}

/* ════════════════════════════════════════
   FAQ
════════════════════════════════════════ */
.faq-list{display:flex;flex-direction:column;gap:.7rem;margin-top:2.5rem;max-width:720px;}
.faq-item{background:var(--card);border-radius:var(--r);border:1px solid rgba(255,255,255,.055);overflow:hidden;}
.faq-q{display:flex;align-items:center;justify-content:space-between;padding:1.1rem 1.4rem;cursor:pointer;font-family:'Syne',sans-serif;font-weight:700;font-size:.9rem;color:var(--white);transition:color .2s;}
.faq-q:hover{color:var(--gold);}
.faq-icon{font-size:1.2rem;color:var(--gold);transition:transform .3s;flex-shrink:0;}
.faq-icon.open{transform:rotate(45deg);}
.faq-a{max-height:0;overflow:hidden;transition:max-height .35s ease,padding .35s ease;font-size:.87rem;color:var(--muted);line-height:1.78;padding:0 1.4rem;}
.faq-a.open{max-height:200px;padding:.2rem 1.4rem 1.2rem;}

/* ════════════════════════════════════════
   CTA SECTION
════════════════════════════════════════ */
.cta-section{text-align:center;position:relative;overflow:hidden;}
.cta-bg{position:absolute;inset:0;background:radial-gradient(ellipse 80% 60% at 50% 50%,rgba(200,151,58,.07) 0%,transparent 70%);pointer-events:none;}
.cta-section .sec-tag{justify-content:center;}
.cta-section .sec-title{font-size:clamp(1.8rem,3.5vw,3rem);}
.cta-section .sec-body{margin:0 auto 2.5rem;}
.cta-actions{display:flex;justify-content:center;gap:1rem;flex-wrap:wrap;}
.cta-phones{display:flex;justify-content:center;flex-wrap:wrap;gap:1.5rem;margin-top:1.5rem;}
.cta-phone{display:flex;align-items:center;gap:.5rem;font-size:.9rem;color:var(--muted);}
.cta-phone strong{color:var(--gold);}

/* ════════════════════════════════════════
   FOOTER
════════════════════════════════════════ */
footer{background:var(--navy-md);border-top:1px solid rgba(255,255,255,.05);padding:4rem 5% 2rem;}
.footer-grid{display:grid;grid-template-columns:2fr 1fr 1fr 1fr;gap:2.5rem;max-width:1140px;margin:0 auto 3rem;}
@media(max-width:768px){.footer-grid{grid-template-columns:1fr 1fr;}}
@media(max-width:480px){.footer-grid{grid-template-columns:1fr;}}
.footer-brand p{font-size:.82rem;color:var(--muted);line-height:1.8;margin-top:.7rem;max-width:250px;}
.footer-col h4{font-family:'Syne',sans-serif;font-weight:700;font-size:.82rem;color:var(--white);margin-bottom:.9rem;}
.footer-col ul{list-style:none;display:flex;flex-direction:column;gap:.5rem;}
.footer-col a{color:var(--muted);text-decoration:none;font-size:.8rem;transition:color .2s;cursor:pointer;}
.footer-col a:hover{color:var(--gold);}
.footer-bottom{border-top:1px solid rgba(255,255,255,.05);padding-top:1.5rem;max-width:1140px;margin:0 auto;display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:1rem;}
.footer-copy{font-size:.73rem;color:var(--muted);}
.social-links{display:flex;gap:.6rem;}
.social-link{width:32px;height:32px;border-radius:7px;background:rgba(255,255,255,.04);border:1px solid rgba(255,255,255,.08);display:flex;align-items:center;justify-content:center;font-size:.75rem;font-weight:600;color:var(--muted);text-decoration:none;transition:all .2s;cursor:pointer;}
.social-link:hover{background:rgba(200,151,58,.1);color:var(--gold);border-color:rgba(200,151,58,.28);}

/* ════════════════════════════════════════
   CERT MODAL
════════════════════════════════════════ */
.modal-overlay{display:none;position:fixed;inset:0;background:rgba(0,0,0,.8);z-index:2000;align-items:center;justify-content:center;padding:2rem;}
.modal-overlay.open{display:flex;}
.modal-box{background:var(--navy-lt);border-radius:20px;padding:2.5rem;max-width:500px;width:100%;border:1px solid rgba(200,151,58,.25);text-align:center;position:relative;}
.modal-close{position:absolute;top:1rem;right:1rem;background:none;border:none;color:var(--muted);font-size:1.4rem;cursor:pointer;}
.modal-close:hover{color:var(--white);}
.cert-icon{font-size:3.5rem;margin-bottom:1rem;}
.cert-title{font-family:'Syne',sans-serif;font-weight:800;font-size:1.3rem;color:var(--white);margin-bottom:.5rem;}
.cert-sub{font-size:.88rem;color:var(--muted);margin-bottom:1.5rem;line-height:1.7;}
.cert-name{font-family:'Syne',sans-serif;font-weight:800;font-size:1.5rem;color:var(--gold);padding:1rem;background:rgba(200,151,58,.08);border-radius:10px;border:1px solid rgba(200,151,58,.2);margin-bottom:1.2rem;}
.cert-badge{display:inline-flex;align-items:center;gap:.5rem;padding:.5rem 1.2rem;border-radius:100px;background:rgba(82,183,136,.1);border:1px solid rgba(82,183,136,.2);color:var(--green);font-family:'Syne',sans-serif;font-weight:700;font-size:.8rem;margin-bottom:1.2rem;}
</style>
</head>
<body>

<!-- Mobile menu -->
<div class="mob-menu" id="mobMenu">
  <button class="mob-close" onclick="closeMob()">✕</button>
  <a href="#home" onclick="closeMob()">Home</a>
  <a href="#courses" onclick="closeMob()">Courses</a>
  <a href="#academy" onclick="closeMob()">Video Lessons</a>
  <a href="#pricing" onclick="closeMob()">Pricing</a>
  <a href="#enroll" onclick="closeMob()">Enrol Now</a>
</div>

<!-- NAV -->
<nav id="mainNav">
  <a class="nav-logo" onclick="scrollTo('home')">
    <span class="nav-logo-3a">3A</span>
    <span class="nav-logo-text">AI Solutions</span>
  </a>
  <ul class="nav-links">
    <li><a onclick="scrollTo('courses')">Courses</a></li>
    <li><a onclick="scrollTo('academy')">Video Lessons</a></li>
    <li><a onclick="scrollTo('pricing')">Pricing</a></li>
    <li><a onclick="scrollTo('testimonials')">Reviews</a></li>
    <li><a onclick="scrollTo('enroll')" class="nav-enroll">Enrol Now →</a></li>
  </ul>
  <button class="hamburger" onclick="document.getElementById('mobMenu').classList.add('open')">
    <span></span><span></span><span></span>
  </button>
</nav>

<!-- HERO -->
<section class="hero" id="home" style="padding-top:8rem;">
  <div class="hero-bg"></div>
  <div class="hero-grid"></div>
  <div class="orb orb-1"></div>
  <div class="orb orb-2"></div>
  <div class="kente kente-tl"></div>
  <div class="kente kente-br"></div>
  <div class="hero-content">
    <div class="hero-badge"><span class="badge-dot"></span>Now Open for Enrolment · 2026</div>
    <h1>
      Africa's AI Training<br>
      <span class="gold">Academy is Live.</span>
    </h1>
    <p class="hero-sub">Learn AI through video lessons, hands-on exercises, and live support — from anywhere in Africa. Built for individuals, school staff, and corporate teams.</p>
    <div class="hero-actions">
      <button class="btn-gold" onclick="scrollTo('academy')">▶ Start Learning Free</button>
      <button class="btn-outline" onclick="scrollTo('courses')">Explore Courses</button>
    </div>
    <div class="hero-stats">
      <div class="hero-stat"><div class="num" id="c1">0</div><div class="lbl">Lessons Available</div></div>
      <div class="hero-stat"><div class="num" id="c2">0</div><div class="lbl">Video Modules</div></div>
      <div class="hero-stat"><div class="num" id="c3">0</div><div class="lbl">% Free to Start</div></div>
      <div class="hero-stat"><div class="num" id="c4">0</div><div class="lbl">Day Certificate</div></div>
    </div>
  </div>
</section>

<hr class="hr">

<!-- COURSES -->
<section id="courses" style="padding:5.5rem 5%;">
  <div class="sec-inner reveal">
    <p class="sec-tag">Choose Your Track</p>
    <h2 class="sec-title">Three Courses. <span>Every Learner Covered.</span></h2>
    <p class="sec-body">Select the track that matches your context. All courses include video lessons, exercises, quizzes, and a certificate.</p>
  </div>
  <div class="sec-inner">
    <div class="tracks-grid reveal">

      <div class="track-card gold-track" onclick="openTrack('individuals')">
        <div class="track-icon">👤</div>
        <div class="track-label">Track A</div>
        <div class="track-title">AI for Individuals & Professionals</div>
        <p class="track-desc">Build practical AI skills for your career, business, or freelance work. No technical background needed — just ambition.</p>
        <div class="track-meta">
          <span class="track-pill">5 Modules</span>
          <span class="track-pill">15 Lessons</span>
          <span class="track-pill">From $49</span>
        </div>
        <button class="track-cta">Start This Course →</button>
      </div>

      <div class="track-card green-track" onclick="openTrack('schools')">
        <div class="track-icon">🏫</div>
        <div class="track-label">Track B</div>
        <div class="track-title">AI for School Staff & Educators</div>
        <p class="track-desc">Learn to plan lessons, reduce admin workload, and prepare your students for an AI-enabled world — in your own time.</p>
        <div class="track-meta">
          <span class="track-pill">5 Modules</span>
          <span class="track-pill">15 Lessons</span>
          <span class="track-pill">From $600 School</span>
        </div>
        <button class="track-cta">Start This Course →</button>
      </div>

      <div class="track-card purple-track" onclick="openTrack('corporate')">
        <div class="track-icon">🏢</div>
        <div class="track-label">Track C</div>
        <div class="track-title">AI for Corporate & Organisation Teams</div>
        <p class="track-desc">Embed AI across your entire organisation — HR, marketing, finance, customer service, and leadership. Measurable ROI guaranteed.</p>
        <div class="track-meta">
          <span class="track-pill">6 Modules</span>
          <span class="track-pill">18 Lessons</span>
          <span class="track-pill">From $800 Team</span>
        </div>
        <button class="track-cta">Start This Course →</button>
      </div>

    </div>
  </div>
</section>

<hr class="hr">

<!-- VIDEO ACADEMY -->
<section id="academy" style="background:var(--navy-md);padding:5.5rem 5%;">
  <div class="sec-inner reveal">
    <p class="sec-tag">Video Lessons</p>
    <h2 class="sec-title">Learn at Your Own Pace — <span>Start Today</span></h2>
    <p class="sec-body">Watch, practise, quiz yourself. Every lesson includes a video, key notes, and a hands-on exercise.</p>
  </div>
  <div class="sec-inner" style="margin-top:2rem;">
    <div class="academy-layout">

      <!-- Sidebar -->
      <div class="academy-sidebar reveal">
        <div class="sidebar-header">
          <div class="sidebar-header-title">Course Curriculum</div>
          <div class="sidebar-header-sub">Select a track · 45 total lessons</div>
        </div>
        <div class="track-tabs">
          <button class="track-tab active-gold" onclick="switchTrack('individuals',this)">👤 Individuals</button>
          <button class="track-tab inactive-green" onclick="switchTrack('schools',this)">🏫 Schools</button>
          <button class="track-tab inactive-purple" onclick="switchTrack('corporate',this)">🏢 Corporate</button>
        </div>
        <div class="lesson-list" id="lessonList"></div>
      </div>

      <!-- Video player -->
      <div class="video-area reveal">
        <div class="video-player">
          <div class="vp-screen">
            <div class="vp-bg"></div>
            <div class="vp-grid"></div>
            <div class="vp-content" id="vpContent">
              <div class="vp-lesson-num" id="vpLessonNum">MODULE 1 · LESSON 1</div>
              <div class="vp-title" id="vpTitle">What Is AI and Why Does It Matter?</div>
              <div class="vp-sub" id="vpSub">From fear to fluency — understand AI in plain language. Your first hands-on interaction.</div>
              <button class="vp-play-btn" onclick="playLesson()">
                <svg width="22" height="26" viewBox="0 0 22 26" fill="none">
                  <path d="M2 2L20 13L2 24V2Z" fill="#07090F"/>
                </svg>
              </button>
            </div>
            <div class="vp-playing" id="vpPlaying">
              <div class="vp-lesson-body" id="vpLessonBody"></div>
            </div>
          </div>
          <div class="vp-controls">
            <button class="vp-btn" id="vpPlayIcon" onclick="togglePlay()">▶</button>
            <div class="vp-progress-wrap" onclick="seekLesson(event)">
              <div class="vp-progress-fill" id="vpProgress" style="width:0%"></div>
            </div>
            <span class="vp-time" id="vpTime">0:00 / 8:00</span>
            <button class="vp-btn" onclick="toggleMute()">🔊</button>
          </div>
          <div class="vp-tabs">
            <button class="vp-tab active" onclick="switchTab('notes',this)">📝 Notes</button>
            <button class="vp-tab" onclick="switchTab('quiz',this)">❓ Quiz</button>
            <button class="vp-tab" onclick="switchTab('resources',this)">📚 Resources</button>
          </div>
          <div id="tabNotes" class="vp-info">
            <div class="vp-info-title" id="vpNotesTitle">What Is AI and Why Does It Matter?</div>
            <div class="vp-info-desc" id="vpNotesDesc">AI (Artificial Intelligence) is software that performs tasks requiring human-like thinking by recognising patterns in large amounts of training data. It does not think like a human — but it is extraordinarily good at language, writing, planning, and analysis.</div>
            <div class="vp-nav-btns">
              <button class="vp-nav-btn prev" onclick="prevLesson()">← Previous</button>
              <button class="vp-nav-btn next" onclick="nextLesson()">Next Lesson →</button>
            </div>
          </div>
          <div id="tabQuiz" class="quiz-panel">
            <div class="quiz-q" id="quizQuestion">Which formula should you use to write effective AI prompts?</div>
            <div class="quiz-opts" id="quizOpts"></div>
            <div class="quiz-result" id="quizResult"></div>
          </div>
          <div id="tabResources" class="vp-info" style="display:none;">
            <div class="vp-info-title">Lesson Resources</div>
            <div class="vp-info-desc" id="vpResources">
              • <strong style="color:var(--gold)">ChatGPT</strong> — chatgpt.com (Free)<br>
              • <strong style="color:var(--gold)">Claude</strong> — claude.ai (Free)<br>
              • <strong style="color:var(--gold)">Google Gemini</strong> — gemini.google.com (Free)<br><br>
              Download your Participant Handbook for the full tools directory.
            </div>
            <div class="vp-nav-btns" style="margin-top:1rem;">
              <button class="vp-nav-btn prev" onclick="prevLesson()">← Previous</button>
              <button class="vp-nav-btn next" onclick="nextLesson()">Next Lesson →</button>
            </div>
          </div>
        </div>

        <!-- Progress bar -->
        <div style="background:var(--card);border-radius:var(--r);padding:1.2rem 1.4rem;border:1px solid rgba(255,255,255,.06);">
          <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:.7rem;">
            <span style="font-family:'Syne',sans-serif;font-weight:700;font-size:.85rem;color:var(--white);">Your Progress</span>
            <span style="font-size:.78rem;color:var(--gold);font-family:'Syne',sans-serif;font-weight:700;" id="progressLabel">0 / 15 lessons</span>
          </div>
          <div style="height:6px;background:rgba(255,255,255,.07);border-radius:6px;overflow:hidden;">
            <div id="progressBar" style="height:100%;background:linear-gradient(90deg,var(--gold),var(--gold-lt));border-radius:6px;transition:width .4s;width:0%;"></div>
          </div>
          <div style="display:flex;gap:.5rem;margin-top:.9rem;flex-wrap:wrap;">
            <span style="font-size:.72rem;color:var(--muted);">Complete all lessons to earn your</span>
            <button onclick="showCert()" style="font-size:.72rem;font-family:'Syne',sans-serif;font-weight:700;color:var(--gold);background:none;border:none;cursor:pointer;text-decoration:underline;">3A Certificate of Completion 🏆</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<hr class="hr">

<!-- PRICING -->
<section id="pricing" style="padding:5.5rem 5%;">
  <div class="sec-inner reveal">
    <p class="sec-tag">Packages & Pricing</p>
    <h2 class="sec-title">Invest in Your <span>AI Future</span></h2>
    <p class="sec-body">Flexible packages for every learner and budget. All include video lessons, exercises, certificate, and 30-day alumni access.</p>
  </div>
  <div class="sec-inner">
    <div class="pricing-grid reveal">

      <div class="price-card">
        <div class="price-track">Track A — Individuals</div>
        <div class="price-name">AI Starter</div>
        <p class="price-desc">Online self-paced access to all individual modules with video lessons and exercises.</p>
        <div class="price-amount"><sup>$</sup>49</div>
        <div class="price-period">One-time · Lifetime access</div>
        <ul class="price-features">
          <li>15 video lessons</li>
          <li>5 hands-on exercise sets</li>
          <li>Module quizzes</li>
          <li>3A Certificate of Completion</li>
          <li>AI Tools Directory download</li>
          <li>Alumni network access</li>
        </ul>
        <button class="price-btn" onclick="scrollTo('enroll')">Enrol Now →</button>
      </div>

      <div class="price-card featured">
        <div class="featured-badge">Most Popular</div>
        <div class="price-track">Track A — Individuals</div>
        <div class="price-name">AI Bootcamp Live</div>
        <p class="price-desc">2-day live online training with instructor, plus lifetime replay access to all recordings.</p>
        <div class="price-amount"><sup>$</sup>120</div>
        <div class="price-period">Per person · 2-day live session</div>
        <ul class="price-features">
          <li>Live 2-day instructor training</li>
          <li>All 15 video lessons on-demand</li>
          <li>Personal AI Action Plan</li>
          <li>3A Certificate of Completion</li>
          <li>30-day follow-up session</li>
          <li>Printed workbook & handbook</li>
          <li>WhatsApp alumni community</li>
        </ul>
        <button class="price-btn" onclick="scrollTo('enroll')">Enrol Now →</button>
      </div>

      <div class="price-card">
        <div class="price-track">Track B & C — Schools & Teams</div>
        <div class="price-name">School / Corporate Package</div>
        <p class="price-desc">Group training for schools and organisations. Custom pricing based on team size and format.</p>
        <div class="price-amount" style="font-size:1.6rem;color:var(--purple);">Custom</div>
        <div class="price-period">Per organisation · All formats</div>
        <ul class="price-features">
          <li>Schools from $600 (15 staff)</li>
          <li>Corporate from $800 (20 staff)</li>
          <li>In-person, online, or hybrid</li>
          <li>Department-specific modules</li>
          <li>90-day AI roadmap</li>
          <li>Certificates for all participants</li>
          <li>20% off for schools &amp; NGOs</li>
        </ul>
        <button class="price-btn" onclick="scrollTo('enroll')">Get a Quote →</button>
      </div>

    </div>
    <p style="text-align:center;margin-top:1.5rem;font-size:.8rem;color:var(--muted);">Schools and registered NGOs receive a 20% solidarity discount automatically. All prices in USD — NGN and GHS equivalents available on request.</p>
  </div>
</section>

<hr class="hr">

<!-- TESTIMONIALS -->
<section id="testimonials" class="testi-bg" style="padding:5.5rem 5%;">
  <div class="sec-inner reveal">
    <p class="sec-tag">What Learners Say</p>
    <h2 class="sec-title">Real Results from <span>Real Participants</span></h2>
  </div>
  <div class="sec-inner">
    <div class="testi-grid reveal">
      <div class="testi-card">
        <div class="testi-qmark">"</div>
        <div class="testi-stars">★★★★★</div>
        <p class="testi-text">I completed the Individual track online in 4 days. The video lessons are clear, practical, and actually fun. I can now write a full business proposal in 10 minutes using AI. My clients are already asking what changed.</p>
        <div class="testi-author">
          <div class="testi-av">OA</div>
          <div>
            <div class="testi-name">Oluwaseun Adeyemi</div>
            <div class="testi-role">Freelance Consultant · Lagos, Nigeria</div>
          </div>
        </div>
      </div>
      <div class="testi-card">
        <div class="testi-qmark">"</div>
        <div class="testi-stars">★★★★★</div>
        <p class="testi-text">As a school principal, I was sceptical. After the school staff programme, our teachers are creating lesson plans in 20 minutes that used to take 3 hours. The online platform made it easy to fit around our schedule.</p>
        <div class="testi-author">
          <div class="testi-av">AM</div>
          <div>
            <div class="testi-name">Abena Mensah</div>
            <div class="testi-role">School Principal · Accra, Ghana</div>
          </div>
        </div>
      </div>
      <div class="testi-card">
        <div class="testi-qmark">"</div>
        <div class="testi-stars">★★★★★</div>
        <p class="testi-text">We enrolled our entire marketing team. Revenue from AI-assisted campaigns is up 38% in 3 months. The video lessons meant staff could learn at their own pace without disrupting operations. Worth every naira.</p>
        <div class="testi-author">
          <div class="testi-av">FK</div>
          <div>
            <div class="testi-name">Fatima Kabiru</div>
            <div class="testi-role">Marketing Director · BrightMart, Abuja</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<hr class="hr">

<!-- FAQ -->
<section style="padding:5.5rem 5%;">
  <div class="sec-inner reveal">
    <p class="sec-tag">Frequently Asked Questions</p>
    <h2 class="sec-title">Everything You Need to <span>Know</span></h2>
    <div class="faq-list">
      <div class="faq-item">
        <div class="faq-q" onclick="toggleFaq(this)">Do I need any technical background to enrol? <span class="faq-icon">+</span></div>
        <div class="faq-a">No. All three tracks are designed to be accessible to complete beginners. If you can send an email and browse the internet, you have everything you need to start.</div>
      </div>
      <div class="faq-item">
        <div class="faq-q" onclick="toggleFaq(this)">How long do I have access to the video lessons? <span class="faq-icon">+</span></div>
        <div class="faq-a">Self-paced learners receive lifetime access to all video lessons. Live bootcamp participants also receive lifetime replay access to all recordings after the session.</div>
      </div>
      <div class="faq-item">
        <div class="faq-q" onclick="toggleFaq(this)">Can I pay in Nigerian Naira or Ghanaian Cedis? <span class="faq-icon">+</span></div>
        <div class="faq-a">Yes. We accept payments via Paystack (Nigeria) and Flutterwave (Ghana and across Africa) in local currencies. Contact us for current Naira and Cedi pricing.</div>
      </div>
      <div class="faq-item">
        <div class="faq-q" onclick="toggleFaq(this)">What certificate do I receive? <span class="faq-icon">+</span></div>
        <div class="faq-a">All participants receive a 3A AI Solutions Certificate of Completion upon finishing all modules and quizzes. The certificate is suitable for LinkedIn, your CV, and professional records. It is issued digitally as a PDF and can also be printed.</div>
      </div>
      <div class="faq-item">
        <div class="faq-q" onclick="toggleFaq(this)">Is the training available in other languages? <span class="faq-icon">+</span></div>
        <div class="faq-a">The primary language of instruction is English. Yoruba and Pidgin supplement guides are available for the Individual track. Contact us if you have specific language requirements for a school or corporate group.</div>
      </div>
      <div class="faq-item">
        <div class="faq-q" onclick="toggleFaq(this)">How do school and corporate group enrolments work? <span class="faq-icon">+</span></div>
        <div class="faq-a">For schools and organisations, contact us directly for a tailored quote. We will schedule a free discovery call, prepare a custom proposal, and set up a group access account for all participants. Schools and NGOs automatically receive a 20% discount.</div>
      </div>
    </div>
  </div>
</section>

<hr class="hr">

<!-- ENROL -->
<section id="enroll" class="enroll-bg" style="padding:5.5rem 5%;">
  <div class="sec-inner">
    <div class="enroll-grid">
      <div class="reveal">
        <p class="sec-tag">Enrol Today</p>
        <h2 class="sec-title">Start Your AI Journey <span>Right Now</span></h2>
        <p class="sec-body">Fill in the form and we will be in touch within one business day to confirm your enrolment and set up your access.</p>

        <div style="margin-top:2rem;">
          <div class="info-card">
            <h4>🕐 What Happens Next</h4>
            <p>After submitting — we send a confirmation email within 1 business day, share your login and course materials, and schedule your onboarding call if you booked a live programme.</p>
          </div>
          <div class="info-card" style="border-left-color:var(--accent);">
            <h4>🌍 Available Across Africa</h4>
            <p>We currently serve learners in Nigeria and Ghana. Online self-paced learning is available to anyone on the continent with internet access.</p>
          </div>
        </div>

        <div class="contact-cards">
          <div class="contact-card">
            <div class="c-icon">📞</div>
            <div class="c-label">Nigeria</div>
            <div class="c-val">+234 806 266 8272</div>
          </div>
          <div class="contact-card">
            <div class="c-icon">📞</div>
            <div class="c-label">Ghana</div>
            <div class="c-val">+233 532 954 184</div>
          </div>
          <div class="contact-card">
            <div class="c-icon">✉</div>
            <div class="c-label">Email</div>
            <div class="c-val">hello@3aaisolutions.com</div>
          </div>
          <div class="contact-card">
            <div class="c-icon">🌐</div>
            <div class="c-label">Website</div>
            <div class="c-val">www.3aaisolutions.com</div>
          </div>
        </div>
      </div>

      <div class="reveal">
        <div class="enroll-form">
          <div class="form-title">Enrol in a Course</div>
          <div class="form-sub">Free discovery call included with every enrolment. No commitment required.</div>
          <div id="successMsg" class="success-msg">
            ✅ Thank you! We have received your enrolment. We will be in touch within one business day.
          </div>
          <form id="enrollForm" onsubmit="submitForm(event)">
            <div class="form-row">
              <div class="form-group">
                <label class="form-label">First Name *</label>
                <input class="form-input" type="text" placeholder="Akanni" required>
              </div>
              <div class="form-group">
                <label class="form-label">Last Name *</label>
                <input class="form-input" type="text" placeholder="Akinlabi" required>
              </div>
            </div>
            <div class="form-group">
              <label class="form-label">Email Address *</label>
              <input class="form-input" type="email" placeholder="you@example.com" required>
            </div>
            <div class="form-group">
              <label class="form-label">Phone Number (WhatsApp) *</label>
              <input class="form-input" type="tel" placeholder="+234 or +233..." required>
            </div>
            <div class="form-group">
              <label class="form-label">Country *</label>
              <select class="form-select" required>
                <option value="">Select your country</option>
                <option>Nigeria</option>
                <option>Ghana</option>
                <option>Kenya</option>
                <option>South Africa</option>
                <option>Other African Country</option>
              </select>
            </div>
            <div class="form-group">
              <label class="form-label">Course Track *</label>
              <select class="form-select" id="trackSelect" required>
                <option value="">Select a track</option>
                <option>Track A — Individuals & Professionals ($49 online)</option>
                <option>Track A — AI Bootcamp Live ($120 per person)</option>
                <option>Track A — AI Bootcamp In-Person ($200)</option>
                <option>Track B — School Staff Programme (from $600)</option>
                <option>Track C — Corporate Team Training (from $800)</option>
                <option>Not sure — I need a recommendation</option>
              </select>
            </div>
            <div class="form-group">
              <label class="form-label">Organisation / School (if applicable)</label>
              <input class="form-input" type="text" placeholder="Optional">
            </div>
            <div class="form-group">
              <label class="form-label">Tell us about your AI experience</label>
              <textarea class="form-textarea" placeholder="I have never used AI before / I have tried ChatGPT a few times / Other..."></textarea>
            </div>
            <button type="submit" class="form-submit">Submit Enrolment →</button>
            <p class="form-note">By submitting you agree to be contacted by 3A AI Solutions regarding your enrolment. We never share your data with third parties.</p>
          </form>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CTA -->
<section class="cta-section" style="padding:7rem 5%;">
  <div class="cta-bg"></div>
  <div style="position:relative;z-index:1;max-width:680px;margin:0 auto;" class="reveal">
    <p class="sec-tag">Ready to Begin?</p>
    <h2 class="sec-title">Your Business Deserves AI.<br><span>We Make It Real.</span></h2>
    <p class="sec-body" style="margin:0 auto 2.5rem;">Book a free 30-minute discovery call. No pressure, no jargon — just an honest conversation about how AI can work for you.</p>
    <div class="cta-actions">
      <button class="btn-gold" onclick="scrollTo('enroll')">Enrol Now →</button>
      <button class="btn-outline" onclick="scrollTo('academy')">▶ Watch Free Lessons</button>
    </div>
    <div class="cta-phones">
      <div class="cta-phone">📞 <strong>Nigeria:</strong> +234 806 266 8272</div>
      <div class="cta-phone">📞 <strong>Ghana:</strong> +233 532 954 184</div>
      <div class="cta-phone">✉ hello@3aaisolutions.com</div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-grid">
    <div class="footer-brand">
      <a class="nav-logo" onclick="scrollTo('home')" style="cursor:pointer;">
        <span class="nav-logo-3a">3A</span>
        <span class="nav-logo-text">AI Solutions</span>
      </a>
      <p>Smarter Business. African Excellence. Empowering African professionals, schools, and organisations with practical AI skills — since 2026.</p>
    </div>
    <div class="footer-col">
      <h4>Courses</h4>
      <ul>
        <li><a onclick="openTrack('individuals')">Track A — Individuals</a></li>
        <li><a onclick="openTrack('schools')">Track B — Schools</a></li>
        <li><a onclick="openTrack('corporate')">Track C — Corporate</a></li>
        <li><a onclick="scrollTo('academy')">Video Lessons</a></li>
        <li><a onclick="scrollTo('pricing')">Pricing</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Company</h4>
      <ul>
        <li><a>About 3A</a></li>
        <li><a>Our Trainers</a></li>
        <li><a onclick="scrollTo('testimonials')">Reviews</a></li>
        <li><a onclick="scrollTo('enroll')">Contact Us</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Contact</h4>
      <ul>
        <li><a>hello@3aaisolutions.com</a></li>
        <li><a>www.3aaisolutions.com</a></li>
        <li><a>Nigeria: +234 806 266 8272</a></li>
        <li><a>Ghana: +233 532 954 184</a></li>
        <li><a>Lagos · Accra</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <p class="footer-copy">© 2026 3A AI Solutions · Akanni · Akinlabi · Adedoyin. All rights reserved.</p>
    <div class="social-links">
      <a class="social-link">in</a>
      <a class="social-link">𝕏</a>
      <a class="social-link">ig</a>
      <a class="social-link">wa</a>
    </div>
  </div>
</footer>

<!-- Certificate Modal -->
<div class="modal-overlay" id="certModal">
  <div class="modal-box">
    <button class="modal-close" onclick="closeCert()">✕</button>
    <div class="cert-icon">🏆</div>
    <div class="cert-title">Certificate of Completion</div>
    <div class="cert-sub">This certifies that</div>
    <div class="cert-name" id="certName">Your Name Here</div>
    <div class="cert-badge">✓ 3A AI Solutions · AI Training Graduate · 2026</div>
    <p style="font-size:.82rem;color:var(--muted);margin-bottom:1.2rem;">Complete all lessons and quizzes to earn your official certificate. Enter your name above to preview.</p>
    <input class="form-input" type="text" placeholder="Enter your full name" oninput="document.getElementById('certName').textContent=this.value||'Your Name Here'" style="margin-bottom:1rem;">
    <button class="btn-gold" style="width:100%;" onclick="scrollTo('enroll');closeCert();">Enrol to Earn Your Certificate →</button>
  </div>
</div>

<script>
// ── DATA ──────────────────────────────────────────────
const courses = {
  individuals: {
    color: 'gold',
    lessons: [
      {num:'01',title:'What Is AI and Why Does It Matter?',dur:'8 min',mod:'Module 1 · Foundations',desc:'AI is software that performs human-like tasks by recognising patterns in data. No technical background required — just curiosity.',content:{points:['AI does not think like a human — it predicts based on patterns in training data','The 3 types of AI: Generative, Automation, and Analytical','5 things AI can do for you right now — writing, research, planning, analysis, design','Why AI literacy is now a career and business essential in Africa'],exercise:'Open ChatGPT or Claude. Type: "I am a [your job] in [your city]. Explain AI to me in 3 simple sentences." Read the result.'},quiz:{q:'What does the C in the CRAFT prompting formula stand for?',opts:['Create','Context','Copy','Command'],answer:1},resources:'ChatGPT (chatgpt.com) · Claude (claude.ai) · Google Gemini (gemini.google.com)'},
      {num:'02',title:'The CRAFT Prompting Formula',dur:'10 min',mod:'Module 1 · Foundations',desc:'The single most valuable AI skill — how to give AI the right instruction every time using the 5-part CRAFT formula.',content:{points:['C = Context: Tell AI who you are and your situation','R = Role: Give AI an expert persona to respond from','A = Action: State exactly what you want — Write, Summarise, Create, List','F = Format: Specify the output — email, table, bullet list, 200 words','T = Tone: Professional, friendly, formal, simple, persuasive'],exercise:'Use CRAFT to write a prompt for a real email you need to send. Test it in ChatGPT. Compare to what you would have written manually.'},quiz:{q:'A weak prompt says "Write me a report." What is the most important element missing?',opts:['Tone','Context and action specifics','Font size','The word "please"'],answer:1},resources:'Prompt Engineering Guide (promptingguide.ai) · 3A AI Solutions Blog'},
      {num:'03',title:'AI for Professional Emails & Reports',dur:'9 min',mod:'Module 2 · Writing',desc:'Write emails 5× faster, produce professional reports from bullet notes, and improve any document with AI.',content:{points:['Draft any email in under 60 seconds using CRAFT','Turn bullet points into a full professional report','Use AI to rewrite, shorten, or improve existing documents','Grammarly + ChatGPT: the ultimate professional writing stack'],exercise:'Take your most time-consuming recurring email. Use ChatGPT to generate a template. Time yourself. Record the result.'},quiz:{q:'Which tool is best for checking grammar and tone in professional writing?',opts:['Zapier','Grammarly','Otter.ai','Zapier'],answer:1},resources:'Grammarly (grammarly.com) · Notion AI (notion.so)'},
      {num:'04',title:'AI for Research & Summarising',dur:'8 min',mod:'Module 2 · Writing',desc:'Research any topic in minutes, summarise long documents instantly, and build knowledge faster than ever before.',content:{points:['Summarise a 40-page report in 5 bullet points in 30 seconds','Use Perplexity AI for research with live internet sources','Build a competitive analysis in minutes with AI','ALWAYS verify important facts — AI can be confidently wrong'],exercise:'Ask Perplexity AI: "Summarise the current state of AI adoption in Nigeria in 5 key points." Verify one fact from a primary source.'},quiz:{q:'What is the most important thing to do after AI gives you research or facts?',opts:['Say thank you','Verify from a reliable primary source','Copy it directly into your report','Share it immediately'],answer:1},resources:'Perplexity AI (perplexity.ai) · Google Gemini (gemini.google.com)'},
      {num:'05',title:'AI for Planning & Productivity',dur:'9 min',mod:'Module 3 · Productivity',desc:'Build 30-day action plans, manage your schedule, and use AI as your personal productivity coach.',content:{points:['Generate a personalised 30-day action plan for any goal','Use AI to prioritise your daily task list in seconds','AI meeting summaries with Otter.ai — never miss a key point again','Build a study plan for any new skill in under 5 minutes'],exercise:'Ask ChatGPT: "I am a [your role]. Create a practical 30-day plan for me to start using AI daily. Maximum 30 minutes per day." Customise the top 5 actions.'},quiz:{q:'Which tool transcribes meetings and generates summaries automatically?',opts:['Canva AI','Otter.ai','Grammarly','Zapier'],answer:1},resources:'Otter.ai (otter.ai) · Notion AI (notion.so) · Reclaim.ai'},
      {num:'06',title:'AI for Social Media & Marketing',dur:'8 min',mod:'Module 3 · Productivity',desc:'Create a full month of social media content in one session, write compelling marketing copy, and grow your business with AI.',content:{points:['Generate 30 days of LinkedIn, Instagram, or Twitter posts in 45 minutes','Write email marketing campaigns — subject line, body, and CTA','Use Canva AI to create professional visuals without a designer','AI for lead generation and customer segmentation basics'],exercise:'Ask ChatGPT: "Write 5 LinkedIn posts for [your profession or business]. Each post should be under 150 words. Mix educational and personal content."'},quiz:{q:'What does Canva AI help you do without needing design skills?',opts:['Code websites','Create professional visual content','Transcribe meetings','Screen job applicants'],answer:1},resources:'Canva AI (canva.com) · Copy.ai (copy.ai)'},
      {num:'07',title:'Your AI Toolkit & Personal Workflow',dur:'10 min',mod:'Module 4 · Toolkit',desc:'Build your personal AI workflow — a repeatable system that saves you hours every week, starting this Monday.',content:{points:['The 10 essential AI tools every African professional should know','How to build a personal AI workflow in 3 steps','Free vs paid: what you actually need to start (hint: free is enough)','Setting up your weekly AI routine for maximum productivity'],exercise:'Map out your top 5 weekly tasks and match each to an AI tool from your directory. This is your starting AI workflow.'},quiz:{q:'How much mobile data does a typical AI tool session use?',opts:['50–100MB','200MB+','5–15MB','1GB'],answer:2},resources:'Full AI Tools Directory in your Participant Handbook · Zapier (zapier.com)'},
      {num:'08',title:'AI Ethics & Responsible Use',dur:'8 min',mod:'Module 5 · Ethics',desc:'Use AI safely, ethically, and in a way that protects you, your clients, and your reputation.',content:{points:['NEVER enter passwords, ID numbers, or client data into public AI tools','5 key limitations: Hallucination, Bias, No Context, Knowledge Cut-Off, No Accountability','The 3 questions before using any AI output: Accurate? Appropriate? My meaning?','AI and academic integrity — what is acceptable and what is not'],exercise:'Take an AI output you generated today. Apply the 3 Questions. Write down any changes you would make before using it professionally.'},quiz:{q:'Which type of data should you NEVER enter into public AI tools like ChatGPT?',opts:['Your job title','Client confidential information and ID numbers','Your country of residence','The name of your employer'],answer:1},resources:'Part 5 of your Participant Handbook · Microsoft Copilot for Business (enterprise data protection)'},
    ]
  },
  schools: {
    color: 'green',
    lessons: [
      {num:'01',title:'AI in Education — Opportunity, Not Threat',dur:'9 min',mod:'Module 1 · Foundations',desc:'Understand what AI can and cannot do for schools. Separate fact from fear and build your AI confidence as an educator.',content:{points:['AI will not replace great teachers — it replaces their most exhausting tasks','What AI can do for your school: lesson plans, admin, communications, assessments','What AI cannot do: build relationships, inspire, judge complex situations','First steps: the 3 AI tools every teacher should try this week'],exercise:'Open MagicSchool AI (magicschool.ai). Create a free account. Explore the tools available. Write down 3 that could help you immediately.'},quiz:{q:'What is the most realistic impact of AI on teaching?',opts:['AI will replace all teachers within 5 years','AI removes exhausting administrative tasks, giving teachers more time for students','AI makes learning completely automated','AI has no role in schools'],answer:1},resources:'MagicSchool AI (magicschool.ai) · Diffit (diffit.me) · SchoolAI (schoolai.com)'},
      {num:'02',title:'AI for Lesson Planning in 20 Minutes',dur:'11 min',mod:'Module 2 · Teaching',desc:'Create a full week of lesson plans, differentiated resources, and assessment questions in a fraction of the usual time.',content:{points:['Use MagicSchool AI to generate a complete lesson plan in under 5 minutes','Differentiate for lower, middle, and higher ability in one prompt','Generate starters, main activities, and plenaries simultaneously','The CRAFT formula adapted for lesson planning prompts'],exercise:'Use this prompt in ChatGPT: "I am a Year [X] [subject] teacher in [country]. Create a 40-minute lesson plan on [topic] for a mixed-ability class. Include: learning objective, starter (5 min), main activity (25 min), and an exit question."'},quiz:{q:'Which tool is specifically designed for teachers to create lesson plans and assessments?',opts:['Zapier','MagicSchool AI','Grammarly','Otter.ai'],answer:1},resources:'MagicSchool AI (magicschool.ai) · Diffit (diffit.me) · Eduaide.Ai (eduaide.ai)'},
      {num:'03',title:'AI for Assessment & Student Feedback',dur:'9 min',mod:'Module 2 · Teaching',desc:'Generate quizzes, rubrics, and personalised feedback comments in minutes — not hours.',content:{points:['Create a 10-question quiz on any topic in under 3 minutes','Build a marking rubric with clear grade criteria automatically','Write personalised feedback for 30 students in the time it used to take for 5','Build a comment bank for report cards — never start from scratch again'],exercise:'Ask ChatGPT: "Create a 5-question quiz on [your current topic] for Year [X] students. Include an answer key. Mix multiple choice and short answer."'},quiz:{q:'How long should it take to create a 5-question quiz using AI?',opts:['45 minutes','3–5 minutes','1 hour','30 minutes'],answer:1},resources:'Diffit (diffit.me) · Brisk Teaching (briskteaching.com)'},
      {num:'04',title:'AI for School Administration',dur:'8 min',mod:'Module 3 · Administration',desc:'Draft newsletters, write policies, prepare meeting agendas, and handle parent communications in minutes.',content:{points:['Draft a parent newsletter in 10 minutes instead of 2 hours','Generate staff meeting agendas with time allocations automatically','Write new school policies from a brief description — review and customise','AI for sensitive parent communications — professional, empathetic templates'],exercise:'Ask ChatGPT: "Write a parent newsletter about our school Sports Day on [date]. Warm tone, under 300 words. Include date, what students need to bring, and contact for questions."'},quiz:{q:'What is a realistic time saving for writing a parent newsletter with AI?',opts:['5 minutes instead of 5 hours','10 minutes instead of 1–2 hours','It takes the same time','30 minutes instead of 30 minutes'],answer:1},resources:'Google Gemini in Google Docs · Gamma (gamma.app)'},
      {num:'05',title:'Teaching Students to Use AI Responsibly',dur:'10 min',mod:'Module 4 · Student Literacy',desc:'How to guide students toward AI as a thinking tool — and design assessments that AI cannot simply complete for them.',content:{points:['Age-appropriate AI literacy: different approaches for primary and secondary','How to detect AI-generated student work — and respond constructively','Design AI-resistant assessments: personal reflection, local context, oral components','The classroom conversation about academic integrity and AI'],exercise:'Redesign one upcoming assessment to require personal experience or local context that AI cannot fabricate. Share your redesigned assessment question in the alumni group.'},quiz:{q:'What type of assessment is hardest for AI to complete on behalf of a student?',opts:['Multiple choice tests','Questions requiring personal experience and local context','Short answer questions','Fill-in-the-blank exercises'],answer:1},resources:'SchoolAI (schoolai.com) · Your school AI use policy template in the Handbook'},
      {num:'06',title:'Building Your School AI Strategy',dur:'11 min',mod:'Module 5 · Strategy',desc:'Build a practical 90-day AI implementation plan for your school — achievable, budgeted, and staff-ready.',content:{points:['Conduct a staff AI skills audit in 15 minutes using a Google Form','Identify the top 3 administrative tasks consuming the most staff time','Create a school AI use policy — template provided in your handbook','Designate an AI Champion and set up a staff AI community of practice'],exercise:'Identify the 3 tasks in your school that consume the most non-teaching staff time each week. For each, identify one AI tool that could reduce that time by at least 50%.'},quiz:{q:'What is the first practical step for a school beginning its AI adoption journey?',opts:['Buy expensive AI software immediately','Conduct a staff AI skills audit and identify top time-consuming tasks','Wait for government guidelines','Replace all textbooks with AI tools'],answer:1},resources:'Full School AI Strategy framework in your Participant Handbook'},
    ]
  },
  corporate: {
    color: 'purple',
    lessons: [
      {num:'01',title:'AI Foundations for the Modern Workplace',dur:'9 min',mod:'Module 1 · Foundations',desc:'What AI means for your organisation right now — and why the next 12 months will separate AI-ready organisations from the rest.',content:{points:['The AI adoption gap in Africa — 80% of SMEs have not started','3 types of AI every organisation should deploy (Generative, Automation, Analytical)','The productivity maths: 2.5 hours saved per employee per day × your team size','How to approach AI adoption — people first, technology second'],exercise:'Calculate the productivity opportunity for your team: [number of staff] × 2.5 hours × [working days per month]. Share the number with your manager.'},quiz:{q:'How many hours per day do AI-trained employees typically save on routine tasks?',opts:['30 minutes','1 hour','2.5 hours','5 hours'],answer:2},resources:'ChatGPT (chatgpt.com) · Claude (claude.ai) · Microsoft Copilot (copilot.microsoft.com)'},
      {num:'02',title:'AI for Productivity & Communication',dur:'10 min',mod:'Module 2 · Productivity',desc:'Write reports and emails 5× faster, summarise any document in seconds, and use Microsoft Copilot inside Office 365.',content:{points:['The CRAFT formula for professional communication','Summarise a 40-page report into an executive brief in under 2 minutes','Use Microsoft Copilot inside Word, Excel, PowerPoint, and Outlook','Create meeting agendas, action items, and follow-up emails automatically'],exercise:'Take a report or document you wrote this week. Paste it into Claude or ChatGPT and ask: "Summarise this in an executive brief of under 200 words for a senior manager." Compare the result.'},quiz:{q:'Which Microsoft product integrates AI directly into Word, Excel, and Outlook?',opts:['Microsoft Azure','Microsoft Copilot','Microsoft Teams','Microsoft Access'],answer:1},resources:'Microsoft Copilot (copilot.microsoft.com) · Otter.ai (otter.ai) · Notion AI (notion.so)'},
      {num:'03',title:'AI for HR & People Operations',dur:'9 min',mod:'Module 3 · Departments',desc:'Write job descriptions in 4 minutes, screen CVs at scale, create onboarding packs, and draft HR policies automatically.',content:{points:['Write a complete job description from a 3-sentence brief — in under 4 minutes','CV screening prompt: paste a JD and CV and ask AI to rate the fit out of 10','Create a 90-day onboarding plan for any role automatically','Generate HR policies, employee handbooks, and performance review frameworks'],exercise:'Ask ChatGPT: "Write a job description for a [role] at a [type of organisation] in [city]. Include: role summary, 5 key responsibilities, 4 requirements, and application instructions."'},quiz:{q:'What is the fastest way to screen a job applicant using AI?',opts:['Upload a photo of the CV','Paste the job description and CV into AI and ask it to rate the fit','Ask AI to interview the candidate','Use AI to check their social media'],answer:1},resources:'ChatGPT (chatgpt.com) · Google Gemini (gemini.google.com)'},
      {num:'04',title:'AI for Marketing & Customer Service',dur:'10 min',mod:'Module 3 · Departments',desc:'Generate a month of social content in one session, build AI chatbot FAQs, and automate customer response workflows.',content:{points:['30 days of social media content — generated in 45 minutes','Write email marketing campaigns with AI — subject, body, CTA, and follow-up sequence','Build a customer service FAQ document — 50 questions answered in one session','Use Tidio or WhatsApp Business API to deploy an AI chatbot for your website'],exercise:'Ask ChatGPT: "Generate 10 social media post ideas for [your business type] targeting [your audience] in Nigeria/Ghana. Mix educational, promotional, and engagement content."'},quiz:{q:'How long does it typically take to generate 30 days of social media content using AI?',opts:['3 days','45 minutes to 1 hour','1 week','2 hours minimum'],answer:1},resources:'Canva AI (canva.com) · Copy.ai · Tidio (tidio.com)'},
      {num:'05',title:'AI for Finance & Operations',dur:'9 min',mod:'Module 3 · Departments',desc:'Write financial commentary in minutes, automate expense reporting, identify operational bottlenecks, and build KPI dashboards.',content:{points:['Write the narrative commentary for a board report from data in under 10 minutes','Automate expense categorisation and monthly reporting with Zapier integrations','Use AI to identify the top 3 operational bottlenecks in any process description','Build a KPI dashboard brief — tell AI your metrics, get a dashboard spec'],exercise:'Describe one recurring process in your operations to ChatGPT and ask: "Identify the 3 most likely bottlenecks in this process and suggest one AI solution for each."'},quiz:{q:'Which tool is best for automating workflows between business apps without coding?',opts:['PowerPoint','Zapier','Grammarly','Canva'],answer:1},resources:'Zapier (zapier.com) · Make (make.com) · Google Looker Studio'},
      {num:'06',title:'AI Strategy for Leaders & Managers',dur:'12 min',mod:'Module 4 · Leadership',desc:'Build your department\'s 90-day AI adoption roadmap, lead your team through change, and measure the return on your AI investment.',content:{points:['The 5-phase AI adoption framework: Awareness → Pilot → Embed → Scale → Lead','How to evaluate AI tools — the 5 questions every leader should ask before buying','Measuring AI ROI: time saved, output quality, error reduction, revenue impact','How to communicate AI change to your team — managing resistance and building buy-in'],exercise:'Complete the AI Adoption Audit: list your department\'s top 5 most repetitive processes, estimate hours per week spent on each, and identify the first one to pilot with AI.'},quiz:{q:'What is Phase 1 of the 3A AI Adoption Framework?',opts:['Scale','Pilot','Awareness','Embed'],answer:2},resources:'Full AI Strategy Framework in your Participant Handbook · 3A AI Solutions consulting services'},
    ]
  }
};

let currentTrack = 'individuals';
let currentLesson = 0;
let completedLessons = new Set();
let isPlaying = false;
let simTime = 0;
let simTimer = null;
let currentTab = 'notes';

// ── NAV SCROLL ─────────────────────────────────────────
window.addEventListener('scroll', () => {
  document.getElementById('mainNav').classList.toggle('scrolled', window.scrollY > 60);
}, {passive:true});

function scrollTo(id) { document.getElementById(id)?.scrollIntoView({behavior:'smooth'}); }
function closeMob() { document.getElementById('mobMenu').classList.remove('open'); }
function openTrack(t) { currentTrack=t; currentLesson=0; switchTrack(t,null); scrollTo('academy'); }

// ── COUNT UP ───────────────────────────────────────────
function countUp(el, target, suffix='') {
  let start; const dur=1600;
  const step=ts => { if(!start)start=ts; const p=Math.min((ts-start)/dur,1); el.textContent=Math.floor(p*target)+suffix; if(p<1)requestAnimationFrame(step); else el.textContent=target+suffix; };
  requestAnimationFrame(step);
}
const io = new IntersectionObserver(entries => { if(entries[0].isIntersecting){ countUp(document.getElementById('c1'),45);countUp(document.getElementById('c2'),15);countUp(document.getElementById('c3'),100,'%');countUp(document.getElementById('c4'),30); io.disconnect(); } },{threshold:.5});
io.observe(document.querySelector('.hero-stats'));

// ── REVEAL ─────────────────────────────────────────────
const revIO = new IntersectionObserver(entries=>entries.forEach(e=>{if(e.isIntersecting){e.target.classList.add('revealed');revIO.unobserve(e.target);}}),{threshold:.1});
document.querySelectorAll('.reveal').forEach(el=>revIO.observe(el));

// ── LESSON LIST ────────────────────────────────────────
function renderLessons() {
  const list = document.getElementById('lessonList');
  const lessons = courses[currentTrack].lessons;
  const col = courses[currentTrack].color;
  list.innerHTML = lessons.map((l,i) => `
    <div class="lesson-item ${i===currentLesson?('active'+(col==='gold'?'':'-'+col)):''}${completedLessons.has(currentTrack+'-'+i)?' done':''}" onclick="selectLesson(${i})">
      <div class="lesson-num ${completedLessons.has(currentTrack+'-'+i)?'done':col}">${completedLessons.has(currentTrack+'-'+i)?'✓':l.num}</div>
      <div class="lesson-info">
        <div class="lesson-title">${l.title}</div>
        <div class="lesson-dur">⏱ ${l.dur}</div>
      </div>
    </div>`).join('');
}

function switchTrack(t, btn) {
  currentTrack = t;
  currentLesson = 0;
  isPlaying = false;
  clearInterval(simTimer);
  // Update tab buttons
  document.querySelectorAll('.track-tab').forEach(b=>{
    const color = b.textContent.includes('👤')?'gold':b.textContent.includes('🏫')?'green':'purple';
    b.className = 'track-tab inactive-'+color;
  });
  if(btn){ const color = t==='individuals'?'gold':t==='schools'?'green':'purple'; btn.className='track-tab active-'+color; }
  else {
    // find the right button
    document.querySelectorAll('.track-tab').forEach(b=>{
      const matches = (t==='individuals'&&b.textContent.includes('👤'))||(t==='schools'&&b.textContent.includes('🏫'))||(t==='corporate'&&b.textContent.includes('🏢'));
      if(matches){const color=t==='individuals'?'gold':t==='schools'?'green':'purple';b.className='track-tab active-'+color;}
    });
  }
  renderLessons();
  loadLesson();
}

function selectLesson(i) {
  currentLesson = i;
  isPlaying = false;
  clearInterval(simTimer);
  simTime = 0;
  renderLessons();
  loadLesson();
}

function loadLesson() {
  const l = courses[currentTrack].lessons[currentLesson];
  const total = courses[currentTrack].lessons.length;
  // Reset player
  document.getElementById('vpContent').style.display = 'flex';
  document.getElementById('vpPlaying').style.display = 'none';
  document.getElementById('vpLessonNum').textContent = l.mod;
  document.getElementById('vpTitle').textContent = l.title;
  document.getElementById('vpSub').textContent = l.desc;
  document.getElementById('vpProgress').style.width = '0%';
  document.getElementById('vpPlayIcon').textContent = '▶';
  document.getElementById('vpTime').textContent = '0:00 / '+l.dur;
  document.getElementById('vpNotesTitle').textContent = l.title;
  document.getElementById('vpNotesDesc').textContent = l.desc;
  document.getElementById('vpResources').innerHTML = l.content.points.map(p=>`<div style="margin-bottom:.5rem;">• ${p}</div>`).join('')+'<br><strong style="color:var(--gold)">Tools:</strong> '+l.resources;
  // Lesson body
  const b = l.content;
  document.getElementById('vpLessonBody').innerHTML = `
    <div class="lesson-section-title">📌 Key Points</div>
    ${b.points.map(p=>`<div class="lesson-point"><span class="lesson-point-icon" style="color:var(--gold)">▸</span><span class="lesson-point-text">${p}</span></div>`).join('')}
    <div class="exercise-box">
      <div class="exercise-label">🎯 Hands-On Exercise</div>
      <div class="exercise-text">${b.exercise}</div>
    </div>`;
  // Quiz
  const q = l.quiz;
  document.getElementById('quizQuestion').textContent = q.q;
  document.getElementById('quizOpts').innerHTML = q.opts.map((o,i)=>`<button class="quiz-opt" onclick="answerQuiz(${i},${q.answer})">${o}</button>`).join('');
  document.getElementById('quizResult').className = 'quiz-result';
  document.getElementById('quizResult').textContent = '';
  // Progress
  const done = [...completedLessons].filter(k=>k.startsWith(currentTrack+'-')).length;
  document.getElementById('progressLabel').textContent = done+' / '+total+' lessons';
  document.getElementById('progressBar').style.width = (done/total*100)+'%';
  if(currentTab==='quiz'){ document.getElementById('tabQuiz').style.display='block'; document.getElementById('tabNotes').style.display='none'; document.getElementById('tabResources').style.display='none'; }
}

function playLesson() {
  document.getElementById('vpContent').style.display = 'none';
  document.getElementById('vpPlaying').style.display = 'block';
  isPlaying = true;
  document.getElementById('vpPlayIcon').textContent = '⏸';
  const dur = parseInt(courses[currentTrack].lessons[currentLesson].dur) * 60;
  simTime = 0;
  clearInterval(simTimer);
  simTimer = setInterval(()=>{
    simTime++;
    const pct = Math.min(simTime/dur*100,100);
    document.getElementById('vpProgress').style.width = pct+'%';
    const m=Math.floor(simTime/60), s=simTime%60;
    const dm=Math.floor(dur/60), ds=dur%60;
    document.getElementById('vpTime').textContent = `${m}:${s<10?'0':''}${s} / ${dm}:${ds<10?'0':''}${ds}`;
    if(simTime >= dur){ clearInterval(simTimer); completeLesson(); }
  }, 100); // Fast sim (100ms = 1 real second)
}

function togglePlay() {
  if(!isPlaying && document.getElementById('vpPlaying').style.display==='none') { playLesson(); return; }
  isPlaying = !isPlaying;
  if(isPlaying){ simTimer=setInterval(()=>{simTime++;},100); document.getElementById('vpPlayIcon').textContent='⏸'; }
  else{ clearInterval(simTimer); document.getElementById('vpPlayIcon').textContent='▶'; }
}

function toggleMute() {}

function seekLesson(e) {
  const rect = e.currentTarget.getBoundingClientRect();
  const pct = (e.clientX - rect.left) / rect.width;
  const dur = parseInt(courses[currentTrack].lessons[currentLesson].dur)*60;
  simTime = Math.floor(pct * dur);
  document.getElementById('vpProgress').style.width = (pct*100)+'%';
  if(document.getElementById('vpPlaying').style.display==='none'){
    document.getElementById('vpContent').style.display='none';
    document.getElementById('vpPlaying').style.display='block';
  }
}

function completeLesson() {
  completedLessons.add(currentTrack+'-'+currentLesson);
  isPlaying = false;
  document.getElementById('vpPlayIcon').textContent = '▶';
  renderLessons();
  loadLesson();
}

function prevLesson() {
  if(currentLesson > 0){ currentLesson--; clearInterval(simTimer); simTime=0; isPlaying=false; renderLessons(); loadLesson(); scrollTo('academy'); }
}

function nextLesson() {
  const total = courses[currentTrack].lessons.length;
  if(currentLesson < total-1){ completeLesson(); currentLesson++; clearInterval(simTimer); simTime=0; isPlaying=false; renderLessons(); loadLesson(); scrollTo('academy'); }
  else{ completeLesson(); }
}

function switchTab(tab, btn) {
  currentTab = tab;
  document.querySelectorAll('.vp-tab').forEach(b=>b.classList.remove('active'));
  if(btn) btn.classList.add('active');
  document.getElementById('tabNotes').style.display = tab==='notes'?'block':'none';
  document.getElementById('tabQuiz').style.display = tab==='quiz'?'block':'none';
  document.getElementById('tabResources').style.display = tab==='resources'?'block':'none';
}

function answerQuiz(chosen, correct) {
  const opts = document.querySelectorAll('.quiz-opt');
  opts.forEach((o,i)=>{ if(i===correct) o.classList.add('correct'); else if(i===chosen) o.classList.add('wrong'); o.disabled=true; });
  const res = document.getElementById('quizResult');
  res.className = 'quiz-result show '+(chosen===correct?'pass':'fail');
  if(chosen===correct){ res.textContent='✓ Correct! Great work. Move on to the next lesson.'; completeLesson(); }
  else res.textContent='✗ Not quite — review the lesson notes and try again.';
}

// ── FORM ───────────────────────────────────────────────
function submitForm(e) {
  e.preventDefault();
  document.getElementById('enrollForm').style.display = 'none';
  document.getElementById('successMsg').style.display = 'block';
}

// ── FAQ ────────────────────────────────────────────────
function toggleFaq(el) {
  const ans = el.nextElementSibling;
  const icon = el.querySelector('.faq-icon');
  const open = ans.classList.contains('open');
  document.querySelectorAll('.faq-a').forEach(a=>a.classList.remove('open'));
  document.querySelectorAll('.faq-icon').forEach(i=>i.classList.remove('open'));
  if(!open){ ans.classList.add('open'); icon.classList.add('open'); }
}

// ── CERT MODAL ─────────────────────────────────────────
function showCert() { document.getElementById('certModal').classList.add('open'); }
function closeCert() { document.getElementById('certModal').classList.remove('open'); }

// ── INIT ───────────────────────────────────────────────
renderLessons();
loadLesson();
</script>
</body>
</html>
