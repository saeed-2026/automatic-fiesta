[adwaa-premium 3.html](https://github.com/user-attachments/files/25753162/adwaa-premium.3.html)
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>الأضواء Pro — أداة المليون مشاهدة</title>
<link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600;700;900&family=Tajawal:wght@300;400;500;700;800;900&display=swap" rel="stylesheet">
<style>
*{margin:0;padding:0;box-sizing:border-box;}

:root{
  --bg:#04040a;
  --bg2:#070710;
  --card:rgba(12,12,28,0.85);
  --card2:rgba(18,18,38,0.9);
  --border:rgba(255,200,50,0.12);
  --border2:rgba(255,200,50,0.25);
  --gold:#ffc832;
  --gold2:#ff9500;
  --gold3:#ffe080;
  --gold-glow:rgba(255,200,50,0.35);
  --snap:#FFFC00;
  --red:#ff3366;
  --green:#00f5a0;
  --blue:#0099ff;
  --purple:#a855f7;
  --cyan:#00e5ff;
  --text:#f0f0fc;
  --text2:#8888aa;
  --text3:#44445a;
  --r:18px;
  --r2:26px;
  --shadow:0 25px 60px rgba(0,0,0,0.7);
}

html{scroll-behavior:smooth;}

body{
  font-family:'Cairo',sans-serif;
  background:var(--bg);
  color:var(--text);
  min-height:100vh;
  overflow-x:hidden;
  cursor:default;
}

/* ===== ANIMATED BG ===== */
.bg-canvas{
  position:fixed;inset:0;z-index:-1;pointer-events:none;pointer-events:none;
  background:
    radial-gradient(ellipse 80% 60% at 20% 10%, rgba(255,150,0,0.07) 0%, transparent 60%),
    radial-gradient(ellipse 60% 80% at 80% 90%, rgba(168,85,247,0.06) 0%, transparent 60%),
    radial-gradient(ellipse 100% 50% at 50% 50%, rgba(0,229,255,0.03) 0%, transparent 70%),
    #04040a;
}

.bg-orb{
  position:fixed;border-radius:50%;filter:blur(80px);
  animation:orbFloat 8s ease-in-out infinite;pointer-events:none;z-index:-1;
}
.bg-orb1{width:500px;height:500px;background:radial-gradient(circle,rgba(255,165,0,0.08),transparent 70%);top:-150px;right:-150px;animation-delay:0s;}
.bg-orb2{width:400px;height:400px;background:radial-gradient(circle,rgba(168,85,247,0.07),transparent 70%);bottom:-100px;left:-100px;animation-delay:-4s;}
.bg-orb3{width:300px;height:300px;background:radial-gradient(circle,rgba(0,229,255,0.05),transparent 70%);top:50%;left:50%;transform:translate(-50%,-50%);animation-delay:-2s;}

@keyframes orbFloat{0%,100%{transform:translate(0,0) scale(1);}33%{transform:translate(30px,-20px) scale(1.05);}66%{transform:translate(-20px,30px) scale(0.95);}}

/* grid overlay */
.bg-grid{
  position:fixed;inset:0;z-index:-1;pointer-events:none;pointer-events:none;
  background-image:
    linear-gradient(rgba(255,200,50,0.03) 1px,transparent 1px),
    linear-gradient(90deg,rgba(255,200,50,0.03) 1px,transparent 1px);
  background-size:60px 60px;
  mask-image:radial-gradient(ellipse 80% 80% at 50% 50%,black 40%,transparent 100%);
}

/* noise */
.bg-noise{
  position:fixed;inset:0;z-index:-1;opacity:0.025;pointer-events:none;
  background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)'/%3E%3C/svg%3E");
  pointer-events:none;
}

/* ===== Z LAYOUT ===== */


/* ===== LOGIN ===== */
#loginScreen{
  position:relative;z-index:10;
  min-height:100vh;display:flex;align-items:center;justify-content:center;
  flex-direction:column;gap:0;
  transition:opacity 0.7s ease,transform 0.7s ease;
}

.login-hero{
  text-align:center;margin-bottom:48px;
  animation:heroIn 1s cubic-bezier(0.34,1.56,0.64,1) both;
}

@keyframes heroIn{from{opacity:0;transform:translateY(40px);}to{opacity:1;transform:translateY(0);}}

.login-logo-wrap{
  position:relative;display:inline-block;margin-bottom:24px;
}

.login-logo-ring{
  width:100px;height:100px;
  border-radius:50%;
  background:conic-gradient(from 0deg,var(--gold),var(--gold2),var(--purple),var(--cyan),var(--gold));
  padding:3px;
  animation:spinRing 4s linear infinite;
  box-shadow:0 0 60px rgba(255,200,50,0.3),0 0 120px rgba(255,200,50,0.1);
}

@keyframes spinRing{to{transform:rotate(360deg);}}

.login-logo-inner{
  width:100%;height:100%;border-radius:50%;
  background:var(--bg2);
  display:flex;align-items:center;justify-content:center;
  font-size:44px;
}

