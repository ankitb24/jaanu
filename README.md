[ForYou.html](https://github.com/user-attachments/files/27319200/ForYou.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For You, Always 🐼</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400;1,600&family=Quicksand:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}

:root{
  --rose-deep:#c0435a;
  --rose-mid:#e07080;
  --rose-soft:#f2b8c0;
  --rose-pale:#fde8ed;
  --gold:#e8c88a;
  --gold-dark:#c9a55a;
  --cream:#fdf6f0;
  --dark:#1a0a0e;
  --dark2:#2d1520;
  --text:#3d1a22;
  --muted:#9b6b78;
  --white:#ffffff;
}

html{scroll-behavior:smooth}

body{
  font-family:'Quicksand',sans-serif;
  background:var(--dark);
  color:var(--white);
  overflow-x:hidden;
  cursor:none;
}

/* CUSTOM CURSOR */
.cursor{
  position:fixed;width:12px;height:12px;
  background:var(--rose-soft);border-radius:50%;
  pointer-events:none;z-index:9999;
  transform:translate(-50%,-50%);
  transition:transform 0.1s,width 0.3s,height 0.3s,opacity 0.3s;
  mix-blend-mode:screen;
}
.cursor-ring{
  position:fixed;width:36px;height:36px;
  border:1.5px solid rgba(240,184,192,0.5);
  border-radius:50%;pointer-events:none;z-index:9998;
  transform:translate(-50%,-50%);
  transition:transform 0.12s ease-out,width 0.3s,height 0.3s;
}

/* PARTICLE CANVAS */
#particleCanvas{
  position:fixed;inset:0;z-index:0;pointer-events:none;opacity:0.6;
}

/* NAV */
nav{
  position:fixed;top:0;left:0;right:0;z-index:100;
  padding:1.2rem 3rem;
  display:flex;align-items:center;justify-content:space-between;
  background:linear-gradient(to bottom,rgba(26,10,14,0.95),transparent);
}
.nav-logo{
  font-family:'Cormorant Garamond',serif;
  font-size:1.4rem;font-style:italic;
  color:var(--gold);letter-spacing:2px;
}
.nav-links{display:flex;gap:2rem}
.nav-links a{
  text-decoration:none;color:rgba(255,255,255,0.6);
  font-size:0.78rem;letter-spacing:2px;text-transform:uppercase;
  font-weight:500;transition:color 0.3s;
}
.nav-links a:hover{color:var(--gold)}

/* HERO */
.hero{
  min-height:100vh;display:flex;flex-direction:column;
  align-items:center;justify-content:center;
  text-align:center;padding:2rem;position:relative;overflow:hidden;
  background:
    radial-gradient(ellipse 80% 60% at 50% 0%,rgba(192,67,90,0.25) 0%,transparent 70%),
    radial-gradient(ellipse 60% 40% at 20% 80%,rgba(232,200,138,0.1) 0%,transparent 60%),
    var(--dark);
}

.hero-eyebrow{
  font-size:0.72rem;letter-spacing:5px;text-transform:uppercase;
  color:var(--gold);margin-bottom:2rem;
  animation:fadeUp 1s ease both;
  display:flex;align-items:center;gap:1rem;
}
.hero-eyebrow::before,.hero-eyebrow::after{
  content:'';display:block;width:40px;height:1px;background:var(--gold);opacity:0.5;
}

.hero h1{
  font-family:'Cormorant Garamond',serif;
  font-size:clamp(3.5rem,9vw,7.5rem);
  font-weight:300;line-height:1;
  letter-spacing:-1px;
  animation:fadeUp 1s 0.15s ease both;
}
.hero h1 em{
  font-style:italic;color:var(--rose-soft);
  display:block;font-size:1.1em;
}

.hero-panda{
  font-size:5rem;margin:2rem 0;
  display:block;
  animation:pandaFloat 3s ease-in-out infinite, fadeUp 1s 0.3s ease both;
  filter:drop-shadow(0 0 30px rgba(240,184,192,0.4));
}
@keyframes pandaFloat{
  0%,100%{transform:translateY(0) rotate(-3deg)}
  50%{transform:translateY(-18px) rotate(3deg)}
}

.hero-sub{
  font-size:clamp(1rem,2vw,1.2rem);
  color:rgba(255,255,255,0.5);
  font-weight:300;letter-spacing:1px;
  animation:fadeUp 1s 0.45s ease both;
  max-width:500px;margin:0 auto 3rem;
  line-height:1.8;
}

.hero-scroll{
  position:absolute;bottom:2.5rem;left:50%;transform:translateX(-50%);
  display:flex;flex-direction:column;align-items:center;gap:0.8rem;
  animation:fadeUp 1s 0.8s ease both;
  color:rgba(255,255,255,0.3);font-size:0.72rem;letter-spacing:3px;text-transform:uppercase;
}
.scroll-line{
  width:1px;height:50px;
  background:linear-gradient(to bottom,transparent,var(--rose-mid),transparent);
  animation:scrollPulse 2s ease-in-out infinite;
}
@keyframes scrollPulse{0%,100%{opacity:0.3;transform:scaleY(1)}50%{opacity:1;transform:scaleY(1.2)}}

@keyframes fadeUp{
  from{opacity:0;transform:translateY(30px)}
  to{opacity:1;transform:translateY(0)}
}

/* DIVIDER */
.divider{
  display:flex;align-items:center;gap:1.5rem;
  max-width:600px;margin:0 auto 3rem;
  opacity:0.3;
}
.divider::before,.divider::after{content:'';flex:1;height:1px;background:var(--rose-soft)}
.divider span{font-size:1rem;color:var(--rose-soft)}

/* SECTIONS */
.section{
  position:relative;z-index:1;
  padding:7rem 2rem;
}
.section-inner{max-width:1100px;margin:0 auto}

.section-eyebrow{
  font-size:0.7rem;letter-spacing:5px;text-transform:uppercase;
  color:var(--gold);margin-bottom:1rem;text-align:center;
}
.section-title{
  font-family:'Cormorant Garamond',serif;
  font-size:clamp(2.2rem,5vw,3.8rem);
  font-weight:300;text-align:center;
  line-height:1.15;margin-bottom:1rem;
}
.section-title em{font-style:italic;color:var(--rose-soft)}

