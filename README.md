<!DOCTYPE html>

<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>LuxeStyle - Premium Branded Fashion</title>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
<link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@400;500;600;700&family=Pacifico&family=Caveat:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
:root{--primary:#D4A76A;--secondary:#8B4513;--accent:#FF6B35;--cream:#FFF8E7;--dbrown:#5C4033;--lbrown:#A67B5B;--beige:#F5E6D3;--dcream:#E8D8B6;--ok:#4CAF50;--err:#f44336;--gray:#999;--dbg:#1a1a1a;--dcard:#2d2d2d;--dtext:#e0e0e0;--dborder:#444}
body.dark{--cream:var(--dbg);--beige:var(--dcard);--dcream:var(--dborder);--dbrown:var(--dtext);--lbrown:#a0a0a0;background:var(--dbg)}
*{margin:0;padding:0;box-sizing:border-box}
body{font-family:'Caveat',cursive;font-size:22px;background:var(--cream);color:var(--dbrown);line-height:1.4;overflow-x:hidden;transition:background .3s,color .3s}
h1,h2,h3,h4{font-family:'Dancing Script',cursive;font-weight:600;color:var(--secondary);font-style:italic;transition:color .3s}
a{text-decoration:none;color:inherit;transition:all .3s}
button{font-family:'Caveat',cursive;font-size:22px;cursor:pointer;border:none;background:none}
.container{width:100%;max-width:1400px;margin:0 auto;padding:0 20px}

/* STARS */
.starry-bg{position:fixed;top:0;left:0;width:100%;height:100%;pointer-events:none;z-index:-1;opacity:0;transition:opacity .5s}
body.dark .starry-bg{opacity:1}
.star{position:absolute;background:#fff;border-radius:50%;animation:twinkle var(–d,4s) ease-in-out infinite}
@keyframes twinkle{0%,100%{opacity:.3;transform:scale(1)}50%{opacity:1;transform:scale(1.2)}}
.confetti-wrap{position:fixed;top:0;left:0;width:100%;height:100%;pointer-events:none;z-index:9998;overflow:hidden}
.confetti-piece{position:absolute;top:-20px;opacity:0}
@keyframes fall{0%{transform:translateY(0) rotate(0deg);opacity:1}100%{transform:translateY(110vh) rotate(720deg);opacity:0}}

/* HEADER */
header{background:var(–cream);position:fixed;width:100%;z-index:1000;padding:15px 0;box-shadow:0 5px 15px rgba(139,69,19,.1);transition:all .4s;border-bottom:2px solid var(–dcream)}
header.scrolled{padding:10px 0;box-shadow:0 8px 20px rgba(139,69,19,.15)}
body.dark header{background:var(–dcard);border-bottom-color:var(–dborder)}
.hd{display:flex;justify-content:space-between;align-items:center}
.logo{font-family:‘Pacifico’,cursive;font-size:32px;color:var(–primary);display:flex;align-items:center;gap:10px}
nav{display:flex}
nav ul{display:flex;list-style:none;gap:30px}
nav a{font-weight:600;font-size:24px;position:relative;padding:5px 0;color:var(–secondary)}
nav a::after{content:’’;position:absolute;width:0;height:2px;background:var(–primary);left:0;bottom:0;transition:width .3s}
nav a:hover::after{width:100%}
nav a:hover{color:var(–primary)}
.ha{display:flex;gap:15px;align-items:center}

/* SEARCH */
.srch-wrap{position:relative}
.srch-btn{width:45px;height:45px;background:var(–beige);border:2px solid var(–dcream);border-radius:50%;display:flex;align-items:center;justify-content:center;cursor:pointer;transition:all .3s;color:var(–secondary);font-size:18px}
.srch-btn:hover{background:var(–primary);border-color:var(–primary);color:var(–dbrown)}
.srch-drop{position:absolute;top:110%;right:0;background:var(–cream);border:2px solid var(–dcream);border-radius:10px;padding:15px;width:300px;box-shadow:0 5px 20px rgba(139,69,19,.2);display:none;z-index:1001}
body.dark .srch-drop{background:var(–dcard);border-color:var(–dborder)}
.srch-drop.open{display:block;animation:fdrop .3s ease}
@keyframes fdrop{from{opacity:0;transform:translateY(-8px)}to{opacity:1;transform:translateY(0)}}
.srch-row{position:relative;margin-bottom:10px}
.srch-inp{width:100%;padding:10px 40px 10px 15px;background:var(–beige);border:2px solid var(–dcream);border-radius:25px;font-family:‘Caveat’,cursive;font-size:18px;color:var(–dbrown);outline:none;transition:all .3s}
.srch-inp:focus{border-color:var(–primary)}
.srch-go{position:absolute;right:5px;top:50%;transform:translateY(-50%);width:30px;height:30px;background:var(–primary);border:none;border-radius:50%;color:var(–dbrown);cursor:pointer;display:flex;align-items:center;justify-content:center;transition:all .3s;font-size:14px}
.srch-go:hover{background:var(–accent);color:#fff}
.srch-res{max-height:280px;overflow-y:auto;border-top:1px solid var(–dcream);padding-top:10px;display:none}
.srch-res.open{display:block}
.srch-item{display:flex;align-items:center;padding:8px;border-bottom:1px solid var(–dcream);cursor:pointer;border-radius:5px;margin-bottom:4px;transition:all .2s}
.srch-item:hover{background:var(–beige);transform:translateX(4px)}
.srch-img{width:48px;height:48px;border-radius:5px;overflow:hidden;margin-right:10px;flex-shrink:0;border:1px solid var(–dcream)}
.srch-img img{width:100%;height:100%;object-fit:cover}
.srch-name{font-weight:600;font-size:16px;color:var(–secondary);white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.srch-price{color:var(–primary);font-size:14px;font-weight:600}
.srch-none{padding:10px;text-align:center;color:var(–lbrown);font-size:16px}
.srch-overlay{position:fixed;inset:0;background:transparent;z-index:1000;display:none}

/* THEME */
.theme-sw{width:50px;height:26px;background:var(–beige);border-radius:13px;position:relative;cursor:pointer;border:2px solid var(–dcream);transition:all .3s}
.theme-sw.on{background:var(–primary);border-color:var(–primary)}
.theme-knob{position:absolute;left:3px;top:3px;width:18px;height:18px;background:#fff;border-radius:50%;transition:transform .3s}
.theme-sw.on .theme-knob{transform:translateX(24px)}
.theme-sw .fa-sun{position:absolute;left:6px;top:50%;transform:translateY(-50%);font-size:12px;color:var(–dbrown)}
.theme-sw .fa-moon{position:absolute;right:6px;top:50%;transform:translateY(-50%);font-size:12px;color:var(–dbrown)}

/* LANG */
.lang-sel{position:relative;display:flex;align-items:center;gap:5px;cursor:pointer;font-weight:600;color:var(–secondary);padding:5px;border-radius:4px;font-size:20px;height:40px}
.lang-sel:hover{background:rgba(212,167,106,.1)}
.lang-flag{width:30px;height:20px;border-radius:2px;overflow:hidden;border:1px solid var(–dcream)}
.lang-flag img{width:100%;height:100%;object-fit:cover}
.lang-drop{position:absolute;top:100%;right:0;background:var(–beige);border-radius:5px;min-width:120px;box-shadow:0 5px 15px rgba(139,69,19,.2);opacity:0;visibility:hidden;transform:translateY(-10px);transition:all .3s;z-index:10;border:1px solid var(–dcream)}
body.dark .lang-drop{background:var(–dcard);border-color:var(–dborder)}
.lang-sel.open .lang-drop{opacity:1;visibility:visible;transform:translateY(5px)}
.lang-opt{display:flex;align-items:center;gap:10px;padding:10px 15px;transition:all .2s;color:var(–dbrown);cursor:pointer;font-family:‘Caveat’,cursive;font-size:18px}
.lang-opt:hover{background:rgba(212,167,106,.2)}

/* PROFILE BTN */
.prof-btn{width:42px;height:42px;border-radius:50%;background:linear-gradient(135deg,var(–primary),var(–secondary));border:2px solid var(–dcream);cursor:pointer;display:flex;align-items:center;justify-content:center;color:#fff;font-size:16px;transition:all .3s;flex-shrink:0}
.prof-btn:hover{transform:scale(1.08);box-shadow:0 4px 15px rgba(212,167,106,.4)}
.prof-btn .initials{font-family:‘Dancing Script’,cursive;font-size:18px;font-weight:700;color:#fff;line-height:1;display:none}
.prof-btn i{color:#fff}

/* CART ICON */
.cart-ic{position:relative;font-size:24px;cursor:pointer;color:var(–secondary);transition:color .3s}
.cart-ic:hover{color:var(–primary)}
.cart-ic.bounce{animation:cbounce .5s ease}
@keyframes cbounce{0%,100%{transform:scale(1)}50%{transform:scale(1.3)}}
.cart-count{position:absolute;top:-8px;right:-8px;background:var(–accent);color:var(–cream);font-size:14px;width:20px;height:20px;border-radius:50%;display:flex;justify-content:center;align-items:center;font-weight:700;font-family:‘Caveat’,cursive}
.mob-btn{display:none;font-size:28px;cursor:pointer;color:var(–primary);background:none;border:none;padding:5px}

/* HERO */
.hero{height:100vh;display:flex;align-items:center;background:linear-gradient(rgba(255,248,231,.9),rgba(255,248,231,.8)),url(‘https://images.unsplash.com/photo-1490481651871-ab68de25d43d?ixlib=rb-4.0.3&auto=format&fit=crop&w=2070&q=80’) center/cover;position:relative;overflow:hidden}
body.dark .hero{background:linear-gradient(rgba(26,26,26,.9),rgba(26,26,26,.8)),url(‘https://images.unsplash.com/photo-1490481651871-ab68de25d43d?ixlib=rb-4.0.3&auto=format&fit=crop&w=2070&q=80’) center/cover}
.hero-box{max-width:750px;position:relative;z-index:2;animation:fup 1s ease-out;background:rgba(255,255,255,.9);padding:50px;border-radius:15px;box-shadow:0 15px 40px rgba(139,69,19,.2);border:2px solid var(–dcream)}
body.dark .hero-box{background:rgba(45,45,45,.9);border-color:var(–dborder)}
.hero h1{font-size:56px;margin-bottom:20px;line-height:1.2;font-weight:700}
.hero p{font-size:26px;margin-bottom:30px;color:var(–dbrown)}
@keyframes fup{from{opacity:0;transform:translateY(40px)}to{opacity:1;transform:translateY(0)}}

/* BTN */
.btn{display:inline-block;background:var(–primary);color:var(–dbrown);padding:15px 35px;font-weight:600;border-radius:30px;border:2px solid var(–primary);transition:all .3s;cursor:pointer;font-size:22px;text-align:center;font-family:‘Caveat’,cursive}
.btn:hover{background:transparent;color:var(–primary);transform:translateY(-3px);box-shadow:0 10px 20px rgba(212,167,106,.3)}
.btn-ol{background:transparent;color:var(–primary);margin-left:15px}
.btn-ol:hover{background:var(–primary);color:var(–dbrown)}
@keyframes pulse{0%{box-shadow:0 0 0 0 rgba(212,167,106,.4)}70%{box-shadow:0 0 0 10px rgba(212,167,106,0)}100%{box-shadow:0 0 0 0 rgba(212,167,106,0)}}
.pulse{animation:pulse 2s infinite}

/* SECTIONS */
section{padding:100px 0;position:relative}
.sec-title{text-align:center;margin-bottom:60px}
.sec-title h2{font-size:46px;display:inline-block;position:relative;font-weight:700;background:linear-gradient(45deg,var(–secondary),var(–primary));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text}
.sec-title h2::after{content:’’;position:absolute;width:80px;height:3px;background:var(–primary);bottom:-15px;left:50%;transform:translateX(-50%)}

/* CATEGORIES */
.cat-sec{background:var(–beige)}
.cat-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(280px,1fr));gap:30px}
.cat-card{background:var(–cream);border-radius:10px;overflow:hidden;transition:all .4s;height:350px;cursor:pointer;border:2px solid var(–dcream);box-shadow:0 5px 15px rgba(139,69,19,.1)}
.cat-card:hover{transform:translateY(-15px);box-shadow:0 20px 40px rgba(139,69,19,.25);border-color:var(–primary)}
.cat-img{height:70%;overflow:hidden}
.cat-img img{width:100%;height:100%;object-fit:cover;transition:transform .7s}
.cat-card:hover .cat-img img{transform:scale(1.1)}
.cat-info{padding:25px 20px;height:30%;display:flex;flex-direction:column;justify-content:center}
.cat-info h3{font-size:26px;margin-bottom:8px;font-weight:600}
.cat-info p{color:var(–lbrown);font-size:18px}

/* PRODUCTS */
.prod-sec{background:var(–cream)}
.filter-row{display:flex;justify-content:center;flex-wrap:wrap;gap:15px;margin-bottom:40px}
.fbtn{background:var(–beige);color:var(–dbrown);border:1px solid var(–dcream);padding:10px 25px;border-radius:30px;cursor:pointer;font-weight:600;transition:all .3s;font-size:22px;font-family:‘Caveat’,cursive}
.fbtn.active,.fbtn:hover{background:var(–primary);color:var(–dbrown);border-color:var(–primary)}
.prod-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(280px,1fr));gap:30px}
.prod-card{background:var(–beige);border-radius:10px;overflow:hidden;transition:all .4s;position:relative;border:2px solid var(–dcream);box-shadow:0 5px 15px rgba(139,69,19,.1)}
.prod-card:hover{transform:translateY(-10px);box-shadow:0 20px 40px rgba(139,69,19,.2);border-color:var(–primary)}
.vip-card{border:2px solid transparent;background:linear-gradient(var(–beige),var(–beige)) padding-box,linear-gradient(45deg,#D4A76A,#FFD700,#D4A76A) border-box}
.badge{position:absolute;top:15px;left:15px;background:var(–accent);color:var(–cream);padding:5px 12px;border-radius:20px;font-weight:600;font-size:18px;z-index:2;font-family:‘Caveat’,cursive}
.vip-badge{position:absolute;top:15px;right:15px;background:linear-gradient(45deg,#D4A76A,#FFD700,#D4A76A);background-size:200%;color:var(–dbrown);padding:5px 12px;border-radius:20px;font-weight:600;font-size:16px;z-index:2;font-family:‘Caveat’,cursive;animation:gold 3s linear infinite;border:1px solid rgba(212,167,106,.5)}
@keyframes gold{0%{background-position:0%}100%{background-position:200%}}
.wish-btn{position:absolute;top:15px;right:15px;width:36px;height:36px;border-radius:50%;background:rgba(255,255,255,.9);border:none;cursor:pointer;display:flex;align-items:center;justify-content:center;transition:all .3s;z-index:3;color:var(–gray);font-size:16px}
.wish-btn:hover,.wish-btn.on{color:#e53935;background:#fff;transform:scale(1.15)}
.prod-img{height:250px;overflow:hidden}
.prod-img img{width:100%;height:100%;object-fit:cover;transition:transform .7s}
.prod-card:hover .prod-img img{transform:scale(1.08)}
.prod-body{padding:20px;background:var(–cream)}
.prod-body h3{font-size:24px;margin-bottom:8px;min-height:48px;font-weight:600}
.prod-desc{font-size:18px;color:var(–lbrown);margin-bottom:10px;min-height:40px}

/* SIZES */
.size-block{margin-bottom:12px}
.size-lbl{font-size:16px;color:var(–lbrown);margin-bottom:6px;display:block}
.size-opts{display:flex;flex-wrap:wrap;gap:6px}
.sz{min-width:36px;height:30px;padding:0 8px;border-radius:5px;border:1.5px solid var(–dcream);background:var(–beige);color:var(–dbrown);font-family:‘Caveat’,cursive;font-size:16px;cursor:pointer;transition:all .2s;display:flex;align-items:center;justify-content:center}
.sz:hover{border-color:var(–primary);background:rgba(212,167,106,.15)}
.sz.sel{background:var(–primary);border-color:var(–primary);color:var(–dbrown);font-weight:700}
.sz-warn{font-size:14px;color:var(–err);display:none;margin-top:4px}
.sz-warn.show{display:block}

.prod-price-row{display:flex;align-items:center;justify-content:space-between;margin-top:10px}
.price{font-size:26px;font-weight:700;color:var(–primary);font-family:‘Caveat’,cursive}
.old-price{text-decoration:line-through;color:var(–gray);font-size:20px;margin-right:5px;font-family:‘Caveat’,cursive}
.prod-actions{display:flex;gap:10px}
.act-btn{width:40px;height:40px;border-radius:50%;background:var(–primary);color:var(–dbrown);display:flex;align-items:center;justify-content:center;cursor:pointer;transition:all .3s;border:1px solid var(–primary)}
.act-btn:hover{background:var(–accent);border-color:var(–accent);color:#fff;transform:scale(1.1)}
.act-btn.ol{background:transparent;color:var(–primary)}
.act-btn.ol:hover{background:var(–primary);color:var(–dbrown)}

/* FLOAT ANIM */
.fly-item{position:fixed;width:40px;height:40px;background:linear-gradient(45deg,var(–primary),var(–accent));border-radius:50%;display:flex;align-items:center;justify-content:center;z-index:9999;pointer-events:none;box-shadow:0 2px 15px rgba(212,167,106,.5);font-size:18px;transition:transform .6s cubic-bezier(.175,.885,.32,1.275),opacity .6s}
.fly-item i{color:var(–dbrown)}

/* MODAL OVERLAY */
.overlay{position:fixed;inset:0;background:rgba(44,24,16,.7);z-index:1500;opacity:0;visibility:hidden;transition:all .3s;backdrop-filter:blur(3px)}
.overlay.open{opacity:1;visibility:visible}

/* CART PANEL */
.cart-panel{position:fixed;top:0;right:-100%;width:100%;max-width:450px;height:100%;background:var(–beige);z-index:2000;transition:right .4s cubic-bezier(.25,.46,.45,.94);box-shadow:-5px 0 30px rgba(139,69,19,.3);display:flex;flex-direction:column;border-left:2px solid var(–dcream)}
.cart-panel.open{right:0}
body.dark .cart-panel{background:var(–dcard);border-left-color:var(–dborder)}
.panel-hdr{display:flex;justify-content:space-between;align-items:center;padding:25px 30px;border-bottom:2px solid var(–dcream);background:var(–cream)}
.panel-hdr h3{font-size:28px;margin:0;font-weight:600}
body.dark .panel-hdr{background:var(–dcard);border-bottom-color:var(–dborder)}
.close-x{font-size:26px;cursor:pointer;color:var(–primary);transition:all .3s;background:none;border:none}
.close-x:hover{transform:rotate(90deg);color:var(–accent)}
.cart-items{flex:1;overflow-y:auto;padding:20px 30px}
.ci{display:flex;padding:15px 0;border-bottom:1px solid var(–dcream);align-items:center;transition:all .3s}
.ci.gone{animation:slide-out .3s ease forwards}
@keyframes slide-out{0%{opacity:1;transform:translateX(0)}100%{opacity:0;transform:translateX(100px)}}
.ci-img{width:80px;height:80px;border-radius:5px;overflow:hidden;margin-right:15px;flex-shrink:0;border:1px solid var(–dcream)}
.ci-img img{width:100%;height:100%;object-fit:cover}
.ci-info{flex:1}
.ci-name{font-weight:600;margin-bottom:3px;font-size:18px}
.ci-sz{font-size:14px;color:var(–lbrown);background:var(–beige);border:1px solid var(–dcream);border-radius:4px;padding:1px 8px;display:inline-block;margin-bottom:4px}
.ci-price{color:var(–primary);font-weight:700;font-size:20px;font-family:‘Caveat’,cursive}
.ci-ctrl{display:flex;align-items:center;margin-top:8px}
.q-btn{width:30px;height:30px;background:var(–cream);color:var(–dbrown);border:1px solid var(–dcream);border-radius:3px;cursor:pointer;display:flex;align-items:center;justify-content:center;font-weight:700;transition:all .2s;font-family:‘Caveat’,cursive;font-size:18px}
.q-btn:hover{background:var(–primary);border-color:var(–primary)}
.ci-qty{margin:0 10px;font-weight:600;min-width:20px;text-align:center;font-size:20px}
.del-btn{margin-left:15px;color:var(–err);cursor:pointer;transition:all .3s;background:none;border:none;font-size:20px;padding:5px;border-radius:50%;width:35px;height:35px;display:flex;align-items:center;justify-content:center}
.del-btn:hover{background:rgba(244,67,54,.1);transform:scale(1.2)}
.cart-footer{padding:25px 30px;border-top:2px solid var(–dcream);background:var(–cream)}
body.dark .cart-footer{background:var(–dcard);border-top-color:var(–dborder)}
.cart-total{display:flex;justify-content:space-between;margin-bottom:25px;font-size:22px;font-weight:600}
.total-sum{color:var(–primary);font-size:26px;font-family:‘Caveat’,cursive}
.checkout-btn{width:100%;padding:15px;background:var(–primary);color:var(–dbrown);border:none;border-radius:5px;font-weight:700;font-size:22px;cursor:pointer;transition:all .3s;font-family:‘Caveat’,cursive}
.checkout-btn:hover{background:var(–accent);color:#fff;transform:translateY(-3px)}
.cart-empty{text-align:center;padding:60px 20px}
.cart-empty i{font-size:70px;color:var(–dcream);margin-bottom:20px;opacity:.5;display:block}
.cart-empty h4{color:var(–secondary);margin-bottom:10px;font-size:26px}
.cart-empty p{color:var(–lbrown);font-size:20px}

/* AUTH MODAL */
.auth-ov{position:fixed;inset:0;background:rgba(44,24,16,.75);z-index:3000;opacity:0;visibility:hidden;transition:all .3s;backdrop-filter:blur(4px);display:flex;align-items:center;justify-content:center}
.auth-ov.open{opacity:1;visibility:visible}
.auth-box{background:var(–cream);border-radius:20px;width:100%;max-width:440px;padding:40px;box-shadow:0 25px 60px rgba(139,69,19,.3);border:2px solid var(–dcream);animation:pop .35s cubic-bezier(.34,1.56,.64,1);position:relative}
body.dark .auth-box{background:var(–dcard);border-color:var(–dborder)}
@keyframes pop{from{opacity:0;transform:scale(.85) translateY(20px)}to{opacity:1;transform:scale(1) translateY(0)}}
.auth-x{position:absolute;top:18px;right:18px;width:32px;height:32px;border-radius:50%;background:var(–beige);border:1px solid var(–dcream);cursor:pointer;display:flex;align-items:center;justify-content:center;color:var(–secondary);font-size:16px;transition:all .2s}
.auth-x:hover{background:var(–primary);color:var(–dbrown);transform:rotate(90deg)}
.auth-logo{text-align:center;margin-bottom:25px}
.auth-logo i{font-size:36px;color:var(–primary)}
.auth-logo h2{font-size:34px;margin-top:8px}
.auth-tabs{display:flex;background:var(–beige);border-radius:30px;padding:4px;margin-bottom:30px;border:1px solid var(–dcream)}
.at{flex:1;padding:10px;border-radius:26px;background:transparent;border:none;cursor:pointer;font-family:‘Caveat’,cursive;font-size:20px;color:var(–lbrown);font-weight:600;transition:all .25s}
.at.active{background:var(–primary);color:var(–dbrown);box-shadow:0 3px 10px rgba(212,167,106,.4)}
.aform{display:none}
.aform.active{display:block}
.afield{margin-bottom:18px}
.afield label{display:block;font-size:17px;color:var(–lbrown);margin-bottom:6px;font-weight:600}
.afield input{width:100%;padding:13px 16px;background:var(–beige);border:2px solid var(–dcream);border-radius:10px;font-family:‘Caveat’,cursive;font-size:20px;color:var(–dbrown);outline:none;transition:all .3s}
.afield input:focus{border-color:var(–primary);background:var(–cream)}
body.dark .afield input{background:#3a3a3a;border-color:var(–dborder);color:var(–dtext)}
.asub{width:100%;padding:15px;background:linear-gradient(135deg,var(–primary),var(–secondary));color:#fff;border:none;border-radius:12px;font-family:‘Dancing Script’,cursive;font-size:24px;font-weight:700;cursor:pointer;transition:all .3s;margin-top:5px}
.asub:hover{transform:translateY(-2px);box-shadow:0 8px 25px rgba(139,69,19,.35)}
.aerr{background:rgba(244,67,54,.1);border:1px solid rgba(244,67,54,.3);border-radius:8px;padding:10px 14px;color:var(–err);font-size:17px;margin-bottom:15px;display:none}
.aerr.show{display:block}
.pw-wrap{position:relative}
.pw-eye{position:absolute;right:12px;top:50%;transform:translateY(-50%);cursor:pointer;color:var(–lbrown);font-size:18px;background:none;border:none;padding:5px}
.pw-eye:hover{color:var(–primary)}

/* PROFILE PANEL */
.prof-panel{position:fixed;top:0;right:-100%;width:100%;max-width:480px;height:100%;background:var(–beige);z-index:2000;transition:right .4s cubic-bezier(.25,.46,.45,.94);box-shadow:-5px 0 30px rgba(139,69,19,.3);display:flex;flex-direction:column;border-left:2px solid var(–dcream);overflow:hidden}
.prof-panel.open{right:0}
body.dark .prof-panel{background:var(–dcard);border-left-color:var(–dborder)}
.prof-hdr{background:linear-gradient(135deg,var(–secondary),var(–dbrown));padding:30px;color:#fff;position:relative}
.close-prof{position:absolute;top:18px;right:18px;width:34px;height:34px;border-radius:50%;background:rgba(255,255,255,.15);border:none;cursor:pointer;color:#fff;font-size:18px;display:flex;align-items:center;justify-content:center;transition:all .3s}
.close-prof:hover{background:rgba(255,255,255,.3);transform:rotate(90deg)}
.prof-av{width:70px;height:70px;border-radius:50%;background:linear-gradient(135deg,var(–primary),#FFD700);display:flex;align-items:center;justify-content:center;margin-bottom:15px;border:3px solid rgba(255,255,255,.3)}
.prof-av span{font-family:‘Dancing Script’,cursive;font-size:30px;font-weight:700;color:var(–dbrown)}
.prof-name{font-family:‘Dancing Script’,cursive;font-size:28px;font-weight:700;color:#fff;margin-bottom:4px}
.prof-email{font-size:17px;color:rgba(255,255,255,.75)}
.prof-stats{display:flex;gap:20px;margin-top:20px}
.pstat{background:rgba(255,255,255,.1);border-radius:10px;padding:10px 15px;text-align:center;flex:1}
.pstat-n{font-family:‘Dancing Script’,cursive;font-size:24px;font-weight:700;color:var(–primary);display:block}
.pstat-l{font-size:14px;color:rgba(255,255,255,.75)}
.ptabs{display:flex;border-bottom:2px solid var(–dcream);background:var(–cream)}
body.dark .ptabs{background:var(–dcard);border-bottom-color:var(–dborder)}
.ptab{flex:1;padding:14px 10px;background:none;border:none;cursor:pointer;font-family:‘Caveat’,cursive;font-size:19px;color:var(–lbrown);font-weight:600;border-bottom:3px solid transparent;margin-bottom:-2px;transition:all .25s}
.ptab.active{color:var(–primary);border-bottom-color:var(–primary)}
.pcontent{flex:1;overflow-y:auto}
.ptab-pane{display:none;padding:25px}
.ptab-pane.active{display:block}
.pfield{margin-bottom:18px}
.pfield label{display:block;font-size:16px;color:var(–lbrown);margin-bottom:6px}
.pfield input{width:100%;padding:12px 15px;background:var(–cream);border:2px solid var(–dcream);border-radius:10px;font-family:‘Caveat’,cursive;font-size:20px;color:var(–dbrown);outline:none;transition:all .3s}
.pfield input:focus{border-color:var(–primary)}
body.dark .pfield input{background:#3a3a3a;border-color:var(–dborder);color:var(–dtext)}
.save-btn{width:100%;padding:13px;background:var(–primary);color:var(–dbrown);border:none;border-radius:10px;font-family:‘Caveat’,cursive;font-size:22px;font-weight:700;cursor:pointer;transition:all .3s;margin-bottom:15px}
.save-btn:hover{background:var(–secondary);color:#fff;transform:translateY(-2px)}
.logout-btn{width:100%;padding:13px;background:transparent;color:var(–err);border:2px solid var(–err);border-radius:10px;font-family:‘Caveat’,cursive;font-size:22px;font-weight:700;cursor:pointer;transition:all .3s}
.logout-btn:hover{background:var(–err);color:#fff}

/* ORDERS */
.ocard{background:var(–cream);border-radius:12px;padding:18px;margin-bottom:15px;border:1.5px solid var(–dcream)}
body.dark .ocard{background:#3a3a3a;border-color:var(–dborder)}
.ocard-hdr{display:flex;justify-content:space-between;align-items:center;margin-bottom:12px}
.oid{font-size:16px;color:var(–lbrown)}
.odate{font-size:16px;color:var(–lbrown)}
.ostatus{padding:3px 12px;border-radius:20px;font-size:15px;font-weight:600}
.ostatus.proc{background:rgba(212,167,106,.2);color:var(–secondary);border:1px solid var(–primary)}
.ostatus.done{background:rgba(76,175,80,.15);color:var(–ok);border:1px solid var(–ok)}
.oitem{display:flex;align-items:center;gap:8px;margin-bottom:6px}
.oitem img{width:40px;height:40px;object-fit:cover;border-radius:5px;border:1px solid var(–dcream)}
.ototal-row{display:flex;justify-content:space-between;border-top:1px solid var(–dcream);padding-top:10px;margin-top:10px}
.ototal-l{font-size:17px;color:var(–lbrown)}
.ototal-v{font-size:20px;font-weight:700;color:var(–primary);font-family:‘Caveat’,cursive}
.empty-msg{text-align:center;padding:40px 20px;color:var(–lbrown)}
.empty-msg i{font-size:50px;color:var(–dcream);margin-bottom:15px;display:block}

/* WISHLIST */
.wl-grid{display:grid;grid-template-columns:1fr 1fr;gap:12px}
.wl-card{background:var(–cream);border-radius:10px;overflow:hidden;border:1.5px solid var(–dcream);transition:all .3s}
body.dark .wl-card{background:#3a3a3a;border-color:var(–dborder)}
.wl-card:hover{border-color:var(–primary);transform:translateY(-3px)}
.wl-img{height:100px;overflow:hidden}
.wl-img img{width:100%;height:100%;object-fit:cover}
.wl-body{padding:10px}
.wl-name{font-size:16px;font-weight:600;color:var(–secondary);margin-bottom:5px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.wl-price{font-size:17px;color:var(–primary);font-weight:700;font-family:‘Caveat’,cursive}
.wl-acts{display:flex;gap:6px;margin-top:8px}
.wl-add{flex:1;padding:5px;background:var(–primary);color:var(–dbrown);border:none;border-radius:6px;font-family:‘Caveat’,cursive;font-size:15px;cursor:pointer;transition:all .2s}
.wl-add:hover{background:var(–accent);color:#fff}
.wl-del{width:30px;background:rgba(244,67,54,.1);color:var(–err);border:none;border-radius:6px;cursor:pointer;font-size:14px;transition:all .2s}
.wl-del:hover{background:var(–err);color:#fff}

/* ABOUT */
.about-sec{background:var(–beige)}
.about-inner{display:flex;align-items:center;gap:50px}
.about-txt{flex:1}
.about-txt h2{font-size:46px;margin-bottom:25px}
.about-txt p{margin-bottom:20px;font-size:22px;color:var(–dbrown)}
.stats-row{display:flex;justify-content:space-between;margin-top:40px}
.stat-item{text-align:center}
.stat-n{font-size:40px;font-weight:700;color:var(–primary);display:block;margin-bottom:5px;font-family:‘Caveat’,cursive}
.stat-l{font-size:20px;color:var(–lbrown)}
.about-img{flex:1;border-radius:10px;overflow:hidden;box-shadow:20px 20px 0 var(–dcream);border:2px solid var(–dcream)}
.about-img img{width:100%;height:auto;display:block;transition:transform .5s}
.about-img:hover img{transform:scale(1.05)}

/* FOOTER */
footer{background:var(–dbrown);padding:70px 0 30px;color:var(–beige);transition:background .3s}
.footer-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:40px;margin-bottom:50px}
.fcol h3{font-size:26px;margin-bottom:25px;position:relative;padding-bottom:10px;color:var(–primary);font-weight:600}
.fcol h3::after{content:’’;position:absolute;width:40px;height:2px;background:var(–primary);bottom:0;left:0}
.fcol p{margin-bottom:20px;color:var(–beige);opacity:.9;font-size:20px}
.social{display:flex;gap:15px;margin-top:20px}
.social a{width:40px;height:40px;border-radius:50%;background:rgba(255,255,255,.1);display:flex;align-items:center;justify-content:center;transition:all .3s;color:var(–beige)}
.social a:hover{background:var(–primary);color:var(–dbrown);transform:translateY(-5px)}
.flinks{list-style:none}
.flinks li{margin-bottom:12px}
.flinks a{color:var(–beige);transition:all .3s;opacity:.9;font-size:20px}
.flinks a:hover{color:var(–primary);padding-left:5px;opacity:1}
.nl-form{display:flex;margin-top:20px}
.nl-inp{flex:1;padding:12px 15px;background:rgba(255,255,255,.1);border:1px solid rgba(212,167,106,.3);border-radius:30px 0 0 30px;color:var(–beige);border-right:none;font-size:18px;font-family:‘Caveat’,cursive}
.nl-inp:focus{outline:none;border-color:var(–primary)}
.nl-inp::placeholder{color:rgba(245,230,211,.6)}
.nl-btn{background:var(–primary);color:var(–dbrown);border:1px solid var(–primary);padding:0 20px;border-radius:0 30px 30px 0;cursor:pointer;font-weight:600;transition:all .3s;font-size:20px;font-family:‘Caveat’,cursive}
.nl-btn:hover{background:var(–accent);border-color:var(–accent);color:#fff}
.copy{text-align:center;padding-top:30px;border-top:1px solid rgba(212,167,106,.2);color:var(–beige);font-size:18px;opacity:.8}

/* NOTIFY */
.notify{position:fixed;top:100px;right:20px;padding:15px 25px;border-radius:8px;font-weight:600;box-shadow:0 5px 15px rgba(0,0,0,.3);opacity:0;transform:translateX(120px);transition:all .3s;z-index:9999;max-width:300px;pointer-events:none;font-family:‘Caveat’,cursive;font-size:20px}
.notify.show{opacity:1;transform:translateX(0)}
.notify.ok{background:var(–ok);color:#fff}
.notify.err{background:var(–err);color:#fff}
.notify.info{background:var(–primary);color:var(–dbrown)}
.spin{display:inline-block;width:20px;height:20px;border:3px solid rgba(212,167,106,.3);border-radius:50%;border-top-color:var(–primary);animation:spin 1s linear infinite}
@keyframes spin{to{transform:rotate(360deg)}}

/* PRODUCT DETAIL MODAL */
.detail-panel{position:fixed;top:0;right:-100%;width:100%;max-width:500px;height:100%;background:var(–beige);z-index:2000;transition:right .4s cubic-bezier(.25,.46,.45,.94);box-shadow:-5px 0 30px rgba(139,69,19,.3);display:flex;flex-direction:column;border-left:2px solid var(–dcream);overflow-y:auto}
.detail-panel.open{right:0}
body.dark .detail-panel{background:var(–dcard);border-left-color:var(–dborder)}
.detail-inner{padding:30px}
.detail-img{width:100%;border-radius:12px;margin-bottom:20px;border:2px solid var(–dcream);max-height:300px;object-fit:cover}
.detail-name{font-size:30px;margin-bottom:10px}
.detail-desc{font-size:19px;color:var(–lbrown);margin-bottom:15px}
.detail-price{font-size:32px;font-weight:700;color:var(–primary);font-family:‘Caveat’,cursive;margin-bottom:5px}
.detail-oldprice{text-decoration:line-through;color:var(–gray);font-size:22px;font-family:‘Caveat’,cursive;margin-bottom:15px;display:block}

/* RESPONSIVE */
@media(max-width:1200px){.footer-grid{grid-template-columns:repeat(2,1fr)}.about-inner{gap:40px}}
@media(max-width:992px){.hero h1{font-size:46px}.about-inner{flex-direction:column;text-align:center}.about-img{order:-1}.stats-row{justify-content:space-around}}
@media(max-width:768px){
body{font-size:20px}
nav{position:fixed;top:0;left:-100%;width:280px;height:100vh;background:var(–beige);flex-direction:column;padding:100px 30px 30px;transition:left .4s;box-shadow:5px 0 15px rgba(139,69,19,.3);border-right:2px solid var(–dcream);z-index:999}
nav.open{left:0}
nav ul{flex-direction:column;gap:25px}
.mob-btn{display:block}
.ha{gap:10px}
.hero h1{font-size:36px}.hero p{font-size:22px}
.hero-box{padding:30px;margin:0 15px}
.sec-title h2{font-size:34px}
.cart-panel,.prof-panel,.detail-panel{max-width:100%}
.srch-drop{position:fixed;top:80px;left:20px;right:20px;width:auto;z-index:1002}
.wl-grid{grid-template-columns:1fr}
}
@media(max-width:576px){
body{font-size:18px}
.hero h1{font-size:32px}.hero p{font-size:20px}
.btn{padding:12px 25px;font-size:18px;display:block;margin-bottom:10px;width:100%}
.btn-ol{margin-left:0}
.cat-grid,.prod-grid{grid-template-columns:1fr}
.footer-grid{grid-template-columns:1fr;gap:30px}
.stats-row{flex-direction:column;gap:25px}
.notify{top:80px;right:10px;left:10px;max-width:none}
.logo{font-size:28px}
.auth-box{padding:25px;margin:0 15px}
}
</style>

</head>
<body>

<div class="starry-bg" id="starsEl"></div>
<div class="confetti-wrap" id="confettiEl"></div>

<!-- HEADER -->

<header id="mainHeader">
  <div class="container">
    <div class="hd">
      <a href="#home" class="logo"><i class="fas fa-crown"></i><span>LuxeStyle</span></a>

```
  <nav id="mainNav">
    <ul>
      <li><a href="#home" class="navlnk">Главная</a></li>
      <li><a href="#categories" class="navlnk">Категории</a></li>
      <li><a href="#products" class="navlnk">Товары</a></li>
      <li><a href="#about" class="navlnk">О нас</a></li>
      <li><a href="#contact" class="navlnk">Контакты</a></li>
    </ul>
  </nav>

  <div class="ha">
    <!-- Search -->
    <div class="srch-wrap">
      <button class="srch-btn" id="srchBtn"><i class="fas fa-search"></i></button>
      <div class="srch-drop" id="srchDrop">
        <div class="srch-row">
          <input type="text" class="srch-inp" id="srchInp" placeholder="Поиск товаров...">
          <button class="srch-go" id="srchGo"><i class="fas fa-search"></i></button>
        </div>
        <div class="srch-res" id="srchRes"></div>
      </div>
    </div>
    <div class="srch-overlay" id="srchOv"></div>

    <!-- Theme -->
    <div class="theme-sw" id="themeSw">
      <i class="fas fa-sun"></i><i class="fas fa-moon"></i>
      <div class="theme-knob"></div>
    </div>

    <!-- Language -->
    <div class="lang-sel" id="langSel">
      <div class="lang-flag"><img src="https://flagcdn.com/w40/ru.png" alt="" id="flagImg"></div>
      <span id="langTxt">РУ</span>
      <div class="lang-drop">
        <div class="lang-opt" data-l="ru"><div class="lang-flag"><img src="https://flagcdn.com/w40/ru.png"></div><span>Русский</span></div>
        <div class="lang-opt" data-l="en"><div class="lang-flag"><img src="https://flagcdn.com/w40/gb.png"></div><span>English</span></div>
        <div class="lang-opt" data-l="kz"><div class="lang-flag"><img src="https://flagcdn.com/w40/kz.png"></div><span>Қазақша</span></div>
      </div>
    </div>

    <!-- Profile -->
    <div class="prof-btn" id="profBtn" title="Профиль">
      <i class="fas fa-user" id="profIcon"></i>
      <span class="initials" id="profInitials"></span>
    </div>

    <!-- Cart -->
    <div class="cart-ic" id="cartIc">
      <i class="fas fa-shopping-bag"></i>
      <span class="cart-count" id="cartCnt">0</span>
    </div>

    <button class="mob-btn" id="mobBtn"><i class="fas fa-bars"></i></button>
  </div>
</div>
```

  </div>
</header>

<!-- ============ AUTH MODAL ============ -->

<div class="auth-ov" id="authOv">
  <div class="auth-box">
    <button class="auth-x" id="authX"><i class="fas fa-times"></i></button>
    <div class="auth-logo">
      <i class="fas fa-crown"></i>
      <h2>LuxeStyle</h2>
    </div>
    <div class="auth-tabs">
      <button class="at active" data-tab="lg">Вход</button>
      <button class="at" data-tab="rg">Регистрация</button>
    </div>
    <!-- Login -->
    <div class="aform active" id="lgForm">
      <div class="aerr" id="lgErr"></div>
      <div class="afield"><label>Email</label><input type="email" id="lgEmail" placeholder="your@email.com"></div>
      <div class="afield"><label>Пароль</label>
        <div class="pw-wrap">
          <input type="password" id="lgPass" placeholder="••••••••">
          <button class="pw-eye" type="button" onclick="togglePw('lgPass',this)"><i class="fas fa-eye"></i></button>
        </div>
      </div>
      <button class="asub" id="lgBtn">Войти</button>
    </div>
    <!-- Register -->
    <div class="aform" id="rgForm">
      <div class="aerr" id="rgErr"></div>
      <div class="afield"><label>Имя</label><input type="text" id="rgName" placeholder="Ваше имя"></div>
      <div class="afield"><label>Email</label><input type="email" id="rgEmail" placeholder="your@email.com"></div>
      <div class="afield"><label>Пароль</label>
        <div class="pw-wrap">
          <input type="password" id="rgPass" placeholder="Минимум 6 символов">
          <button class="pw-eye" type="button" onclick="togglePw('rgPass',this)"><i class="fas fa-eye"></i></button>
        </div>
      </div>
      <div class="afield"><label>Повторите пароль</label>
        <div class="pw-wrap">
          <input type="password" id="rgPass2" placeholder="Повторите пароль">
          <button class="pw-eye" type="button" onclick="togglePw('rgPass2',this)"><i class="fas fa-eye"></i></button>
        </div>
      </div>
      <button class="asub" id="rgBtn">Создать аккаунт</button>
    </div>
  </div>
</div>

<!-- ============ PROFILE PANEL ============ -->

<div class="prof-panel" id="profPanel">
  <div class="prof-hdr">
    <button class="close-prof" id="closeProfBtn"><i class="fas fa-times"></i></button>
    <div class="prof-av"><span id="ppInitials">А</span></div>
    <div class="prof-name" id="ppName">Пользователь</div>
    <div class="prof-email" id="ppEmail">email@example.com</div>
    <div class="prof-stats">
      <div class="pstat"><span class="pstat-n" id="ppOrders">0</span><span class="pstat-l">Заказов</span></div>
      <div class="pstat"><span class="pstat-n" id="ppWish">0</span><span class="pstat-l">Избранное</span></div>
      <div class="pstat"><span class="pstat-n" id="ppSpent">0₽</span><span class="pstat-l">Потрачено</span></div>
    </div>
  </div>
  <div class="ptabs">
    <button class="ptab active" data-pt="info">Профиль</button>
    <button class="ptab" data-pt="orders">Заказы</button>
    <button class="ptab" data-pt="wish">Избранное</button>
  </div>
  <div class="pcontent">
    <div class="ptab-pane active" id="pt-info">
      <div class="pfield"><label>Имя</label><input type="text" id="edName"></div>
      <div class="pfield"><label>Email</label><input type="email" id="edEmail"></div>
      <div class="pfield"><label>Телефон</label><input type="tel" id="edPhone" placeholder="+7 (___) ___-__-__"></div>
      <button class="save-btn" id="saveProfBtn">Сохранить изменения</button>
      <button class="logout-btn" id="logoutBtn">Выйти из аккаунта</button>
    </div>
    <div class="ptab-pane" id="pt-orders"><div id="ordersEl"></div></div>
    <div class="ptab-pane" id="pt-wish"><div class="wl-grid" id="wishEl"></div></div>
  </div>
</div>

<!-- ============ CART PANEL ============ -->

<div class="overlay" id="mainOverlay"></div>
<div class="cart-panel" id="cartPanel">
  <div class="panel-hdr">
    <h3>Корзина</h3>
    <button class="close-x" id="closeCart"><i class="fas fa-times"></i></button>
  </div>
  <div class="cart-items" id="cartItems"></div>
  <div class="cart-footer" id="cartFooter" style="display:none">
    <div class="cart-total"><span>Итого:</span><span class="total-sum" id="cartSum">0 ₽</span></div>
    <button class="checkout-btn" id="checkoutBtn">Оформить заказ</button>
  </div>
</div>

<!-- ============ PRODUCT DETAIL PANEL ============ -->

<div class="detail-panel" id="detailPanel">
  <div class="panel-hdr">
    <h3>Детали товара</h3>
    <button class="close-x" id="closeDetail"><i class="fas fa-times"></i></button>
  </div>
  <div class="detail-inner" id="detailInner"></div>
</div>

<!-- ============ HERO ============ -->

<section class="hero" id="home">
  <div class="container">
    <div class="hero-box">
      <h1 id="heroTitle">Эксклюзивные брендовые вещи для истинных ценителей</h1>
      <p id="heroSub">Откройте для себя мир роскоши и стиля с нашей коллекцией премиальных брендов. Качество, которое говорит само за себя.</p>
      <div>
        <a href="#products" class="btn pulse" id="heroBtn1">Коллекция</a>
        <a href="#about" class="btn btn-ol" id="heroBtn2">О нас</a>
      </div>
    </div>
  </div>
</section>

<!-- ============ CATEGORIES ============ -->

<section class="cat-sec" id="categories">
  <div class="container">
    <div class="sec-title"><h2 id="catTitle">Категории</h2></div>
    <div class="cat-grid">
      <div class="cat-card" data-cat="clothing">
        <div class="cat-img"><img src="https://images.unsplash.com/photo-1591047139829-d91aecb6caea?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Одежда" loading="lazy"></div>
        <div class="cat-info"><h3 id="catClothing">Одежда</h3><p id="catClothingD">Эксклюзивная одежда от мировых брендов</p></div>
      </div>
      <div class="cat-card" data-cat="shoes">
        <div class="cat-img"><img src="https://images.unsplash.com/photo-1543163521-1bf539c55dd2?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Обувь" loading="lazy"></div>
        <div class="cat-info"><h3 id="catShoes">Обувь</h3><p id="catShoesD">Коллекция премиальной обуви</p></div>
      </div>
      <div class="cat-card" data-cat="accessories">
        <div class="cat-img"><img src="https://images.unsplash.com/photo-1599643478518-a784e5dc4c8f?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Аксессуары" loading="lazy"></div>
        <div class="cat-info"><h3 id="catAcc">Аксессуары</h3><p id="catAccD">Роскошные аксессуары для завершения образа</p></div>
      </div>
    </div>
  </div>
</section>

<!-- ============ PRODUCTS ============ -->

<section class="prod-sec" id="products">
  <div class="container">
    <div class="sec-title"><h2 id="prodTitle">Популярные товары</h2></div>
    <div class="filter-row" id="filterRow">
      <button class="fbtn active" data-f="all">Все товары</button>
      <button class="fbtn" data-f="clothing">Одежда</button>
      <button class="fbtn" data-f="shoes">Обувь</button>
      <button class="fbtn" data-f="accessories">Аксессуары</button>
    </div>
    <div class="prod-grid" id="prodGrid"></div>
  </div>
</section>

<!-- ============ ABOUT ============ -->

<section class="about-sec" id="about">
  <div class="container">
    <div class="about-inner">
      <div class="about-txt">
        <h2 id="aboutTitle">О LuxeStyle</h2>
        <p id="aboutD1">Мы — эксклюзивный ритейлер люксовых брендов, предлагающий тщательно отобранную коллекцию премиальных товаров.</p>
        <p id="aboutD2">Наша миссия — предоставить доступ к самым востребованным и редким предметам роскоши.</p>
        <div class="stats-row">
          <div class="stat-item"><span class="stat-n">2010</span><span class="stat-l" id="statYear">Год основания</span></div>
          <div class="stat-item"><span class="stat-n">50+</span><span class="stat-l" id="statBrands">Брендов</span></div>
          <div class="stat-item"><span class="stat-n">25k+</span><span class="stat-l" id="statClients">Довольных клиентов</span></div>
        </div>
      </div>
      <div class="about-img"><img src="https://images.unsplash.com/photo-1445205170230-053b83016050?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="О нас"></div>
    </div>
  </div>
</section>

<!-- ============ FOOTER ============ -->

<footer id="contact">
  <div class="container">
    <div class="footer-grid">
      <div class="fcol">
        <h3 id="fAboutT">О компании</h3>
        <p id="fAboutD">Эксклюзивные брендовые вещи для истинных ценителей роскоши и стиля.</p>
        <div class="social">
          <a href="#"><i class="fab fa-instagram"></i></a>
          <a href="#"><i class="fab fa-facebook-f"></i></a>
          <a href="#"><i class="fab fa-twitter"></i></a>
          <a href="#"><i class="fab fa-pinterest-p"></i></a>
        </div>
      </div>
      <div class="fcol">
        <h3 id="fCatT">Категории</h3>
        <ul class="flinks">
          <li><a href="#categories" id="fCat1">Одежда</a></li>
          <li><a href="#categories" id="fCat2">Обувь</a></li>
          <li><a href="#categories" id="fCat3">Аксессуары</a></li>
          <li><a href="#products" id="fCat4">Новая коллекция</a></li>
          <li><a href="#products" id="fCat5">Распродажа</a></li>
        </ul>
      </div>
      <div class="fcol">
        <h3 id="fInfoT">Информация</h3>
        <ul class="flinks">
          <li><a href="#about" id="fInfo1">О нас</a></li>
          <li><a href="#" id="fInfo2">Доставка и оплата</a></li>
          <li><a href="#" id="fInfo3">Возврат и обмен</a></li>
          <li><a href="#" id="fInfo4">Политика конфиденциальности</a></li>
          <li><a href="#contact" id="fInfo5">Контакты</a></li>
        </ul>
      </div>
      <div class="fcol">
        <h3 id="fNlT">Новостная рассылка</h3>
        <p id="fNlD">Подпишитесь и получите скидку 10% на первый заказ.</p>
        <form class="nl-form" id="nlForm">
          <input type="email" class="nl-inp" id="nlInp" placeholder="Ваш email" required>
          <button type="submit" class="nl-btn"><i class="fas fa-paper-plane"></i></button>
        </form>
      </div>
    </div>
    <div class="copy"><p>&copy; 2024 LuxeStyle. <span id="fRights">Все права защищены.</span></p></div>
  </div>
</footer>

<!-- ============================================================
     JAVASCRIPT
============================================================ -->

<script>
// ── DATA ──────────────────────────────────────────────────────
var SIZES = {
  clothing:    ['XS','S','M','L','XL','XXL'],
  shoes:       ['36','37','38','39','40','41','42','43','44','45'],
  accessories: ['ONE SIZE']
};

var PRODUCTS = [
  {id:1,  cat:'clothing',  price:53999,               name:{ru:'Кожаная куртка премиум',       en:'Premium Leather Jacket',         kz:'Премиум былған кожа куртка'},    desc:{ru:'Итальянская кожа, ручная работа',      en:'Italian leather, handmade',           kz:'Итальян кожасы, қолдан жасалған'},   img:'https://primovello.ru/upload/phpthumb/13/28eb40578103936682746c3e48c30fa8.webp', badge:'New'},
  {id:2,  cat:'clothing',  price:74999,               name:{ru:'Кашемировое пальто',            en:'Cashmere Coat',                  kz:'Кашемир пальто'},                desc:{ru:'100% кашемир, ограниченная серия',     en:'100% cashmere, limited edition',      kz:'100% кашемир, шектеулі басылым'},     img:'https://st.aestatic.net/items-img/R/F/2/N/A698e03202c994d77963cb55cc22e685b3.jpeg_960x960.jpg', badge:'Luxury'},
  {id:3,  cat:'clothing',  price:110999,              name:{ru:'Дизайнерское вечернее платье',  en:'Designer Evening Dress',         kz:'Дизайнерлік кешкі көйлек'},      desc:{ru:'Ручная вышивка, эксклюзивный дизайн', en:'Hand embroidery, exclusive design',   kz:'Қолдан кестеленген, эксклюзивті'},   img:'https://i.pinimg.com/originals/cf/dc/4e/cfdc4e7119a954b5134961e9c53c87c8.jpg', badge:'Exclusive'},
  {id:4,  cat:'clothing',  price:14999,  old:20999,  name:{ru:'Брендовая рубашка',             en:'Branded Shirt',                  kz:'Брендтік жейде'},                desc:{ru:'Хлопок премиум, итальянский пошив',    en:'Premium cotton, Italian tailoring',   kz:'Премиум мақта, итальяндық тігін'},   img:'https://n.cdn.cdek.shopping/images/shopping/64VkVYwOk7hz03dR.jpg?v=1', badge:'Sale'},
  {id:5,  cat:'shoes',     price:44999,               name:{ru:'Кроссовки Limited Edition',    en:'Sneakers Limited Edition',       kz:'Кросовкалар шектеулі басылым'},  desc:{ru:'Эксклюзивная коллекция',              en:'Exclusive collection',                kz:'Эксклюзивті жинақ'},                 img:'https://ir.ozone.ru/s3/multimedia-1/c600/6705766117.jpg', badge:'Хит'},
  {id:6,  cat:'shoes',     price:38999,               name:{ru:'Кожаные туфли ручной работы',  en:'Handmade Leather Shoes',         kz:'Қолдан жасалған туфли'},          desc:{ru:'Ручная работа, натуральная кожа',      en:'Handmade, genuine leather',           kz:'Қолдан жасалған, нағыз кожа'},       img:'https://avatars.mds.yandex.net/i?id=7ed11f0327e5fb840693e3e1ce8998b4_sr-3688950-images-thumbs&n=13', badge:'Handmade'},
  {id:7,  cat:'shoes',     price:31999,               name:{ru:'Зимние ботинки из нубука',     en:'Winter Nubuck Boots',            kz:'Қысқы нубук етік'},              desc:{ru:'Водонепроницаемые, утепленные',        en:'Waterproof, insulated',               kz:'Су өткізбейтін, жылы'},              img:'https://static.insales-cdn.com/images/products/1/1109/138077269/lg-001.jpg', badge:'Winter'},
  {id:8,  cat:'shoes',     price:53999,               name:{ru:'Классические оксфорды',        en:'Classic Oxfords',                kz:'Классикалық оксфордтар'},        desc:{ru:'Английский стиль, премиум кожа',       en:'English style, premium leather',      kz:'Ағылшын стилі, премиум кожа'},       img:'https://cdn-sh1.vigbo.com/shops/119009/products/13673558/images/3-6ef45b54b04624037e8fe8db5bb8f74d.jpg', badge:'Classic'},
  {id:9,  cat:'accessories',price:194999, vip:true,  name:{ru:'Швейцарские часы золото',      en:'Swiss Watch Gold Bracelet',      kz:'Алтын білезікпен сағат'},        desc:{ru:'Автоматический механизм, сапфир',      en:'Automatic movement, sapphire crystal',kz:'Автоматты механизм, сапфир'},        img:'https://avatars.mds.yandex.net/i?id=2c421457220dc1e7aab26d65f5656851_l-5209742-images-thumbs&n=13', badge:'VIP'},
  {id:10, cat:'accessories',price:67999,  old:86999, name:{ru:'Дизайнерская кожаная сумка',   en:'Designer Leather Bag',           kz:'Дизайнерлік былған кожа сөмке'}, desc:{ru:'Натуральная кожа, золотая фурнитура',  en:'Genuine leather, gold hardware',      kz:'Нағыз кожа, алтын фурнитура'},       img:'https://i.pinimg.com/originals/67/5a/59/675a598b33e74527f4d8110a354080fb.jpg', badge:'Sale'},
  {id:11, cat:'accessories',price:46999,             name:{ru:'Золотые запонки с бриллиантами',en:'Gold Cufflinks Diamonds',       kz:'Алмастары бар алтын манжет'},    desc:{ru:'18-каратное золото, 0.5 карат',        en:'18-karat gold, 0.5 carat diamonds',   kz:'18 карат алтын, 0.5 карат алмас'},   img:'https://avatars.mds.yandex.net/i?id=68c934408b0e5a4753734e7087d383d7_l-10752576-images-thumbs&n=13', badge:'New'},
  {id:12, cat:'accessories',price:11400,             name:{ru:'Дизайнерский кожаный ремень',  en:'Designer Leather Belt',          kz:'Дизайнерлік кожа белбеу'},       desc:{ru:'Натуральная кожа, позолота',           en:'Genuine leather, gold-plated buckle', kz:'Нағыз кожа, алтынмен қапталған'},    img:'https://img.joomcdn.net/3570a0f6db84bbeac03fa9a36a55b6b5fcbaa72f_original.jpeg', badge:'Premium'},
  {id:13, cat:'clothing',  price:40999,               name:{ru:'Шерстяной блейзер',            en:'Wool Blazer',                    kz:'Жүн блейзер'},                   desc:{ru:'Шерсть мериноса, классический крой',   en:'Merino wool, classic cut',            kz:'Мерино жүні, классикалық кесу'},     img:'https://avatars.mds.yandex.net/i?id=affe3ede110aa9222ee58509a02317ef2f0e3b1b-5869570-images-thumbs&n=13', badge:'New'},
  {id:14, cat:'clothing',  price:56999,               name:{ru:'Шелковое платье',              en:'Silk Dress',                     kz:'Жібек көйлек'},                  desc:{ru:'100% натуральный шелк, роспись',       en:'100% natural silk, hand-painted',     kz:'100% табиғи жібек, қолмен боялған'}, img:'https://avatars.mds.yandex.net/i?id=5aa291879f3ada160d8e8cb91c55d1255bd30733-5133916-images-thumbs&n=13', badge:'Luxury'},
  {id:15, cat:'clothing',  price:44999,  old:50999,  name:{ru:'Кожаные штаны',                en:'Leather Pants',                  kz:'Былған кожа шалбар'},            desc:{ru:'Мягкая кожа, идеальная посадка',       en:'Soft leather, perfect fit',           kz:'Жұмсақ кожа, тамаша сәйкестік'},    img:'https://avatars.mds.yandex.net/i?id=f6c133850977e7b5823ac1beb9133c49e81fa5d0-4385982-images-thumbs&n=13', badge:'Sale'},
  {id:16, cat:'clothing',  price:26999,               name:{ru:'Кашемировый свитер',           en:'Cashmere Sweater',               kz:'Кашемир свитер'},                desc:{ru:'Невероятно мягкий, сохраняет тепло',   en:'Incredibly soft, retains heat',       kz:'Өте жұмсақ, жылуды сақтайды'},      img:'https://avatars.mds.yandex.net/i?id=7efa45f36a90062258668d63321a39a62577dc84-12154389-images-thumbs&n=13', badge:'Хит'},
  {id:17, cat:'shoes',     price:32999,               name:{ru:'Кожаные лоферы',               en:'Leather Loafers',                kz:'Былған кожа лоферлер'},          desc:{ru:'Комфорт на весь день, премиум кожа',   en:'All-day comfort, premium leather',    kz:'Күні бойы ыңғайлылық, премиум'},     img:'https://avatars.mds.yandex.net/i?id=9650be67ea17d3fe72918999826d1f9e67d91b4c-4219872-images-thumbs&n=13', badge:'Classic'},
  {id:18, cat:'shoes',     price:24999,               name:{ru:'Спортивные кроссовки',         en:'Sports Sneakers',                kz:'Спорттық кросовкалар'},          desc:{ru:'Технологичная подошва, дышащий',        en:'Technological sole, breathable',      kz:'Технологиялық табан, тыныс алатын'}, img:'https://avatars.mds.yandex.net/i?id=e53882dafcf7d50425e88aecd6abe5bf827c51c7-5887670-images-thumbs&n=13', badge:'Sport'},
  {id:19, cat:'shoes',     price:46999,               name:{ru:'Сапоги на каблуке',            en:'Heeled Boots',                   kz:'Өкшелі етік'},                   desc:{ru:'Стильные, удобные, модный фасон',      en:'Stylish, comfortable, fashionable',   kz:'Стильді, ыңғайлы, сәнді'},           img:'https://avatars.mds.yandex.net/i?id=599b382bf4a86f7ab98360c0ca1fca29e57256b7-4517378-images-thumbs&n=13', badge:'Fashion'},
  {id:20, cat:'shoes',     price:21999,  old:26999,  name:{ru:'Кроссовки для бега',           en:'Running Sneakers',               kz:'Жүгіру кросовкалары'},           desc:{ru:'Амортизация, поддержка стопы',         en:'Cushioning, foot support',            kz:'Амортизация, аяқты қолдау'},         img:'https://avatars.mds.yandex.net/i?id=7e94ab4d9e92a3c442aa5bc8e2aed0fbfaf1c2fd-12146892-images-thumbs&n=13', badge:'Sale'},
  {id:21, cat:'accessories',price:18999,             name:{ru:'Солнечные очки',               en:'Sunglasses',                     kz:'Күннен қорғайтын көзілдірік'},   desc:{ru:'UV защита, стильная оправа',           en:'UV protection, stylish frame',        kz:'UV қорғаныс, стильді рама'},         img:'https://avatars.mds.yandex.net/i?id=1363f2896e16c2f192cee3e125ac167e-4575620-images-thumbs&n=13', badge:'New'},
  {id:22, cat:'accessories',price:8999,              name:{ru:'Кожаный бумажник',             en:'Leather Wallet',                 kz:'Былған кожа әмиян'},             desc:{ru:'Вместительный, натуральная кожа',      en:'Spacious, genuine leather',           kz:'Сыйымды, нағыз кожа'},               img:'https://avatars.mds.yandex.net/i?id=e3df1907290f8abb0c0b7ade3973a3c2bbf28c6e-5147471-images-thumbs&n=13', badge:'Premium'},
  {id:23, cat:'accessories',price:12999,             name:{ru:'Шелковый шарф',                en:'Silk Scarf',                     kz:'Жібек шарф'},                    desc:{ru:'Ручная роспись, итальянский шелк',     en:'Hand-painted, Italian silk',          kz:'Қолмен боялған, итальян жібегі'},    img:'https://avatars.mds.yandex.net/i?id=2a4089059da56db826cf41a38c02440d3f87fc45-5693960-images-thumbs&n=13', badge:'Luxury'},
  {id:24, cat:'accessories',price:58999,             name:{ru:'Ювелирное колье',              en:'Jewelry Necklace',               kz:'Зергерлік алқа'},                desc:{ru:'Серебро с позолотой, натур. камни',    en:'Silver gold plating, natural stones', kz:'Алтынмен қапталған күміс, тастар'},  img:'https://avatars.mds.yandex.net/i?id=ba49fe7ec3ceb383b61e21bd963683084ce7b428-4259532-images-thumbs&n=13', badge:'Exclusive'},
  {id:25, cat:'clothing',  price:74999,  vip:true,  name:{ru:'Кожаный жилет с мехом',        en:'Leather Vest with Fur',          kz:'Мехпен жилет'},                  desc:{ru:'Натуральный мех, ручная отделка',      en:'Natural fur, handmade finishing',     kz:'Табиғи мех, қолмен өңделген'},       img:'https://avatars.mds.yandex.net/i?id=bf9ba6cc0d17161bb53a1606ff4fe071822237ac-5232580-images-thumbs&n=13', badge:'VIP'},
  {id:26, cat:'clothing',  price:40999,               name:{ru:'Шёлковый халат',              en:'Silk Robe',                      kz:'Жібек халат'},                   desc:{ru:'100% шёлк, вышивка золотом',           en:'100% natural silk, gold embroidery',  kz:'100% жібек, алтынмен кесте'},        img:'https://avatars.mds.yandex.net/i?id=6fc21753887b4c0a23fa006462bd27e6b2666d8d-9211032-images-thumbs&n=13', badge:'Luxury'},
  {id:27, cat:'clothing',  price:18999,               name:{ru:'Кожаные перчатки',            en:'Leather Gloves',                 kz:'Былған кожа қолғап'},            desc:{ru:'Мягкая кожа, подкладка из кашемира',  en:'Soft leather, cashmere lining',       kz:'Жұмсақ кожа, кашемир астары'},       img:'https://avatars.mds.yandex.net/i?id=d0697f08f61463be3dfb3bee0b1b155a85caeca6-5287696-images-thumbs&n=13', badge:'Winter'},
  {id:28, cat:'clothing',  price:50999,               name:{ru:'Вельветовый пиджак',          en:'Velvet Blazer',                  kz:'Вельвет пиджак'},                desc:{ru:'Итальянский вельвет, классич. крой',   en:'Italian velvet, classic cut',         kz:'Итальян вельветі, классикалық'},     img:'https://avatars.mds.yandex.net/i?id=be42a59545b3c35b6256843205985eb4ee33e615-5239905-images-thumbs&n=13', badge:'New'},
  {id:29, cat:'shoes',     price:54999,  vip:true,  name:{ru:'Ботинки Chelsea',              en:'Chelsea Boots',                  kz:'Челси етік'},                    desc:{ru:'Английская кожа, резиновая подошва',   en:'English leather, rubber sole',        kz:'Ағылшын кожасы, резина табан'},      img:'https://avatars.mds.yandex.net/i?id=7b0d81dbf4cc5fcf484af994df37eb7505bf22a7-4306555-images-thumbs&n=13', badge:'VIP'},
  {id:30, cat:'shoes',     price:34999,  old:42999, name:{ru:'Кроссовки из замши',           en:'Suede Sneakers',                 kz:'Замша кросовкалар'},             desc:{ru:'Итальянская замша, кожаная подкладка', en:'Italian suede, leather lining',       kz:'Итальян замшасы, кожа астары'},      img:'https://avatars.mds.yandex.net/i?id=9b2661750e0bb4e46e3a8c98543ac28ac413e808-5024048-images-thumbs&n=13', badge:'Sale'},
  {id:31, cat:'shoes',     price:40999,               name:{ru:'Лодочки на шпильке',          en:'Stiletto Pumps',                 kz:'Шпилькадағы лодочка'},           desc:{ru:'Каблук 10 см, кожа премиум',           en:'10 cm heel, premium leather',         kz:'Өкше биіктігі 10 см, премиум'},      img:'https://avatars.mds.yandex.net/i?id=3d47006cc9173c84cb32410679795c885dc7b968-4575491-images-thumbs&n=13', badge:'Fashion'},
  {id:32, cat:'shoes',     price:14999,               name:{ru:'Спортивные тапочки',          en:'Sports Slippers',                kz:'Спорттық тақия'},                desc:{ru:'Память формы, антибактер. стелька',    en:'Memory foam, antibacterial insole',   kz:'Еске сақтау, антибактериялық'},      img:'https://avatars.mds.yandex.net/i?id=ad7391ff447dd5fcba453a9064563001e2fa840d-8210080-images-thumbs&n=13', badge:'Comfort'},
  {id:33, cat:'accessories',price:110999, vip:true, name:{ru:'Золотое кольцо с сапфиром',    en:'Gold Ring with Sapphire',        kz:'Сапфирмен алтын сақина'},        desc:{ru:'18-каратное золото, натур. сапфир',    en:'18-karat gold, natural sapphire',     kz:'18 карат алтын, табиғи сапфир'},     img:'https://avatars.mds.yandex.net/i?id=b0ed31128c4ed7a7c7171666e1654d3de0489d0c-12475132-images-thumbs&n=13', badge:'VIP'},
  {id:34, cat:'accessories',price:26999,             name:{ru:'Кожаный клатч',               en:'Leather Clutch',                 kz:'Былған кожа клатч'},             desc:{ru:'Вечерняя сумка, цепочка',              en:'Evening bag, shoulder chain',         kz:'Кешкі сөмке, иық тізбегі'},          img:'https://avatars.mds.yandex.net/i?id=512e30ee9df791651e36cb8f8fd79596f3235c1c-7662942-images-thumbs&n=13', badge:'New'},
  {id:35, cat:'accessories',price:10999,             name:{ru:'Шелковый галстук',             en:'Silk Tie',                       kz:'Жібек галстук'},                 desc:{ru:'Ручная роспись, итальянский шелк',     en:'Hand-painted, Italian silk',          kz:'Қолмен боялған, итальян жібегі'},    img:'https://avatars.mds.yandex.net/i?id=5617bac3dd1839c49460f5afabe1485f8e89111e-12145584-images-thumbs&n=13', badge:'Classic'},
  {id:36, cat:'accessories',price:24999,             name:{ru:'Дизайнерские очки',            en:'Designer Glasses',               kz:'Дизайнерлік көзілдірік'},        desc:{ru:'Ацетат целлюлозы, поляриз. линзы',    en:'Cellulose acetate, polarized lenses', kz:'Целлюлоза ацетаты, поляризацияланған'}, img:'https://avatars.mds.yandex.net/i?id=c203b4248bc5ebc1aa2cd3f738c1b0a6aa5cd12d-5234452-images-thumbs&n=13', badge:'Premium'}
];

var TR = {
  ru:{sl:'Выберите размер',sr:'Пожалуйста, выберите размер',ci:'Добавлено в корзину',ce:'Корзина пуста',cd:'Добавьте товары из каталога',ct:'Итого:',co:'Оформить заказ',ty:'Спасибо! Заказ оформлен.',wi:'Добавлено в избранное ❤',wr:'Удалено из избранного',nl:'Вы успешно подписались!',ne:'Введите корректный email',sv:'Профиль сохранён!',ll:'Добро пожаловать,',lo:'Вы вышли из аккаунта',re:'Аккаунт создан! Добро пожаловать,',de:'Детали товара',ac:'В корзину',vd:'Смотреть'},
  en:{sl:'Select size',sr:'Please select a size',ci:'Item added to cart',ce:'Your cart is empty',cd:'Add items from the catalog',ct:'Total:',co:'Checkout',ty:'Thank you! Order placed.',wi:'Added to wishlist ❤',wr:'Removed from wishlist',nl:'Successfully subscribed!',ne:'Please enter a valid email',sv:'Profile saved!',ll:'Welcome,',lo:'Logged out',re:'Account created! Welcome,',de:'Product Details',ac:'Add to Cart',vd:'View'},
  kz:{sl:'Өлшем таңдаңыз',sr:'Өлшем таңдаңыз',ci:'Тауар себетке қосылды',ce:'Себетіңіз бос',cd:'Каталогтан тауарлар қосыңыз',ct:'Барлығы:',co:'Тапсырысты рәсімдеу',ty:'Рахмет! Тапсырыс рәсімделді.',wi:'Таңдаулыларға қосылды ❤',wr:'Таңдаулылардан жойылды',nl:'Сәтті жазылдыңыз!',ne:'Дұрыс email енгізіңіз',sv:'Профиль сақталды!',ll:'Қош келдіңіз,',lo:'Шықтыңыз',re:'Аккаунт жасалды! Қош келдіңіз,',de:'Тауар туралы',ac:'Себетке қосу',vd:'Қарау'}
};

// ── STATE ─────────────────────────────────────────────────────
var lang     = localStorage.getItem('ls_lang') || 'ru';
var dark     = localStorage.getItem('ls_dark') === 'true';
var cart     = JSON.parse(localStorage.getItem('ls_cart')  || '[]');
var users    = JSON.parse(localStorage.getItem('ls_users') || '[]');
var me       = JSON.parse(localStorage.getItem('ls_me')    || 'null');
var wishlist = JSON.parse(localStorage.getItem('ls_wish_' + (me ? me.email : 'g')) || '[]');
var selSizes = {}; // productId -> selected size string
var curFilter= 'all';

// ── UTILS ─────────────────────────────────────────────────────
function t(k){ return TR[lang][k] || k; }

function fmtPrice(p){
  var f = {ru:{s:'₽',m:1}, en:{s:'$',m:1/90}, kz:{s:'₸',m:5}};
  var x = f[lang]||f.ru;
  return Math.round(p*x.m).toLocaleString()+' '+x.s;
}

function isEmail(e){ return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(e); }

function notify(msg, type){
  type = type||'info';
  document.querySelectorAll('.notify').forEach(function(n){ n.remove(); });
  var n = document.createElement('div');
  n.className = 'notify ' + type;
  n.textContent = msg;
  document.body.appendChild(n);
  setTimeout(function(){ n.classList.add('show'); }, 10);
  setTimeout(function(){ n.classList.remove('show'); setTimeout(function(){ n.remove(); }, 300); }, 3000);
}

function saveCart(){ localStorage.setItem('ls_cart', JSON.stringify(cart)); }
function saveUsers(){ localStorage.setItem('ls_users', JSON.stringify(users)); }
function saveMe(){ localStorage.setItem('ls_me', JSON.stringify(me)); }
function saveWish(){
  var k = 'ls_wish_' + (me ? me.email : 'g');
  localStorage.setItem(k, JSON.stringify(wishlist));
}

function pName(p){ return p.name[lang] || p.name.ru; }
function pDesc(p){ return p.desc[lang] || p.desc.ru; }
function catSizes(cat){ return SIZES[cat] || ['ONE SIZE']; }
function isOneSize(cat){ var s = catSizes(cat); return s.length===1 && s[0]==='ONE SIZE'; }

// ── STARS ─────────────────────────────────────────────────────
function buildStars(){
  var el = document.getElementById('starsEl');
  el.innerHTML = '';
  if(!dark) return;
  for(var i=0;i<150;i++){
    var s = document.createElement('div');
    s.className = 'star';
    var sz = Math.random()*3+1;
    s.style.cssText = 'width:'+sz+'px;height:'+sz+'px;left:'+(Math.random()*100)+'vw;top:'+(Math.random()*100)+'vh;opacity:'+(Math.random()*.5+.2)+';--d:'+(Math.random()*5+3)+'s;animation-delay:'+(Math.random()*5)+'s';
    el.appendChild(s);
  }
}

function confetti(){
  var el = document.getElementById('confettiEl');
  el.innerHTML = '';
  var cols = ['#FF6B35','#D4A76A','#FFD700','#4CAF50','#2196F3','#9C27B0','#FF4081','#00BCD4'];
  for(var i=0;i<120;i++){
    var c = document.createElement('div');
    c.className = 'confetti-piece';
    var col = cols[Math.floor(Math.random()*cols.length)];
    var sz = Math.random()*10+5;
    var dur = Math.random()*3+2;
    var delay = Math.random()*2;
    c.style.cssText = 'background:'+col+';width:'+sz+'px;height:'+(Math.random()>.5?sz:sz/2)+'px;border-radius:'+(Math.random()>.5?'50%':'2px')+';left:'+(Math.random()*100)+'vw;animation:fall '+dur+'s ease-in '+delay+'s forwards;';
    el.appendChild(c);
    (function(piece,d){ setTimeout(function(){ if(piece.parentNode) piece.remove(); }, (d)*1000); })(c, (dur+delay));
  }
}

// ── THEME ─────────────────────────────────────────────────────
function applyTheme(){
  document.body.classList.toggle('dark', dark);
  var sw = document.getElementById('themeSw');
  if(sw) sw.classList.toggle('on', dark);
  buildStars();
}

function toggleTheme(){
  dark = !dark;
  localStorage.setItem('ls_dark', dark);
  applyTheme();
  notify(dark ? 'Тёмная тема включена' : 'Светлая тема включена', 'info');
}

// ── LANGUAGE ──────────────────────────────────────────────────
var FLAGDATA = {
  ru:{src:'https://flagcdn.com/w40/ru.png', txt:'РУ'},
  en:{src:'https://flagcdn.com/w40/gb.png', txt:'EN'},
  kz:{src:'https://flagcdn.com/w40/kz.png', txt:'ҚАЗ'}
};

function applyLang(){
  var f = FLAGDATA[lang];
  document.getElementById('flagImg').src = f.src;
  document.getElementById('langTxt').textContent = f.txt;
  // static texts
  var map = {
    ru:{heroTitle:'Эксклюзивные брендовые вещи для истинных ценителей',heroSub:'Откройте для себя мир роскоши и стиля с нашей коллекцией.',heroBtn1:'Коллекция',heroBtn2:'О нас',catTitle:'Категории',catClothing:'Одежда',catClothingD:'Эксклюзивная одежда от мировых брендов',catShoes:'Обувь',catShoesD:'Коллекция премиальной обуви',catAcc:'Аксессуары',catAccD:'Роскошные аксессуары для завершения образа',prodTitle:'Популярные товары',aboutTitle:'О LuxeStyle',aboutD1:'Мы — эксклюзивный ритейлер люксовых брендов.',aboutD2:'Наша миссия — доступ к редким предметам роскоши.',statYear:'Год основания',statBrands:'Брендов',statClients:'Довольных клиентов',fAboutT:'О компании',fAboutD:'Эксклюзивные брендовые вещи для ценителей.',fCatT:'Категории',fCat1:'Одежда',fCat2:'Обувь',fCat3:'Аксессуары',fCat4:'Новая коллекция',fCat5:'Распродажа',fInfoT:'Информация',fInfo1:'О нас',fInfo2:'Доставка и оплата',fInfo3:'Возврат и обмен',fInfo4:'Конфиденциальность',fInfo5:'Контакты',fNlT:'Рассылка',fNlD:'Подпишитесь и получите скидку 10%.',fRights:'Все права защищены.'},
    en:{heroTitle:'Exclusive Branded Items for True Connoisseurs',heroSub:'Discover the world of luxury and style with our premium collection.',heroBtn1:'Collection',heroBtn2:'About',catTitle:'Categories',catClothing:'Clothing',catClothingD:'Exclusive clothing from world brands',catShoes:'Shoes',catShoesD:'Collection of premium footwear',catAcc:'Accessories',catAccD:'Luxurious accessories to complete your look',prodTitle:'Popular Products',aboutTitle:'About LuxeStyle',aboutD1:'We are an exclusive retailer of luxury brands.',aboutD2:'Our mission — access to rare luxury items.',statYear:'Year founded',statBrands:'Brands',statClients:'Satisfied clients',fAboutT:'About Company',fAboutD:'Exclusive branded items for true connoisseurs.',fCatT:'Categories',fCat1:'Clothing',fCat2:'Shoes',fCat3:'Accessories',fCat4:'New Collection',fCat5:'Sale',fInfoT:'Information',fInfo1:'About',fInfo2:'Delivery & Payment',fInfo3:'Returns & Exchange',fInfo4:'Privacy Policy',fInfo5:'Contacts',fNlT:'Newsletter',fNlD:'Subscribe and get 10% off your first order.',fRights:'All rights reserved.'},
    kz:{heroTitle:'Нағыз талғампаздарға арналған эксклюзивті заттар',heroSub:'Біздің премиум жинағымызбен сән әлемін ашыңыз.',heroBtn1:'Жинақ',heroBtn2:'Біз туралы',catTitle:'Санаттар',catClothing:'Киім',catClothingD:'Әлемдік брендтердің эксклюзивті киімдері',catShoes:'Аяқ киім',catShoesD:'Премиум аяқ киімдер жинағы',catAcc:'Аксессуарлар',catAccD:'Сіздің бейнеңізді аяқтайтын аксессуарлар',prodTitle:'Танымал тауарлар',aboutTitle:'LuxeStyle туралы',aboutD1:'Біз — люкс брендтердің эксклюзивті дистрибьюторымыз.',aboutD2:'Біздің миссиямыз — сирек люкс заттарға қол жеткізу.',statYear:'Құрылған жылы',statBrands:'Брендтер',statClients:'Қанағаттанған клиенттер',fAboutT:'Компания туралы',fAboutD:'Нағыз сән талғампаздарына арналған заттар.',fCatT:'Санаттар',fCat1:'Киім',fCat2:'Аяқ киім',fCat3:'Аксессуарлар',fCat4:'Жаңа жинақ',fCat5:'Сатылым',fInfoT:'Ақпарат',fInfo1:'Біз туралы',fInfo2:'Жеткізу және төлем',fInfo3:'Қайтару және алмасу',fInfo4:'Құпиялылық саясаты',fInfo5:'Байланыс',fNlT:'Жаңалықтар тарату',fNlD:'Жазылыңыз және 10% жеңілдік алыңыз.',fRights:'Барлық құқықтар қорғалған.'}
  };
  var m = map[lang];
  Object.keys(m).forEach(function(id){
    var el = document.getElementById(id);
    if(el) el.textContent = m[id];
  });
  // filter buttons
  var fbtns = document.querySelectorAll('.fbtn');
  var flabels = {ru:['Все товары','Одежда','Обувь','Аксессуары'],en:['All Products','Clothing','Shoes','Accessories'],kz:['Барлық тауарлар','Киім','Аяқ киім','Аксессуарлар']};
  var lbls = flabels[lang];
  fbtns.forEach(function(b,i){ if(lbls[i]) b.textContent = lbls[i]; });
}

function setLang(l){
  lang = l;
  localStorage.setItem('ls_lang', l);
  applyLang();
  renderProducts(curFilter);
}

// ── SEARCH ────────────────────────────────────────────────────
var srchTimer = null;

function openSearch(){
  document.getElementById('srchDrop').classList.add('open');
  document.getElementById('srchOv').style.display = 'block';
  setTimeout(function(){ document.getElementById('srchInp').focus(); }, 50);
}

function closeSearch(){
  document.getElementById('srchDrop').classList.remove('open');
  document.getElementById('srchOv').style.display = 'none';
  document.getElementById('srchRes').innerHTML = '';
  document.getElementById('srchRes').classList.remove('open');
  document.getElementById('srchInp').value = '';
}

function doSearch(q){
  var res = document.getElementById('srchRes');
  if(!q.trim()){ res.classList.remove('open'); return; }
  var ql = q.toLowerCase();
  var found = PRODUCTS.filter(function(p){ return pName(p).toLowerCase().indexOf(ql)>-1 || pDesc(p).toLowerCase().indexOf(ql)>-1; });
  if(!found.length){ res.innerHTML = '<div class="srch-none">Ничего не найдено по «'+q+'»</div>'; res.classList.add('open'); return; }
  res.innerHTML = found.slice(0,5).map(function(p){
    return '<div class="srch-item" data-id="'+p.id+'">'
      +'<div class="srch-img"><img src="'+p.img+'" loading="lazy"></div>'
      +'<div><div class="srch-name">'+pName(p)+'</div><div class="srch-price">'+fmtPrice(p.price)+'</div></div></div>';
  }).join('');
  res.classList.add('open');
  res.querySelectorAll('.srch-item').forEach(function(item){
    item.addEventListener('click', function(){
      var pid = parseInt(this.dataset.id);
      var p = PRODUCTS.find(function(x){ return x.id===pid; });
      if(!p) return;
      closeSearch();
      document.querySelectorAll('.fbtn').forEach(function(b){ b.classList.toggle('active', b.dataset.f===p.cat); });
      renderProducts(p.cat);
      var sec = document.getElementById('products');
      window.scrollTo({top: sec.offsetTop - 80, behavior:'smooth'});
    });
  });
}

// ── WISHLIST ──────────────────────────────────────────────────
function toggleWish(pid){
  var p = PRODUCTS.find(function(x){ return x.id===pid; });
  if(!p) return;
  var idx = wishlist.findIndex(function(w){ return w.id===pid; });
  if(idx>-1){
    wishlist.splice(idx,1);
    notify(t('wr'),'info');
  } else {
    wishlist.push({id:p.id, name:pName(p), price:p.price, img:p.img, cat:p.cat});
    notify(t('wi'),'ok');
  }
  saveWish();
  // update heart icon on card
  var btn = document.querySelector('.wish-btn[data-id="'+pid+'"]');
  if(btn){
    var inW = wishlist.some(function(w){ return w.id===pid; });
    btn.classList.toggle('on', inW);
    btn.querySelector('i').className = inW ? 'fas fa-heart' : 'far fa-heart';
  }
  // update counter in profile
  var ppW = document.getElementById('ppWish');
  if(ppW) ppW.textContent = wishlist.length;
}

function removeWish(pid){
  var idx = wishlist.findIndex(function(w){ return w.id===pid; });
  if(idx>-1){ wishlist.splice(idx,1); saveWish(); renderWish(); renderProducts(curFilter); }
}

function renderWish(){
  var el = document.getElementById('wishEl');
  if(!el) return;
  if(!wishlist.length){
    el.innerHTML = '<div class="empty-msg" style="grid-column:1/-1"><i class="fas fa-heart"></i><p>Список избранного пуст</p></div>';
    return;
  }
  el.innerHTML = wishlist.map(function(w){
    return '<div class="wl-card">'
      +'<div class="wl-img"><img src="'+w.img+'" loading="lazy"></div>'
      +'<div class="wl-body">'
      +'<div class="wl-name">'+w.name+'</div>'
      +'<div class="wl-price">'+fmtPrice(w.price)+'</div>'
      +'<div class="wl-acts">'
      +'<button class="wl-add" onclick="addToCartDirect('+w.id+')"><i class="fas fa-cart-plus"></i> '+t('ac')+'</button>'
      +'<button class="wl-del" onclick="removeWish('+w.id+')"><i class="fas fa-times"></i></button>'
      +'</div></div></div>';
  }).join('');
}

function addToCartDirect(pid){
  // add with no size check (accessories / or allow direct add from wishlist)
  var p = PRODUCTS.find(function(x){ return x.id===pid; });
  if(!p) return;
  var sz = isOneSize(p.cat) ? 'ONE SIZE' : (selSizes[pid] || null);
  if(!sz){
    // just add with size TBD and note
    sz = 'ONE SIZE';
  }
  doAddToCart(p, sz, null);
  closeProfPanel();
  setTimeout(openCart, 300);
}

// ── CART ──────────────────────────────────────────────────────
function updateCartCount(){
  var n = cart.reduce(function(s,i){ return s+i.qty; }, 0);
  document.getElementById('cartCnt').textContent = n;
}

function openCart(){
  document.getElementById('cartPanel').classList.add('open');
  document.getElementById('mainOverlay').classList.add('open');
  document.body.style.overflow = 'hidden';
  renderCart();
}

function closeCart(){
  document.getElementById('cartPanel').classList.remove('open');
  document.getElementById('mainOverlay').classList.remove('open');
  document.body.style.overflow = '';
}

function flyAnim(btnEl){
  var cartEl = document.getElementById('cartIc');
  var br = btnEl.getBoundingClientRect();
  var cr = cartEl.getBoundingClientRect();
  var fly = document.createElement('div');
  fly.className = 'fly-item';
  fly.innerHTML = '<i class="fas fa-shopping-cart"></i>';
  fly.style.left = (br.left + br.width/2 - 20) + 'px';
  fly.style.top  = (br.top  + br.height/2 - 20) + 'px';
  document.body.appendChild(fly);
  setTimeout(function(){
    fly.style.transform = 'translate('+(cr.left-br.left)+'px,'+(cr.top-br.top)+'px) scale(.4)';
    fly.style.opacity = '.6';
  }, 20);
  setTimeout(function(){
    fly.remove();
    cartEl.classList.add('bounce');
    setTimeout(function(){ cartEl.classList.remove('bounce'); }, 500);
  }, 650);
}

function doAddToCart(product, size, btnEl){
  var key = product.id + '_' + size;
  var idx = cart.findIndex(function(i){ return i.key===key; });
  if(idx>-1){
    cart[idx].qty++;
  } else {
    cart.push({key:key, id:product.id, name:pName(product), price:product.price, img:product.img, size:size, qty:1});
  }
  saveCart();
  updateCartCount();
  if(btnEl) flyAnim(btnEl);
  if(document.getElementById('cartPanel').classList.contains('open')) renderCart();
  notify(t('ci'), 'ok');
}

function addToCart(pid, btnEl){
  var p = PRODUCTS.find(function(x){ return x.id===pid; });
  if(!p) return;

  var osz = isOneSize(p.cat);
  var sz  = osz ? 'ONE SIZE' : selSizes[pid];

  if(!osz && !sz){
    // flash the size block
    var card = document.querySelector('.prod-card[data-id="'+pid+'"]');
    if(card){
      var warn = card.querySelector('.sz-warn');
      if(warn){ warn.classList.add('show'); setTimeout(function(){ warn.classList.remove('show'); }, 2500); }
    }
    notify(t('sr'), 'err');
    return;
  }
  doAddToCart(p, sz, btnEl);
}

function changeQty(key, delta){
  var idx = cart.findIndex(function(i){ return i.key===key; });
  if(idx<0) return;
  cart[idx].qty += delta;
  if(cart[idx].qty < 1) cart.splice(idx,1);
  saveCart();
  updateCartCount();
  renderCart();
}

function removeItem(key){
  var row = document.querySelector('.ci[data-key="'+key+'"]');
  if(row){
    row.classList.add('gone');
    setTimeout(function(){
      cart = cart.filter(function(i){ return i.key!==key; });
      saveCart(); updateCartCount(); renderCart();
    }, 320);
  }
}

function renderCart(){
  var el  = document.getElementById('cartItems');
  var ft  = document.getElementById('cartFooter');
  var sum = document.getElementById('cartSum');
  if(!cart.length){
    el.innerHTML = '<div class="cart-empty"><i class="fas fa-shopping-bag"></i><h4>'+t('ce')+'</h4><p>'+t('cd')+'</p></div>';
    ft.style.display = 'none';
    return;
  }
  ft.style.display = 'block';
  var total = 0;
  el.innerHTML = cart.map(function(item){
    total += item.price * item.qty;
    return '<div class="ci" data-key="'+item.key+'">'
      +'<div class="ci-img"><img src="'+item.img+'" loading="lazy"></div>'
      +'<div class="ci-info">'
      +'<div class="ci-name">'+item.name+'</div>'
      +(item.size && item.size!=='ONE SIZE' ? '<span class="ci-sz">Размер: '+item.size+'</span>' : '')
      +'<div class="ci-price">'+fmtPrice(item.price)+'</div>'
      +'<div class="ci-ctrl">'
      +'<button class="q-btn" data-k="'+item.key+'" data-d="-1">−</button>'
      +'<span class="ci-qty">'+item.qty+'</span>'
      +'<button class="q-btn" data-k="'+item.key+'" data-d="1">+</button>'
      +'<button class="del-btn" data-k="'+item.key+'"><i class="fas fa-trash"></i></button>'
      +'</div></div></div>';
  }).join('');
  sum.textContent = fmtPrice(total);

  el.querySelectorAll('.q-btn').forEach(function(b){
    b.addEventListener('click', function(){ changeQty(this.dataset.k, parseInt(this.dataset.d)); });
  });
  el.querySelectorAll('.del-btn').forEach(function(b){
    b.addEventListener('click', function(){ removeItem(this.dataset.k); });
  });
}

function checkout(){
  if(!cart.length){ notify(t('ce'),'err'); return; }
  var total = cart.reduce(function(s,i){ return s+i.price*i.qty; }, 0);

  if(me){
    var order = {id:Date.now().toString().slice(-6), date:new Date().toLocaleDateString('ru-RU'), items:JSON.parse(JSON.stringify(cart)), total:total, status:'В обработке'};
    var ui = users.findIndex(function(u){ return u.email===me.email; });
    if(ui>-1){ users[ui].orders = users[ui].orders||[]; users[ui].orders.push(order); me = users[ui]; saveUsers(); saveMe(); }
  }

  confetti();
  notify(t('ty'),'ok');
  cart=[]; saveCart(); updateCartCount();
  setTimeout(function(){ closeCart(); renderCart(); }, 1500);
}

// ── AUTH ──────────────────────────────────────────────────────
function openAuth(){ document.getElementById('authOv').classList.add('open'); }
function closeAuth(){
  document.getElementById('authOv').classList.remove('open');
  ['lgErr','rgErr'].forEach(function(id){ document.getElementById(id).classList.remove('show'); });
  ['lgEmail','lgPass','rgName','rgEmail','rgPass','rgPass2'].forEach(function(id){
    var el=document.getElementById(id); if(el) el.value='';
  });
}

function switchAuthTab(tab){
  document.querySelectorAll('.at').forEach(function(b){ b.classList.toggle('active', b.dataset.tab===tab); });
  document.getElementById('lgForm').classList.toggle('active', tab==='lg');
  document.getElementById('rgForm').classList.toggle('active', tab==='rg');
}

function doLogin(){
  var email = document.getElementById('lgEmail').value.trim();
  var pass  = document.getElementById('lgPass').value;
  var err   = document.getElementById('lgErr');
  if(!email||!pass){ err.textContent='Заполните все поля'; err.classList.add('show'); return; }
  var user = users.find(function(u){ return u.email===email && u.password===pass; });
  if(!user){ err.textContent='Неверный email или пароль'; err.classList.add('show'); return; }
  me = user; saveMe();
  wishlist = JSON.parse(localStorage.getItem('ls_wish_'+me.email)||'[]');
  closeAuth(); updateProfBtn();
  notify(t('ll')+' '+me.name+'!','ok');
}

function doRegister(){
  var name  = document.getElementById('rgName').value.trim();
  var email = document.getElementById('rgEmail').value.trim();
  var pass  = document.getElementById('rgPass').value;
  var pass2 = document.getElementById('rgPass2').value;
  var err   = document.getElementById('rgErr');
  if(!name||!email||!pass||!pass2){ err.textContent='Заполните все поля'; err.classList.add('show'); return; }
  if(!isEmail(email)){ err.textContent='Некорректный email'; err.classList.add('show'); return; }
  if(pass.length<6){ err.textContent='Пароль минимум 6 символов'; err.classList.add('show'); return; }
  if(pass!==pass2){ err.textContent='Пароли не совпадают'; err.classList.add('show'); return; }
  if(users.find(function(u){ return u.email===email; })){ err.textContent='Email уже зарегистрирован'; err.classList.add('show'); return; }
  var user = {name:name, email:email, password:pass, phone:'', orders:[]};
  users.push(user); saveUsers();
  me = user; saveMe();
  wishlist = [];
  closeAuth(); updateProfBtn();
  notify(t('re')+' '+name+'!','ok');
}

function doLogout(){
  me = null; localStorage.removeItem('ls_me'); wishlist = [];
  closeProfPanel(); updateProfBtn(); renderProducts(curFilter);
  notify(t('lo'),'info');
}

function togglePw(id, btn){
  var inp = document.getElementById(id);
  var isP = inp.type==='password';
  inp.type = isP ? 'text' : 'password';
  btn.querySelector('i').className = isP ? 'fas fa-eye-slash' : 'fas fa-eye';
}

function updateProfBtn(){
  var icon = document.getElementById('profIcon');
  var init = document.getElementById('profInitials');
  if(me){
    icon.style.display='none'; init.style.display='block';
    init.textContent = me.name.charAt(0).toUpperCase();
  } else {
    icon.style.display='block'; init.style.display='none';
  }
}

// ── PROFILE PANEL ─────────────────────────────────────────────
function openProfPanel(){
  if(!me){ openAuth(); return; }
  var u = users.find(function(x){ return x.email===me.email; });
  if(u) me = u;
  renderProfPanel();
  document.getElementById('profPanel').classList.add('open');
  document.getElementById('mainOverlay').classList.add('open');
  document.body.style.overflow='hidden';
}

function closeProfPanel(){
  document.getElementById('profPanel').classList.remove('open');
  document.getElementById('mainOverlay').classList.remove('open');
  document.body.style.overflow='';
}

function renderProfPanel(){
  if(!me) return;
  var orders = me.orders || [];
  var spent  = orders.reduce(function(s,o){ return s+o.total; }, 0);
  document.getElementById('ppInitials').textContent = me.name.charAt(0).toUpperCase();
  document.getElementById('ppName').textContent     = me.name;
  document.getElementById('ppEmail').textContent    = me.email;
  document.getElementById('ppOrders').textContent   = orders.length;
  document.getElementById('ppWish').textContent     = wishlist.length;
  document.getElementById('ppSpent').textContent    = fmtPrice(spent);
  document.getElementById('edName').value  = me.name;
  document.getElementById('edEmail').value = me.email;
  document.getElementById('edPhone').value = me.phone||'';
  renderOrders(); renderWish();
}

function saveProf(){
  var name  = document.getElementById('edName').value.trim();
  var email = document.getElementById('edEmail').value.trim();
  var phone = document.getElementById('edPhone').value.trim();
  if(!name||!email){ notify('Заполните имя и email','err'); return; }
  if(!isEmail(email)){ notify('Некорректный email','err'); return; }
  var ui = users.findIndex(function(u){ return u.email===me.email; });
  if(ui>-1){ users[ui].name=name; users[ui].email=email; users[ui].phone=phone; me=users[ui]; saveUsers(); saveMe(); }
  renderProfPanel(); updateProfBtn(); notify(t('sv'),'ok');
}

function switchProfTab(tab){
  document.querySelectorAll('.ptab').forEach(function(b){ b.classList.toggle('active', b.dataset.pt===tab); });
  document.querySelectorAll('.ptab-pane').forEach(function(p){ p.classList.toggle('active', p.id==='pt-'+tab); });
  if(tab==='orders') renderOrders();
  if(tab==='wish')   renderWish();
}

function renderOrders(){
  var el = document.getElementById('ordersEl');
  if(!el) return;
  var orders = (me && me.orders) ? me.orders : [];
  if(!orders.length){
    el.innerHTML = '<div class="empty-msg"><i class="fas fa-box-open"></i><p>Заказов пока нет</p></div>';
    return;
  }
  el.innerHTML = orders.slice().reverse().map(function(o){
    return '<div class="ocard">'
      +'<div class="ocard-hdr"><span class="oid">Заказ #'+o.id+'</span><span class="odate">'+o.date+'</span></div>'
      +'<span class="ostatus '+(o.status==='Доставлен'?'done':'proc')+'">'+o.status+'</span>'
      +'<div style="margin-top:10px">'+o.items.map(function(i){
          return '<div class="oitem"><img src="'+i.img+'" loading="lazy">'
            +'<span>'+i.name+(i.size&&i.size!=='ONE SIZE'?' — <b>'+i.size+'</b>':'')
            +' × '+i.qty+'</span></div>';
        }).join('')+'</div>'
      +'<div class="ototal-row"><span class="ototal-l">Итого:</span><span class="ototal-v">'+fmtPrice(o.total)+'</span></div>'
      +'</div>';
  }).join('');
}

// ── PRODUCTS ──────────────────────────────────────────────────
function selectSize(pid, sz, btn){
  selSizes[pid] = sz;
  var card = btn.closest('.prod-card');
  card.querySelectorAll('.sz').forEach(function(b){ b.classList.remove('sel'); });
  btn.classList.add('sel');
  var w = card.querySelector('.sz-warn');
  if(w) w.classList.remove('show');
}

function openDetail(pid){
  var p = PRODUCTS.find(function(x){ return x.id===pid; });
  if(!p) return;
  var osz = isOneSize(p.cat);
  var sizes = catSizes(p.cat);
  var inW = wishlist.some(function(w){ return w.id===pid; });

  var html = '<img class="detail-img" src="'+p.img+'" loading="lazy">'
    +'<h3 class="detail-name">'+pName(p)+'</h3>'
    +'<p class="detail-desc">'+pDesc(p)+'</p>'
    +(p.old ? '<span class="detail-oldprice">'+fmtPrice(p.old)+'</span>' : '')
    +'<div class="detail-price">'+fmtPrice(p.price)+'</div>';

  if(!osz){
    html += '<div class="size-block" style="margin-bottom:16px">'
      +'<span class="size-lbl">'+t('sl')+':</span>'
      +'<div class="size-opts" id="detailSzOpts">'
      +sizes.map(function(s){
        return '<button class="sz'+(selSizes[pid]===s?' sel':'')+'" onclick="selSizes['+pid+']=\''+s+'\';document.querySelectorAll(\'#detailSzOpts .sz\').forEach(function(b){b.classList.remove(\'sel\')});this.classList.add(\'sel\')">'+s+'</button>';
      }).join('')
      +'</div>'
      +'<div class="sz-warn" id="detailWarn">'+t('sr')+'</div>'
      +'</div>';
  }

  html += '<div style="display:flex;gap:10px;margin-top:10px">'
    +'<button class="btn" style="flex:1" onclick="addCartFromDetail('+pid+')"><i class="fas fa-shopping-cart"></i> '+t('ac')+'</button>'
    +'<button class="btn btn-ol" onclick="toggleWish('+pid+');var i=this.querySelector(\'i\');var inW='+JSON.stringify(inW)+';i.className=inW?\'far fa-heart\':\'fas fa-heart\'" style="min-width:50px"><i class="'+(inW?'fas':'far')+' fa-heart"></i></button>'
    +'</div>';

  document.getElementById('detailInner').innerHTML = html;
  document.getElementById('detailPanel').classList.add('open');
  document.getElementById('mainOverlay').classList.add('open');
  document.body.style.overflow='hidden';
}

function closeDetail(){
  document.getElementById('detailPanel').classList.remove('open');
  document.getElementById('mainOverlay').classList.remove('open');
  document.body.style.overflow='';
}

// Called from detail panel add button
window.addCartFromDetail = function(pid){
  var p = PRODUCTS.find(function(x){ return x.id===pid; });
  if(!p) return;
  var osz = isOneSize(p.cat);
  var sz  = osz ? 'ONE SIZE' : selSizes[pid];
  if(!osz && !sz){
    var w = document.getElementById('detailWarn');
    if(w){ w.classList.add('show'); setTimeout(function(){ w.classList.remove('show'); }, 2000); }
    notify(t('sr'),'err');
    return;
  }
  doAddToCart(p, sz, null);
  closeDetail();
  setTimeout(openCart, 300);
};

window.selSizes = selSizes;
window.selectSize = selectSize;
window.toggleWish = toggleWish;
window.removeWish = removeWish;
window.addToCartDirect = addToCartDirect;
window.togglePw = togglePw;

function renderProducts(filter){
  curFilter = filter || 'all';
  var grid = document.getElementById('prodGrid');
  if(!grid) return;

  var list = curFilter==='all' ? PRODUCTS : PRODUCTS.filter(function(p){ return p.cat===curFilter; });

  if(!list.length){
    grid.innerHTML = '<div style="text-align:center;padding:40px;grid-column:1/-1;color:var(--lbrown)"><i class="fas fa-box-open" style="font-size:60px;color:var(--dcream);display:block;margin-bottom:15px"></i><h3>Товары не найдены</h3></div>';
    return;
  }

  grid.innerHTML = list.map(function(p){
    var osz   = isOneSize(p.cat);
    var sizes = catSizes(p.cat);
    var inW   = wishlist.some(function(w){ return w.id===p.id; });

    var szHtml = osz ? '' :
      '<div class="size-block">'
      +'<span class="size-lbl">'+t('sl')+':</span>'
      +'<div class="size-opts">'
      +sizes.map(function(s){
        return '<button class="sz'+(selSizes[p.id]===s?' sel':'')+'" onclick="selectSize('+p.id+',\''+s+'\',this)">'+s+'</button>';
      }).join('')
      +'</div>'
      +'<div class="sz-warn">'+t('sr')+'</div>'
      +'</div>';

    return '<div class="prod-card'+(p.vip?' vip-card':'')+'" data-id="'+p.id+'">'
      +(p.badge ? '<div class="'+(p.badge==='VIP'?'vip-badge':'badge')+'">'+p.badge+'</div>' : '')
      +(!p.vip ? '<button class="wish-btn'+(inW?' on':'')+'" data-id="'+p.id+'" onclick="toggleWish('+p.id+')" title="Избранное"><i class="'+(inW?'fas':'far')+' fa-heart"></i></button>' : '')
      +'<div class="prod-img"><img src="'+p.img+'" alt="'+pName(p)+'" loading="lazy"></div>'
      +'<div class="prod-body">'
      +'<h3>'+pName(p)+'</h3>'
      +'<div class="prod-desc">'+pDesc(p)+'</div>'
      +szHtml
      +'<div class="prod-price-row">'
      +'<div>'+(p.old?'<span class="old-price">'+fmtPrice(p.old)+'</span>':'')+'<span class="price">'+fmtPrice(p.price)+'</span></div>'
      +'<div class="prod-actions">'
      +'<button class="act-btn ol view-d" data-id="'+p.id+'" title="'+t('vd')+'"><i class="fas fa-eye"></i></button>'
      +'<button class="act-btn add-c" data-id="'+p.id+'" title="'+t('ac')+'"><i class="fas fa-shopping-cart"></i></button>'
      +'</div></div></div></div>';
  }).join('');

  // bind add-to-cart buttons
  grid.querySelectorAll('.add-c').forEach(function(btn){
    btn.addEventListener('click', function(e){
      e.stopPropagation();
      var pid = parseInt(this.dataset.id);
      addToCart(pid, this);
    });
  });

  // bind view-detail buttons
  grid.querySelectorAll('.view-d').forEach(function(btn){
    btn.addEventListener('click', function(e){
      e.stopPropagation();
      openDetail(parseInt(this.dataset.id));
    });
  });
}

// ── INIT ──────────────────────────────────────────────────────
document.addEventListener('DOMContentLoaded', function(){
  applyTheme();
  applyLang();
  updateCartCount();
  updateProfBtn();
  renderProducts('all');

  // Theme toggle
  document.getElementById('themeSw').addEventListener('click', toggleTheme);

  // Search
  document.getElementById('srchBtn').addEventListener('click', function(e){ e.stopPropagation(); openSearch(); });
  document.getElementById('srchOv').addEventListener('click', closeSearch);
  document.getElementById('srchGo').addEventListener('click', function(){ doSearch(document.getElementById('srchInp').value); });
  document.getElementById('srchInp').addEventListener('input', function(){
    clearTimeout(srchTimer);
    var v = this.value;
    srchTimer = setTimeout(function(){ doSearch(v); }, 280);
  });
  document.getElementById('srchInp').addEventListener('keypress', function(e){
    if(e.key==='Enter'){ e.preventDefault(); doSearch(this.value); }
  });

  // Language
  var ls = document.getElementById('langSel');
  ls.addEventListener('click', function(e){ e.stopPropagation(); ls.classList.toggle('open'); });
  document.addEventListener('click', function(){ ls.classList.remove('open'); });
  document.querySelectorAll('.lang-opt').forEach(function(o){
    o.addEventListener('click', function(e){ e.stopPropagation(); setLang(this.dataset.l); ls.classList.remove('open'); });
  });

  // Profile btn
  document.getElementById('profBtn').addEventListener('click', function(){ me ? openProfPanel() : openAuth(); });
  document.getElementById('closeProfBtn').addEventListener('click', closeProfPanel);
  document.getElementById('logoutBtn').addEventListener('click', doLogout);
  document.getElementById('saveProfBtn').addEventListener('click', saveProf);
  document.querySelectorAll('.ptab').forEach(function(b){
    b.addEventListener('click', function(){ switchProfTab(this.dataset.pt); });
  });

  // Auth
  document.getElementById('authX').addEventListener('click', closeAuth);
  document.getElementById('authOv').addEventListener('click', function(e){ if(e.target===this) closeAuth(); });
  document.querySelectorAll('.at').forEach(function(b){
    b.addEventListener('click', function(){ switchAuthTab(this.dataset.tab); });
  });
  document.getElementById('lgBtn').addEventListener('click', doLogin);
  document.getElementById('rgBtn').addEventListener('click', doRegister);
  document.getElementById('lgPass').addEventListener('keypress',  function(e){ if(e.key==='Enter') doLogin(); });
  document.getElementById('rgPass2').addEventListener('keypress', function(e){ if(e.key==='Enter') doRegister(); });

  // Cart
  document.getElementById('cartIc').addEventListener('click', openCart);
  document.getElementById('closeCart').addEventListener('click', closeCart);
  document.getElementById('checkoutBtn').addEventListener('click', checkout);
  document.getElementById('closeDetail').addEventListener('click', closeDetail);

  // Overlay click
  document.getElementById('mainOverlay').addEventListener('click', function(){
    closeCart(); closeProfPanel(); closeDetail();
  });

  // Filters
  document.querySelectorAll('.fbtn').forEach(function(btn){
    btn.addEventListener('click', function(){
      document.querySelectorAll('.fbtn').forEach(function(b){ b.classList.remove('active'); });
      this.classList.add('active');
      renderProducts(this.dataset.f);
    });
  });

  // Category cards
  document.querySelectorAll('.cat-card').forEach(function(card){
    card.addEventListener('click', function(){
      var cat = this.dataset.cat;
      document.querySelectorAll('.fbtn').forEach(function(b){ b.classList.toggle('active', b.dataset.f===cat); });
      window.scrollTo({top: document.getElementById('products').offsetTop - 80, behavior:'smooth'});
      renderProducts(cat);
    });
  });

  // Mobile nav
  document.getElementById('mobBtn').addEventListener('click', function(){
    document.getElementById('mainNav').classList.add('open');
    document.body.style.overflow='hidden';
  });
  document.querySelectorAll('.navlnk').forEach(function(l){
    l.addEventListener('click', function(){
      document.getElementById('mainNav').classList.remove('open');
      document.body.style.overflow='';
    });
  });
  document.addEventListener('click', function(e){
    var nav = document.getElementById('mainNav');
    if(nav.classList.contains('open') && !e.target.closest('#mainNav') && !e.target.closest('#mobBtn')){
      nav.classList.remove('open');
      document.body.style.overflow='';
    }
  });

  // Smooth scroll
  document.querySelectorAll('a[href^="#"]').forEach(function(a){
    a.addEventListener('click', function(e){
      var target = document.querySelector(this.getAttribute('href'));
      if(!target) return;
      e.preventDefault();
      document.getElementById('mainNav').classList.remove('open');
      document.body.style.overflow='';
      window.scrollTo({top: target.offsetTop - 80, behavior:'smooth'});
    });
  });

  // Scroll header
  window.addEventListener('scroll', function(){
    document.getElementById('mainHeader').classList.toggle('scrolled', window.scrollY > 100);
  });

  // Newsletter
  document.getElementById('nlForm').addEventListener('submit', function(e){
    e.preventDefault();
    var inp = document.getElementById('nlInp');
    var btn = this.querySelector('.nl-btn');
    if(!isEmail(inp.value.trim())){ notify(t('ne'),'err'); return; }
    var orig = btn.innerHTML;
    btn.innerHTML = '<div class="spin"></div>'; btn.disabled = true;
    setTimeout(function(){
      btn.innerHTML = '<i class="fas fa-check"></i>';
      btn.style.background = 'var(--ok)';
      setTimeout(function(){
        btn.innerHTML = orig; btn.style.background = ''; btn.disabled = false;
        inp.value = ''; notify(t('nl'),'ok');
      }, 1400);
    }, 900);
  });

  // Keyboard ESC
  document.addEventListener('keydown', function(e){
    if(e.key==='Escape'){
      closeCart(); closeProfPanel(); closeDetail(); closeAuth(); closeSearch();
      document.getElementById('mainNav').classList.remove('open');
      document.body.style.overflow='';
    }
  });

  notify('Добро пожаловать в LuxeStyle!', 'info');
});
</script>

</body>
</html>