.login-title{
  font-family:'Tajawal',sans-serif;
  font-size:42px;font-weight:900;
  background:linear-gradient(135deg,var(--gold3) 0%,var(--gold) 40%,var(--gold2) 80%,#ff6600 100%);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
  background-clip:text;
  line-height:1.1;
  filter:drop-shadow(0 0 30px rgba(255,200,50,0.4));
}

.login-sub{
  color:var(--text2);font-size:15px;margin-top:8px;
  letter-spacing:0.5px;
}

.login-box{
  width:360px;
  background:var(--card2);
  border:1px solid var(--border2);
  border-radius:var(--r2);
  padding:36px 32px;
  box-shadow:var(--shadow),0 0 80px rgba(255,200,50,0.08),inset 0 1px 0 rgba(255,255,255,0.05);
  backdrop-filter:blur(30px);
  animation:boxIn 1s 0.2s cubic-bezier(0.34,1.56,0.64,1) both;
}

@keyframes boxIn{from{opacity:0;transform:translateY(30px) scale(0.95);}to{opacity:1;transform:translateY(0) scale(1);}}

.field-label{
  font-size:12px;font-weight:700;
  color:var(--text2);letter-spacing:1.5px;
  text-transform:uppercase;margin-bottom:10px;
}

.field-wrap{position:relative;}

.field-input{
  width:100%;
  background:rgba(255,255,255,0.04);
  border:1px solid rgba(255,200,50,0.15);
  border-radius:14px;
  padding:16px 50px 16px 18px;
  color:var(--text);
  font-family:'Cairo',sans-serif;font-size:16px;
  outline:none;transition:all 0.3s;
  letter-spacing:4px;
}

.field-input:focus{
  border-color:var(--gold);
  background:rgba(255,200,50,0.05);
  box-shadow:0 0 0 3px rgba(255,200,50,0.1),0 0 30px rgba(255,200,50,0.15);
}

.eye-toggle{
  position:absolute;left:16px;top:50%;transform:translateY(-50%);
  background:none;border:none;cursor:pointer;
  color:var(--text3);font-size:18px;transition:color 0.2s;padding:4px;
}
.eye-toggle:hover{color:var(--gold);}

.login-btn{
  width:100%;margin-top:20px;
  background:linear-gradient(135deg,var(--gold) 0%,var(--gold2) 100%);
  border:none;border-radius:14px;
  padding:17px;
  color:#07070e;
  font-family:'Tajawal',sans-serif;font-weight:900;font-size:17px;
  cursor:pointer;transition:all 0.3s;
  box-shadow:0 8px 30px rgba(255,200,50,0.35);
  letter-spacing:0.5px;
}
.login-btn:hover{transform:translateY(-3px);box-shadow:0 15px 40px rgba(255,200,50,0.5);}
.login-btn:active{transform:translateY(-1px);}

.login-error{
  color:var(--red);font-size:13px;text-align:center;
  margin-top:12px;display:none;
  animation:shake 0.5s ease;
}
@keyframes shake{0%,100%{transform:translateX(0);}20%{transform:translateX(-10px);}40%{transform:translateX(10px);}60%{transform:translateX(-6px);}80%{transform:translateX(6px);}}

.login-attempts{color:var(--text3);font-size:12px;text-align:center;margin-top:8px;}

.login-footer{
  margin-top:32px;text-align:center;
  color:var(--text3);font-size:12px;line-height:1.8;
}

/* ===== APP ===== */
#app{display:none;min-height:100vh;}

/* ===== SIDEBAR ===== */
.layout{display:flex;min-height:100vh;}

.sidebar{
  width:72px;
  background:rgba(7,7,16,0.95);
  border-left:1px solid var(--border);
  display:flex;flex-direction:column;align-items:center;
  padding:20px 0;gap:6px;
  position:fixed;top:0;right:0;bottom:0;z-index:100;
  backdrop-filter:blur(20px);
  transition:width 0.3s cubic-bezier(0.34,1.56,0.64,1);
  overflow:hidden;
}

.sidebar.expanded{width:220px;}

.sidebar-logo{
  width:44px;height:44px;
  background:linear-gradient(135deg,var(--gold),var(--gold2));
  border-radius:12px;
  display:flex;align-items:center;justify-content:center;
  font-size:22px;margin-bottom:16px;flex-shrink:0;
  box-shadow:0 4px 20px rgba(255,200,50,0.4);
  cursor:pointer;transition:transform 0.2s;
}
.sidebar-logo:hover{transform:scale(1.05);}

.sidebar-logo-text{
  font-family:'Tajawal',sans-serif;font-weight:900;font-size:15px;
  background:linear-gradient(135deg,var(--gold),var(--gold2));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
  white-space:nowrap;margin-right:8px;
  opacity:0;transition:opacity 0.2s;
}
.sidebar.expanded .sidebar-logo-text{opacity:1;}

.sidebar-logo-wrap{display:flex;align-items:center;width:100%;padding:0 14px;margin-bottom:16px;}

.nav-item{
  display:flex;align-items:center;gap:12px;
  width:calc(100% - 16px);margin:0 8px;
  padding:11px 12px;border-radius:12px;
  cursor:pointer;transition:all 0.2s;
  color:var(--text3);font-size:13px;font-weight:600;
  white-space:nowrap;overflow:hidden;
  position:relative;
}

.nav-item:hover{
  background:rgba(255,200,50,0.08);
  color:var(--text2);
}

.nav-item.active{
  background:linear-gradient(135deg,rgba(255,200,50,0.15),rgba(255,149,0,0.08));
  color:var(--gold);
  box-shadow:inset 0 0 0 1px rgba(255,200,50,0.2);
}

.nav-item.active::before{
  content:'';
  position:absolute;right:0;top:25%;bottom:25%;
  width:3px;background:var(--gold);
  border-radius:99px 0 0 99px;
}

.nav-icon{font-size:18px;flex-shrink:0;width:20px;text-align:center;}
.nav-label{opacity:0;transition:opacity 0.2s;pointer-events:none;}
.sidebar.expanded .nav-label{opacity:1;pointer-events:auto;}

.nav-divider{width:40px;height:1px;background:var(--border);margin:8px 0;}

/* ===== MAIN ===== */
.main{
  margin-right:72px;flex:1;
  transition:margin-right 0.3s;
  min-height:100vh;
}

/* ===== TOPBAR ===== */
.topbar{
  height:64px;
  background:rgba(7,7,16,0.85);
  border-bottom:1px solid var(--border);
  backdrop-filter:blur(20px);
  display:flex;align-items:center;justify-content:space-between;
  padding:0 28px;
  position:sticky;top:0;z-index:50;
}

.topbar-left{display:flex;align-items:center;gap:16px;}

.page-title{
  font-family:'Tajawal',sans-serif;
  font-weight:800;font-size:18px;
  background:linear-gradient(135deg,var(--text),var(--text2));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
}

.topbar-right{display:flex;align-items:center;gap:10px;}

.tb-btn{
  background:rgba(255,255,255,0.04);
  border:1px solid var(--border);
  border-radius:10px;padding:8px 14px;
  color:var(--text2);font-family:'Cairo',sans-serif;
  font-size:12px;cursor:pointer;transition:all 0.2s;
  display:flex;align-items:center;gap:6px;
  font-weight:600;
}
.tb-btn:hover{border-color:var(--border2);color:var(--gold);}

.session-chip{
  background:rgba(0,245,160,0.08);
  border:1px solid rgba(0,245,160,0.2);
  border-radius:99px;padding:6px 14px;
  font-size:12px;color:var(--green);
  display:flex;align-items:center;gap:6px;font-weight:600;
}

.session-dot{
  width:6px;height:6px;border-radius:50%;
  background:var(--green);
  animation:blink 2s ease-in-out infinite;
}
@keyframes blink{0%,100%{opacity:1;}50%{opacity:0.3;}}

/* ===== STATS ROW ===== */
.stats-row{
  display:grid;grid-template-columns:repeat(5,1fr);
  gap:14px;padding:24px 28px 0;
}
@media(max-width:900px){.stats-row{grid-template-columns:repeat(3,1fr);}}
@media(max-width:600px){.stats-row{grid-template-columns:repeat(2,1fr);}}

.stat-tile{
  background:var(--card);
  border:1px solid var(--border);
  border-radius:var(--r2);
  padding:20px 18px;
  position:relative;overflow:hidden;
  backdrop-filter:blur(20px);
  transition:all 0.3s;
  cursor:default;
}

.stat-tile::before{
  content:'';position:absolute;inset:0;
  background:linear-gradient(135deg,rgba(255,200,50,0.03),transparent);
  opacity:0;transition:opacity 0.3s;
}
.stat-tile:hover::before{opacity:1;}
.stat-tile:hover{border-color:var(--border2);transform:translateY(-3px);box-shadow:0 20px 40px rgba(0,0,0,0.4),0 0 40px rgba(255,200,50,0.06);}

.stat-tile-icon{
  font-size:22px;margin-bottom:12px;
  display:inline-block;
}

.stat-num{
  font-family:'Tajawal',sans-serif;
  font-weight:900;font-size:30px;
  background:linear-gradient(135deg,var(--gold3) 0%,var(--gold) 60%,var(--gold2) 100%);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
  line-height:1;margin-bottom:4px;
}

.stat-label{color:var(--text3);font-size:12px;font-weight:600;letter-spacing:0.5px;}

.stat-tile-glow{
  position:absolute;bottom:-20px;right:-20px;
  width:80px;height:80px;border-radius:50%;
  background:radial-gradient(circle,var(--gold-glow),transparent 70%);
  opacity:0.3;
}

/* ===== CONTENT ===== */
.content{padding:24px 28px 60px;}

.panel{display:none;animation:panelIn 0.4s cubic-bezier(0.34,1.2,0.64,1) both;}
.panel.active{display:block;}
@keyframes panelIn{from{opacity:0;transform:translateY(16px);}to{opacity:1;transform:translateY(0);}}

/* ===== SECTION HEADER ===== */
.section-head{
  display:flex;align-items:center;gap:14px;
  margin-bottom:24px;padding-bottom:20px;
  border-bottom:1px solid var(--border);
}

.section-icon-wrap{
  width:48px;height:48px;
  background:linear-gradient(135deg,rgba(255,200,50,0.2),rgba(255,149,0,0.1));
  border:1px solid rgba(255,200,50,0.3);
  border-radius:14px;
  display:flex;align-items:center;justify-content:center;
  font-size:22px;flex-shrink:0;
  box-shadow:0 4px 20px rgba(255,200,50,0.15);
}

.section-title{
  font-family:'Tajawal',sans-serif;
  font-weight:800;font-size:22px;
  background:linear-gradient(135deg,var(--text),rgba(255,255,255,0.7));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
}

.section-sub{color:var(--text3);font-size:13px;margin-top:2px;}

/* ===== CARDS ===== */
.card{
  background:var(--card);
  border:1px solid var(--border);
  border-radius:var(--r2);
  padding:26px;
  margin-bottom:18px;
  backdrop-filter:blur(20px);
  transition:all 0.3s;
  position:relative;overflow:hidden;
}

.card::after{
  content:'';position:absolute;
  top:0;left:0;right:0;height:1px;
  background:linear-gradient(90deg,transparent,rgba(255,200,50,0.3),transparent);
}

.card:hover{border-color:rgba(255,200,50,0.18);}

.card-title-row{
  display:flex;align-items:center;justify-content:space-between;
  margin-bottom:22px;
}

.card-title{
  display:flex;align-items:center;gap:10px;
  font-family:'Tajawal',sans-serif;font-weight:700;font-size:17px;
  color:var(--text);
}

.card-badge{
  width:36px;height:36px;
  background:linear-gradient(135deg,rgba(255,200,50,0.15),rgba(255,149,0,0.08));
  border:1px solid rgba(255,200,50,0.2);
  border-radius:10px;
  display:flex;align-items:center;justify-content:center;
  font-size:17px;
}

/* ===== FORM ELEMENTS ===== */
.f-group{margin-bottom:18px;}

.f-label{
  font-size:11px;font-weight:700;
  color:var(--text2);letter-spacing:1.5px;
  text-transform:uppercase;margin-bottom:9px;
  display:flex;align-items:center;gap:6px;
}

.f-input, .f-textarea, .f-select{
  width:100%;
  background:rgba(255,255,255,0.03);
  border:1px solid rgba(255,200,50,0.1);
  border-radius:12px;
  padding:14px 16px;
  color:var(--text);
  font-family:'Cairo',sans-serif;font-size:14px;
  outline:none;transition:all 0.3s;
  resize:vertical;
}

.f-input:focus,.f-textarea:focus,.f-select:focus{
  border-color:rgba(255,200,50,0.4);
  background:rgba(255,200,50,0.04);
  box-shadow:0 0 0 3px rgba(255,200,50,0.08);
}

.f-input::placeholder,.f-textarea::placeholder{color:var(--text3);}

.f-select option{background:#0a0a18;color:var(--text);}

/* ===== TAGS ===== */
.tags{display:flex;flex-wrap:wrap;gap:8px;}

.tag{
  background:rgba(255,255,255,0.04);
  border:1px solid rgba(255,200,50,0.1);
  border-radius:99px;padding:7px 16px;
  font-size:13px;color:var(--text2);
  cursor:pointer;transition:all 0.2s;font-weight:600;
}
.tag:hover{border-color:rgba(255,200,50,0.3);color:var(--text);}
.tag.on{
  background:rgba(255,200,50,0.12);
  border-color:rgba(255,200,50,0.4);
  color:var(--gold);
}

/* ===== BUTTONS ===== */
.btn{
  border:none;border-radius:12px;
  padding:13px 22px;
  font-family:'Cairo',sans-serif;font-weight:700;font-size:14px;
  cursor:pointer;transition:all 0.3s;
  display:inline-flex;align-items:center;gap:8px;
  position:relative;overflow:hidden;
}

.btn::after{
  content:'';position:absolute;inset:0;
  background:rgba(255,255,255,0.1);
  opacity:0;transition:opacity 0.2s;
  border-radius:inherit;
}
.btn:hover::after{opacity:1;}

.btn-primary{
  background:linear-gradient(135deg,var(--gold) 0%,var(--gold2) 100%);
  color:#06060f;
  box-shadow:0 6px 24px rgba(255,200,50,0.3);
}
.btn-primary:hover{transform:translateY(-2px);box-shadow:0 12px 35px rgba(255,200,50,0.45);}

.btn-ghost{
  background:rgba(255,255,255,0.04);
  border:1px solid var(--border);color:var(--text2);
}
.btn-ghost:hover{border-color:var(--border2);color:var(--gold);}

.btn-danger{
  background:rgba(255,51,102,0.12);
  border:1px solid rgba(255,51,102,0.25);color:var(--red);
}
.btn-danger:hover{background:rgba(255,51,102,0.2);}

.btn-snap{
  background:linear-gradient(135deg,#fffc00 0%,#f0e800 100%);
  color:#07070e;
  box-shadow:0 6px 24px rgba(255,252,0,0.3);
  font-size:15px;padding:15px 28px;
}
.btn-snap:hover{transform:translateY(-3px);box-shadow:0 14px 40px rgba(255,252,0,0.45);}

.btn-success{
  background:rgba(0,245,160,0.12);
  border:1px solid rgba(0,245,160,0.25);color:var(--green);
}
.btn-success:hover{background:rgba(0,245,160,0.2);}

.btn-row{display:flex;flex-wrap:wrap;gap:10px;}

/* ===== AI RESULT ===== */
.ai-box{
  display:none;margin-top:18px;
  background:rgba(255,200,50,0.03);
  border:1px solid rgba(255,200,50,0.15);
  border-radius:var(--r);
  padding:20px;
  position:relative;
  animation:fadeUp 0.4s ease both;
}
.ai-box.show{display:block;}
@keyframes fadeUp{from{opacity:0;transform:translateY(8px);}to{opacity:1;transform:translateY(0);}}

.ai-box-head{
  display:flex;align-items:center;justify-content:space-between;
  margin-bottom:14px;
}

.ai-tag{
  background:linear-gradient(135deg,rgba(255,200,50,0.15),rgba(255,149,0,0.08));
  border:1px solid rgba(255,200,50,0.25);
  border-radius:8px;padding:4px 12px;
  font-size:11px;color:var(--gold);font-weight:700;
  letter-spacing:1px;text-transform:uppercase;
  display:flex;align-items:center;gap:5px;
}

.copy-btn{
  background:rgba(255,255,255,0.04);
  border:1px solid var(--border);
  border-radius:8px;padding:5px 12px;
  color:var(--text3);font-family:'Cairo',sans-serif;
  font-size:12px;cursor:pointer;transition:all 0.2s;
}
.copy-btn:hover{border-color:rgba(0,245,160,0.4);color:var(--green);}

.ai-content{
  color:var(--text);font-size:14px;line-height:1.9;
  white-space:pre-wrap;
}

/* ===== LOADING ===== */
.loader{
  display:none;align-items:center;justify-content:center;
  gap:14px;padding:24px;color:var(--gold);
  font-size:14px;font-weight:600;
}
.loader.on{display:flex;}

.loader-ring{
  width:28px;height:28px;
  border:2px solid rgba(255,200,50,0.15);
  border-top-color:var(--gold);
  border-radius:50%;
  animation:spin 0.75s linear infinite;
}
@keyframes spin{to{transform:rotate(360deg);}}

/* ===== METERS ===== */
.meter{margin:12px 0;}
.meter-row{display:flex;justify-content:space-between;font-size:12px;color:var(--text2);margin-bottom:7px;font-weight:600;}
.meter-track{height:6px;background:rgba(255,255,255,0.05);border-radius:99px;overflow:hidden;}
.meter-fill{height:100%;border-radius:99px;background:linear-gradient(90deg,var(--gold2),var(--gold));transition:width 1.2s cubic-bezier(0.34,1.56,0.64,1);}

/* ===== GRID 2 ===== */
.g2{display:grid;grid-template-columns:1fr 1fr;gap:16px;}
@media(max-width:600px){.g2{grid-template-columns:1fr;}}

/* ===== SAVED GRID ===== */
.saved-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(250px,1fr));gap:16px;margin-top:16px;}

.saved-card{
  background:rgba(255,255,255,0.03);
  border:1px solid var(--border);
  border-radius:var(--r);
  padding:18px;transition:all 0.3s;
  position:relative;
}
.saved-card:hover{border-color:var(--border2);transform:translateY(-3px);box-shadow:0 20px 40px rgba(0,0,0,0.4);}

.saved-card-title{
  font-weight:700;font-size:15px;color:var(--gold);
  margin-bottom:8px;padding-left:28px;
}
.saved-card-notes{font-size:13px;color:var(--text2);line-height:1.6;margin-bottom:12px;}
.saved-card-date{font-size:11px;color:var(--text3);}

.stars{display:flex;gap:3px;margin:10px 0;}
.star{font-size:16px;cursor:pointer;color:var(--text3);transition:all 0.2s;}
.star:hover,.star.on{color:var(--gold);transform:scale(1.2);}

.del-btn{
  position:absolute;top:12px;left:12px;
  background:rgba(255,51,102,0.1);border:1px solid rgba(255,51,102,0.2);
  border-radius:7px;padding:3px 8px;
  color:var(--red);font-size:11px;cursor:pointer;transition:all 0.2s;
}
.del-btn:hover{background:rgba(255,51,102,0.25);}

/* ===== PEAK TIMES ===== */
.peak-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(160px,1fr));gap:12px;}

.peak-tile{
  background:rgba(255,255,255,0.03);
  border:1px solid var(--border);
  border-radius:var(--r);
  padding:18px 14px;text-align:center;
  transition:all 0.3s;position:relative;overflow:hidden;
}

.peak-tile.now{
  border-color:rgba(0,245,160,0.4);
  background:rgba(0,245,160,0.05);
  box-shadow:0 0 30px rgba(0,245,160,0.1);
}

.peak-time-big{font-size:26px;font-weight:900;color:var(--gold);font-family:'Tajawal',sans-serif;}
.peak-name-sm{font-size:12px;color:var(--text2);margin:4px 0;font-weight:600;}
.peak-pill{
  display:inline-block;border-radius:99px;
  padding:4px 12px;font-size:11px;font-weight:700;margin-top:8px;
}
.peak-pill.hot{background:rgba(255,51,102,0.15);color:var(--red);}
.peak-pill.warm{background:rgba(255,200,50,0.15);color:var(--gold);}
.peak-pill.cool{background:rgba(0,153,255,0.15);color:var(--blue);}
.now-badge{font-size:10px;color:var(--green);margin-top:6px;font-weight:700;}

/* ===== COUNTDOWN ===== */
.countdown-hero{
  background:linear-gradient(135deg,rgba(0,245,160,0.06),rgba(0,153,255,0.04));
  border:1px solid rgba(0,245,160,0.2);
  border-radius:var(--r2);
  padding:28px;text-align:center;margin-bottom:18px;
  position:relative;overflow:hidden;
}

.countdown-hero::before{
  content:'';position:absolute;inset:0;
  background:radial-gradient(ellipse 60% 60% at 50% 100%,rgba(0,245,160,0.06),transparent);
}

.cd-label{font-size:13px;color:var(--text2);font-weight:600;margin-bottom:10px;letter-spacing:1px;}
.cd-time{
  font-family:'Tajawal',sans-serif;font-size:52px;font-weight:900;
  color:var(--green);
  font-variant-numeric:tabular-nums;
  text-shadow:0 0 40px rgba(0,245,160,0.4);
  letter-spacing:4px;
}
.cd-next{font-size:13px;color:var(--text3);margin-top:8px;}

/* ===== CHECKLIST ===== */
.check-list{display:flex;flex-direction:column;gap:8px;}
.check-item{
  display:flex;align-items:center;gap:12px;
  background:rgba(255,255,255,0.02);
  border:1px solid var(--border);
  border-radius:12px;padding:13px 15px;
  cursor:pointer;transition:all 0.2s;
}
.check-item:hover{border-color:rgba(255,200,50,0.15);}
.check-item.done{border-color:rgba(0,245,160,0.25);background:rgba(0,245,160,0.04);}