/* MUSIC */
.music-section{
  background:
    radial-gradient(ellipse 70% 50% at 50% 50%,rgba(192,67,90,0.12) 0%,transparent 70%),
    var(--dark2);
}

.player-wrap{
  max-width:560px;margin:0 auto;
  background:rgba(255,255,255,0.03);
  border:1px solid rgba(240,184,192,0.12);
  border-radius:30px;padding:3rem;
  backdrop-filter:blur(20px);
  box-shadow:0 40px 80px rgba(0,0,0,0.4),inset 0 1px 0 rgba(255,255,255,0.05);
}

.player-panda{
  display:block;font-size:4rem;text-align:center;
  margin-bottom:1.5rem;
  transition:animation 0.3s;
  animation:pandaIdle 3s ease-in-out infinite;
}
.player-panda.grooving{animation:pandaGroove 0.4s ease-in-out infinite!important}
@keyframes pandaIdle{0%,100%{transform:rotate(-5deg)}50%{transform:rotate(5deg)}}
@keyframes pandaGroove{0%,100%{transform:rotate(-15deg) scale(1.1)}50%{transform:rotate(15deg) scale(0.9)}}

.song-info{text-align:center;margin-bottom:2rem}
.song-name{
  font-family:'Cormorant Garamond',serif;
  font-size:1.5rem;font-style:italic;color:var(--white);
  margin-bottom:0.3rem;white-space:nowrap;overflow:hidden;
  text-overflow:ellipsis;
}
.song-sub{font-size:0.8rem;color:var(--muted);letter-spacing:2px;text-transform:uppercase}

.upload-song{
  display:flex;align-items:center;justify-content:center;gap:0.6rem;
  width:100%;padding:0.9rem;border-radius:50px;
  background:linear-gradient(135deg,rgba(192,67,90,0.2),rgba(232,200,138,0.1));
  border:1px solid rgba(240,184,192,0.25);
  color:var(--rose-soft);font-family:'Quicksand',sans-serif;
  font-size:0.88rem;font-weight:600;letter-spacing:1px;
  cursor:pointer;transition:all 0.3s;margin-bottom:2rem;
}
.upload-song:hover{
  background:linear-gradient(135deg,rgba(192,67,90,0.35),rgba(232,200,138,0.15));
  border-color:rgba(240,184,192,0.5);transform:translateY(-2px);
}

.progress-wrap{
  background:rgba(255,255,255,0.06);border-radius:4px;height:4px;
  cursor:pointer;margin-bottom:0.8rem;position:relative;overflow:hidden;
}
.progress-fill{
  height:100%;border-radius:4px;width:0%;
  background:linear-gradient(90deg,var(--rose-deep),var(--rose-soft),var(--gold));
  transition:width 0.1s linear;
}
.time-row{
  display:flex;justify-content:space-between;
  font-size:0.72rem;color:var(--muted);margin-bottom:2rem;
}

.controls-row{
  display:flex;align-items:center;justify-content:center;gap:1.5rem;
}
.ctrl-btn{
  background:none;border:none;cursor:pointer;
  color:rgba(255,255,255,0.4);font-size:1.2rem;
  transition:all 0.2s;padding:0.5rem;
}
.ctrl-btn:hover{color:var(--rose-soft);transform:scale(1.15)}
.play-pause-btn{
  width:62px;height:62px;border-radius:50%;border:none;cursor:pointer;
  background:linear-gradient(135deg,var(--rose-deep),var(--rose-mid));
  color:#fff;font-size:1.4rem;
  display:flex;align-items:center;justify-content:center;
  box-shadow:0 8px 30px rgba(192,67,90,0.5);
  transition:all 0.3s;
}
.play-pause-btn:hover{transform:scale(1.08);box-shadow:0 12px 40px rgba(192,67,90,0.7)}

audio{display:none}

/* PHOTOS */
.photos-section{
  background:var(--dark);
}

.photo-grid{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:1rem;
  margin-bottom:2rem;
}
@media(max-width:700px){.photo-grid{grid-template-columns:repeat(2,1fr)}}
@media(max-width:440px){.photo-grid{grid-template-columns:1fr 1fr}}

.photo-slot{
  aspect-ratio:1;border-radius:20px;overflow:hidden;
  position:relative;cursor:pointer;
  border:1px solid rgba(240,184,192,0.1);
  background:rgba(255,255,255,0.03);
  transition:all 0.3s;
  display:flex;flex-direction:column;align-items:center;justify-content:center;
  gap:0.5rem;
}
.photo-slot:hover{
  border-color:rgba(240,184,192,0.3);
  transform:translateY(-4px) scale(1.02);
  box-shadow:0 20px 40px rgba(192,67,90,0.2);
}
.photo-slot img{
  position:absolute;inset:0;width:100%;height:100%;object-fit:cover;
}
.slot-icon{font-size:1.8rem;opacity:0.3}
.slot-text{font-size:0.72rem;color:var(--muted);letter-spacing:1px;text-transform:uppercase}

.photo-overlay{
  position:absolute;inset:0;
  background:linear-gradient(to top,rgba(26,10,14,0.85) 0%,transparent 50%);
  opacity:0;transition:opacity 0.3s;
  display:flex;align-items:flex-end;justify-content:space-between;
  padding:0.8rem;
}
.photo-slot:hover .photo-overlay{opacity:1}
.photo-caption-text{
  font-family:'Cormorant Garamond',serif;
  font-size:0.9rem;font-style:italic;color:rgba(255,255,255,0.9);
  flex:1;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;
}
.photo-del-btn{
  background:rgba(255,255,255,0.15);border:none;
  width:26px;height:26px;border-radius:50%;cursor:pointer;
  color:#fff;font-size:0.75rem;display:flex;align-items:center;justify-content:center;
  transition:all 0.2s;flex-shrink:0;margin-left:0.5rem;
}
.photo-del-btn:hover{background:var(--rose-deep)}

.add-photo-label{
  display:flex;align-items:center;justify-content:center;gap:0.6rem;
  margin:0 auto;
  padding:0.9rem 2.2rem;border-radius:50px;
  background:transparent;
  border:1px solid rgba(240,184,192,0.25);
  color:var(--rose-soft);font-family:'Quicksand',sans-serif;
  font-size:0.88rem;font-weight:600;letter-spacing:2px;text-transform:uppercase;
  cursor:pointer;transition:all 0.3s;width:fit-content;
}
.add-photo-label:hover{
  background:rgba(192,67,90,0.15);
  border-color:rgba(240,184,192,0.5);transform:translateY(-2px);
}

