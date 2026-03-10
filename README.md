[Quiz_Antincendio_STANDALONE (2).html](https://github.com/user-attachments/files/25871504/Quiz_Antincendio_STANDALONE.2.html)
<!DOCTYPE html>
<html lang="it">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
<title>Antincendio — Verifica Finale</title>
<script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=IBM+Plex+Sans:wght@300;400;600;700&family=IBM+Plex+Mono:wght@400;600&display=swap" rel="stylesheet">
<style>
:root{--fire:#FF4500;--ember:#FF7400;--gold:#FFC107;--smoke:#0D1117;--ash:#161B22;--card:#1C2128;--border:rgba(255,69,0,0.22);--white:#F0EDE8;--muted:#8B949E;--success:#3FB950;--danger:#F85149;--radius:10px;}
*{margin:0;padding:0;box-sizing:border-box;}
body{background:var(--smoke);color:var(--white);font-family:'IBM Plex Sans',sans-serif;min-height:100vh;}
header{background:var(--ash);border-bottom:1px solid var(--border);padding:14px 22px;display:flex;align-items:center;gap:12px;position:sticky;top:0;z-index:50;}
.htitle{font-family:'Bebas Neue',sans-serif;font-size:20px;letter-spacing:2px;color:var(--ember);}
.hsub{font-size:10px;color:var(--muted);letter-spacing:1px;text-transform:uppercase;}
.hbadge{margin-left:auto;background:rgba(255,69,0,0.15);border:1px solid var(--border);color:var(--ember);font-size:10px;padding:3px 10px;border-radius:20px;font-family:'IBM Plex Mono',monospace;}
.hadmin{background:rgba(255,193,7,0.12);border:1px solid rgba(255,193,7,0.3);color:var(--gold);font-size:10px;padding:3px 10px;border-radius:20px;cursor:pointer;margin-left:8px;font-family:'IBM Plex Mono',monospace;}
#pb-wrap{height:3px;background:rgba(255,255,255,0.06);position:sticky;top:59px;z-index:49;}
#pb{height:100%;background:linear-gradient(90deg,var(--fire),var(--gold));transition:width 0.4s;width:0%;}
main{max-width:700px;margin:0 auto;padding:28px 18px 80px;}

/* REGISTRAZIONE */
#s-reg{text-align:center;}
#s-reg h1{font-family:'Bebas Neue',sans-serif;font-size:42px;letter-spacing:3px;background:linear-gradient(135deg,var(--fire),var(--gold));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;line-height:1.1;margin-bottom:6px;}
.sub{color:var(--muted);font-size:13px;margin-bottom:24px;line-height:1.6;}
.igrid{display:grid;grid-template-columns:repeat(3,1fr);gap:10px;margin-bottom:24px;}
.icard{background:var(--card);border:1px solid var(--border);border-radius:var(--radius);padding:14px 10px;text-align:center;}
.icard .n{font-family:'Bebas Neue',sans-serif;font-size:28px;color:var(--ember);}
.icard .l{font-size:10px;color:var(--muted);text-transform:uppercase;letter-spacing:1px;}
.fg{text-align:left;margin-bottom:14px;}
.fg label{display:block;font-size:11px;font-weight:600;color:var(--muted);text-transform:uppercase;letter-spacing:1px;margin-bottom:6px;}
.fg input{width:100%;background:var(--card);border:1px solid rgba(255,255,255,0.1);border-radius:var(--radius);padding:12px 14px;color:var(--white);font-family:'IBM Plex Sans',sans-serif;font-size:14px;outline:none;transition:border-color 0.2s;}
.fg input:focus{border-color:var(--ember);}
.fg input::placeholder{color:var(--muted);}

/* QR */
.qr-section{background:var(--card);border:1px solid var(--border);border-radius:var(--radius);padding:16px;margin-bottom:20px;}
.qr-label{font-size:11px;font-weight:600;color:var(--muted);text-transform:uppercase;letter-spacing:1px;margin-bottom:12px;}
.qr-inner{display:flex;align-items:center;gap:18px;}
.qr-box{background:white;border-radius:10px;padding:7px;flex-shrink:0;width:108px;height:108px;display:flex;align-items:center;justify-content:center;}
.qr-box img,.qr-box canvas{width:94px!important;height:94px!important;}
.qr-info .qn{font-family:'Bebas Neue',sans-serif;font-size:17px;letter-spacing:1px;margin-bottom:3px;}
.qr-info .qi{font-family:'IBM Plex Mono',monospace;font-size:11px;color:var(--ember);letter-spacing:2px;margin-bottom:5px;}
.qr-info .qd{font-size:11px;color:var(--muted);line-height:1.5;}

/* FIRMA */
.firma-box{text-align:left;margin-bottom:14px;}
.firma-box label{display:block;font-size:11px;font-weight:600;color:var(--muted);text-transform:uppercase;letter-spacing:1px;margin-bottom:6px;}
.firma-wrap{background:white;border-radius:var(--radius);overflow:hidden;position:relative;width:100%;height:120px;touch-action:none;}
#firma-svg{position:absolute;top:0;left:0;width:100%;height:100%;cursor:crosshair;display:block;user-select:none;-webkit-user-select:none;}
.firma-actions{display:flex;align-items:center;gap:8px;margin-top:6px;}
.btn-clear{background:rgba(255,255,255,0.05);border:1px solid rgba(255,255,255,0.1);color:var(--muted);border-radius:6px;padding:5px 12px;font-size:11px;cursor:pointer;}
.firma-hint{font-size:11px;color:var(--muted);}
.btn-start{width:100%;background:linear-gradient(135deg,var(--fire),var(--ember));color:white;border:none;border-radius:var(--radius);padding:14px;font-family:'Bebas Neue',sans-serif;font-size:18px;letter-spacing:2px;cursor:pointer;margin-top:6px;}
.disclaimer{margin-top:10px;font-size:11px;color:var(--muted);line-height:1.5;}

/* QUIZ */
#s-quiz{display:none;}
.qh{display:flex;justify-content:space-between;align-items:center;margin-bottom:22px;}
.qcnt{font-family:'IBM Plex Mono',monospace;font-size:12px;color:var(--muted);}
.qcnt span{color:var(--ember);font-weight:600;}
.qtimer{font-family:'IBM Plex Mono',monospace;font-size:12px;color:var(--muted);background:var(--card);border:1px solid var(--border);padding:4px 10px;border-radius:20px;}
.qtimer.warn{color:var(--danger);border-color:var(--danger);}
.qcard{background:var(--card);border:1px solid var(--border);border-radius:14px;padding:22px;margin-bottom:14px;}
.qnum{font-family:'Bebas Neue',sans-serif;font-size:11px;letter-spacing:2px;color:var(--ember);margin-bottom:8px;}
.qtext{font-size:16px;line-height:1.6;}
.opts{display:flex;flex-direction:column;gap:8px;}
.opt{background:var(--ash);border:1.5px solid rgba(255,255,255,0.08);border-radius:var(--radius);padding:11px 15px;cursor:pointer;display:flex;align-items:center;gap:12px;transition:all 0.15s;user-select:none;}
.opt:hover{border-color:var(--ember);background:rgba(255,116,0,0.06);}
.opt.sel{border-color:var(--ember);background:rgba(255,116,0,0.12);}
.opt.ok{border-color:var(--success);background:rgba(63,185,80,0.12);}
.opt.ko{border-color:var(--danger);background:rgba(248,81,73,0.12);}
.oletter{width:28px;height:28px;border-radius:50%;background:rgba(255,255,255,0.05);border:1px solid rgba(255,255,255,0.12);display:flex;align-items:center;justify-content:center;font-family:'Bebas Neue',sans-serif;font-size:14px;color:var(--muted);flex-shrink:0;}
.opt.sel .oletter{background:var(--ember);border-color:var(--ember);color:white;}
.opt.ok .oletter{background:var(--success);border-color:var(--success);color:white;}
.opt.ko .oletter{background:var(--danger);border-color:var(--danger);color:white;}
.otext{font-size:13px;line-height:1.5;}
.fb{background:var(--card);border-radius:var(--radius);padding:12px 15px;font-size:12px;line-height:1.6;display:none;margin-top:4px;}
.fb.ok{border-left:3px solid var(--success);color:#8edd99;}
.fb.ko{border-left:3px solid var(--danger);color:#f8908a;}
.navb{display:flex;justify-content:flex-end;gap:10px;margin-top:18px;}
.btn-nav{background:var(--card);border:1px solid var(--border);color:var(--white);border-radius:var(--radius);padding:10px 22px;font-size:13px;font-weight:600;cursor:pointer;transition:all 0.2s;}
.btn-nav:hover{border-color:var(--ember);color:var(--ember);}
.btn-nav.pri{background:linear-gradient(135deg,var(--fire),var(--ember));border-color:transparent;color:white;}
.btn-nav:disabled{opacity:0.3;cursor:not-allowed;}

/* RISULTATI */
#s-res{display:none;text-align:center;}
.rcircle{width:150px;height:150px;margin:0 auto 22px;display:flex;flex-direction:column;align-items:center;justify-content:center;font-family:'Bebas Neue',sans-serif;position:relative;}
.rcircle svg{position:absolute;top:0;left:0;transform:rotate(-90deg);}
.rscore{font-size:46px;line-height:1;position:relative;z-index:1;}
.rfrac{font-size:12px;color:var(--muted);position:relative;z-index:1;}
#s-res h2{font-family:'Bebas Neue',sans-serif;font-size:30px;letter-spacing:2px;margin-bottom:6px;}
.srow{display:grid;grid-template-columns:repeat(3,1fr);gap:10px;margin:18px 0 24px;}
.sc{background:var(--card);border:1px solid var(--border);border-radius:var(--radius);padding:13px 10px;}
.sc .sv{font-family:'Bebas Neue',sans-serif;font-size:25px;}
.sc .sl{font-size:10px;color:var(--muted);text-transform:uppercase;letter-spacing:1px;margin-top:2px;}
.res-card{background:var(--card);border:1px solid var(--border);border-radius:var(--radius);padding:16px;margin-bottom:16px;text-align:left;}
.res-card-title{font-size:11px;font-weight:600;color:var(--muted);text-transform:uppercase;letter-spacing:1px;margin-bottom:10px;}
.res-firma-img{max-width:200px;background:white;border-radius:6px;padding:3px;}
.res-qr-box{background:white;border-radius:8px;padding:6px;display:inline-block;}
.res-qr-box img,.res-qr-box canvas{width:80px!important;height:80px!important;}
.rtitle{text-align:left;font-family:'Bebas Neue',sans-serif;font-size:17px;letter-spacing:1px;color:var(--ember);margin-bottom:12px;}
.ri{background:var(--card);border:1px solid rgba(255,255,255,0.05);border-radius:var(--radius);padding:12px 14px;margin-bottom:8px;text-align:left;}
.ri.rok{border-left:3px solid var(--success);}
.ri.rko{border-left:3px solid var(--danger);}
.rq{font-size:12px;line-height:1.5;margin-bottom:5px;}
.ra{font-size:11px;color:var(--muted);}
.ra .ca{color:var(--success);}
.ra .wa{color:var(--danger);}
.sbox{background:var(--card);border:1px solid var(--border);border-radius:var(--radius);padding:12px;font-size:12px;color:var(--muted);margin-top:18px;display:none;align-items:center;gap:10px;}
.spin{width:13px;height:13px;border:2px solid rgba(255,255,255,0.1);border-top-color:var(--ember);border-radius:50%;animation:sp 0.8s linear infinite;flex-shrink:0;}
@keyframes sp{to{transform:rotate(360deg);}}
.sok{color:var(--success);}

/* BARCODE */
.barcode-section{background:var(--card);border:1px solid var(--border);border-radius:var(--radius);padding:16px;margin-bottom:16px;text-align:center;}
.barcode-label{font-size:11px;font-weight:600;color:var(--muted);text-transform:uppercase;letter-spacing:1px;margin-bottom:10px;}
.barcode-svg{max-width:100%;overflow-x:auto;}
.barcode-code{font-family:'IBM Plex Mono',monospace;font-size:11px;color:var(--ember);margin-top:6px;letter-spacing:2px;}

/* ADMIN */
#s-admin{display:none;}
.adm-hd{display:flex;align-items:center;justify-content:space-between;margin-bottom:22px;flex-wrap:wrap;gap:10px;}
.adm-hd h2{font-family:'Bebas Neue',sans-serif;font-size:26px;letter-spacing:2px;color:var(--gold);}
.adm-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:10px;margin-bottom:22px;}
.astat{background:var(--card);border:1px solid var(--border);border-radius:var(--radius);padding:13px 10px;text-align:center;}
.astat .av{font-family:'Bebas Neue',sans-serif;font-size:26px;color:var(--ember);}
.astat .al{font-size:10px;color:var(--muted);text-transform:uppercase;letter-spacing:1px;}
.atab{width:100%;border-collapse:collapse;font-size:12px;}
.atab th{background:var(--card);border-bottom:1px solid var(--border);padding:9px 11px;text-align:left;font-size:10px;font-weight:600;color:var(--muted);text-transform:uppercase;letter-spacing:1px;}
.atab td{padding:9px 11px;border-bottom:1px solid rgba(255,255,255,0.04);vertical-align:middle;}
.atab tr:hover td{background:rgba(255,255,255,0.025);cursor:pointer;}
.badge-ok{background:rgba(63,185,80,0.15);color:var(--success);border-radius:20px;padding:2px 8px;font-size:10px;font-weight:600;}
.badge-ko{background:rgba(248,81,73,0.15);color:var(--danger);border-radius:20px;padding:2px 8px;font-size:10px;font-weight:600;}
.btn-act{background:rgba(255,193,7,0.12);border:1px solid rgba(255,193,7,0.3);color:var(--gold);border-radius:var(--radius);padding:7px 14px;font-size:12px;font-weight:600;cursor:pointer;}
.btn-back{background:var(--card);border:1px solid var(--border);color:var(--white);border-radius:var(--radius);padding:7px 14px;font-size:12px;cursor:pointer;}
.btn-danger{background:rgba(248,81,73,0.1);border:1px solid rgba(248,81,73,0.3);color:var(--danger);border-radius:var(--radius);padding:7px 14px;font-size:12px;cursor:pointer;}
.no-results{text-align:center;padding:40px 20px;color:var(--muted);font-size:13px;line-height:1.8;}
.view-btn{background:rgba(255,116,0,0.12);border:1px solid rgba(255,116,0,0.3);color:var(--ember);border-radius:6px;padding:3px 10px;font-size:10px;font-weight:600;cursor:pointer;}

/* DETTAGLIO */
#s-detail{display:none;}
.detail-hd{display:flex;align-items:flex-start;justify-content:space-between;margin-bottom:20px;gap:12px;flex-wrap:wrap;}
.detail-hd h2{font-family:'Bebas Neue',sans-serif;font-size:22px;letter-spacing:2px;color:var(--gold);}
.detail-hero{background:var(--card);border:1px solid var(--border);border-radius:14px;padding:18px;margin-bottom:18px;}
.detail-top{display:flex;align-items:center;justify-content:space-between;margin-bottom:14px;flex-wrap:wrap;gap:8px;}
.detail-name{font-family:'Bebas Neue',sans-serif;font-size:24px;letter-spacing:1px;}
.detail-meta{font-size:12px;color:var(--muted);line-height:1.8;}
.dscore-row{display:grid;grid-template-columns:repeat(4,1fr);gap:8px;}
.dscore{text-align:center;background:var(--ash);border-radius:var(--radius);padding:10px 6px;}
.dscore .dv{font-family:'Bebas Neue',sans-serif;font-size:22px;}
.dscore .dl{font-size:10px;color:var(--muted);text-transform:uppercase;letter-spacing:1px;margin-top:2px;}
.firma-res{background:var(--card);border:1px solid var(--border);border-radius:var(--radius);padding:14px;margin-bottom:16px;}
.firma-res-title{font-size:11px;font-weight:600;color:var(--muted);text-transform:uppercase;letter-spacing:1px;margin-bottom:8px;}
.firma-res img{background:white;border-radius:6px;padding:3px;max-width:200px;}
.test-title{font-family:'Bebas Neue',sans-serif;font-size:18px;letter-spacing:2px;color:var(--ember);margin-bottom:14px;}
.tq{background:var(--card);border:1px solid rgba(255,255,255,0.05);border-radius:10px;padding:14px;margin-bottom:10px;}
.tq.tok{border-left:4px solid var(--success);}
.tq.tko{border-left:4px solid var(--danger);}
.tq.tom{border-left:4px solid var(--muted);}
.tq-num{font-family:'IBM Plex Mono',monospace;font-size:10px;color:var(--muted);margin-bottom:4px;}
.tq-text{font-size:13px;font-weight:600;line-height:1.5;margin-bottom:8px;}
.topt{display:flex;align-items:center;gap:8px;padding:5px 8px;border-radius:6px;font-size:12px;margin-bottom:3px;}
.topt.uok{background:rgba(63,185,80,0.12);border:1px solid rgba(63,185,80,0.3);}
.topt.uko{background:rgba(248,81,73,0.12);border:1px solid rgba(248,81,73,0.3);}
.topt.cor{background:rgba(63,185,80,0.05);border:1px solid rgba(63,185,80,0.12);}
.topt.neu{background:transparent;border:1px solid rgba(255,255,255,0.04);}
.topt-l{width:20px;height:20px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-family:'Bebas Neue',sans-serif;font-size:11px;flex-shrink:0;}
.uok .topt-l{background:var(--success);color:white;}
.uko .topt-l{background:var(--danger);color:white;}
.cor .topt-l{background:rgba(63,185,80,0.4);color:white;}
.neu .topt-l{background:rgba(255,255,255,0.06);color:var(--muted);}
.topt-icon{margin-left:auto;font-size:11px;}
.tspieg{font-size:11px;color:var(--muted);margin-top:6px;padding-top:6px;border-top:1px solid rgba(255,255,255,0.04);line-height:1.5;}

@media(max-width:480px){main{padding:18px 12px 60px;}#s-reg h1{font-size:32px;}.adm-grid{grid-template-columns:repeat(2,1fr);}.dscore-row{grid-template-columns:repeat(2,1fr);}.qr-inner{flex-direction:column;text-align:center;}}
</style>
</head>
<body>

<header>
  <span style="font-size:24px">🔥</span>
  <div>
    <div class="htitle">Corso Antincendio</div>
    <div class="hsub">D.Lgs. 81/08 — D.M. 02/09/2021</div>
  </div>
  <div class="hbadge">VERIFICA FINALE</div>
  <div class="hadmin" onclick="showAdmin()">⚙ ADMIN</div>
</header>
<div id="pb-wrap"><div id="pb"></div></div>

<main>

<!-- REGISTRAZIONE -->
<div id="s-reg">
  <div style="font-size:52px;margin-bottom:14px">🔥</div>
  <h1>QUIZ DI VERIFICA<br>ANTINCENDIO</h1>
  <p class="sub">Addetto alla Prevenzione Incendi — Rischio Medio<br>Inserisci i tuoi dati per iniziare la verifica finale.</p>
  <div class="igrid">
    <div class="icard"><div class="n">20</div><div class="l">Domande</div></div>
    <div class="icard"><div class="n">30'</div><div class="l">Tempo</div></div>
    <div class="icard"><div class="n">70%</div><div class="l">Sufficienza</div></div>
  </div>
  <div class="qr-section">
    <div class="qr-label">📱 QR Code Identificativo Corso</div>
    <div class="qr-inner">
      <div class="qr-box" id="qr-reg"></div>
      <div class="qr-info">
        <div class="qn">Antincendio Rischio Medio</div>
        <div class="qi" id="corso-id-display">ANT-2025-01</div>
        <div class="qd">Scansiona per accedere al quiz<br>Codice univoco per questa lezione</div>
      </div>
    </div>
  </div>
  <div class="fg"><label>Nome e Cognome *</label><input type="text" id="inp-nome" placeholder="Es. Mario Rossi" autocomplete="name"></div>
  <div class="fg"><label>Azienda / Ente</label><input type="text" id="inp-az" placeholder="Es. Rossi Srl"></div>
  <div class="fg"><label>Email</label><input type="email" id="inp-email" placeholder="mario.rossi@email.it" autocomplete="email"></div>
  <div class="firma-box">
    <label>✍️ Firma Digitale *</label>
    <div class="firma-wrap">
      <svg id="firma-svg" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" preserveAspectRatio="none">
        <line x1="4" y1="80" x2="96" y2="80" stroke="#ddd" stroke-width="0.5" stroke-dasharray="4,3"/>
      </svg>
    </div>
    <div class="firma-actions">
      <button class="btn-clear" onclick="clearFirma()">🗑 Cancella</button>
      <span class="firma-hint">Firma con il dito (telefono) o mouse (PC)</span>
    </div>
  </div>
  <button class="btn-start" onclick="startQuiz()">▶ INIZIA IL QUIZ</button>
  <p class="disclaimer">⚠️ Una volta avviato il timer non si ferma. Hai 30 minuti per le 20 domande.</p>
</div>

<!-- QUIZ -->
<div id="s-quiz">
  <div class="qh">
    <div class="qcnt">Domanda <span id="q-cur">1</span> di <span>20</span></div>
    <div class="qtimer" id="q-timer">⏱ 30:00</div>
  </div>
  <div class="qcard"><div class="qnum" id="q-num">DOMANDA 01</div><div class="qtext" id="q-text"></div></div>
  <div class="opts" id="q-opts"></div>
  <div class="fb" id="q-fb"></div>
  <div class="navb">
    <button class="btn-nav" id="btn-prev" onclick="prevQ()" disabled>← Precedente</button>
    <button class="btn-nav pri" id="btn-next" onclick="nextQ()">Successiva →</button>
  </div>
</div>

<!-- RISULTATI -->
<div id="s-res">
  <div class="rcircle">
    <svg width="150" height="150" viewBox="0 0 150 150">
      <circle cx="75" cy="75" r="65" fill="none" stroke="rgba(255,255,255,0.06)" stroke-width="7"/>
      <circle cx="75" cy="75" r="65" fill="none" stroke-width="7" id="r-arc" stroke="var(--ember)" stroke-dasharray="408.41" stroke-dashoffset="408.41" stroke-linecap="round" style="transition:stroke-dashoffset 1.2s ease"/>
    </svg>
    <div class="rscore" id="r-pct">0%</div>
    <div class="rfrac" id="r-frac">0/20</div>
  </div>
  <h2 id="r-title">Risultato</h2>
  <p class="sub" id="r-sub"></p>
  <div class="srow">
    <div class="sc"><div class="sv" style="color:var(--success)" id="r-ok">0</div><div class="sl">Corrette</div></div>
    <div class="sc"><div class="sv" style="color:var(--danger)" id="r-ko">0</div><div class="sl">Errate</div></div>
    <div class="sc"><div class="sv" id="r-time">—</div><div class="sl">Tempo</div></div>
  </div>
  <div class="res-card"><div class="res-card-title">📱 QR Code Corso</div><div class="res-qr-box" id="qr-res"></div></div>
  <!-- BARCODE -->
  <div class="barcode-section" id="barcode-section">
    <div class="barcode-label">📊 Codice a Barre Partecipante</div>
    <svg id="barcode-svg" class="barcode-svg"></svg>
    <div class="barcode-code" id="barcode-code"></div>
  </div>
  <div class="res-card"><div class="res-card-title">✍️ Firma del Partecipante</div><img class="res-firma-img" id="firma-img" src="" alt="Firma"></div>
  <div class="rtitle">📋 RIEPILOGO RISPOSTE</div>
  <div id="r-rev"></div>
  <div class="sbox" id="sbox"><div class="spin" id="spin"></div><span id="sstatus">Salvataggio in corso...</span></div>
</div>

<!-- ADMIN -->
<div id="s-admin">
  <div class="adm-hd">
    <h2>⚙ PANNELLO ADMIN</h2>
    <div style="display:flex;gap:8px;flex-wrap:wrap">
      <button class="btn-act" onclick="loadData()">🔄 Aggiorna</button>
      <button class="btn-act" onclick="exportCSV()">⬇ CSV</button>
      <button class="btn-danger" onclick="clearAll()">🗑 Cancella locale</button>
      <button class="btn-back" onclick="showScreen('s-reg')">← Esci</button>
    </div>
  </div>
  <div class="adm-grid">
    <div class="astat"><div class="av" id="a-tot">0</div><div class="al">Totale</div></div>
    <div class="astat"><div class="av" id="a-ok" style="color:var(--success)">0</div><div class="al">Superati</div></div>
    <div class="astat"><div class="av" id="a-ko" style="color:var(--danger)">0</div><div class="al">Non sup.</div></div>
    <div class="astat"><div class="av" id="a-avg">—</div><div class="al">Media %</div></div>
  </div>
  <div style="overflow-x:auto">
    <table class="atab">
      <thead><tr><th>#</th><th>Nome</th><th>Azienda</th><th>Corso</th><th>Punteggio</th><th>Esito</th><th>Tempo</th><th>Data</th><th></th></tr></thead>
      <tbody id="a-tbody"></tbody>
    </table>
  </div>
  <div class="no-results" id="a-empty" style="display:none">Nessun partecipante ancora.<br><span style="font-size:11px">I dati appaiono qui dopo che i partecipanti completano il quiz.</span></div>
  <div id="a-loading" style="text-align:center;padding:30px;color:var(--muted);font-size:13px"><div class="spin" style="margin:0 auto 10px"></div>Caricamento dati...</div>
</div>

<!-- DETTAGLIO -->
<div id="s-detail">
  <div class="detail-hd">
    <h2>📋 VERIFICA COMPLETA</h2>
    <div style="display:flex;gap:8px">
      <button class="btn-act" onclick="window.print()">🖨 Stampa</button>
      <button class="btn-back" onclick="showScreen('s-admin')">← Torna</button>
    </div>
  </div>
  <div class="detail-hero">
    <div class="detail-top">
      <div><div class="detail-name" id="d-nome">—</div><div class="detail-meta" id="d-meta">—</div></div>
      <span id="d-badge" class="badge-ok">SUPERATO</span>
    </div>
    <div class="dscore-row">
      <div class="dscore"><div class="dv" id="d-pct">—</div><div class="dl">Punteggio</div></div>
      <div class="dscore"><div class="dv" style="color:var(--success)" id="d-ok">—</div><div class="dl">Corrette</div></div>
      <div class="dscore"><div class="dv" style="color:var(--danger)" id="d-ko">—</div><div class="dl">Errate</div></div>
      <div class="dscore"><div class="dv" id="d-time">—</div><div class="dl">Tempo</div></div>
    </div>
  </div>
  <div class="firma-res" id="d-firma-box">
    <div class="firma-res-title">✍️ Firma del Partecipante</div>
    <img id="d-firma" src="" alt="Firma" style="max-width:200px;background:white;border-radius:6px;padding:3px;">
  </div>
  <div class="test-title">📝 TEST COMPLETO</div>
  <div id="d-test"></div>
</div>

</main>

<script>
// ══════════════════════════════════════════════════════
// CONFIGURAZIONE
// ══════════════════════════════════════════════════════
const CORSO_ID   = 'ANT-2025-01';
const CORSO_NOME = 'Antincendio Rischio Medio';
const QUIZ_URL   = window.location.href.split('?')[0];
const FB_URL     = 'https://formazione-camardo-default-rtdb.europe-west1.firebasedatabase.app';

document.getElementById('corso-id-display').textContent = CORSO_ID;

// ══════════════════════════════════════════════════════
// DOMANDE
// ══════════════════════════════════════════════════════
const QUESTIONS = [
  {q:"Cos'è la combustione?",opts:["Reazione fisica tra sostanza e acqua","Reazione chimica tra combustibile e comburente che produce calore, fiamma, gas e fumo","Raffreddamento spontaneo dei materiali","Sola produzione di fumo senza fiamma"],c:1,sp:"La combustione è una reazione chimica tra combustibile e comburente (ossigeno) che genera calore, fiamma, gas e fumo."},
  {q:"Il 'triangolo del fuoco' è composto da:",opts:["Calore, fumo e fiamma","Ossigeno, azoto e idrogeno","Combustibile, comburente ed energia di attivazione","Temperatura, pressione e umidità"],c:2,sp:"Solo la contemporanea presenza di combustibile, comburente ed energia di attivazione genera la combustione."},
  {q:"Quale metodo di spegnimento riduce la concentrazione di ossigeno?",opts:["Raffreddamento","Separazione del combustibile","Soffocamento","Azione chimica anticatalitica"],c:2,sp:"Il soffocamento riduce l'ossigeno al di sotto del 15%, impedendo la combustione."},
  {q:"Quante classi di fuoco definisce la norma UNI EN 2:2005?",opts:["3","4","5","6"],c:2,sp:"La norma UNI EN 2:2005 definisce 5 classi: A, B, C, D, F."},
  {q:"La Classe A degli incendi riguarda:",opts:["Liquidi infiammabili","Gas infiammabili","Materiali solidi che generano braci (legno, carta, tessuti)","Metalli combustibili"],c:2,sp:"La Classe A comprende materiali solidi la cui combustione genera braci. Estinguente: acqua."},
  {q:"Per gli incendi di Classe B l'estinguente più indicato è:",opts:["Acqua a getto pieno","Schiuma (agisce per soffocamento)","Sabbia asciutta","CO2 sempre"],c:1,sp:"Per la Classe B (liquidi infiammabili) la schiuma è il migliore estinguente."},
  {q:"La Classe C degli incendi riguarda:",opts:["Materiali solidi","Mezzi di cottura","Gas infiammabili (metano, GPL, idrogeno)","Metalli combustibili"],c:2,sp:"La Classe C comprende gli incendi di gas infiammabili: metano, GPL, idrogeno, acetilene."},
  {q:"La Classe F degli incendi riguarda:",opts:["Fibre ottiche","Oli e grassi vegetali/animali da cucina","Materiale fotografico","Fuochi d'artificio"],c:1,sp:"La Classe F riguarda gli incendi dei mezzi di cottura con oli e grassi."},
  {q:"Perché la vecchia 'Classe E' è stata eliminata?",opts:["Gli impianti elettrici non bruciano","Riconducibile alle classi A o B","Sostituita dalla classe F","Disciplinata da altra normativa"],c:1,sp:"I fuochi elettrici sono riconducibili alle classi A o B in base al materiale che brucia."},
  {q:"Quale normativa disciplina la sicurezza nei luoghi di lavoro in Italia?",opts:["D.M. 2 settembre 2021","D.Lgs. 9 aprile 2008 n. 81","UNI EN 2:2005","D.M. 26 giugno 1984"],c:1,sp:"Il D.Lgs. 81/2008 è il Testo Unico sulla Sicurezza sul Lavoro."},
  {q:"Il D.M. 2 settembre 2021 definisce:",opts:["Classificazioni europee dei prodotti da costruzione","Criteri sicurezza antincendio e requisiti dei corsi di formazione","Norme per la certificazione degli estintori","Sanzioni per violazioni antincendio"],c:1,sp:"Il D.M. 02/09/2021 definisce i criteri di sicurezza antincendio e i requisiti minimi dei corsi."},
  {q:"Cosa sono i 'limiti di infiammabilità'?",opts:["Temperature massima e minima di combustione","Concentrazione % di combustibile nell'aria entro cui avviene l'accensione","Pressione minima per la combustione","Velocità di propagazione della fiamma"],c:1,sp:"I limiti di infiammabilità indicano l'intervallo di concentrazione del combustibile nell'aria."},
  {q:"Cos'è la 'pirolisi'?",opts:["Produzione di fumo nero","Raffreddamento rapido a contatto con acqua","Decomposizione termochimica del solido per effetto del calore","Aumento di pressione in caso d'incendio"],c:2,sp:"La pirolisi è la decomposizione termochimica del materiale solido causata dal calore."},
  {q:"Cosa indica 'REI 90'?",opts:["Resistenza al fuoco di 90 secondi","Stabilità, tenuta e isolamento termico per almeno 90 minuti","Classe di reazione al fuoco 90","Testato a 90°C"],c:1,sp:"REI 90: R=stabilità meccanica, E=tenuta, I=isolamento termico, per almeno 90 minuti."},
  {q:"La lettera 'R' nella resistenza al fuoco indica:",opts:["Resistenza termica","Riduzione propagazione fumo","Capacità portante (stabilità meccanica)","Resistenza all'umidità"],c:2,sp:"R indica la Capacità portante, ovvero la stabilità meccanica dell'elemento strutturale."},
  {q:"Nelle Euroclassi i materiali incombustibili sono:",opts:["Classe E e F","Classe A1 e A2","Classe 0 e 1","Classe B e C"],c:1,sp:"Nelle Euroclassi (UNI EN 13501-1), A1 e A2 identificano i materiali incombustibili."},
  {q:"Cosa significa 'A2-s1,d0'?",opts:["Quasi incombustibile, fumo scarso, nessuna goccia infiammabile","Classe A2 con fumo elevato e gocce","Combustibile con resistenza 2 minuti","Pavimentazione classe A"],c:0,sp:"A2=quasi incombustibile; s1=fumo scarso; d0=nessuna goccia o particella infiammabile."},
  {q:"Cos'è il 'carico d'incendio specifico di progetto' qf,d?",opts:["Peso massimo combustibili ammesso","Carico d'incendio corretto con parametri di rischio; riferimento per la resistenza al fuoco","Quantità di estinguente necessaria","Temperatura massima raggiungibile"],c:1,sp:"Il qf,d è il carico d'incendio corretto con i parametri di rischio e le misure antincendio presenti."},
  {q:"Affermazione CORRETTA sulla trasmissione del calore:",opts:["La convezione avviene solo nei solidi","L'irraggiamento richiede un mezzo materiale","Conduzione=contatto diretto, convezione=fluidi, irraggiamento=onde EM","La conduzione è principale negli incendi grandi"],c:2,sp:"Conduzione=contatto; Convezione=fluidi in movimento; Irraggiamento=onde elettromagnetiche."},
  {q:"Corso da 8 ore (D.M. 02/09/2021) corrisponde a quale livello di rischio?",opts:["Rischio basso","Rischio medio","Rischio alto","Non correlato alla durata"],c:1,sp:"D.M. 02/09/2021: 4 ore=rischio basso, 8 ore=rischio medio, 16 ore=rischio alto."}
];

// ══════════════════════════════════════════════════════
// BARCODE CODE128
// ══════════════════════════════════════════════════════
const CODE128_TABLE=[
  [2,1,2,2,2,2],[2,2,2,1,2,2],[2,2,2,2,2,1],[1,2,1,2,2,3],[1,2,1,3,2,2],
  [1,3,1,2,2,2],[1,2,2,2,1,3],[1,2,2,3,1,2],[1,3,2,2,1,2],[2,2,1,2,1,3],
  [2,2,1,3,1,2],[2,3,1,2,1,2],[1,1,2,2,3,2],[1,2,2,1,3,2],[1,2,2,2,3,1],
  [1,1,3,2,2,2],[1,2,3,1,2,2],[1,2,3,2,2,1],[2,2,3,2,1,1],[2,2,1,1,3,2],
  [2,2,1,2,3,1],[2,1,3,2,1,2],[2,2,3,1,1,2],[3,1,2,1,3,1],[3,1,1,2,2,2],
  [3,2,1,1,2,2],[3,2,1,2,2,1],[3,1,2,2,1,2],[3,2,2,1,1,2],[3,2,2,2,1,1],
  [2,1,2,1,2,3],[2,1,2,3,2,1],[2,3,2,1,2,1],[1,1,1,3,2,3],[1,3,1,1,2,3],
  [1,3,1,3,2,1],[1,1,2,3,1,3],[1,3,2,1,1,3],[1,3,2,3,1,1],[2,1,1,3,1,3],
  [2,3,1,1,1,3],[2,3,1,3,1,1],[1,1,2,1,3,3],[1,1,2,3,3,1],[1,3,2,1,3,1],
  [1,1,3,1,2,3],[1,1,3,3,2,1],[1,3,3,1,2,1],[3,1,3,1,2,1],[2,1,1,3,3,1],
  [2,3,1,1,3,1],[2,1,3,1,1,3],[2,1,3,3,1,1],[2,1,3,1,3,1],[3,1,1,1,2,3],
  [3,1,1,3,2,1],[3,3,1,1,2,1],[3,1,2,1,1,3],[3,1,2,3,1,1],[3,3,2,1,1,1],
  [3,1,4,1,1,1],[2,2,1,4,1,1],[4,3,1,1,1,1],[1,1,1,2,2,4],[1,1,1,4,2,2],
  [1,2,1,1,2,4],[1,2,1,4,2,1],[1,4,1,1,2,2],[1,4,1,2,2,1],[1,1,2,2,1,4],
  [1,1,2,4,1,2],[1,2,2,1,1,4],[1,2,2,4,1,1],[1,4,2,1,1,2],[1,4,2,2,1,1],
  [2,4,1,2,1,1],[2,2,1,1,1,4],[4,1,3,1,1,1],[2,4,1,1,1,2],[1,3,4,1,1,1],
  [1,1,1,2,4,2],[1,2,1,1,4,2],[1,2,1,2,4,1],[1,1,4,2,1,2],[1,2,4,1,1,2],
  [1,2,4,2,1,1],[4,1,1,2,1,2],[4,2,1,1,1,2],[4,2,1,2,1,1],[2,1,2,1,4,1],
  [2,1,4,1,2,1],[4,1,2,1,2,1],[1,1,1,1,4,3],[1,1,1,3,4,1],[1,3,1,1,4,1],
  [1,1,4,1,1,3],[1,1,4,3,1,1],[4,1,1,1,1,3],[4,1,1,3,1,1],[1,1,3,1,4,1],
  [1,1,4,1,3,1],[3,1,1,1,4,1],[4,1,1,1,3,1],[2,1,1,4,1,2],[2,1,1,2,1,4],
  [2,1,1,2,3,2],[2,3,3,1,1,1,2]
];
const START_B=104,STOP_IDX=106;
function encodeBarcode(text){
  const chars=[];
  for(let i=0;i<text.length;i++){const c=text.charCodeAt(i)-32;if(c>=0&&c<96)chars.push(c);}
  let check=START_B;
  chars.forEach((c,i)=>check+=(c*(i+1)));
  check=check%103;
  return [START_B,...chars,check,STOP_IDX];
}
function drawBarcode(svgEl,text,barW=2,barH=60){
  const indices=encodeBarcode(text);
  const bars=[];
  indices.forEach(idx=>{const p=CODE128_TABLE[idx];if(p)bars.push(...p);});
  const totalW=bars.reduce((s,b)=>s+b,0)*barW+20;
  svgEl.setAttribute('width',totalW);
  svgEl.setAttribute('height',barH+20);
  svgEl.innerHTML='';
  let x=10;
  bars.forEach((w,i)=>{
    if(i%2===0){
      const rect=document.createElementNS('http://www.w3.org/2000/svg','rect');
      rect.setAttribute('x',x);rect.setAttribute('y',10);
      rect.setAttribute('width',w*barW);rect.setAttribute('height',barH);
      rect.setAttribute('fill','#000');
      svgEl.appendChild(rect);
    }
    x+=w*barW;
  });
}
function makeBarcodeCode(nome,corsoId){
  const ini=nome.split(' ').map(p=>p[0]||'').join('').toUpperCase().slice(0,3).padEnd(3,'X');
  const cor=(corsoId||'ANT').replace(/[^A-Z0-9]/gi,'').toUpperCase().slice(0,6);
  const dt=new Date();
  const dateStr=`${dt.getFullYear()}${String(dt.getMonth()+1).padStart(2,'0')}${String(dt.getDate()).padStart(2,'0')}`;
  return `${ini}-${cor}-${dateStr}`;
}

// ══════════════════════════════════════════════════════
// FIRMA SVG
// ══════════════════════════════════════════════════════
const svg=document.getElementById('firma-svg');
let drawing=false,curPath=null,pathD='';
function getSVGPos(e){const r=svg.getBoundingClientRect(),s=e.touches?e.touches[0]:e;return{x:((s.clientX-r.left)/r.width*100).toFixed(2),y:((s.clientY-r.top)/r.height*100).toFixed(2)};}
function startDraw(e){e.preventDefault();drawing=true;const p=getSVGPos(e);pathD=`M${p.x} ${p.y}`;curPath=document.createElementNS('http://www.w3.org/2000/svg','path');curPath.setAttribute('fill','none');curPath.setAttribute('stroke','#111');curPath.setAttribute('stroke-width','2.5');curPath.setAttribute('stroke-linecap','round');curPath.setAttribute('stroke-linejoin','round');svg.appendChild(curPath);}
function moveDraw(e){if(!drawing||!curPath)return;e.preventDefault();const p=getSVGPos(e);pathD+=` L${p.x} ${p.y}`;curPath.setAttribute('d',pathD);}
function endDraw(){drawing=false;curPath=null;}
svg.addEventListener('mousedown',startDraw);svg.addEventListener('mousemove',moveDraw);svg.addEventListener('mouseup',endDraw);svg.addEventListener('mouseleave',endDraw);
svg.addEventListener('touchstart',startDraw,{passive:false});svg.addEventListener('touchmove',moveDraw,{passive:false});svg.addEventListener('touchend',endDraw);svg.addEventListener('touchcancel',endDraw);
function clearFirma(){[...svg.querySelectorAll('path')].forEach(p=>p.remove());}
function isFirmaVuota(){return svg.querySelectorAll('path').length===0;}
function getSVGDataURL(){const c=svg.cloneNode(true),r=svg.getBoundingClientRect();c.setAttribute('width',r.width);c.setAttribute('height',r.height);c.setAttribute('viewBox','0 0 100 100');c.style.background='white';return 'data:image/svg+xml;base64,'+btoa(unescape(encodeURIComponent(new XMLSerializer().serializeToString(c))));}

// ══════════════════════════════════════════════════════
// QR CODE
// ══════════════════════════════════════════════════════
function makeQR(id,url,sz){const el=document.getElementById(id);if(!el)return;el.innerHTML='';new QRCode(el,{text:url,width:sz||94,height:sz||94,colorDark:'#000',colorLight:'#fff',correctLevel:QRCode.CorrectLevel.M});}
window.addEventListener('load',()=>makeQR('qr-reg',QUIZ_URL,94));

// ══════════════════════════════════════════════════════
// STATO QUIZ
// ══════════════════════════════════════════════════════
const L=['A','B','C','D'];
let cQ=0,ans=new Array(QUESTIONS.length).fill(null);
let startTime,timerInt,secLeft=30*60;
let pData={},firmaURL='',done=false;

function showScreen(id){
  ['s-reg','s-quiz','s-res','s-admin','s-detail'].forEach(s=>document.getElementById(s).style.display='none');
  document.getElementById(id).style.display='block';
  document.getElementById('pb').style.width='0%';
  window.scrollTo(0,0);
}

function startQuiz(){
  const nome=document.getElementById('inp-nome').value.trim();
  if(!nome){alert('Inserisci nome e cognome per procedere.');return;}
  if(isFirmaVuota()){alert('Firma digitale obbligatoria prima di iniziare.');return;}
  firmaURL=getSVGDataURL();
  pData={nome,azienda:document.getElementById('inp-az').value.trim()||'—',email:document.getElementById('inp-email').value.trim()||'—'};
  showScreen('s-quiz');startTime=new Date();startTimer();renderQ();
}
function startTimer(){timerInt=setInterval(()=>{secLeft--;const m=Math.floor(secLeft/60),s=secLeft%60;const el=document.getElementById('q-timer');el.textContent=`⏱ ${String(m).padStart(2,'0')}:${String(s).padStart(2,'0')}`;if(secLeft<=300)el.classList.add('warn');if(secLeft<=0){clearInterval(timerInt);finishQuiz();}},1000);}
function renderQ(){const q=QUESTIONS[cQ];document.getElementById('q-cur').textContent=cQ+1;document.getElementById('q-num').textContent=`DOMANDA ${String(cQ+1).padStart(2,'0')}`;document.getElementById('q-text').textContent=q.q;const oc=document.getElementById('q-opts');oc.innerHTML='';q.opts.forEach((o,i)=>{const d=document.createElement('div');d.className='opt'+(ans[cQ]===i?' sel':'');d.innerHTML=`<div class="oletter">${L[i]}</div><div class="otext">${o}</div>`;if(ans[cQ]===null)d.onclick=()=>selectAns(i);oc.appendChild(d);});const fb=document.getElementById('q-fb');fb.style.display='none';fb.className='fb';if(ans[cQ]!==null){showFB(ans[cQ]);markOpts(ans[cQ]);}document.getElementById('btn-prev').disabled=cQ===0;const nb=document.getElementById('btn-next');if(cQ===QUESTIONS.length-1){nb.textContent='Termina quiz ✓';nb.onclick=finishQuiz;}else{nb.textContent='Successiva →';nb.onclick=nextQ;}document.getElementById('pb').style.width=(cQ/QUESTIONS.length*100)+'%';}
function selectAns(i){if(ans[cQ]!==null)return;ans[cQ]=i;markOpts(i);showFB(i);}
function markOpts(sel){const cor=QUESTIONS[cQ].c;document.querySelectorAll('.opt').forEach((o,i)=>{o.onclick=null;if(i===cor)o.classList.add('ok');else if(i===sel&&sel!==cor)o.classList.add('ko');});}
function showFB(sel){const q=QUESTIONS[cQ],ok=sel===q.c;const fb=document.getElementById('q-fb');fb.className='fb '+(ok?'ok':'ko');fb.textContent=(ok?'✅ Risposta corretta! ':'❌ Risposta errata. ')+q.sp;fb.style.display='block';}
function nextQ(){if(cQ<QUESTIONS.length-1){cQ++;renderQ();}}
function prevQ(){if(cQ>0){cQ--;renderQ();}}

// ══════════════════════════════════════════════════════
// FINE QUIZ
// ══════════════════════════════════════════════════════
function finishQuiz(){
  if(done)return;done=true;clearInterval(timerInt);
  const elapsed=Math.floor((new Date()-startTime)/1000);
  const eM=Math.floor(elapsed/60),eS=elapsed%60;
  const ok=ans.filter((a,i)=>a===QUESTIONS[i].c).length;
  const ko=ans.filter((a,i)=>a!==null&&a!==QUESTIONS[i].c).length;
  const pct=Math.round(ok/QUESTIONS.length*100);
  const passed=pct>=70;
  document.getElementById('pb').style.width='100%';
  showScreen('s-res');
  setTimeout(()=>{const arc=document.getElementById('r-arc');arc.style.strokeDashoffset=408.41-(pct/100)*408.41;arc.style.stroke=passed?'var(--success)':'var(--danger)';},100);
  document.getElementById('r-pct').textContent=pct+'%';
  document.getElementById('r-pct').style.color=passed?'var(--success)':'var(--danger)';
  document.getElementById('r-frac').textContent=`${ok}/${QUESTIONS.length}`;
  document.getElementById('r-title').textContent=passed?'🎉 SUPERATO!':'❌ NON SUPERATO';
  document.getElementById('r-title').style.color=passed?'var(--success)':'var(--danger)';
  document.getElementById('r-sub').textContent=passed?`Complimenti ${pData.nome}! Hai superato la verifica con il ${pct}%.`:`${pData.nome}, hai ottenuto ${pct}%. La sufficienza è al 70%.`;
  document.getElementById('r-ok').textContent=ok;
  document.getElementById('r-ko').textContent=ko;
  document.getElementById('r-time').textContent=`${eM}'${String(eS).padStart(2,'0')}"`;
  document.getElementById('firma-img').src=firmaURL;
  makeQR('qr-res',QUIZ_URL,80);

  // BARCODE
  const bcode=makeBarcodeCode(pData.nome,CORSO_ID);
  document.getElementById('barcode-code').textContent=bcode;
  drawBarcode(document.getElementById('barcode-svg'),bcode);

  const rc=document.getElementById('r-rev');rc.innerHTML='';
  QUESTIONS.forEach((q,i)=>{const ua=ans[i],isok=ua===q.c;const d=document.createElement('div');d.className=`ri ${isok?'rok':'rko'}`;d.innerHTML=`<div class="rq"><strong>${i+1}.</strong> ${q.q}</div><div class="ra">${ua!==null?`<span class="${isok?'ca':'wa'}">Tua: ${L[ua]}. ${q.opts[ua]}</span>`:'<span>Non risposta</span>'}${!isok?`<br><span class="ca">✓ Corretta: ${L[q.c]}. ${q.opts[q.c]}</span>`:''}</div>`;rc.appendChild(d);});

  const record={nome:pData.nome,azienda:pData.azienda,email:pData.email,corso_id:CORSO_ID,corso_nome:CORSO_NOME,ok,ko,pct,passed,tempo:`${eM}m ${eS}s`,data:new Date().toLocaleString('it-IT'),firma:firmaURL,barcode:bcode,answers:[...ans]};
  saveRecord(record);
}

// ══════════════════════════════════════════════════════
// SALVATAGGIO — Firebase + localStorage (NO Netlify)
// ══════════════════════════════════════════════════════
async function saveRecord(record){
  const sb=document.getElementById('sbox');sb.style.display='flex';
  // Firebase
  try{
    await fetch(`${FB_URL}/quiz_antincendio.json`,{
      method:'POST',
      headers:{'Content-Type':'application/json'},
      body:JSON.stringify({
        nome:record.nome,azienda:record.azienda,email:record.email,
        corso_id:record.corso_id,corso_nome:record.corso_nome,
        ok:record.ok,ko:record.ko,pct:record.pct,passed:record.passed,
        tempo:record.tempo,data:record.data,firma:record.firma,
        barcode:record.barcode,answers:record.answers
      })
    });
  }catch(e){console.log('Firebase error',e);}
  // localStorage backup
  const local=JSON.parse(localStorage.getItem('ant_results')||'[]');
  local.push(record);
  localStorage.setItem('ant_results',JSON.stringify(local));

  document.getElementById('spin').style.display='none';
  document.getElementById('sstatus').innerHTML='<span class="sok">✅ Quiz completato! Risultati salvati.</span>';
}

// ══════════════════════════════════════════════════════
// ADMIN
// ══════════════════════════════════════════════════════
let adminData=[];

function showAdmin(){
  const pw=prompt('🔐 Password admin:');
  if(pw!=='1234'){alert('Password errata.');return;}
  showScreen('s-admin');
  loadData();
}

async function loadData(){
  document.getElementById('a-loading').style.display='block';
  document.getElementById('a-empty').style.display='none';
  document.getElementById('a-tbody').innerHTML='';
  adminData=[];
  try{
    const res=await fetch(`${FB_URL}/quiz_antincendio.json`);
    const data=await res.json();
    if(data){Object.values(data).forEach(r=>{if(r&&r.nome)adminData.push(r);});}
    adminData.sort((a,b)=>new Date(b.data)-new Date(a.data));
  }catch(e){
    adminData=JSON.parse(localStorage.getItem('ant_results')||'[]');
  }
  renderAdminTable();
}

function renderAdminTable(){
  document.getElementById('a-loading').style.display='none';
  const tot=adminData.length;
  const ok=adminData.filter(r=>r.passed).length;
  document.getElementById('a-tot').textContent=tot;
  document.getElementById('a-ok').textContent=ok;
  document.getElementById('a-ko').textContent=tot-ok;
  document.getElementById('a-avg').textContent=tot?Math.round(adminData.reduce((s,r)=>s+(r.pct||0),0)/tot)+'%':'—';
  const tb=document.getElementById('a-tbody');tb.innerHTML='';
  document.getElementById('a-empty').style.display=tot?'none':'block';
  adminData.forEach((r,i)=>{
    const hasDetail=r.answers!=null;
    const tr=document.createElement('tr');
    tr.innerHTML=`<td style="color:var(--muted)">${i+1}</td>
      <td style="font-weight:600">${r.nome}</td>
      <td style="color:var(--muted)">${r.azienda||'—'}</td>
      <td style="font-family:'IBM Plex Mono',monospace;font-size:10px;color:var(--muted)">${r.corso_id||'—'}</td>
      <td>${r.ok!==undefined?r.ok:'-'}/20 <span style="color:var(--muted)">(${r.pct}%)</span></td>
      <td><span class="${r.passed?'badge-ok':'badge-ko'}">${r.passed?'SUPERATO':'NON SUP.'}</span></td>
      <td style="color:var(--muted)">${r.tempo||'—'}</td>
      <td style="color:var(--muted);font-size:11px">${r.data||'—'}</td>
      <td>${hasDetail?`<button class="view-btn" onclick="openDetail(${i})">👁 Apri</button>`:'—'}</td>`;
    if(hasDetail)tr.onclick=()=>openDetail(i);
    tb.appendChild(tr);
  });
}

function openDetail(idx){
  const r=adminData[idx];if(!r||!r.answers)return;
  document.getElementById('d-nome').textContent=r.nome;
  document.getElementById('d-meta').innerHTML=`🏢 ${r.azienda||'—'} &nbsp;|&nbsp; 📧 ${r.email||'—'} &nbsp;|&nbsp; 📅 ${r.data}<br>📱 Corso: ${r.corso_id||'—'}`;
  document.getElementById('d-badge').className=r.passed?'badge-ok':'badge-ko';
  document.getElementById('d-badge').textContent=r.passed?'✅ SUPERATO':'❌ NON SUPERATO';
  document.getElementById('d-pct').textContent=r.pct+'%';
  document.getElementById('d-pct').style.color=r.passed?'var(--success)':'var(--danger)';
  document.getElementById('d-ok').textContent=r.ok||'—';
  document.getElementById('d-ko').textContent=r.ko||'—';
  document.getElementById('d-time').textContent=r.tempo||'—';
  const firmaEl=document.getElementById('d-firma');
  if(r.firma){firmaEl.src=r.firma;document.getElementById('d-firma-box').style.display='block';}
  else{document.getElementById('d-firma-box').style.display='none';}
  const cont=document.getElementById('d-test');cont.innerHTML='';
  QUESTIONS.forEach((q,i)=>{
    const ua=r.answers[i];const isok=ua===q.c;const om=ua===null||ua===undefined;
    const div=document.createElement('div');div.className=`tq ${om?'tom':isok?'tok':'tko'}`;
    let optsHtml='';
    q.opts.forEach((opt,oi)=>{
      const isU=ua===oi,isC=q.c===oi;
      let cls='neu',icon='';
      if(isU&&isC){cls='uok';icon='✅';}else if(isU&&!isC){cls='uko';icon='❌';}else if(!isU&&isC&&!isok){cls='cor';icon='✓';}
      optsHtml+=`<div class="topt ${cls}"><div class="topt-l">${L[oi]}</div><span>${opt}</span><span class="topt-icon">${icon}</span></div>`;
    });
    const stato=om?'<span style="color:var(--muted)">⚪ Omessa</span>':isok?'<span style="color:var(--success)">✅ Corretta</span>':'<span style="color:var(--danger)">❌ Errata</span>';
    div.innerHTML=`<div class="tq-num">DOMANDA ${String(i+1).padStart(2,'0')} • ${stato}</div><div class="tq-text">${q.q}</div><div>${optsHtml}</div><div class="tspieg">💡 ${q.sp}</div>`;
    cont.appendChild(div);
  });
  showScreen('s-detail');
}

function clearAll(){
  if(!confirm('Cancellare tutti i dati locali?'))return;
  localStorage.removeItem('ant_results');adminData=[];renderAdminTable();
}
function exportCSV(){
  if(!adminData.length){alert('Nessun dato da esportare.');return;}
  const h='Nome,Azienda,Email,Corso,Punteggio,Esito,Tempo,Data,Barcode\n';
  const rows=adminData.map(r=>`"${r.nome}","${r.azienda||''}","${r.email||''}","${r.corso_id||''}","${r.ok!==undefined?r.ok:''}/20 (${r.pct}%)","${r.passed?'SUPERATO':'NON SUPERATO'}","${r.tempo||''}","${r.data||''}","${r.barcode||''}"`).join('\n');
  const a=document.createElement('a');a.href='data:text/csv;charset=utf-8,\uFEFF'+encodeURIComponent(h+rows);a.download='risultati_antincendio.csv';a.click();
}
</script>
</body>
</html>