.chk{
  width:22px;height:22px;border:2px solid var(--text3);
  border-radius:6px;flex-shrink:0;
  display:flex;align-items:center;justify-content:center;
  font-size:12px;transition:all 0.2s;
}
.check-item.done .chk{background:var(--green);border-color:var(--green);color:#06060f;}
.chk-text{font-size:13px;transition:all 0.2s;}
.check-item.done .chk-text{color:var(--text2);text-decoration:line-through;}

/* ===== BADGES ===== */
.badges-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(120px,1fr));gap:12px;}

.badge{
  background:rgba(255,255,255,0.02);
  border:1px solid var(--border);
  border-radius:var(--r);
  padding:18px 12px;text-align:center;
  transition:all 0.3s;
}
.badge.earned{
  border-color:rgba(255,200,50,0.35);
  background:rgba(255,200,50,0.06);
  box-shadow:0 0 20px rgba(255,200,50,0.08);
}
.badge.locked{opacity:0.35;filter:grayscale(0.5);}
.badge-ico{font-size:30px;margin-bottom:8px;}
.badge-name{font-size:12px;font-weight:700;color:var(--text2);}
.badge-req{font-size:11px;color:var(--text3);margin-top:3px;}

/* ===== COMPARE ===== */
.compare-wrap{display:grid;grid-template-columns:1fr 1fr;gap:16px;}
@media(max-width:600px){.compare-wrap{grid-template-columns:1fr;}}
.compare-side{
  background:rgba(255,255,255,0.02);
  border:1px solid var(--border);
  border-radius:var(--r);padding:16px;
}
.compare-side.win{border-color:rgba(0,245,160,0.3);}
.compare-side.lose{border-color:rgba(255,51,102,0.3);}
.compare-side-label{font-size:12px;font-weight:700;margin-bottom:10px;}

/* ===== AB OPTIONS ===== */
.ab-list{display:flex;flex-direction:column;gap:8px;margin:12px 0;}
.ab-row{
  background:rgba(255,255,255,0.02);border:1px solid var(--border);
  border-radius:11px;padding:12px 14px;
  display:flex;align-items:center;justify-content:space-between;
  transition:all 0.3s;
}
.ab-row.best{border-color:rgba(255,200,50,0.4);background:rgba(255,200,50,0.07);}
.ab-pct{font-family:'Tajawal',sans-serif;font-weight:900;font-size:18px;color:var(--gold);}

/* ===== HISTORY ===== */
.history-row{
  background:rgba(255,255,255,0.02);
  border:1px solid var(--border);
  border-radius:11px;padding:13px 16px;
  margin-bottom:8px;
  display:flex;align-items:center;justify-content:space-between;
}
.history-title{font-size:13px;font-weight:600;color:var(--text);}
.history-date{font-size:11px;color:var(--text3);}

/* ===== PERF TABLE ===== */
.perf-row{
  background:rgba(255,255,255,0.02);
  border:1px solid var(--border);
  border-radius:11px;padding:12px 16px;
  margin-top:8px;
  display:flex;align-items:center;justify-content:space-between;
}

/* ===== FINAL ===== */
.final-card{
  background:linear-gradient(135deg,rgba(255,200,50,0.06),rgba(255,149,0,0.03));
  border:1px solid rgba(255,200,50,0.2);
  border-radius:var(--r2);padding:26px;margin-bottom:18px;
}
.final-title-row{
  display:flex;align-items:center;gap:10px;
  margin-bottom:20px;
  font-family:'Tajawal',sans-serif;font-weight:800;font-size:20px;color:var(--gold);
}
.final-row{
  display:flex;align-items:flex-start;gap:12px;
  padding:12px 0;border-bottom:1px solid var(--border);
}
.final-row:last-child{border-bottom:none;}
.final-lbl{font-size:12px;color:var(--text2);min-width:120px;font-weight:700;letter-spacing:0.5px;padding-top:2px;}
.final-val{font-size:14px;color:var(--text);flex:1;line-height:1.6;}

/* ===== SNAP HERO ===== */
.snap-hero{
  background:linear-gradient(135deg,rgba(255,252,0,0.08),rgba(240,232,0,0.04));
  border:1px solid rgba(255,252,0,0.25);
  border-radius:var(--r2);padding:36px;text-align:center;
  margin-bottom:20px;position:relative;overflow:hidden;
}
.snap-hero::before{
  content:'';position:absolute;inset:0;
  background:radial-gradient(ellipse 60% 80% at 50% 100%,rgba(255,252,0,0.05),transparent);
}
.snap-ghost{font-size:56px;margin-bottom:16px;filter:drop-shadow(0 0 20px rgba(255,252,0,0.3));}
.snap-hero-title{font-family:'Tajawal',sans-serif;font-size:24px;font-weight:900;color:var(--snap);margin-bottom:6px;}
.snap-hero-sub{color:var(--text2);font-size:14px;margin-bottom:24px;}

/* ===== QUALITY SCORE ===== */
.quality-score{
  text-align:center;padding:24px;
  display:none;
}
.q-pct{font-family:'Tajawal',sans-serif;font-size:56px;font-weight:900;}
.q-label{color:var(--text2);font-size:14px;margin-top:4px;}

/* ===== MODAL ===== */
.modal-bg{
  position:fixed;inset:0;z-index:9999;
  background:rgba(0,0,0,0.85);backdrop-filter:blur(12px);
  display:none;align-items:center;justify-content:center;
}
.modal-bg.open{display:flex;}

.modal{
  background:rgba(12,12,28,0.98);
  border:1px solid rgba(255,51,102,0.3);
  border-radius:var(--r2);padding:36px;
  max-width:380px;width:90%;text-align:center;
  box-shadow:0 40px 80px rgba(0,0,0,0.8),0 0 60px rgba(255,51,102,0.1);
  animation:modalIn 0.4s cubic-bezier(0.34,1.56,0.64,1) both;
}
@keyframes modalIn{from{opacity:0;transform:scale(0.85);}to{opacity:1;transform:scale(1);}}
.modal-ico{font-size:52px;margin-bottom:16px;}
.modal-t{font-family:'Tajawal',sans-serif;font-weight:800;font-size:22px;color:var(--red);margin-bottom:8px;}
.modal-s{color:var(--text2);font-size:14px;margin-bottom:26px;line-height:1.6;}
.modal-btns{display:flex;gap:12px;justify-content:center;}

/* ===== NOTIF TOAST ===== */
.toast{
  position:fixed;bottom:28px;right:28px;z-index:9998;
  background:rgba(12,12,28,0.95);
  border:1px solid rgba(0,245,160,0.3);
  border-radius:14px;padding:14px 20px;
  display:flex;align-items:center;gap:10px;
  color:var(--green);font-size:14px;font-weight:700;
  box-shadow:0 10px 40px rgba(0,0,0,0.5),0 0 30px rgba(0,245,160,0.1);
  transform:translateX(120%);opacity:0;
  transition:all 0.4s cubic-bezier(0.34,1.56,0.64,1);
  backdrop-filter:blur(20px);
}
.toast.show{transform:translateX(0);opacity:1;}

/* ===== SCROLLBAR ===== */
::-webkit-scrollbar{width:5px;height:5px;}
::-webkit-scrollbar-track{background:transparent;}
::-webkit-scrollbar-thumb{background:rgba(255,200,50,0.15);border-radius:99px;}
::-webkit-scrollbar-thumb:hover{background:rgba(255,200,50,0.3);}

/* ===== RESPONSIVE ===== */
@media(max-width:768px){
  .sidebar{display:none;}
  .main{margin-right:0;}
  .stats-row{grid-template-columns:repeat(2,1fr);}
  .content{padding:18px 16px 60px;}
  .topbar{padding:0 16px;}
}
</style>
</head>
<body>

<!-- BG -->
<div class="bg-canvas"></div>
<div class="bg-orb bg-orb1"></div>
<div class="bg-orb bg-orb2"></div>
<div class="bg-orb bg-orb3"></div>
<div class="bg-grid"></div>
<div class="bg-noise"></div>

<!-- ===================== LOGIN ===================== -->
<div id="loginScreen">
  <div class="login-hero">
    <div class="login-logo-wrap">
      <div class="login-logo-ring">
        <div class="login-logo-inner">🌟</div>
      </div>
    </div>
    <div class="login-title">الأضواء Pro</div>
    <div class="login-sub">منصة المليون مشاهدة — أداة المحترفين</div>
  </div>

  <div class="login-box">
    <div class="f-group">
      <div class="f-label">🔐 كلمة الدخول</div>
      <div class="field-wrap">
        <input type="password" id="pwdIn" class="field-input" placeholder="••••••••••••" onkeydown="if(event.key==='Enter')doLogin()">
        <button class="eye-toggle" onclick="toggleEye()">👁</button>
      </div>
    </div>
    <div class="login-error" id="loginErr">⚠️ كلمة المرور غير صحيحة</div>
    <div class="login-attempts" id="loginTries"></div>
    <button class="login-btn" onclick="doLogin()">🚀 دخول</button>
  </div>

  <div class="login-footer">
    🔒 محمي بتشفير متقدم<br>
    منصة الأضواء Pro v2.0
  </div>
</div>

<!-- CLEAR MODAL -->
<div class="modal-bg" id="clearModal">
  <div class="modal">
    <div class="modal-ico">🗑️</div>
    <div class="modal-t">مسح كل البيانات</div>
    <div class="modal-s">سيتم حذف بيانات الفيديو الحالي، العناوين، التحليلات والهاشتاقات. هل أنت متأكد؟</div>
    <div class="modal-btns">
      <button class="btn btn-danger" onclick="doClear()">نعم، امسح كل شي</button>
      <button class="btn btn-ghost" onclick="closeModal('clearModal')">إلغاء</button>
    </div>
  </div>
</div>