/* PANDAS */
.pandas-section{
  background:var(--dark2);
  overflow:hidden;
}
.panda-showcase{
  display:flex;gap:1.5rem;justify-content:center;flex-wrap:wrap;
  margin-bottom:3rem;
}
.panda-card{
  background:rgba(255,255,255,0.03);
  border:1px solid rgba(240,184,192,0.1);
  border-radius:24px;padding:2rem 1.5rem;
  text-align:center;min-width:130px;
  transition:all 0.4s cubic-bezier(0.34,1.56,0.64,1);
}
.panda-card:hover{
  background:rgba(192,67,90,0.08);
  border-color:rgba(240,184,192,0.3);
  transform:translateY(-10px) scale(1.05);
  box-shadow:0 24px 50px rgba(192,67,90,0.2);
}
.panda-emoji{font-size:3rem;display:block;margin-bottom:0.6rem}
.panda-lbl{
  font-family:'Cormorant Garamond',serif;
  font-size:0.9rem;font-style:italic;color:var(--muted);
}

.p-spin{animation:pSpin 3s ease-in-out infinite}
.p-wave{animation:pWave 1.5s ease-in-out infinite}
.p-bob{animation:pBob 2s ease-in-out infinite}
.p-shake{animation:pShake 0.7s ease-in-out infinite}
.p-float{animation:pFloat 3s ease-in-out infinite}
.p-spin2{animation:pSpin 2s linear infinite}
@keyframes pSpin{0%,100%{transform:rotate(-12deg) scale(1)}50%{transform:rotate(12deg) scale(1.1)}}
@keyframes pWave{0%,100%{transform:rotate(0)}25%{transform:rotate(-22deg)}75%{transform:rotate(22deg)}}
@keyframes pBob{0%,100%{transform:translateY(0)}50%{transform:translateY(-14px)}}
@keyframes pShake{0%,100%{transform:translateX(0)}33%{transform:translateX(-6px)}66%{transform:translateX(6px)}}
@keyframes pFloat{0%,100%{transform:translateY(0) rotate(-5deg)}50%{transform:translateY(-14px) rotate(5deg)}}

.panda-gifs{
  display:flex;gap:1.5rem;justify-content:center;flex-wrap:wrap;
}
.panda-gif-card{
  background:rgba(255,255,255,0.03);
  border:1px solid rgba(240,184,192,0.1);
  border-radius:20px;overflow:hidden;
  transition:all 0.3s;width:170px;
}
.panda-gif-card:hover{
  transform:translateY(-6px);
  box-shadow:0 20px 40px rgba(192,67,90,0.25);
  border-color:rgba(240,184,192,0.3);
}
.panda-gif-card img{width:100%;height:130px;object-fit:cover;display:block}
.panda-gif-lbl{
  padding:0.7rem;text-align:center;
  font-family:'Cormorant Garamond',serif;
  font-style:italic;font-size:0.9rem;color:var(--muted);
}

/* HERO ORB */
.hero-orb{
  width:220px;height:220px;border-radius:50%;
  background:radial-gradient(circle at 35% 35%,rgba(240,184,192,0.18),rgba(192,67,90,0.08) 60%,transparent);
  border:1px solid rgba(240,184,192,0.15);
  margin:2rem auto;
  position:relative;
  animation:orbPulse 4s ease-in-out infinite, fadeUp 1s 0.3s ease both;
  box-shadow:0 0 80px rgba(192,67,90,0.12),inset 0 0 60px rgba(240,184,192,0.06);
}
.hero-orb::before{
  content:'✦';
  position:absolute;top:50%;left:50%;
  transform:translate(-50%,-50%);
  font-size:3rem;color:rgba(240,184,192,0.5);
  animation:orbSpin 8s linear infinite;
}
.hero-orb::after{
  content:'';
  position:absolute;inset:-20px;border-radius:50%;
  border:1px solid rgba(240,184,192,0.07);
  animation:orbSpin 12s linear infinite reverse;
}
@keyframes orbPulse{0%,100%{transform:scale(1);box-shadow:0 0 80px rgba(192,67,90,0.12)}50%{transform:scale(1.04);box-shadow:0 0 120px rgba(192,67,90,0.2)}}
@keyframes orbSpin{from{transform:translate(-50%,-50%) rotate(0deg)}to{transform:translate(-50%,-50%) rotate(360deg)}}