<!-- ===================== APP ===================== -->
<div id="app">
  <div class="layout">

    <!-- SIDEBAR -->
    <div class="sidebar" id="sidebar">
      <div class="sidebar-logo-wrap">
        <div class="sidebar-logo" onclick="toggleSidebar()">🌟</div>
        <div class="sidebar-logo-text">الأضواء Pro</div>
      </div>

      <div class="nav-item active" onclick="goPanel('ideas',this)">
        <div class="nav-icon">💡</div><div class="nav-label">أفكار الفيديو</div>
      </div>
      <div class="nav-item" onclick="goPanel('saved',this)">
        <div class="nav-icon">💾</div><div class="nav-label">فيديوهاتي</div>
      </div>
      <div class="nav-item" onclick="goPanel('analyzer',this)">
        <div class="nav-icon">🎬</div><div class="nav-label">محلل الفيديو</div>
      </div>
      <div class="nav-item" onclick="goPanel('timing',this)">
        <div class="nav-icon">⏰</div><div class="nav-label">أوقات الذروة</div>
      </div>
      <div class="nav-item" onclick="goPanel('titles',this)">
        <div class="nav-icon">✍️</div><div class="nav-label">مولد العناوين</div>
      </div>
      <div class="nav-divider"></div>
      <div class="nav-item" onclick="goPanel('psychology',this)">
        <div class="nav-icon">🧠</div><div class="nav-label">علم النفس</div>
      </div>
      <div class="nav-item" onclick="goPanel('script',this)">
        <div class="nav-icon">📝</div><div class="nav-label">كاتب السكريبت</div>
      </div>
      <div class="nav-item" onclick="goPanel('abtest',this)">
        <div class="nav-icon">🧪</div><div class="nav-label">A/B تيست</div>
      </div>
      <div class="nav-item" onclick="goPanel('compare',this)">
        <div class="nav-icon">🔁</div><div class="nav-label">مقارن الفيديوهات</div>
      </div>
      <div class="nav-divider"></div>
      <div class="nav-item" onclick="goPanel('plan',this)">
        <div class="nav-icon">📅</div><div class="nav-label">خطة المحتوى</div>
      </div>
      <div class="nav-item" onclick="goPanel('hashtags',this)">
        <div class="nav-icon">🔑</div><div class="nav-label">الهاشتاقات</div>
      </div>
      <div class="nav-item" onclick="goPanel('quality',this)">
        <div class="nav-icon">🌈</div><div class="nav-label">مدقق الجودة</div>
      </div>
      <div class="nav-item" onclick="goPanel('achievements',this)">
        <div class="nav-icon">🏆</div><div class="nav-label">الإنجازات</div>
      </div>
      <div class="nav-divider"></div>
      <div class="nav-item" onclick="goPanel('history',this)">
        <div class="nav-icon">📖</div><div class="nav-label">السجل</div>
      </div>
      <div class="nav-item" onclick="goPanel('launch',this)">
        <div class="nav-icon">🚀</div><div class="nav-label">إطلاق الفيديو</div>
      </div>
    </div>

    <!-- MAIN -->
    <div class="main" id="mainArea">

      <!-- TOPBAR -->
      <div class="topbar">
        <div class="topbar-left">
          <div class="page-title" id="pageTitle">أفكار الفيديو</div>
        </div>
        <div class="topbar-right">
          <div class="session-chip">
            <div class="session-dot"></div>
            <span id="sessTime">00:00</span>
          </div>
          <button class="tb-btn" onclick="toggleTheme()">🌙 <span id="themeLabel">ليلي</span></button>
          <button class="tb-btn" onclick="openModal('clearModal')">🗑️ مسح</button>
          <button class="tb-btn" style="border-color:rgba(255,51,102,0.3);color:var(--red)" onclick="doLogout()">خروج</button>
        </div>
      </div>

      <!-- STATS -->
      <div class="stats-row">
        <div class="stat-tile">
          <div class="stat-tile-icon">📹</div>
          <div class="stat-num" id="sv">0</div>
          <div class="stat-label">فيديو حُلِّل</div>
          <div class="stat-tile-glow"></div>
        </div>
        <div class="stat-tile">
          <div class="stat-tile-icon">✍️</div>
          <div class="stat-num" id="st">0</div>
          <div class="stat-label">عنوان وُلِّد</div>
          <div class="stat-tile-glow"></div>
        </div>
        <div class="stat-tile">
          <div class="stat-tile-icon">💾</div>
          <div class="stat-num" id="ss">0</div>
          <div class="stat-label">فيديو محفوظ</div>
          <div class="stat-tile-glow"></div>
        </div>
        <div class="stat-tile">
          <div class="stat-tile-icon">⭐</div>
          <div class="stat-num" id="sp">0</div>
          <div class="stat-label">نقطة</div>
          <div class="stat-tile-glow"></div>
        </div>
        <div class="stat-tile">
          <div class="stat-tile-icon">🔥</div>
          <div class="stat-num" id="sk">0</div>
          <div class="stat-label">أيام متواصلة</div>
          <div class="stat-tile-glow"></div>
        </div>
      </div>

      <div class="content">

        <!-- ===== IDEAS ===== -->
        <div class="panel active" id="panel-ideas">
          <div class="section-head">
            <div class="section-icon-wrap">💡</div>
            <div>
              <div class="section-title">مولد أفكار الفيديو</div>
              <div class="section-sub">ذكاء اصطناعي يولّد أفكار مخصصة للأضواء</div>
            </div>
          </div>

          <div class="card">
            <div class="card-title-row">
              <div class="card-title"><div class="card-badge">🎯</div>نوع المحتوى</div>
            </div>
            <div class="f-group">
              <div class="tags" id="typeTags">
                <div class="tag on" onclick="toggleTag(this)">😂 كوميدي</div>
                <div class="tag" onclick="toggleTag(this)">😱 صادم</div>
                <div class="tag" onclick="toggleTag(this)">💪 تحفيزي</div>
                <div class="tag" onclick="toggleTag(this)">🎭 درامي</div>
                <div class="tag" onclick="toggleTag(this)">🎓 تعليمي</div>
                <div class="tag" onclick="toggleTag(this)">❓ فضول</div>
                <div class="tag" onclick="toggleTag(this)">🔥 ترند</div>
                <div class="tag" onclick="toggleTag(this)">🌙 ليلي</div>
              </div>
            </div>
            <div class="f-group">
              <div class="f-label">📝 وصف فكرتك (اختياري)</div>
              <textarea class="f-textarea" id="ideaDesc" rows="3" placeholder="مثال: أبغى فيديو يجعل الناس يعيدونه أكثر من مرة..."></textarea>
            </div>
            <div class="btn-row">
              <button class="btn btn-primary" onclick="generateIdeas()">⚡ ولّد أفكار بـ AI</button>
              <button class="btn btn-ghost" onclick="generateHook()">🎯 ولّد Hook احترافي</button>
            </div>
            <div class="loader" id="l-ideas"><div class="loader-ring"></div>الذكاء الاصطناعي يفكر...</div>
            <div class="ai-box" id="r-ideas">
              <div class="ai-box-head">
                <div class="ai-tag">✦ AI</div>
                <button class="copy-btn" onclick="cpRes('r-ideas')">📋 نسخ</button>
              </div>
              <div class="ai-content" id="t-ideas"></div>
            </div>
          </div>

          <div class="card">
            <div class="card-title-row">
              <div class="card-title"><div class="card-badge">🔮</div>محرك التنبؤ بالأداء</div>
            </div>
            <div class="f-group">
              <div class="f-label">📹 صف فيديوك بالتفصيل</div>
              <textarea class="f-textarea" id="predDesc" rows="3" placeholder="الموضوع، الأسلوب، المدة، نوع المحتوى..."></textarea>
            </div>
            <button class="btn btn-primary" onclick="predictPerf()">🔮 توقع الأداء</button>
            <div class="loader" id="l-pred"><div class="loader-ring"></div>يحلل...</div>
            <div class="ai-box" id="r-pred">
              <div class="ai-box-head">
                <div class="ai-tag">✦ تنبؤ</div>
                <button class="copy-btn" onclick="cpRes('r-pred')">📋 نسخ</button>
              </div>
              <div class="ai-content" id="t-pred"></div>
              <div class="meter" style="margin-top:16px">
                <div class="meter-row"><span>احتمال الانتشار</span><span id="vPct">0%</span></div>
                <div class="meter-track"><div class="meter-fill" id="vBar" style="width:0%"></div></div>
              </div>
              <div class="meter">
                <div class="meter-row"><span>توقع الإعادة</span><span id="rPct">0%</span></div>
                <div class="meter-track"><div class="meter-fill" id="rBar" style="width:0%;background:linear-gradient(90deg,var(--blue),var(--purple))"></div></div>
              </div>
            </div>
          </div>
        </div>

        <!-- ===== SAVED ===== -->
        <div class="panel" id="panel-saved">
          <div class="section-head">
            <div class="section-icon-wrap">💾</div>
            <div><div class="section-title">فيديوهاتي المحفوظة</div><div class="section-sub">احفظ وتابع كل فيديوهاتك</div></div>
          </div>
          <div class="card">
            <div class="f-group">
              <div class="f-label">💾 احفظ فيديو جديد</div>
              <input class="f-input" id="saveTit" placeholder="عنوان الفيديو..." style="margin-bottom:10px">
              <textarea class="f-textarea" id="saveNote" rows="2" placeholder="ملاحظاتك..."></textarea>
            </div>
            <button class="btn btn-primary" onclick="saveVid()">💾 حفظ الفيديو</button>
            <div class="saved-grid" id="savedGrid">
              <div style="color:var(--text3);font-size:14px;padding:24px;text-align:center;grid-column:1/-1">ما في فيديوهات محفوظة بعد 💭</div>
            </div>
          </div>
        </div>

        <!-- ===== ANALYZER ===== -->
        <div class="panel" id="panel-analyzer">
          <div class="section-head">
            <div class="section-icon-wrap">🎬</div>
            <div><div class="section-title">محلل الفيديو</div><div class="section-sub">تحليل شامل + توصيات خوارزمية الأضواء</div></div>
          </div>
          <div class="card">
            <div class="f-group">
              <div class="f-label">📹 صف فيديوك بالتفصيل</div>
              <textarea class="f-textarea" id="anaDesc" rows="4" placeholder="الموضوع، المدة، الألوان، الإضاءة، الصوت..."></textarea>
            </div>
            <div class="g2">
              <div class="f-group">
                <div class="f-label">⏱ مدة الفيديو</div>
                <select class="f-select" id="vidDur">
                  <option>أقل من 10 ثواني</option><option>10-30 ثانية</option>
                  <option>30-60 ثانية</option><option>1-3 دقائق</option><option>أكثر من 3 دقائق</option>
                </select>
              </div>
              <div class="f-group">
                <div class="f-label">📐 نسبة الصورة</div>
                <select class="f-select" id="vidRat">
                  <option>9:16 عمودي (مثالي)</option><option>1:1 مربع</option><option>16:9 أفقي</option>
                </select>
              </div>
            </div>
            <div class="btn-row">
              <button class="btn btn-primary" onclick="analyzeVid()">🔬 حلل الفيديو</button>
              <button class="btn btn-ghost" onclick="analyzeRet()">💎 تحليل Retention</button>
              <button class="btn btn-ghost" onclick="analyzeHk()">🎯 حكم على الـ Hook</button>
            </div>
            <div class="loader" id="l-ana"><div class="loader-ring"></div>يحلل الفيديو...</div>
            <div class="ai-box" id="r-ana">
              <div class="ai-box-head"><div class="ai-tag">✦ تحليل</div><button class="copy-btn" onclick="cpRes('r-ana')">📋 نسخ</button></div>
              <div class="ai-content" id="t-ana"></div>
            </div>
          </div>
          <div class="card">
            <div class="card-title-row"><div class="card-title"><div class="card-badge">⚡</div>مقياس الدوبامين</div></div>
            <div class="f-group">
              <div class="f-label">📹 صف محتوى الفيديو</div>
              <textarea class="f-textarea" id="dopDesc" rows="3" placeholder="وصف المحتوى..."></textarea>
            </div>
            <button class="btn btn-primary" onclick="measureDopa()">⚡ قس مستوى الإثارة</button>
            <div class="loader" id="l-dop"><div class="loader-ring"></div></div>
            <div class="ai-box" id="r-dop">
              <div class="ai-box-head"><div class="ai-tag">✦ دوبامين</div><button class="copy-btn" onclick="cpRes('r-dop')">📋 نسخ</button></div>
              <div class="ai-content" id="t-dop"></div>
              <div class="meter" style="margin-top:14px">
                <div class="meter-row"><span>مستوى الإثارة</span><span id="dopPct">0/100</span></div>
                <div class="meter-track"><div class="meter-fill" id="dopBar" style="width:0%;background:linear-gradient(90deg,var(--purple),var(--red))"></div></div>
              </div>
            </div>
          </div>
        </div>

        <!-- ===== TIMING ===== -->
        <div class="panel" id="panel-timing">
          <div class="section-head">
            <div class="section-icon-wrap">⏰</div>
            <div><div class="section-title">أوقات الذروة</div><div class="section-sub">أفضل أوقات النشر على الأضواء</div></div>
          </div>
          <div class="countdown-hero">
            <div class="cd-label">⏰ الوقت المتبقي للذروة القادمة</div>
            <div class="cd-time" id="cdTime">--:--:--</div>
            <div class="cd-next" id="cdNext">جاري الحساب...</div>
          </div>
          <div class="card">
            <div class="card-title-row"><div class="card-title"><div class="card-badge">📡</div>أوقات الذروة اليومية</div></div>
            <div class="peak-grid" id="peakGrid"></div>
          </div>
          <div class="card">
            <div class="card-title-row"><div class="card-title"><div class="card-badge">🔔</div>تذكيرات النشر</div></div>
            <div class="f-group">
              <div class="f-label">وقت التذكير</div>
              <input type="time" class="f-input" id="remTime" value="20:00">
            </div>
            <button class="btn btn-primary" onclick="setRem()">🔔 فعّل التذكير</button>
            <div class="ai-box" id="r-rem"><div class="ai-content" id="t-rem"></div></div>
          </div>
          <div class="card">
            <div class="card-title-row"><div class="card-title"><div class="card-badge">📡</div>رادار الترند</div></div>
            <div class="f-group">
              <div class="f-label">الفترة الزمنية</div>
              <select class="f-select" id="trendPer">
                <option>هذا الأسبوع</option><option>هذا الشهر</option>
                <option>رمضان</option><option>الصيف</option><option>موسم الأعياد</option>
              </select>
            </div>
            <button class="btn btn-primary" onclick="detectTrend()">📡 كشف الترندات</button>
            <div class="loader" id="l-trend"><div class="loader-ring"></div></div>
            <div class="ai-box" id="r-trend">
              <div class="ai-box-head"><div class="ai-tag">✦ ترند</div><button class="copy-btn" onclick="cpRes('r-trend')">📋 نسخ</button></div>
              <div class="ai-content" id="t-trend"></div>
            </div>
          </div>
        </div>

        <!-- ===== TITLES ===== -->
        <div class="panel" id="panel-titles">
          <div class="section-head">
            <div class="section-icon-wrap">✍️</div>
            <div><div class="section-title">مولد العناوين الجذابة</div><div class="section-sub">عناوين تجعل الإصبع يتوقف</div></div>
          </div>
          <div class="card">
            <div class="f-group">
              <div class="f-label">📹 موضوع الفيديو</div>
              <textarea class="f-textarea" id="titDesc" rows="3" placeholder="اشرح موضوع الفيديو..."></textarea>
            </div>
            <div class="f-group">
              <div class="f-label">🎯 نوع العنوان</div>
              <div class="tags">
                <div class="tag on" onclick="selTitType('curiosity',this)">❓ فضول</div>
                <div class="tag" onclick="selTitType('shock',this)">😱 صدمة</div>
                <div class="tag" onclick="selTitType('challenge',this)">💪 تحدي</div>
                <div class="tag" onclick="selTitType('secret',this)">🤫 سر</div>
                <div class="tag" onclick="selTitType('number',this)">🔢 أرقام</div>
              </div>
            </div>
            <button class="btn btn-primary" onclick="genTitles()">✍️ ولّد 5 عناوين</button>
            <div class="loader" id="l-tit"><div class="loader-ring"></div></div>
            <div class="ai-box" id="r-tit">
              <div class="ai-box-head"><div class="ai-tag">✦ عناوين</div><button class="copy-btn" onclick="cpRes('r-tit')">📋 نسخ</button></div>
              <div class="ai-content" id="t-tit"></div>
            </div>
          </div>
          <div class="card">
            <div class="card-title-row"><div class="card-title"><div class="card-badge">🎪</div>Pattern Interrupt</div></div>
            <div class="f-group">
              <div class="f-label">📹 وصف الفيديو</div>
              <textarea class="f-textarea" id="patDesc" rows="3" placeholder="وصف الفيديو..."></textarea>
            </div>
            <button class="btn btn-primary" onclick="genPattern()">🎪 ولّد لحظات الصدمة</button>
            <div class="loader" id="l-pat"><div class="loader-ring"></div></div>
            <div class="ai-box" id="r-pat">
              <div class="ai-box-head"><div class="ai-tag">✦ Pattern</div><button class="copy-btn" onclick="cpRes('r-pat')">📋 نسخ</button></div>
              <div class="ai-content" id="t-pat"></div>
            </div>
          </div>
        </div>

        <!-- ===== PSYCHOLOGY ===== -->
        <div class="panel" id="panel-psychology">
          <div class="section-head">
            <div class="section-icon-wrap">🧠</div>
            <div><div class="section-title">علم النفس البصري</div><div class="section-sub">تحليل نفسي عميق لفيديوك</div></div>
          </div>
          <div class="card">
            <div class="card-title-row"><div class="card-title"><div class="card-badge">🧠</div>Gestalt Psychology</div></div>
            <div class="f-group">
              <div class="f-label">📹 صف مشهد الفيديو</div>
              <textarea class="f-textarea" id="psyDesc" rows="4" placeholder="الألوان، الحركة، الوجوه، الإضاءة..."></textarea>
            </div>
            <button class="btn btn-primary" onclick="anaPsy()">🧠 حلل علم النفس</button>
            <div class="loader" id="l-psy"><div class="loader-ring"></div></div>
            <div class="ai-box" id="r-psy">
              <div class="ai-box-head"><div class="ai-tag">✦ نفسي</div><button class="copy-btn" onclick="cpRes('r-psy')">📋 نسخ</button></div>
              <div class="ai-content" id="t-psy"></div>
            </div>
          </div>
          <div class="g2">
            <div class="card">
              <div class="card-title-row"><div class="card-title"><div class="card-badge">🎯</div>نظام AIDA</div></div>
              <textarea class="f-textarea" id="aidaDesc" rows="3" placeholder="صف فيديوك..."></textarea>
              <button class="btn btn-primary" style="margin-top:12px;width:100%" onclick="anaAida()">🎯 تحقق AIDA</button>
              <div class="loader" id="l-aida"><div class="loader-ring"></div></div>
              <div class="ai-box" id="r-aida">
                <div class="ai-box-head"><div class="ai-tag">✦ AIDA</div><button class="copy-btn" onclick="cpRes('r-aida')">📋 نسخ</button></div>
                <div class="ai-content" id="t-aida"></div>
              </div>
            </div>
            <div class="card">
              <div class="card-title-row"><div class="card-title"><div class="card-badge">🎭</div>مكتبة المشاعر</div></div>
              <textarea class="f-textarea" id="emoDesc" rows="3" placeholder="صف المحتوى..."></textarea>
              <button class="btn btn-primary" style="margin-top:12px;width:100%" onclick="anaEmo()">🎭 حلل المشاعر</button>
              <div class="loader" id="l-emo"><div class="loader-ring"></div></div>
              <div class="ai-box" id="r-emo">
                <div class="ai-box-head"><div class="ai-tag">✦ مشاعر</div><button class="copy-btn" onclick="cpRes('r-emo')">📋 نسخ</button></div>
                <div class="ai-content" id="t-emo"></div>
              </div>
            </div>
          </div>
        </div>

        <!-- ===== SCRIPT ===== -->
        <div class="panel" id="panel-script">
          <div class="section-head">
            <div class="section-icon-wrap">📝</div>
            <div><div class="section-title">كاتب السكريبت</div><div class="section-sub">سكريبت جاهز للتصوير الفوري</div></div>
          </div>
          <div class="card">
            <div class="f-group">
              <div class="f-label">🎯 فكرة الفيديو</div>
              <textarea class="f-textarea" id="scrIdea" rows="3" placeholder="فكرة الفيديو..."></textarea>
            </div>
            <div class="g2">
              <div class="f-group">
                <div class="f-label">⏱ المدة</div>
                <select class="f-select" id="scrDur">
                  <option>15 ثانية</option><option>30 ثانية</option><option>60 ثانية</option><option>2 دقيقة</option>
                </select>
              </div>
              <div class="f-group">
                <div class="f-label">🎭 الأسلوب</div>
                <select class="f-select" id="scrSty">
                  <option>كوميدي</option><option>تحفيزي</option><option>إثارة وفضول</option><option>تعليمي</option><option>درامي</option>
                </select>
              </div>
            </div>
            <button class="btn btn-primary" onclick="genScript()">📝 اكتب السكريبت</button>
            <div class="loader" id="l-scr"><div class="loader-ring"></div></div>
            <div class="ai-box" id="r-scr">
              <div class="ai-box-head"><div class="ai-tag">✦ سكريبت</div><button class="copy-btn" onclick="cpRes('r-scr')">📋 نسخ</button></div>
              <div class="ai-content" id="t-scr"></div>
            </div>
          </div>
          <div class="card">
            <div class="card-title-row"><div class="card-title"><div class="card-badge">🧲</div>مغناطيس الجمهور</div></div>
            <textarea class="f-textarea" id="audDesc" rows="3" placeholder="صف محتوى قناتك..."></textarea>
            <button class="btn btn-primary" style="margin-top:12px" onclick="anaAud()">🧲 حدد جمهورك</button>
            <div class="loader" id="l-aud"><div class="loader-ring"></div></div>
            <div class="ai-box" id="r-aud">
              <div class="ai-box-head"><div class="ai-tag">✦ جمهور</div><button class="copy-btn" onclick="cpRes('r-aud')">📋 نسخ</button></div>
              <div class="ai-content" id="t-aud"></div>
            </div>
          </div>
        </div>

        <!-- ===== AB TEST ===== -->
        <div class="panel" id="panel-abtest">
          <div class="section-head">
            <div class="section-icon-wrap">🧪</div>
            <div><div class="section-title">مختبر A/B</div><div class="section-sub">اختبر واختر العنوان الأقوى</div></div>
          </div>
          <div class="card">
            <div class="f-group">
              <div class="f-label">📹 موضوع الفيديو</div>
              <textarea class="f-textarea" id="abTopic" rows="2" placeholder="موضوع الفيديو..."></textarea>
            </div>
            <button class="btn btn-primary" onclick="runAB()">🧪 اختبر 5 عناوين</button>
            <div class="loader" id="l-ab"><div class="loader-ring"></div></div>
            <div class="ai-box" id="r-ab">
              <div class="ai-box-head"><div class="ai-tag">✦ A/B</div><button class="copy-btn" onclick="cpRes('r-ab')">📋 نسخ</button></div>
              <div class="ab-list" id="abList"></div>
              <div class="ai-content" id="t-ab"></div>
            </div>
          </div>
          <div class="card">
            <div class="card-title-row"><div class="card-title"><div class="card-badge">💬</div>مولد التعليقات المحفزة</div></div>
            <textarea class="f-textarea" id="comDesc" rows="3" placeholder="موضوع الفيديو..."></textarea>
            <button class="btn btn-primary" style="margin-top:12px" onclick="genComs()">💬 ولّد تعليقات</button>
            <div class="loader" id="l-com"><div class="loader-ring"></div></div>
            <div class="ai-box" id="r-com">
              <div class="ai-box-head"><div class="ai-tag">✦ تعليقات</div><button class="copy-btn" onclick="cpRes('r-com')">📋 نسخ</button></div>
              <div class="ai-content" id="t-com"></div>
            </div>
          </div>
        </div>

        <!-- ===== COMPARE ===== -->
        <div class="panel" id="panel-compare">
          <div class="section-head">
            <div class="section-icon-wrap">🔁</div>
            <div><div class="section-title">مقارن الفيديوهات</div><div class="section-sub">افهم لماذا يشتغل البعض ولا يشتغل الآخر</div></div>
          </div>
          <div class="card">
            <div class="compare-wrap">
              <div class="compare-side win">
                <div class="compare-side-label" style="color:var(--green)">✅ فيديو ناجح</div>
                <textarea class="f-textarea" id="cmpWin" rows="4" placeholder="صف الفيديو الناجح..."></textarea>
              </div>
              <div class="compare-side lose">
                <div class="compare-side-label" style="color:var(--red)">❌ فيديو فاشل</div>
                <textarea class="f-textarea" id="cmpLose" rows="4" placeholder="صف الفيديو الفاشل..."></textarea>
              </div>
            </div>
            <div style="margin-top:14px">
              <button class="btn btn-primary" onclick="cmpVids()">🔁 قارن وحلل</button>
            </div>
            <div class="loader" id="l-cmp"><div class="loader-ring"></div></div>
            <div class="ai-box" id="r-cmp">
              <div class="ai-box-head"><div class="ai-tag">✦ مقارنة</div><button class="copy-btn" onclick="cpRes('r-cmp')">📋 نسخ</button></div>
              <div class="ai-content" id="t-cmp"></div>
            </div>
          </div>
          <div class="card">
            <div class="card-title-row"><div class="card-title"><div class="card-badge">📊</div>سجل الأداء</div></div>
            <div class="g2">
              <div class="f-group">
                <div class="f-label">اسم الفيديو</div>
                <input class="f-input" id="perfTit" placeholder="اسم الفيديو...">
              </div>
              <div class="f-group">
                <div class="f-label">المشاهدات</div>
                <input class="f-input" id="perfVws" type="number" placeholder="1000">
              </div>
            </div>
            <div class="g2">
              <div class="f-group">
                <div class="f-label">التقييم</div>
                <select class="f-select" id="perfRat">
                  <option>⭐</option><option>⭐⭐</option><option>⭐⭐⭐</option>
                  <option>⭐⭐⭐⭐</option><option>⭐⭐⭐⭐⭐</option>
                </select>
              </div>
              <div style="display:flex;align-items:flex-end;padding-bottom:18px">
                <button class="btn btn-primary" style="width:100%" onclick="addPerf()">+ أضف للسجل</button>
              </div>
            </div>
            <div id="perfList"></div>
          </div>
        </div>

        <!-- ===== PLAN ===== -->
        <div class="panel" id="panel-plan">
          <div class="section-head">
            <div class="section-icon-wrap">📅</div>
            <div><div class="section-title">خطة المحتوى</div><div class="section-sub">خطة أسبوعية كاملة بـ AI</div></div>
          </div>
          <div class="card">
            <div class="f-group">
              <div class="f-label">🎯 نوع قناتك</div>
              <textarea class="f-textarea" id="planChan" rows="2" placeholder="كوميدي، تحفيزي، يومي..."></textarea>
            </div>
            <div class="f-group">
              <div class="f-label">🎬 تردد النشر أسبوعياً</div>
              <select class="f-select" id="planFreq">
                <option>3 فيديوهات</option><option>5 فيديوهات</option>
                <option>7 فيديوهات (يومي)</option><option>10 فيديوهات</option>
              </select>
            </div>
            <button class="btn btn-primary" onclick="genPlan()">📅 ولّد الخطة الأسبوعية</button>
            <div class="loader" id="l-plan"><div class="loader-ring"></div></div>
            <div class="ai-box" id="r-plan">
              <div class="ai-box-head"><div class="ai-tag">✦ خطة</div><button class="copy-btn" onclick="cpRes('r-plan')">📋 نسخ</button></div>
              <div class="ai-content" id="t-plan"></div>
            </div>
          </div>
          <div class="card">
            <div class="card-title-row"><div class="card-title"><div class="card-badge">📖</div>مكتبة القوالب (50+)</div></div>
            <div class="f-group">
              <div class="f-label">نوع القالب</div>
              <select class="f-select" id="tmpType">
                <option>فضول وإثارة</option><option>تحدي مستحيل</option><option>سر لا يعرفه أحد</option>
                <option>خطأ شائع</option><option>قبل وبعد</option><option>رد فعل</option>
                <option>عد تنازلي</option><option>سؤال محرج</option>
              </select>
            </div>
            <button class="btn btn-primary" onclick="getTmpl()">📖 احصل على القالب</button>
            <div class="loader" id="l-tmp"><div class="loader-ring"></div></div>
            <div class="ai-box" id="r-tmp">
              <div class="ai-box-head"><div class="ai-tag">✦ قالب</div><button class="copy-btn" onclick="cpRes('r-tmp')">📋 نسخ</button></div>
              <div class="ai-content" id="t-tmp"></div>
            </div>
          </div>
        </div>

        <!-- ===== HASHTAGS ===== -->
        <div class="panel" id="panel-hashtags">
          <div class="section-head">
            <div class="section-icon-wrap">🔑</div>
            <div><div class="section-title">بنك الهاشتاقات</div><div class="section-sub">هاشتاقات مخصصة لأقصى وصول</div></div>
          </div>
          <div class="card">
            <div class="f-group">
              <div class="f-label">📹 موضوع الفيديو</div>
              <textarea class="f-textarea" id="hashDesc" rows="3" placeholder="موضوع الفيديو..."></textarea>
            </div>
            <button class="btn btn-primary" onclick="genHash()">🔑 ولّد الهاشتاقات</button>
            <div class="loader" id="l-hash"><div class="loader-ring"></div></div>
            <div class="ai-box" id="r-hash">
              <div class="ai-box-head"><div class="ai-tag">✦ هاشتاقات</div><button class="copy-btn" onclick="cpRes('r-hash')">📋 نسخ</button></div>
              <div class="ai-content" id="t-hash"></div>
            </div>
          </div>
          <div class="card">
            <div class="card-title-row"><div class="card-title"><div class="card-badge">🌐</div>مقارنة المنصات</div></div>
            <textarea class="f-textarea" id="platDesc" rows="3" placeholder="صف المحتوى..."></textarea>
            <button class="btn btn-primary" style="margin-top:12px" onclick="cmpPlat()">🌐 قارن المنصات</button>
            <div class="loader" id="l-plat"><div class="loader-ring"></div></div>
            <div class="ai-box" id="r-plat">
              <div class="ai-box-head"><div class="ai-tag">✦ منصات</div><button class="copy-btn" onclick="cpRes('r-plat')">📋 نسخ</button></div>
              <div class="ai-content" id="t-plat"></div>
            </div>
          </div>
        </div>

        <!-- ===== QUALITY ===== -->
        <div class="panel" id="panel-quality">
          <div class="section-head">
            <div class="section-icon-wrap">🌈</div>
            <div><div class="section-title">مدقق الجودة</div><div class="section-sub">تحقق من كل شروط الأضواء قبل النشر</div></div>
          </div>
          <div class="card">
            <div class="card-title-row">
              <div class="card-title"><div class="card-badge">✅</div>قائمة التحقق</div>
              <div class="btn-row">
                <button class="btn btn-success" onclick="chkAll()">✅ كل شي</button>
                <button class="btn btn-ghost" onclick="resetChk()">🔄 إعادة</button>
              </div>
            </div>
            <div class="check-list" id="qualChk"></div>
            <div class="quality-score" id="qScore">
              <div class="q-pct" id="qPct">0%</div>
              <div class="q-label">جاهزية الفيديو للنشر</div>
            </div>
          </div>
          <div class="card">
            <div class="card-title-row"><div class="card-title"><div class="card-badge">⏱</div>محسّن المدة</div></div>
            <textarea class="f-textarea" id="durDesc" rows="3" placeholder="موضوع الفيديو..."></textarea>
            <button class="btn btn-primary" style="margin-top:12px" onclick="optDur()">⏱ حدد المدة المثالية</button>
            <div class="loader" id="l-dur"><div class="loader-ring"></div></div>
            <div class="ai-box" id="r-dur">
              <div class="ai-box-head"><div class="ai-tag">✦ مدة</div><button class="copy-btn" onclick="cpRes('r-dur')">📋 نسخ</button></div>
              <div class="ai-content" id="t-dur"></div>
            </div>
          </div>
        </div>

        <!-- ===== ACHIEVEMENTS ===== -->
        <div class="panel" id="panel-achievements">
          <div class="section-head">
            <div class="section-icon-wrap">🏆</div>
            <div><div class="section-title">الإنجازات والنقاط</div><div class="section-sub">تابع تقدمك وافتح الإنجازات</div></div>
          </div>
          <div class="g2" style="margin-bottom:18px">
            <div class="card" style="text-align:center">
              <div style="font-size:42px;font-weight:900;color:var(--gold);font-family:'Tajawal',sans-serif" id="achPts">0</div>
              <div style="color:var(--text2);font-size:13px">⭐ إجمالي النقاط</div>
            </div>
            <div class="card" style="text-align:center">
              <div style="font-size:42px;font-weight:900;color:var(--gold);font-family:'Tajawal',sans-serif" id="achBdg">0</div>
              <div style="color:var(--text2);font-size:13px">🏅 إنجاز مفتوح</div>
            </div>
          </div>
          <div class="card">
            <div class="badges-grid" id="badgesGrid"></div>
          </div>
        </div>

        <!-- ===== HISTORY ===== -->
        <div class="panel" id="panel-history">
          <div class="section-head">
            <div class="section-icon-wrap">📖</div>
            <div><div class="section-title">سجل الجلسات</div><div class="section-sub">آخر 20 جلسة</div></div>
          </div>
          <div class="card">
            <div class="card-title-row">
              <div class="card-title"><div class="card-badge">📖</div>السجل</div>
              <button class="btn btn-danger" onclick="clearHist()">🗑️ مسح السجل</button>
            </div>
            <div id="histList"><div style="color:var(--text3);font-size:14px;padding:20px;text-align:center">ما في سجل بعد 📭</div></div>
          </div>
        </div>

        <!-- ===== LAUNCH ===== -->
        <div class="panel" id="panel-launch">
          <div class="section-head">
            <div class="section-icon-wrap">🚀</div>
            <div><div class="section-title">إطلاق الفيديو</div><div class="section-sub">الخطوة النهائية قبل النشر</div></div>
          </div>

          <div class="snap-hero">
            <div class="snap-ghost">👻</div>
            <div class="snap-hero-title">جاهز تنشر على الأضواء؟</div>
            <div class="snap-hero-sub">تأكد من إكمال كل الخطوات ثم افتح سناب شات مباشرة</div>
            <button class="btn btn-snap" onclick="openSnap()">👻 افتح سناب شات الآن</button>
          </div>

          <div class="card">
            <div class="card-title-row"><div class="card-title"><div class="card-badge">✅</div>قائمة التحقق النهائية</div></div>
            <div class="check-list" id="launchChk"></div>
          </div>

          <div class="card">
            <div class="final-title-row">🎬 بطاقة الفيديو الكاملة</div>
            <div class="final-card">
              <div class="final-row"><div class="final-lbl">📝 العنوان</div><div class="final-val" id="fTit">—</div></div>
              <div class="final-row"><div class="final-lbl">⏱ المدة المثالية</div><div class="final-val" id="fDur">—</div></div>
              <div class="final-row"><div class="final-lbl">⏰ وقت النشر</div><div class="final-val" id="fTime">—</div></div>
              <div class="final-row"><div class="final-lbl">🔑 الهاشتاقات</div><div class="final-val" id="fHash">—</div></div>
              <div class="final-row"><div class="final-lbl">📊 توقع الأداء</div><div class="final-val" id="fPred">—</div></div>
            </div>
            <div class="btn-row" style="margin-top:16px">
              <button class="btn btn-primary" onclick="genFinal()">🤖 ولّد تقرير نهائي</button>
              <button class="btn btn-ghost" onclick="copyAll()">📋 نسخ كل شي</button>
              <button class="btn btn-snap" onclick="openSnap()">👻 سناب</button>
              <button class="btn btn-danger" onclick="openModal('clearModal')">🗑️ مسح وابدأ من جديد</button>
            </div>
            <div class="loader" id="l-fin"><div class="loader-ring"></div></div>
            <div class="ai-box" id="r-fin">
              <div class="ai-box-head"><div class="ai-tag">✦ تقرير نهائي</div><button class="copy-btn" onclick="cpRes('r-fin')">📋 نسخ</button></div>
              <div class="ai-content" id="t-fin"></div>
            </div>
          </div>
        </div>

      </div><!-- /content -->
    </div><!-- /main -->
  </div><!-- /layout -->
</div><!-- /app -->

<!-- TOAST -->
<div class="toast" id="toast">
  <span id="toastIco">✅</span>
  <span id="toastTxt">تم!</span>
</div>

<script>
// ======= AUTH =======
const PWD_B64 = 'U3NAMTEyMjMzNDQ1NQ==';
let tries = 0;
let sessInt, cdInt, sessS = 0;

let D = {
  videos:0,titles:0,saved:[],points:0,streak:0,
  history:[],performance:[],
  curTitle:'',curDur:'',curHash:'',curPred:'',
  titType:'curiosity'
};
try { const s = localStorage.getItem('adwaapro'); if(s) D={...D,...JSON.parse(s)}; } catch(e){}
function save(){ try{localStorage.setItem('adwaapro',JSON.stringify(D));}catch(e){} }

function toggleEye(){
  const i=document.getElementById('pwdIn');
  i.type=i.type==='password'?'text':'password';
}

function doLogin(){
  const v=document.getElementById('pwdIn').value;
  if(btoa(v)===PWD_B64){
    const s=document.getElementById('loginScreen');
    s.style.transition='opacity 0.6s ease,transform 0.6s ease';
    s.style.opacity='0';s.style.transform='translateY(-20px)';
    setTimeout(()=>{s.style.display='none';document.getElementById('app').style.display='block';initApp();},600);
  } else {
    tries++;
    const e=document.getElementById('loginErr');
    e.style.display='block';e.style.animation='none';
    setTimeout(()=>e.style.animation='shake 0.5s ease',10);
    document.getElementById('loginTries').textContent=tries>=3?`تنبيه: ${tries} محاولات فاشلة`:'';
    document.getElementById('pwdIn').value='';
    if(tries>=5){e.textContent='🚫 تم قفل الدخول لمدة 30 ثانية';setTimeout(()=>{tries=0;e.textContent='⚠️ كلمة المرور غير صحيحة';},30000);}
  }
}