/* VINYL DISC */
.vinyl-disc{
  width:110px;height:110px;border-radius:50%;
  background:
    radial-gradient(circle at 50% 50%,#1a0a0e 0%,#1a0a0e 20%,transparent 21%),
    conic-gradient(from 0deg,#2a1218,#1a0a0e,#2a1218,#1a0a0e,#2a1218,#1a0a0e,#2a1218,#1a0a0e);
  border:3px solid rgba(240,184,192,0.15);
  margin:0 auto 1.5rem;
  display:flex;align-items:center;justify-content:center;
  position:relative;
  transition:animation 0.3s;
  box-shadow:0 8px 32px rgba(0,0,0,0.4);
}
.vinyl-disc.spinning{animation:vinylSpin 2s linear infinite}
@keyframes vinylSpin{from{transform:rotate(0deg)}to{transform:rotate(360deg)}}
.vinyl-inner{
  width:36px;height:36px;border-radius:50%;
  background:radial-gradient(circle,var(--rose-deep),var(--dark2));
  display:flex;align-items:center;justify-content:center;
  font-size:0.9rem;color:rgba(255,255,255,0.6);
  border:2px solid rgba(240,184,192,0.2);
  position:absolute;
}

/* QUOTES SECTION */
.quotes-section{
  background:
    radial-gradient(ellipse 60% 50% at 80% 20%,rgba(232,200,138,0.07) 0%,transparent 60%),
    var(--dark2);
}
.quotes-grid{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  grid-template-rows:auto auto;
  gap:1.2rem;
  max-width:1000px;margin:0 auto;
}
@media(max-width:800px){.quotes-grid{grid-template-columns:1fr 1fr}}
@media(max-width:500px){.quotes-grid{grid-template-columns:1fr}}

.quote-card{
  background:rgba(255,255,255,0.025);
  border:1px solid rgba(240,184,192,0.08);
  border-radius:20px;padding:2rem;
  position:relative;overflow:hidden;
  transition:all 0.4s;
}
.quote-card::after{
  content:'';position:absolute;
  top:0;left:0;right:0;height:1px;
  background:linear-gradient(90deg,transparent,rgba(240,184,192,0.3),transparent);
}
.quote-card:hover{
  border-color:rgba(240,184,192,0.2);
  transform:translateY(-5px);
  box-shadow:0 20px 50px rgba(0,0,0,0.3);
  background:rgba(255,255,255,0.04);
}
.quote-large{grid-column:span 2}
.quote-wide{grid-column:span 2}
@media(max-width:800px){.quote-large,.quote-wide{grid-column:span 1}}

.quote-mark{
  font-family:'Cormorant Garamond',serif;
  font-size:5rem;line-height:0.6;
  color:var(--rose-deep);opacity:0.4;
  margin-bottom:0.8rem;display:block;
}
.quote-text{
  font-family:'Cormorant Garamond',serif;
  font-size:1.15rem;font-style:italic;
  color:rgba(255,255,255,0.82);
  line-height:1.7;margin-bottom:1rem;
}
.quote-large .quote-text{font-size:1.3rem}
.quote-attr{
  font-size:0.72rem;letter-spacing:2px;
  text-transform:uppercase;color:var(--muted);
}

/* AESTHETIC SECTION */
.aesthetic-section{
  background:var(--dark);
}
.aesthetic-grid{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  grid-template-rows:200px 200px;
  gap:1rem;
  max-width:1000px;margin:0 auto;
}
@media(max-width:800px){
  .aesthetic-grid{grid-template-columns:repeat(2,1fr);grid-template-rows:repeat(4,160px)}
  .aes-tall{grid-row:span 1!important}
  .aes-wide{grid-column:span 2!important}
}
@media(max-width:480px){
  .aesthetic-grid{grid-template-columns:1fr 1fr;grid-template-rows:repeat(4,140px)}
}

.aes-card{
  border-radius:20px;overflow:hidden;
  display:flex;align-items:center;justify-content:center;
  cursor:default;position:relative;
  transition:all 0.4s cubic-bezier(0.34,1.2,0.64,1);
  border:1px solid rgba(255,255,255,0.05);
}
.aes-card:hover{transform:scale(1.03);box-shadow:0 24px 60px rgba(0,0,0,0.5);z-index:2}
.aes-tall{grid-row:span 2}
.aes-wide{grid-column:span 2}

.aes-gradient-1{background:linear-gradient(145deg,#0d0510,#2a0d1f,#0d0510)}
.aes-gradient-2{background:linear-gradient(145deg,#1a0e0a,#3d1f10,#1a0e0a)}
.aes-gradient-3{background:linear-gradient(145deg,#08090f,#1a1a2e,#08090f)}
.aes-gradient-4{background:linear-gradient(90deg,#1a0a0e,#2d0f1f,#1a0a1e,#2d0f1f,#1a0a0e)}
.aes-gradient-5{background:linear-gradient(145deg,#0f0a1a,#1e0f2e,#0f0a1a)}
.aes-gradient-6{background:linear-gradient(145deg,#0a0f0a,#0f2a1a,#0a0f0a)}
.aes-gradient-7{background:linear-gradient(145deg,#1a0a0e,#2d1520,#3d1a2a,#1a0a0e)}

.aes-inner{
  text-align:center;padding:1.5rem;
  position:relative;z-index:1;
}
.aes-symbol{
  font-size:3rem;
  font-family:'Cormorant Garamond',serif;
  color:rgba(240,184,192,0.35);
  display:block;margin-bottom:0.8rem;
  animation:symbolPulse 3s ease-in-out infinite;
  line-height:1;
}
.aes-tall .aes-symbol{font-size:4.5rem}
.aes-symbol-row{
  font-size:1.5rem;letter-spacing:8px;
  color:rgba(240,184,192,0.25);
  display:block;margin-bottom:0.8rem;
  animation:symbolPulse 3s ease-in-out infinite;
}
@keyframes symbolPulse{0%,100%{opacity:0.5;transform:scale(1)}50%{opacity:1;transform:scale(1.05)}}
.aes-label{
  font-family:'Cormorant Garamond',serif;
  font-style:italic;
  font-size:0.88rem;letter-spacing:2px;
  color:rgba(255,255,255,0.3);
  text-transform:lowercase;line-height:1.5;
}
.aes-tall .aes-label{font-size:1rem}

/* add glow overlays per card */
.aes-gradient-1::before{content:'';position:absolute;inset:0;background:radial-gradient(circle at 50% 40%,rgba(192,67,90,0.15),transparent 65%)}
.aes-gradient-2::before{content:'';position:absolute;inset:0;background:radial-gradient(circle at 50% 50%,rgba(232,200,138,0.12),transparent 65%)}
.aes-gradient-3::before{content:'';position:absolute;inset:0;background:radial-gradient(circle at 50% 50%,rgba(100,120,200,0.15),transparent 65%)}
.aes-gradient-4::before{content:'';position:absolute;inset:0;background:radial-gradient(ellipse at 50% 50%,rgba(192,67,90,0.12),transparent 65%)}
.aes-gradient-5::before{content:'';position:absolute;inset:0;background:radial-gradient(circle at 50% 50%,rgba(150,90,200,0.15),transparent 65%)}
.aes-gradient-6::before{content:'';position:absolute;inset:0;background:radial-gradient(circle at 50% 50%,rgba(90,180,130,0.1),transparent 65%)}
.aes-gradient-7::before{content:'';position:absolute;inset:0;background:radial-gradient(circle at 50% 30%,rgba(240,184,192,0.12),transparent 60%)}

/* FOOTER SYMBOL */
.footer-symbol{
  font-size:2.5rem;
  color:var(--rose-soft);opacity:0.4;
  display:block;margin-bottom:1rem;
  animation:symbolPulse 3s ease-in-out infinite;
}

/* ── keep old reason/panda CSS removed, patch cursor selector ── */

/* LOVE LETTER */
.letter-section{
  background:var(--dark2);
}
.letter-card{
  max-width:720px;margin:0 auto;
  background:rgba(255,255,255,0.025);
  border:1px solid rgba(240,184,192,0.12);
  border-radius:30px;padding:3.5rem;
  box-shadow:0 40px 80px rgba(0,0,0,0.3);
  position:relative;
}
.letter-card::before{
  content:'💌';
  position:absolute;top:-22px;left:50%;transform:translateX(-50%);
  font-size:2.5rem;filter:drop-shadow(0 4px 12px rgba(192,67,90,0.4));
}
.letter-header{
  font-family:'Cormorant Garamond',serif;
  font-size:1.15rem;font-style:italic;
  color:var(--rose-soft);margin-bottom:1.5rem;opacity:0.7;
}
.letter-textarea{
  width:100%;min-height:260px;
  background:transparent;border:none;
  font-family:'Cormorant Garamond',serif;
  font-size:1.2rem;line-height:1.9;
  color:rgba(255,255,255,0.85);
  resize:none;outline:none;
}
.letter-textarea::placeholder{
  color:rgba(255,255,255,0.15);
  font-style:italic;
}
.letter-divider{
  border:none;border-top:1px solid rgba(240,184,192,0.1);
  margin:1.5rem 0;
}
.letter-footer-row{
  display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:1rem;
}
.letter-sign{
  font-family:'Cormorant Garamond',serif;
  font-style:italic;font-size:1.05rem;
  color:var(--muted);
}
.save-btn{
  padding:0.75rem 1.8rem;border-radius:50px;border:none;
  background:linear-gradient(135deg,var(--rose-deep),var(--rose-mid));
  color:#fff;font-family:'Quicksand',sans-serif;
  font-weight:600;font-size:0.88rem;letter-spacing:1px;
  cursor:pointer;transition:all 0.3s;
  box-shadow:0 8px 24px rgba(192,67,90,0.35);
}
.save-btn:hover{transform:translateY(-2px);box-shadow:0 14px 32px rgba(192,67,90,0.5)}

/* COUNTDOWN */
.countdown-section{
  background:
    radial-gradient(ellipse 80% 50% at 50% 0%,rgba(192,67,90,0.15) 0%,transparent 70%),
    var(--dark);
  text-align:center;
}
.date-label-text{
  font-size:0.82rem;color:var(--muted);letter-spacing:2px;text-transform:uppercase;
  margin-bottom:1rem;display:block;
}
.date-input{
  background:rgba(255,255,255,0.04);
  border:1px solid rgba(240,184,192,0.2);
  border-radius:12px;padding:0.75rem 1.5rem;
  color:var(--white);font-family:'Quicksand',sans-serif;
  font-size:0.95rem;outline:none;
  color-scheme:dark;
  margin-bottom:3rem;
  transition:border-color 0.3s;
}
.date-input:focus{border-color:var(--rose-soft)}
.date-input::-webkit-calendar-picker-indicator{filter:invert(1) opacity(0.5)}

.countdown-grid{
  display:flex;gap:1.5rem;justify-content:center;flex-wrap:wrap;
}
.count-card{
  background:rgba(255,255,255,0.03);
  border:1px solid rgba(240,184,192,0.1);
  border-radius:24px;padding:2rem 2.5rem;
  min-width:130px;
  box-shadow:0 20px 40px rgba(0,0,0,0.2);
}
.count-number{
  font-family:'Cormorant Garamond',serif;
  font-size:3.5rem;font-weight:300;
  color:var(--rose-soft);display:block;
  line-height:1;margin-bottom:0.3rem;
}
.count-unit{
  font-size:0.68rem;letter-spacing:3px;
  text-transform:uppercase;color:var(--muted);
}

/* MODAL */
.modal-bg{
  position:fixed;inset:0;
  background:rgba(10,0,5,0.75);
  backdrop-filter:blur(8px);
  z-index:500;display:none;
  align-items:center;justify-content:center;
}
.modal-bg.open{display:flex}
.modal-box{
  background:var(--dark2);
  border:1px solid rgba(240,184,192,0.15);
  border-radius:24px;padding:2.5rem;
  width:90%;max-width:400px;
  box-shadow:0 40px 80px rgba(0,0,0,0.5);
  animation:modalIn 0.35s cubic-bezier(0.34,1.56,0.64,1);
}
@keyframes modalIn{from{opacity:0;transform:scale(0.85)}to{opacity:1;transform:scale(1)}}
.modal-title{
  font-family:'Cormorant Garamond',serif;
  font-size:1.6rem;font-style:italic;
  color:var(--rose-soft);margin-bottom:0.5rem;text-align:center;
}
.modal-sub{font-size:0.8rem;color:var(--muted);text-align:center;margin-bottom:1.5rem}
.modal-input{
  width:100%;background:rgba(255,255,255,0.04);
  border:1px solid rgba(240,184,192,0.2);
  border-radius:12px;padding:0.85rem 1rem;
  color:var(--white);font-family:'Cormorant Garamond',serif;
  font-size:1.1rem;font-style:italic;
  outline:none;margin-bottom:1.2rem;
  transition:border-color 0.3s;
}
.modal-input:focus{border-color:var(--rose-soft)}
.modal-input::placeholder{color:rgba(255,255,255,0.2)}
.modal-btns{display:flex;gap:0.8rem}
.modal-btn{
  flex:1;padding:0.8rem;border-radius:50px;
  font-family:'Quicksand',sans-serif;font-weight:600;
  font-size:0.88rem;cursor:pointer;transition:all 0.25s;border:none;
}
.modal-ok{
  background:linear-gradient(135deg,var(--rose-deep),var(--rose-mid));
  color:#fff;box-shadow:0 6px 20px rgba(192,67,90,0.35);
}
.modal-ok:hover{transform:translateY(-2px);box-shadow:0 10px 28px rgba(192,67,90,0.5)}
.modal-skip{
  background:rgba(255,255,255,0.05);
  border:1px solid rgba(255,255,255,0.1);
  color:var(--muted);
}
.modal-skip:hover{background:rgba(255,255,255,0.08)}

/* TOAST */
.toast{
  position:fixed;bottom:2rem;left:50%;
  transform:translateX(-50%) translateY(100px);
  background:linear-gradient(135deg,var(--rose-deep),var(--rose-mid));
  color:#fff;padding:0.85rem 2rem;border-radius:50px;
  font-size:0.88rem;font-weight:600;letter-spacing:0.5px;
  z-index:1000;white-space:nowrap;
  box-shadow:0 12px 32px rgba(192,67,90,0.4);
  transition:transform 0.4s cubic-bezier(0.34,1.56,0.64,1),opacity 0.4s;
  opacity:0;
}
.toast.show{transform:translateX(-50%) translateY(0);opacity:1}

/* FOOTER */
footer{
  position:relative;z-index:1;
  background:var(--dark2);
  padding:4rem 2rem;text-align:center;
  border-top:1px solid rgba(240,184,192,0.08);
}
.footer-panda{
  font-size:3.5rem;display:block;margin-bottom:1rem;
  animation:pandaFloat 3s ease-in-out infinite;
}
.footer-title{
  font-family:'Cormorant Garamond',serif;
  font-size:2rem;font-style:italic;
  color:var(--rose-soft);margin-bottom:0.5rem;
}
.footer-sub{font-size:0.82rem;color:var(--muted);letter-spacing:1px}

/* SCROLLBAR */
::-webkit-scrollbar{width:4px}
::-webkit-scrollbar-track{background:var(--dark)}
::-webkit-scrollbar-thumb{background:var(--rose-deep);border-radius:2px}

/* RESPONSIVE */
@media(max-width:768px){
  nav{padding:1rem 1.5rem}
  .nav-links{display:none}
  .section{padding:5rem 1.2rem}
  .letter-card{padding:2.5rem 1.5rem}
  .player-wrap{padding:2rem 1.5rem}
  .count-card{padding:1.5rem}
  .count-number{font-size:2.8rem}
}
</style>
</head>
<body>

<!-- Custom cursor -->
<div class="cursor" id="cursor"></div>
<div class="cursor-ring" id="cursorRing"></div>

<!-- Particle canvas -->
<canvas id="particleCanvas"></canvas>

<!-- NAV -->
<nav>
  <div class="nav-logo">For You, Always</div>
  <div class="nav-links">
    <a href="#music">Our Song</a>
    <a href="#photos">Memories</a>
    <a href="#vibes">Quotes</a>
    <a href="#aesthetic">Aesthetic</a>
    <a href="#letter">Letter</a>
    <a href="#time">Time</a>
  </div>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-eyebrow">made with love</div>
  <h1>My Heart<em>Belongs to You</em></h1>
  <div class="hero-orb"></div>
  <p class="hero-sub">A little corner of the internet, built just for you — because you deserve the whole world, but I'll start with this.</p>
  <div class="hero-scroll">
    <span>scroll</span>
    <div class="scroll-line"></div>
  </div>
</section>

<!-- ══ MUSIC ══ -->
<section class="section music-section" id="music">
  <div class="section-inner">
    <div class="section-eyebrow">our soundtrack</div>
    <div class="section-title">The Song That's <em>Always You</em></div>
    <br><br>
    <div class="player-wrap">
      <div class="vinyl-disc" id="vinylDisc">
        <div class="vinyl-inner">♪</div>
      </div>

      <div class="song-info">
        <div class="song-name" id="songName">Upload your special song</div>
        <div class="song-sub" id="songSub">the one that makes you think of her</div>
      </div>

      <label class="upload-song">
        ♪ &nbsp; Choose a Song
        <input type="file" accept="audio/*" id="songFileInput" style="display:none" onchange="handleSongUpload(this)">
      </label>

      <audio id="audio"></audio>

      <div class="progress-wrap" id="progressWrap" onclick="seekTo(event)">
        <div class="progress-fill" id="progressFill"></div>
      </div>
      <div class="time-row">
        <span id="curTime">0:00</span>
        <span id="durTime">0:00</span>
      </div>

      <div class="controls-row">
        <button class="ctrl-btn" onclick="skipBack()" title="Rewind 10s">⏮</button>
        <button class="play-pause-btn" id="playPauseBtn" onclick="togglePlay()">▶</button>
        <button class="ctrl-btn" onclick="skipForward()" title="Forward 10s">⏭</button>
      </div>
    </div>
  </div>
</section>

<!-- ══ PHOTOS ══ -->
<section class="section photos-section" id="photos">
  <div class="section-inner">
    <div class="section-eyebrow">our story</div>
    <div class="section-title"><em>Moments</em> I Treasure</div>
    <br><br>
    <div class="photo-grid" id="photoGrid"></div>
    <div style="display:flex;justify-content:center">
      <label class="add-photo-label">
        + &nbsp; Add a Memory
        <input type="file" accept="image/*" id="photoInput" style="display:none" onchange="handlePhotoUpload(this)">
      </label>
    </div>
  </div>
</section>

<!-- ══ QUOTES ══ -->
<section class="section quotes-section" id="vibes">
  <div class="section-inner">
    <div class="section-eyebrow">written in the stars</div>
    <div class="section-title">Words That Feel <em>Like Us</em></div>
    <br><br>
    <div class="quotes-grid">
      <div class="quote-card quote-large">
        <div class="quote-mark">"</div>
        <div class="quote-text">I have waited for this day so long that I had forgotten what I was waiting for — and then you happened.</div>
        <div class="quote-attr">— Atticus</div>
      </div>
      <div class="quote-card">
        <div class="quote-mark">"</div>
        <div class="quote-text">You are my today and all of my tomorrows.</div>
        <div class="quote-attr">— Leo Christopher</div>
      </div>
      <div class="quote-card">
        <div class="quote-mark">"</div>
        <div class="quote-text">In a sea of people, my eyes will always search for you.</div>
        <div class="quote-attr">— Unknown</div>
      </div>
      <div class="quote-card quote-wide">
        <div class="quote-mark">"</div>
        <div class="quote-text">Whatever our souls are made of, yours and mine are the same.</div>
        <div class="quote-attr">— Emily Brontë</div>
      </div>
      <div class="quote-card">
        <div class="quote-mark">"</div>
        <div class="quote-text">She was chaos and beauty intertwined — a tornado of roses from the divine.</div>
        <div class="quote-attr">— Shakieb Orgunwall</div>
      </div>
      <div class="quote-card">
        <div class="quote-mark">"</div>
        <div class="quote-text">I look at you and I'm home. There is no more searching.</div>
        <div class="quote-attr">— Finding Nemo</div>
      </div>
    </div>
  </div>
</section>

<!-- ══ AESTHETIC GALLERY ══ -->
<section class="section aesthetic-section" id="aesthetic">
  <div class="section-inner">
    <div class="section-eyebrow">our universe</div>
    <div class="section-title">The <em>Feeling</em> of You</div>
    <br><br>
    <div class="aesthetic-grid">
      <div class="aes-card aes-tall aes-gradient-1">
        <div class="aes-inner">
          <div class="aes-symbol">✦</div>
          <div class="aes-label">late nights</div>
        </div>
      </div>
      <div class="aes-card aes-gradient-2">
        <div class="aes-inner">
          <div class="aes-symbol">◯</div>
          <div class="aes-label">golden hour</div>
        </div>
      </div>
      <div class="aes-card aes-gradient-3">
        <div class="aes-inner">
          <div class="aes-symbol">☽</div>
          <div class="aes-label">moonlight</div>
        </div>
      </div>
      <div class="aes-card aes-wide aes-gradient-4">
        <div class="aes-inner">
          <div class="aes-symbol-row">✦ · ✦ · ✦</div>
          <div class="aes-label">every moment with you</div>
        </div>
      </div>
      <div class="aes-card aes-gradient-5">
        <div class="aes-inner">
          <div class="aes-symbol">♡</div>
          <div class="aes-label">heartbeats</div>
        </div>
      </div>
      <div class="aes-card aes-gradient-6">
        <div class="aes-inner">
          <div class="aes-symbol">∞</div>
          <div class="aes-label">forever</div>
        </div>
      </div>
      <div class="aes-card aes-tall aes-gradient-7">
        <div class="aes-inner">
          <div class="aes-symbol">★</div>
          <div class="aes-label">you are my<br>favourite star</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ══ LETTER ══ -->
<section class="section letter-section" id="letter">
  <div class="section-inner">
    <div class="section-eyebrow">just for her</div>
    <div class="section-title">A Letter <em>From Me</em></div>
    <br><br>
    <div class="letter-card">
      <div class="letter-header">Dear my love,</div>
      <textarea class="letter-textarea" id="letterTextarea"
        placeholder="Write everything you feel... every word here is just for her. Let your heart speak freely — she deserves to hear it all."></textarea>
      <hr class="letter-divider">
      <div class="letter-footer-row">
        <div class="letter-sign">Yours, always &amp; forever ✦</div>
        <button class="save-btn" onclick="saveLetter()">Save Letter 💾</button>
      </div>
    </div>
  </div>
</section>

<!-- ══ COUNTDOWN ══ -->
<section class="section countdown-section" id="time">
  <div class="section-inner">
    <div class="section-eyebrow">counting every second</div>
    <div class="section-title"><em>Together</em> Since</div>
    <br>
    <span class="date-label-text">Enter the day your love story began</span>
    <br>
    <input type="date" class="date-input" id="dateInput" onchange="onDateChange()">
    <div class="countdown-grid">
      <div class="count-card"><span class="count-number" id="cDays">0</span><span class="count-unit">Days</span></div>
      <div class="count-card"><span class="count-number" id="cHours">0</span><span class="count-unit">Hours</span></div>
      <div class="count-card"><span class="count-number" id="cMins">0</span><span class="count-unit">Minutes</span></div>
      <div class="count-card"><span class="count-number" id="cSecs">0</span><span class="count-unit">Seconds</span></div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-symbol">✦</div>
  <div class="footer-title">Made with every piece of my heart</div>
  <div class="footer-sub">For you — today, tomorrow, and always</div>
</footer>

<!-- Caption Modal -->
<div class="modal-bg" id="captionModal">
  <div class="modal-box">
    <div class="modal-title">Add a caption</div>
    <div class="modal-sub">Give this memory a name 🌸</div>
    <input class="modal-input" id="captionInput" placeholder="e.g. Our first date…" maxlength="50">
    <div class="modal-btns">
      <button class="modal-btn modal-skip" onclick="confirmCaption(false)">Skip</button>
      <button class="modal-btn modal-ok" onclick="confirmCaption(true)">Add ✓</button>
    </div>
  </div>
</div>

<!-- Toast -->
<div class="toast" id="toast"></div>

<script>
// ── CURSOR ──
const cursor = document.getElementById('cursor');
const ring   = document.getElementById('cursorRing');
let mx=0,my=0,rx=0,ry=0;
document.addEventListener('mousemove', e=>{
  mx=e.clientX; my=e.clientY;
  cursor.style.left=mx+'px'; cursor.style.top=my+'px';
});
(function animRing(){
  rx+=(mx-rx)*0.12; ry+=(my-ry)*0.12;
  ring.style.left=rx+'px'; ring.style.top=ry+'px';
  requestAnimationFrame(animRing);
})();
document.querySelectorAll('button,a,label,.quote-card,.aes-card,.photo-slot,.count-card').forEach(el=>{
  el.addEventListener('mouseenter',()=>{cursor.style.transform='translate(-50%,-50%) scale(2.5)';ring.style.transform='translate(-50%,-50%) scale(1.5)'});
  el.addEventListener('mouseleave',()=>{cursor.style.transform='translate(-50%,-50%) scale(1)';ring.style.transform='translate(-50%,-50%) scale(1)'});
});

// ── PARTICLES ──
const canvas=document.getElementById('particleCanvas');
const ctx=canvas.getContext('2d');
let W,H,particles=[];
function resizeCanvas(){W=canvas.width=window.innerWidth;H=canvas.height=window.innerHeight}
resizeCanvas();
window.addEventListener('resize',resizeCanvas);
const emojis=['✦','·','✧','◦','⭑','✶','·','✦','◯','☽'];
class Particle{
  constructor(){this.reset(true)}
  reset(init){
    this.x=Math.random()*W;
    this.y=init?Math.random()*H:H+20;
    this.size=10+Math.random()*14;
    this.speed=0.4+Math.random()*0.6;
    this.emo=emojis[Math.floor(Math.random()*emojis.length)];
    this.alpha=0.15+Math.random()*0.35;
    this.drift=(Math.random()-0.5)*0.5;
    this.rot=Math.random()*Math.PI*2;
    this.rotSpeed=(Math.random()-0.5)*0.02;
  }
  update(){
    this.y-=this.speed;this.x+=this.drift;
    this.rot+=this.rotSpeed;
    if(this.y<-30)this.reset(false);
  }
  draw(){
    ctx.save();
    ctx.globalAlpha=this.alpha;
    ctx.font=this.size+'px serif';
    ctx.translate(this.x,this.y);
    ctx.rotate(this.rot);
    ctx.fillText(this.emo,-this.size/2,-this.size/2);
    ctx.restore();
  }
}
for(let i=0;i<30;i++)particles.push(new Particle());
(function animParticles(){
  ctx.clearRect(0,0,W,H);
  particles.forEach(p=>{p.update();p.draw()});
  requestAnimationFrame(animParticles);
})();

// ── MUSIC PLAYER ──
const audio=document.getElementById('audio');
const vinyl=document.getElementById('vinylDisc');
const playBtn=document.getElementById('playPauseBtn');
const prog=document.getElementById('progressFill');
const curTimeEl=document.getElementById('curTime');
const durTimeEl=document.getElementById('durTime');
let playing=false;

function handleSongUpload(input){
  const f=input.files[0];if(!f)return;
  const url=URL.createObjectURL(f);
  audio.src=url;audio.load();
  let name=f.name.replace(/\.[^.]+$/,'');
  if(name.length>40)name=name.slice(0,40)+'…';
  document.getElementById('songName').textContent=name;
  document.getElementById('songSub').textContent='your special song 🎶';
  input.value='';
  showToast('♪ Song loaded — hit play');
}

function togglePlay(){
  if(!audio.src){showToast('♪ Upload a song first');return;}
  if(playing){audio.pause();playBtn.textContent='▶';vinyl.classList.remove('spinning');playing=false;}
  else{audio.play();playBtn.textContent='⏸';vinyl.classList.add('spinning');playing=true;}
}

function skipBack(){if(audio.src){audio.currentTime=Math.max(0,audio.currentTime-10);}}
function skipForward(){if(audio.src){audio.currentTime=Math.min(audio.duration||0,audio.currentTime+10);}}

function fmtTime(s){
  if(!s||isNaN(s))return'0:00';
  const m=Math.floor(s/60),sec=Math.floor(s%60);
  return m+':'+(sec<10?'0':'')+sec;
}

audio.addEventListener('timeupdate',()=>{
  if(!audio.duration)return;
  prog.style.width=(audio.currentTime/audio.duration*100)+'%';
  curTimeEl.textContent=fmtTime(audio.currentTime);
  durTimeEl.textContent=fmtTime(audio.duration);
});
audio.addEventListener('ended',()=>{playBtn.textContent='▶';vinyl.classList.remove('spinning');playing=false;prog.style.width='0%';});
audio.addEventListener('loadedmetadata',()=>{durTimeEl.textContent=fmtTime(audio.duration);});

function seekTo(e){
  if(!audio.duration)return;
  const bar=document.getElementById('progressWrap');
  const rect=bar.getBoundingClientRect();
  const pct=(e.clientX-rect.left)/rect.width;
  audio.currentTime=Math.max(0,Math.min(audio.duration,pct*audio.duration));
}

// ── PHOTOS ──
let photos=[]; // {url,caption}
let pendingUrl=null;

function renderPhotos(){
  const grid=document.getElementById('photoGrid');
  const slots=Math.max(6,photos.length+2);
  let html='';
  for(let i=0;i<slots;i++){
    if(photos[i]){
      html+=`<div class="photo-slot" style="cursor:default">
        <img src="${photos[i].url}" alt="memory">
        <div class="photo-overlay">
          <div class="photo-caption-text">${photos[i].caption||''}</div>
          <button class="photo-del-btn" onclick="removePhoto(${i},event)" title="Remove">✕</button>
        </div>
      </div>`;
    } else {
      html+=`<div class="photo-slot" onclick="document.getElementById('photoInput').click()">
        <div class="slot-icon">📷</div>
        <div class="slot-text">Add memory</div>
      </div>`;
    }
  }
  grid.innerHTML=html;
}

function handlePhotoUpload(input){
  const f=input.files[0];if(!f)return;
  pendingUrl=URL.createObjectURL(f);
  input.value='';
  document.getElementById('captionInput').value='';
  document.getElementById('captionModal').classList.add('open');
  setTimeout(()=>document.getElementById('captionInput').focus(),100);
}

function confirmCaption(useCaption){
  const cap=useCaption?document.getElementById('captionInput').value.trim():'';
  if(pendingUrl){photos.push({url:pendingUrl,caption:cap});pendingUrl=null;renderPhotos();showToast(cap?'📸 Memory saved! 💕':'📸 Photo added!');}
  document.getElementById('captionModal').classList.remove('open');
}

function removePhoto(i,e){
  e.stopPropagation();photos.splice(i,1);renderPhotos();showToast('Photo removed.');
}

document.getElementById('captionInput').addEventListener('keydown',e=>{
  if(e.key==='Enter'){e.preventDefault();confirmCaption(true);}
  if(e.key==='Escape'){e.preventDefault();confirmCaption(false);}
});

document.getElementById('captionModal').addEventListener('click',e=>{
  if(e.target===document.getElementById('captionModal'))confirmCaption(false);
});

renderPhotos();

// ── LETTER ──
const saved=localStorage.getItem('lv_letter');
if(saved)document.getElementById('letterTextarea').value=saved;
function saveLetter(){
  const t=document.getElementById('letterTextarea').value;
  localStorage.setItem('lv_letter',t);
  showToast('💌 Letter saved with love 🐼');
}

// ── COUNTDOWN ──
const savedDate=localStorage.getItem('lv_date');
if(savedDate){document.getElementById('dateInput').value=savedDate;tick();}
function onDateChange(){
  const v=document.getElementById('dateInput').value;
  if(v)localStorage.setItem('lv_date',v);
  tick();
}
function tick(){
  const v=document.getElementById('dateInput').value;
  if(!v)return;
  const start=new Date(v),now=new Date();
  const diff=now-start;
  if(diff<0){['cDays','cHours','cMins','cSecs'].forEach(id=>document.getElementById(id).textContent='?');return;}
  document.getElementById('cDays').textContent=Math.floor(diff/86400000);
  document.getElementById('cHours').textContent=Math.floor(diff%86400000/3600000);
  document.getElementById('cMins').textContent=Math.floor(diff%3600000/60000);
  document.getElementById('cSecs').textContent=Math.floor(diff%60000/1000);
}
setInterval(tick,1000);

// ── TOAST ──
function showToast(msg){
  const t=document.getElementById('toast');
  t.textContent=msg;t.classList.add('show');
  clearTimeout(t._t);t._t=setTimeout(()=>t.classList.remove('show'),3000);
}
</script>
</body>
</html>