function doLogout(){
  clearInterval(sessInt);clearInterval(cdInt);
  document.getElementById('app').style.display='none';
  document.getElementById('loginScreen').style.cssText='';
  document.getElementById('pwdIn').value='';
  sessS=0;document.getElementById('sessTime').textContent='00:00';
}

// ======= INIT =======
function initApp(){
  updStats();initPeaks();initQual();initLaunch();initBadges();
  renderSaved();renderPerf();renderHist();
  sessInt=setInterval(()=>{
    sessS++;
    document.getElementById('sessTime').textContent=
      String(Math.floor(sessS/60)).padStart(2,'0')+':'+String(sessS%60).padStart(2,'0');
  },1000);
  startCd();
  setTimeout(doLogout,30*60*1000);
}

function updStats(){
  document.getElementById('sv').textContent=D.videos;
  document.getElementById('st').textContent=D.titles;
  document.getElementById('ss').textContent=D.saved.length;
  document.getElementById('sp').textContent=D.points;
  document.getElementById('sk').textContent=D.streak;
  document.getElementById('achPts').textContent=D.points;
}

// ======= NAV =======
const PANEL_TITLES={
  ideas:'أفكار الفيديو',saved:'فيديوهاتي',analyzer:'محلل الفيديو',
  timing:'أوقات الذروة',titles:'مولد العناوين',psychology:'علم النفس البصري',
  script:'كاتب السكريبت',abtest:'مختبر A/B',compare:'مقارن الفيديوهات',
  plan:'خطة المحتوى',hashtags:'بنك الهاشتاقات',quality:'مدقق الجودة',
  achievements:'الإنجازات',history:'السجل',launch:'إطلاق الفيديو'
};

function goPanel(name,el){
  document.querySelectorAll('.panel').forEach(p=>p.classList.remove('active'));
  document.querySelectorAll('.nav-item').forEach(n=>n.classList.remove('active'));
  document.getElementById('panel-'+name).classList.add('active');
  if(el)el.classList.add('active');
  document.getElementById('pageTitle').textContent=PANEL_TITLES[name]||'';
  if(name==='launch')updFinal();
  if(name==='achievements')initBadges();
}

function toggleSidebar(){
  document.getElementById('sidebar').classList.toggle('expanded');
}

function toggleTheme(){
  document.body.classList.toggle('light-mode');
  document.getElementById('themeLabel').textContent=
    document.body.classList.contains('light-mode')?'نهاري':'ليلي';
}

// ======= AI =======
async function ai(prompt,lid,rid,tid,cb){
  const L=document.getElementById(lid);
  const R=document.getElementById(rid);
  const T=document.getElementById(tid);
  L.classList.add('on');R.classList.remove('show');
  try{
    const res=await fetch('https://api.anthropic.com/v1/messages',{
      method:'POST',
      headers:{'Content-Type':'application/json'},
      body:JSON.stringify({
        model:'claude-sonnet-4-20250514',max_tokens:1000,
        messages:[{role:'user',content:prompt}]
      })
    });
    const d=await res.json();
    const txt=d.content?.map(i=>i.text||'').join('')||'حدث خطأ';
    T.textContent=txt;R.classList.add('show');
    addHist(prompt.substring(0,60)+'...');
    if(cb)cb(txt);
  }catch(e){T.textContent='⚠️ خطأ في الاتصال. حاول مرة ثانية.';R.classList.add('show');}
  finally{L.classList.remove('on');}
}

// ======= IDEAS =======
function generateIdeas(){
  const tags=[...document.querySelectorAll('#typeTags .tag.on')].map(t=>t.textContent.trim()).join('، ');
  const desc=document.getElementById('ideaDesc').value;
  ai(`أنت خبير في منصة الأضواء (Snapchat Spotlight) وخوارزمياتها.
ولّد 5 أفكار فيديو إبداعية لمنصة الأضواء.
نوع المحتوى: ${tags}${desc?'\nوصف: '+desc:''}
لكل فكرة: الفكرة، لماذا تجذب نفسياً، ما يجعل الناس يعيدونها، المدة المثالية، نقطة التشويق.
اكتب بالعربية.`,
  'l-ideas','r-ideas','t-ideas',()=>{D.videos++;D.points+=10;save();updStats();toast('⚡','أفكار جاهزة! +10 نقاط');});
}

function generateHook(){
  const desc=document.getElementById('ideaDesc').value||'محتوى عام';
  ai(`أنت خبير Hook لفيديوهات الأضواء.
اكتب 5 Hook احترافية لـ: ${desc}
كل Hook: 3 ثواني أو أقل، يخلق فضول، يستخدم Open Loop، يجبر على الإكمال.
فسّر لماذا كل Hook فعّال. اكتب بالعربية.`,
  'l-ideas','r-ideas','t-ideas',()=>toast('🎯','Hooks جاهزة!'));
}

function predictPerf(){
  const desc=document.getElementById('predDesc').value;
  if(!desc)return toast('⚠️','صف فيديوك أولاً');
  ai(`أنت محلل خوارزميات الأضواء.
الفيديو: ${desc}
أعطني: توقع المشاهدات 24h و7d، احتمال الانتشار (رقم 0-100)، احتمال الإعادة (رقم 0-100)، أقوى 3 نقاط، أضعف 3 نقاط مع تحسينها. اكتب بالعربية.`,
  'l-pred','r-pred','t-pred',(txt)=>{
    const v=Math.floor(Math.random()*40+40);const r=Math.floor(Math.random()*30+35);
    document.getElementById('vPct').textContent=v+'%';document.getElementById('rPct').textContent=r+'%';
    setTimeout(()=>{document.getElementById('vBar').style.width=v+'%';document.getElementById('rBar').style.width=r+'%';},100);
    D.curPred=`انتشار ${v}% - إعادة ${r}%`;save();toast('🔮','التنبؤ جاهز!');
  });
}

// ======= ANALYZER =======
function analyzeVid(){
  const desc=document.getElementById('anaDesc').value;
  if(!desc)return toast('⚠️','صف فيديوك أولاً');
  const dur=document.getElementById('vidDur').value;
  const rat=document.getElementById('vidRat').value;
  ai(`أنت خبير تحرير فيديو للأضواء.
الفيديو: ${desc}\nالمدة: ${dur}\nالنسبة: ${rat}
قدم: توصيات الألوان والإضاءة، توصيات المونتاج، التحسينات التقنية، توصيات الصوت، أخطاء تسبب الحذف، ما يضمن المليون مشاهدة، إعدادات CapCut المحددة. اكتب بالعربية.`,
  'l-ana','r-ana','t-ana',()=>{D.videos++;D.points+=15;save();updStats();toast('🎬','التحليل جاهز! +15 نقاط');});
}

function analyzeRet(){
  const desc=document.getElementById('anaDesc').value||'محتوى عام';
  ai(`أنت خبير Retention Rate للأضواء.
الفيديو: ${desc}
اشرح: استراتيجية Retention كاملة، متى يغادر المشاهدون وكيف تمنع ذلك، ما يجعل الناس يعيدون 3 مرات، كيف تبني Loop نفسي، 3 تقنيات إبقاء محددة. اكتب بالعربية.`,
  'l-ana','r-ana','t-ana',()=>toast('💎','تحليل Retention جاهز!'));
}

function analyzeHk(){
  const desc=document.getElementById('anaDesc').value||'محتوى عام';
  ai(`أنت خبير Hook للفيديوهات القصيرة.
الفيديو: ${desc}
احكم على الـ Hook: تقييم من 10، هل يخلق فضول كافي، هل يصلح لأول 3 ثواني، 3 تحسينات محددة، Hook بديل أقوى. اكتب بالعربية.`,
  'l-ana','r-ana','t-ana',()=>toast('🎯','تحليل Hook جاهز!'));
}

function measureDopa(){
  const desc=document.getElementById('dopDesc').value;
  if(!desc)return toast('⚠️','صف الفيديو أولاً');
  ai(`أنت خبير علم الأعصاب والتسويق.
الفيديو: ${desc}
قيّم: مستوى الدوبامين (رقم 0-100)، العناصر المثيرة، كيف ترفع المستوى، أكثر لحظة ستفرز دوبامين، 3 إضافات تجعل الدماغ يطلب المزيد. اكتب بالعربية.`,
  'l-dop','r-dop','t-dop',(txt)=>{
    const s=Math.floor(Math.random()*40+45);
    document.getElementById('dopPct').textContent=s+'/100';
    setTimeout(()=>document.getElementById('dopBar').style.width=s+'%',100);
    toast('⚡','قياس الدوبامين جاهز!');
  });
}

// ======= TIMING =======
const PEAKS=[
  {t:'08:00',n:'صباح الخير',c:'warm',l:'متوسط 🟡'},
  {t:'12:00',n:'وقت الغداء',c:'warm',l:'جيد 🟡'},
  {t:'15:00',n:'بعد الظهر',c:'cool',l:'منخفض 🔵'},
  {t:'18:00',n:'المساء',c:'hot',l:'ممتاز 🔴'},
  {t:'20:00',n:'السهرة',c:'hot',l:'الأفضل 🔥'},
  {t:'22:00',n:'الليل',c:'hot',l:'ممتاز 🔴'},
  {t:'00:00',n:'منتصف الليل',c:'warm',l:'جيد 🟡'},
];

function initPeaks(){
  const now=new Date().getHours();
  document.getElementById('peakGrid').innerHTML=PEAKS.map(p=>{
    const ph=parseInt(p.t);
    const isNow=Math.abs(ph-now)<=1;
    return `<div class="peak-tile ${isNow?'now':''}">
      <div class="peak-time-big">${p.t}</div>
      <div class="peak-name-sm">${p.n}</div>
      <div class="peak-pill ${p.c}">${p.l}</div>
      ${isNow?'<div class="now-badge">◉ الآن</div>':''}
    </div>`;
  }).join('');
}

function startCd(){
  cdInt=setInterval(()=>{
    const now=new Date();const h=now.getHours();
    let next=[18,20,22].find(x=>h<x)||(18+24);
    const tgt=new Date();tgt.setHours(next%24,0,0,0);
    if(next>=24)tgt.setDate(tgt.getDate()+1);
    const d=tgt-now;
    document.getElementById('cdTime').textContent=
      String(Math.floor(d/3600000)).padStart(2,'0')+':'+
      String(Math.floor((d%3600000)/60000)).padStart(2,'0')+':'+
      String(Math.floor((d%60000)/1000)).padStart(2,'0');
    document.getElementById('cdNext').textContent=`الذروة القادمة الساعة ${next%24}:00`;
  },1000);
}

function setRem(){
  const t=document.getElementById('remTime').value;
  document.getElementById('t-rem').textContent=`✅ تم ضبط التذكير الساعة ${t}\nستُذكَّر قبل 15 دقيقة من وقت النشر.`;
  document.getElementById('r-rem').classList.add('show');
  toast('🔔',`تذكير مضبوط: ${t}`);
}

function detectTrend(){
  const per=document.getElementById('trendPer').value;
  ai(`أنت خبير ترندات الأضواء في السعودية والخليج.
الفترة: ${per}
حدد: أكثر 5 أنواع محتوى مشاهدة، الأنماط قبل الترند، الأسلوب المناسب، 3 أفكار استباقية، أفضل المواضيع. اكتب بالعربية.`,
  'l-trend','r-trend','t-trend',()=>toast('📡','رادار الترند جاهز!'));
}

// ======= TITLES =======
function selTitType(type,el){
  document.querySelectorAll('[onclick^="selTitType"]').forEach(t=>t.classList.remove('on'));
  el.classList.add('on');D.titType=type;
}

function genTitles(){
  const desc=document.getElementById('titDesc').value;
  if(!desc)return toast('⚠️','صف الفيديو أولاً');
  const types={curiosity:'فضول',shock:'صدمة',challenge:'تحدي',secret:'سر',number:'أرقام'};
  ai(`أنت خبير عناوين للأضواء.
الفيديو: ${desc}\nالنوع: ${types[D.titType]||'فضول'}
اكتب 5 عناوين: لا تتجاوز 50 حرف، تخلق رغبة لا تقاوم، تستخدم تقنيات نفسية، مناسبة للخليج، تجعل الناس يعيدون الفيديو.
بعد كل عنوان: لماذا هو فعّال نفسياً. اكتب بالعربية.`,
  'l-tit','r-tit','t-tit',(txt)=>{
    D.titles++;D.points+=5;
    D.curTitle=txt.split('\n')[0]?.replace(/^[^:]+:/,'').trim()||'';
    save();updStats();toast('✍️','العناوين جاهزة! +5 نقاط');
  });
}

function genPattern(){
  const desc=document.getElementById('patDesc').value||'محتوى عام';
  ai(`أنت خبير Pattern Interrupt للأضواء.
الفيديو: ${desc}
صمم 5 لحظات صدمة: متى تحدث (الثانية)، ما هي بالضبط، لماذا تمنع الخروج، كيف تجبر على الإعادة. اكتب بالعربية.`,
  'l-pat','r-pat','t-pat',()=>toast('🎪','Pattern Interrupts جاهزة!'));
}

// ======= PSYCHOLOGY =======
function anaPsy(){
  const desc=document.getElementById('psyDesc').value;
  if(!desc)return toast('⚠️','صف الفيديو أولاً');
  ai(`أنت خبير Gestalt Psychology للأضواء.
المشهد: ${desc}
حلل: مبادئ Gestalt، تأثير الألوان، التكوين البصري، العناصر التي توقف العين، ما يجذب الانتباه أولاً، 5 تحسينات بصرية محددة. اكتب بالعربية.`,
  'l-psy','r-psy','t-psy',()=>toast('🧠','التحليل النفسي جاهز!'));
}

function anaAida(){
  const desc=document.getElementById('aidaDesc').value;
  if(!desc)return toast('⚠️','صف الفيديو أولاً');
  ai(`أنت خبير AIDA للأضواء.
الفيديو: ${desc}
تحقق: Attention (0-10)، Interest (0-10)، Desire (0-10)، Action (0-10).
لكل عنصر: التقييم، نقاط الضعف، كيف تحسنه. التقييم الكلي والتوصية. اكتب بالعربية.`,
  'l-aida','r-aida','t-aida',()=>toast('🎯','تحليل AIDA جاهز!'));
}

function anaEmo(){
  const desc=document.getElementById('emoDesc').value;
  if(!desc)return toast('⚠️','صف الفيديو أولاً');
  ai(`أنت خبير علم المشاعر للأضواء.
الفيديو: ${desc}
صنّف: الضحك، الصدمة، الفضول، الإلهام، التعاطف، الغضب.
لكل مشاعر: درجة وجوده (%)، تأثيره على المشاهدة. الخلاصة والتوصية. اكتب بالعربية.`,
  'l-emo','r-emo','t-emo',()=>toast('🎭','تحليل المشاعر جاهز!'));
}

// ======= SCRIPT =======
function genScript(){
  const idea=document.getElementById('scrIdea').value;
  if(!idea)return toast('⚠️','أدخل فكرة الفيديو');
  ai(`أنت كاتب سكريبت للأضواء.
الفكرة: ${idea}\nالمدة: ${document.getElementById('scrDur').value}\nالأسلوب: ${document.getElementById('scrSty').value}
اكتب سكريبت كامل: Hook (0-3ث)، النص المنطوق، موسيقى ومؤثرات، وصف المشاهد، Pattern Interrupts، النهاية المثالية. اكتب بالعربية.`,
  'l-scr','r-scr','t-scr',()=>{D.points+=20;save();updStats();toast('📝','السكريبت جاهز! +20 نقاط');});
}

function anaAud(){
  const desc=document.getElementById('audDesc').value;
  if(!desc)return toast('⚠️','صف محتواك');
  ai(`أنت خبير تحليل جمهور الأضواء.
المحتوى: ${desc}
حدد: الفئة العمرية المثالية، الدول، وقت النشاط، ماذا يريدون، كيف تكتب لهم مباشرة، كيف تجعلهم يشاركون. اكتب بالعربية.`,
  'l-aud','r-aud','t-aud',()=>toast('🧲','تحليل الجمهور جاهز!'));
}

// ======= AB TEST =======
function runAB(){
  const topic=document.getElementById('abTopic').value;
  if(!topic)return toast('⚠️','أدخل الموضوع');
  ai(`أنت خبير A/B Testing للأضواء.
الموضوع: ${topic}
اكتب 5 عناوين مختلفة تماماً. لكل عنوان: العنوان، احتمالية النقر (%)، التقنية النفسية، الجمهور. في النهاية: أي عنوان تختار ولماذا. اكتب بالعربية.`,
  'l-ab','r-ab','t-ab',(txt)=>{
    const lines=txt.split('\n').filter(l=>l.trim().length>10).slice(0,5);
    document.getElementById('abList').innerHTML=lines.map((l,i)=>{
      const p=l.match(/(\d+)%/)?.[1]||(78-i*5);
      return `<div class="ab-row ${i===0?'best':''}">
        <span style="font-size:13px">${l.replace(/\d+%/,'').trim().substring(0,70)}</span>
        <span class="ab-pct">${p}%</span>
      </div>`;
    }).join('');
    toast('🧪','A/B Test جاهز!');
  });
}

function genComs(){
  const desc=document.getElementById('comDesc').value;
  if(!desc)return toast('⚠️','صف الفيديو');
  ai(`أنت خبير Community Management للأضواء.
الفيديو: ${desc}
اكتب: 5 تعليقات تحفز النقاش، 3 أسئلة تجبر على الرد، 2 تحدي للمشاركة، رد على التعليقات السلبية، Call to Action. اكتب بالعربية.`,
  'l-com','r-com','t-com',()=>toast('💬','التعليقات جاهزة!'));
}

// ======= COMPARE =======
function cmpVids(){
  const w=document.getElementById('cmpWin').value;
  const l=document.getElementById('cmpLose').value;
  if(!w||!l)return toast('⚠️','صف الفيديوين');
  ai(`أنت محلل محتوى للأضواء.
فيديو ناجح: ${w}\nفيديو فاشل: ${l}
قارن: لماذا نجح الأول (5 أسباب)، لماذا فشل الثاني (5 أسباب)، الفرق الجوهري، كيف تحول الفاشل لناجح، الدرس الأساسي. اكتب بالعربية.`,
  'l-cmp','r-cmp','t-cmp',()=>toast('🔁','المقارنة جاهزة!'));
}

function addPerf(){
  const t=document.getElementById('perfTit').value;
  if(!t)return toast('⚠️','أدخل اسم الفيديو');
  D.performance.push({t,v:parseInt(document.getElementById('perfVws').value)||0,r:document.getElementById('perfRat').value,d:new Date().toLocaleDateString('ar')});
  save();renderPerf();
  document.getElementById('perfTit').value='';document.getElementById('perfVws').value='';
  toast('📊','تم الإضافة!');
}

function renderPerf(){
  const el=document.getElementById('perfList');
  if(!D.performance.length){el.innerHTML='';return;}
  el.innerHTML=D.performance.map((p,i)=>`
    <div class="perf-row">
      <div><div style="font-weight:700;font-size:14px">${p.t}</div><div style="font-size:12px;color:var(--text3)">${p.d}</div></div>
      <div style="display:flex;align-items:center;gap:12px">
        <span style="font-size:13px;color:var(--gold)">${p.v.toLocaleString()} 👁</span>
        <span style="font-size:12px">${p.r}</span>
        <button onclick="D.performance.splice(${i},1);save();renderPerf()" style="background:none;border:none;color:var(--red);cursor:pointer;font-size:16px">×</button>
      </div>
    </div>`).join('');
}

// ======= PLAN =======
function genPlan(){
  ai(`أنت مدير محتوى للأضواء.
النوع: ${document.getElementById('planChan').value||'عام'}\nالتردد: ${document.getElementById('planFreq').value}
خطة أسبوعية: كل يوم (موضوع+نوع+وقت+Hook). أضف: الهدف الأسبوعي، استراتيجية النمو، الفيديو المتوقع انفجاره، كيف تبني momentum أسبوعي. اكتب بالعربية.`,
  'l-plan','r-plan','t-plan',()=>toast('📅','الخطة الأسبوعية جاهزة!'));
}

function getTmpl(){
  ai(`أنت خبير قوالب الأضواء.
القالب: ${document.getElementById('tmpType').value}
قدم قالب كامل: هيكل الفيديو ثانية بثانية، نص Hook، وصف المشاهد، الموسيقى المناسبة، المدة المثالية، 3 عناوين جاهزة، أمثلة ناجحة. اكتب بالعربية.`,
  'l-tmp','r-tmp','t-tmp',()=>toast('📖','القالب جاهز!'));
}

// ======= HASHTAGS =======
function genHash(){
  const desc=document.getElementById('hashDesc').value;
  if(!desc)return toast('⚠️','صف الفيديو');
  ai(`أنت خبير هاشتاقات الأضواء في السعودية.
الفيديو: ${desc}
ولّد: 5 هاشتاقات ترند، 10 مخصصة للموضوع، 5 للنمو، 3 للجمهور الدولي. استراتيجية ترتيب الهاشتاقات، هاشتاقات يجب تجنبها. اكتب بالعربية.`,
  'l-hash','r-hash','t-hash',(txt)=>{
    D.curHash=txt.match(/#\w+/g)?.slice(0,5).join(' ')||'';save();toast('🔑','الهاشتاقات جاهزة!');
  });
}

function cmpPlat(){
  const desc=document.getElementById('platDesc').value;
  if(!desc)return toast('⚠️','صف المحتوى');
  ai(`أنت خبير متعدد المنصات.
المحتوى: ${desc}
قارن على الأضواء وتيك توك ويوتيوب Shorts: احتمال الانتشار، الجمهور الأنسب، التعديلات المطلوبة، أفضل وقت، Call to Action. التوصية النهائية. اكتب بالعربية.`,
  'l-plat','r-plat','t-plat',()=>toast('🌐','مقارنة المنصات جاهزة!'));
}

// ======= QUALITY =======
const QUAL_ITEMS=[
  'الفيديو بنسبة 9:16 (عمودي)',
  'الجودة 1080p أو أعلى',
  'المدة بين 5-60 ثانية',
  'لا توجد علامات مائية',
  'الصوت واضح وبجودة عالية',
  'الـ Hook في أول 3 ثواني',
  'لا توجد موسيقى محمية بحقوق ملكية',
  'المحتوى أصلي وغير مكرر',
  'لا يوجد محتوى يخالف سياسات سناب',
  'العنوان لا يتجاوز 50 حرف',
  'الهاشتاقات مضافة',
  'الإضاءة جيدة وواضحة',
  'السرعة والإيقاع مناسبان',
  'تم اختبار الفيديو قبل النشر',
  'النهاية قوية وتدفع للإعادة',
];

function initQual(){
  document.getElementById('qualChk').innerHTML=QUAL_ITEMS.map((item,i)=>`
    <div class="check-item" onclick="toggleChk(this)" data-i="${i}">
      <div class="chk">✓</div>
      <div class="chk-text">${item}</div>
    </div>`).join('');
}

function toggleChk(el){
  el.classList.toggle('done');updQScore();
}

function updQScore(){
  const tot=document.querySelectorAll('#qualChk .check-item').length;
  const done=document.querySelectorAll('#qualChk .check-item.done').length;
  const pct=Math.round(done/tot*100);
  const s=document.getElementById('qScore');s.style.display='block';
  document.getElementById('qPct').textContent=pct+'%';
  document.getElementById('qPct').style.color=pct>=80?'var(--green)':pct>=50?'var(--gold)':'var(--red)';
}

function chkAll(){
  document.querySelectorAll('#qualChk .check-item').forEach(el=>el.classList.add('done'));
  updQScore();toast('✅','كل الشروط مكتملة!');
}

function resetChk(){
  document.querySelectorAll('#qualChk .check-item').forEach(el=>el.classList.remove('done'));
  document.getElementById('qScore').style.display='none';
}

function optDur(){
  const desc=document.getElementById('durDesc').value;
  if(!desc)return toast('⚠️','صف الفيديو');
  ai(`أنت خبير Retention للأضواء.
موضوع الفيديو: ${desc}
حدد: المدة المثالية بالثانية (رقم دقيق)، لماذا هذه المدة، ماذا يحدث لو أقصر أو أطول، أين تضع لحظات التشويق، متى تنتهي بالضبط. اكتب بالعربية.`,
  'l-dur','r-dur','t-dur',(txt)=>{
    const m=txt.match(/\d+\s*ثانية/);if(m)D.curDur=m[0];save();toast('⏱','المدة المثالية محددة!');
  });
}

// ======= BADGES =======
const BADGES=[
  {ico:'🎬',n:'أول خطوة',req:'حلل فيديو واحد',need:1,type:'videos'},
  {ico:'🔟',n:'10 فيديوهات',req:'حلل 10 فيديوهات',need:10,type:'videos'},
  {ico:'💯',n:'100 فيديو',req:'حلل 100 فيديو',need:100,type:'videos'},
  {ico:'✍️',n:'كاتب',req:'ولّد 5 عناوين',need:5,type:'titles'},
  {ico:'📝',n:'محترف',req:'ولّد 20 عنوان',need:20,type:'titles'},
  {ico:'⭐',n:'100 نقطة',req:'اجمع 100 نقطة',need:100,type:'points'},
  {ico:'🏆',n:'500 نقطة',req:'اجمع 500 نقطة',need:500,type:'points'},
  {ico:'💾',n:'حافظ',req:'احفظ 5 فيديوهات',need:5,type:'saved'},
  {ico:'🔥',n:'7 أيام',req:'7 أيام متواصلة',need:7,type:'streak'},
  {ico:'👑',n:'ملك الأضواء',req:'اجمع 1000 نقطة',need:1000,type:'points'},
];

function initBadges(){
  const vals={videos:D.videos,titles:D.titles,points:D.points,saved:D.saved.length,streak:D.streak};
  let earned=0;
  document.getElementById('badgesGrid').innerHTML=BADGES.map(b=>{
    const ok=vals[b.type]>=b.need;if(ok)earned++;
    return `<div class="badge ${ok?'earned':'locked'}">
      <div class="badge-ico">${b.ico}</div>
      <div class="badge-name">${b.n}</div>
      <div class="badge-req">${b.req}</div>
    </div>`;
  }).join('');
  document.getElementById('achBdg').textContent=earned;
}

// ======= SAVED =======
function saveVid(){
  const t=document.getElementById('saveTit').value;
  if(!t)return toast('⚠️','أدخل عنوان الفيديو');
  D.saved.push({id:Date.now(),t,n:document.getElementById('saveNote').value,r:0,d:new Date().toLocaleDateString('ar')});
  save();updStats();renderSaved();
  document.getElementById('saveTit').value='';document.getElementById('saveNote').value='';
  toast('💾','تم الحفظ! +5 نقاط');D.points+=5;save();updStats();
}

function renderSaved(){
  const g=document.getElementById('savedGrid');
  if(!D.saved.length){g.innerHTML='<div style="color:var(--text3);font-size:14px;padding:24px;text-align:center;grid-column:1/-1">ما في فيديوهات محفوظة بعد 💭</div>';return;}
  g.innerHTML=D.saved.map((v,i)=>`
    <div class="saved-card">
      <button class="del-btn" onclick="delSaved(${i})">✕</button>
      <div class="saved-card-title">${v.t}</div>
      <div class="saved-card-notes">${v.n||'بدون ملاحظات'}</div>
      <div class="saved-card-date">📅 ${v.d}</div>
      <div class="stars">${[1,2,3,4,5].map(s=>`<span class="star ${v.r>=s?'on':''}" onclick="rateSaved(${i},${s})">★</span>`).join('')}</div>
    </div>`).join('');
}

function delSaved(i){D.saved.splice(i,1);save();updStats();renderSaved();toast('🗑️','تم الحذف');}
function rateSaved(i,r){D.saved[i].r=r;save();renderSaved();}

// ======= HISTORY =======
function addHist(t){
  D.history.unshift({t,d:new Date().toLocaleString('ar')});
  if(D.history.length>20)D.history=D.history.slice(0,20);
  save();renderHist();
}

function renderHist(){
  const el=document.getElementById('histList');
  if(!D.history.length){el.innerHTML='<div style="color:var(--text3);font-size:14px;padding:20px;text-align:center">ما في سجل بعد 📭</div>';return;}
  el.innerHTML=D.history.map(h=>`
    <div class="history-row">
      <div class="history-title">${h.t}</div>
      <div class="history-date">${h.d}</div>
    </div>`).join('');
}

function clearHist(){D.history=[];save();renderHist();toast('🗑️','تم مسح السجل');}

// ======= LAUNCH =======
const LAUNCH_ITEMS=[
  'الفيديو جاهز بجودة عالية',
  'العنوان الجذاب محدد',
  'الهاشتاقات مضافة',
  'وقت النشر في الذروة',
  'الـ Hook في أول 3 ثواني',
  'المدة المثالية محددة',
  'المحتوى أصلي ولا يخالف سياسات سناب',
  'تم مراجعة الفيديو مرة نهائية',
  'إعدادات الأضواء صحيحة',
];

function initLaunch(){
  document.getElementById('launchChk').innerHTML=LAUNCH_ITEMS.map((item,i)=>`
    <div class="check-item" onclick="this.classList.toggle('done')">
      <div class="chk">✓</div>
      <div class="chk-text">${item}</div>
    </div>`).join('');
}

function updFinal(){
  document.getElementById('fTit').textContent=D.curTitle||'—';
  document.getElementById('fDur').textContent=D.curDur||'—';
  document.getElementById('fHash').textContent=D.curHash||'—';
  document.getElementById('fPred').textContent=D.curPred||'—';
  const h=new Date().getHours();
  document.getElementById('fTime').textContent=h<18?'الساعة 20:00 الليلة 🌙':h<20?'قريبًا - الساعة 20:00 ⏰':'الآن هو الوقت المثالي! 🔥';
}

function genFinal(){
  ai(`أنت مستشار محتوى للأضواء.
الفيديو:
العنوان: ${D.curTitle||'غير محدد'}
المدة: ${D.curDur||'غير محدد'}
الهاشتاقات: ${D.curHash||'غير محدد'}
التنبؤ: ${D.curPred||'غير محدد'}
اكتب تقرير نشر نهائي: خطة الإطلاق، خطوات النشر، توقعات أول 24 ساعة، كيف تزيد المشاهدات، 3 نصائح ذهبية للمليون مشاهدة. اكتب بالعربية.`,
  'l-fin','r-fin','t-fin',()=>{D.points+=25;save();updStats();toast('🚀','التقرير النهائي جاهز! +25 نقطة');});
}

function openSnap(){
  window.location.href='snapchat://spotlight';
  setTimeout(()=>window.open('https://www.snapchat.com/spotlight','_blank'),500);
  toast('👻','فتح سناب شات...');
}

function copyAll(){
  const txt=`🌟 بطاقة فيديو الأضواء Pro
العنوان: ${D.curTitle}
المدة: ${D.curDur}
الهاشتاقات: ${D.curHash}
توقع الأداء: ${D.curPred}
وقت النشر المثالي: 20:00`;
  navigator.clipboard?.writeText(txt);toast('📋','تم نسخ كل شي!');
}

// ======= UTILS =======
function toggleTag(el){el.classList.toggle('on');}

function cpRes(rid){
  const txt=document.getElementById(rid).querySelector('.ai-content')?.textContent||'';
  navigator.clipboard?.writeText(txt);toast('📋','تم النسخ!');
}

function openModal(id){document.getElementById(id).classList.add('open');}
function closeModal(id){document.getElementById(id).classList.remove('open');}

function doClear(){
  D.curTitle='';D.curDur='';D.curHash='';D.curPred='';save();
  document.querySelectorAll('.ai-box').forEach(el=>el.classList.remove('show'));
  document.querySelectorAll('.f-input,.f-textarea').forEach(el=>el.value='');
  closeModal('clearModal');toast('🗑️','تم مسح كل البيانات');
}

function toast(ico,txt){
  const t=document.getElementById('toast');
  document.getElementById('toastIco').textContent=ico;
  document.getElementById('toastTxt').textContent=txt;
  t.classList.add('show');setTimeout(()=>t.classList.remove('show'),2800);
}

// auto-focus
document.addEventListener('DOMContentLoaded',()=>{
  document.getElementById('pwdIn').focus();
});
</script>
</body>
</html>
