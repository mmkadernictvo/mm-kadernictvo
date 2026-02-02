<!DOCTYPE html>
<html lang="sk">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>M&M Kaderníctvo</title>

  <style>
    :root{
      --bg:#f6f6f6;
      --card:#ffffff;
      --text:#111111;
      --muted:#5a5a5a;
      --line:#e7e7e7;
      --shadow: 0 10px 30px rgba(0,0,0,.07);
      --radius:18px;
    }

    *{box-sizing:border-box}

    body{
      margin:0;
      font-family: Arial, sans-serif;
      color:var(--text);
      background:
        radial-gradient(900px 500px at 20% 0%, rgba(0,0,0,.06), transparent 60%),
        radial-gradient(800px 500px at 80% 10%, rgba(0,0,0,.04), transparent 55%),
        var(--bg);
    }

    a{color:inherit}
    .wrap{max-width:1100px; margin:0 auto; padding:0 18px;}

    /* ===== TOPBAR ===== */
    .topbar{
      position:sticky;
      top:0;
      z-index:50;
      background: rgba(246,246,246,.9);
      backdrop-filter: blur(10px);
      border-bottom:1px solid var(--line);
    }

    .topbar .inner{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:14px;
      padding:12px 0;
    }

    .brand{
      display:flex;
      align-items:center;
      gap:12px;
      min-width:240px;
    }

    .logo{
      width:100px;
      height:100px;
      border-radius:16px;
      background:#fff;
      border:1px solid var(--line);
      box-shadow: 0 8px 18px rgba(0,0,0,.06);
      display:flex;
      align-items:center;
      justify-content:center;
      overflow:hidden;
      flex:0 0 auto;
      padding:6px;
    }

    .logo img{
      width:100%;
      height:100%;
      object-fit:contain;
      display:block;
    }

    .brand h1{
      margin:0;
      font-size:24px;
      letter-spacing:2px;
    }

    .brand small{
      display:block;
      margin-top:4px;
      color:var(--muted);
      font-size:15px;
      line-height:1.4;
    }

    nav{
      display:flex;
      gap:16px;
      flex-wrap:wrap;
      justify-content:flex-end;
    }

    nav a{
      text-decoration:none;
      color:var(--muted);
      font-size:15px;
      letter-spacing:1px;
      padding:10px 12px;
      border-radius:12px;
    }

    nav a:hover{
      color:var(--text);
      background: rgba(0,0,0,.05);
    }

    /* ===== HERO ===== */
    .hero{padding:56px 0 24px;}

    .hero-grid{
      display:grid;
      grid-template-columns: 1.2fr .8fr;
      gap:18px;
      align-items:stretch;
    }

    .hero-card{
      background: linear-gradient(180deg, rgba(255,255,255,1), rgba(255,255,255,.92));
      border:1px solid var(--line);
      border-radius: var(--radius);
      padding:26px;
      box-shadow: var(--shadow);
      position:relative;
      overflow:hidden;
    }

    .hero-card:before{
      content:"";
      position:absolute;
      inset:-90px -130px auto auto;
      width:280px;
      height:280px;
      border-radius:999px;
      background: rgba(0,0,0,.08);
      filter: blur(45px);
      transform: rotate(18deg);
    }

    .hero h2{
      margin:0 0 10px;
      font-size:44px;
      line-height:1.06;
      letter-spacing:.3px;
      position:relative;
    }

    .hero p{
      margin:0 0 16px;
      color:var(--muted);
      font-size:16px;
      position:relative;
      max-width: 650px;
    }

    .chips{
      display:flex;
      gap:10px;
      flex-wrap:wrap;
      position:relative;
    }

    .chip{
      font-size:12px;
      padding:8px 10px;
      border-radius:999px;
      border:1px solid var(--line);
      background: rgba(0,0,0,.03);
      color: #222;
    }

    .side-card{
      background: var(--card);
      border:1px solid var(--line);
      border-radius: var(--radius);
      padding:18px;
      box-shadow: var(--shadow);
    }

    .side-card h3{
      margin:0 0 10px;
      font-size:14px;
      color:#111;
      letter-spacing:.4px;
    }

    .kv{
      display:grid;
      gap:10px;
      color:var(--muted);
      font-size:14px;
    }

    .kv b{color:var(--text)}

    /* ===== SEKCIE ===== */
    section{padding:22px 0;}

    h3.section-title{
      margin:0 0 12px;
      color:#111;
      font-size:18px;
      letter-spacing:.4px;
    }

    .grid{
      display:grid;
      grid-template-columns: repeat(3, 1fr);
      gap:14px;
    }

    .card{
      background: var(--card);
      border:1px solid var(--line);
      border-radius:16px;
      padding:16px;
      box-shadow: 0 10px 22px rgba(0,0,0,.05);
    }

    .list{margin:0; padding-left:18px; color:var(--muted)}
    .list li{margin:8px 0}

    /* Team */
    .team-role{
      font-weight:700;
      letter-spacing:.3px;
      margin-bottom:8px;
    }
    .team-desc{color:var(--muted); margin:0; line-height:1.6;}

    /* Kontakt / O nás */
    .contact-card{
      background: var(--card);
      border:1px solid var(--line);
      border-radius: var(--radius);
      padding:18px;
      box-shadow: var(--shadow);
      display:grid;
      grid-template-columns: 1fr 1fr;
      gap:16px;
    }
    .contact-card p{margin:8px 0; color:var(--muted)}

    /* O nás – jeden stĺpec, text ako v knihe (doľava), ale blok v strede */
    #onas .contact-card{
      grid-template-columns: 1fr;
    }
    #onas .contact-card p{
      max-width: 700px;
      margin: 0 auto 12px;
      text-align: left;
    }

    /* Galéria – aby fotky neboli obrovské */
    .gallery-img{
      width: 100%;
      height: 180px;
      object-fit: cover;
      border-radius: 16px;
      display: block;
    }

    /* Spodný box */
    .bottom-message{
      margin:34px auto 10px;
      max-width: 900px;
      background: #111;
      color:#fff;
      border-radius: var(--radius);
      padding:18px 18px;
      text-align:center;
      box-shadow: 0 14px 28px rgba(0,0,0,.12);
      letter-spacing:.2px;
    }
    .bottom-message span{
      color: rgba(255,255,255,.95);
    }

    .footer{
      padding:18px 0;
      border-top:1px solid var(--line);
      color:#777;
      font-size:13px;
      text-align:center;
      margin-top:10px;
    }

    @media (max-width: 900px){
      .hero-grid{grid-template-columns:1fr}
      .grid{grid-template-columns:1fr}
      .contact-card{grid-template-columns:1fr}
      nav{display:none}
      .hero h2{font-size:34px}
    }
  </style>
</head>

<body>

  <!-- TOPBAR -->
  <div class="topbar">
    <div class="wrap">
      <div class="inner">

        <div class="brand">
          <div class="logo">
            <img src="logo.png" alt="M&M Kaderníctvo logo" onerror="this.style.display='none'">
          </div>
          <div>
            <h1>M&M KADERNÍCTVO</h1>
            <small>„Štýl pre ženy, mužov a deti“</small>
          </div>
        </div>

        <nav>
          <a href="#sluzby">Služby</a>
          <a href="#tim">Náš tím</a>
          <a href="#cennik">Cenník</a>
          <a href="#galeria">Galéria</a>
          <a href="#kontakt">Kontakt</a>
          <a href="#onas">O nás</a>
        </nav>

      </div>
    </div>
  </div>

  <!-- HERO -->
  <div class="hero">
    <div class="wrap">
      <div class="hero-grid">

        <div class="hero-card">
          <h2>Štýl, ktorý sadne hneď na prvý pohľad</h2>
          <p>
            V M&M Kaderníctve kladieme dôraz na detail, čistotu, profesionalitu a individuálny prístup.
            Príď si po zmenu, ktorá ti bude sedieť.
          </p>
          <div class="chips">
            <div class="chip">Dámske strihanie</div>
            <div class="chip">Pánske strihanie</div>
            <div class="chip">Detské strihanie</div>
            <div class="chip">Farbenie</div>
            <div class="chip">Umývanie vlasov</div>
            <div class="chip">Sušenie vlasov</div>
            <div class="chip">Melír</div>
            <div class="chip">Styling</div>
            <div class="chip">Spoločenské účesy</div>
            <div class="chip">Úprava brady</div>
            <div class="chip">...</div>
          </div>
        </div>

        <!-- RÝCHLE INFO -->
        <div class="side-card">
          <h3>Rýchle info</h3>
          <div class="kv">
            <div><b>📍 Adresa:</b> Aténska 25, Košice</div>
            <div><b>🕒 Otváracie hodiny:</b> Podľa objednávok</div>
            <div><b>📞 Telefón:</b> Melinda Pavlíková: 0908 985 971</div>
            <div><b>📞 Telefón:</b> Marcela Tkáčová: 0950 749 145</div>
          </div>
          <p style="margin:12px 0 0; color:var(--muted); font-size:13px;">
            Rezervácia odporúčaná – termíny sa rýchlo míňajú.
          </p>
        </div>

      </div>
    </div>
  </div>

  <!-- SLUŽBY -->
  <section id="sluzby">
    <div class="wrap">
      <h3 class="section-title">Služby</h3>

      <div class="grid">
        <div class="card">
          <b>Dámske</b>
          <ul class="list">
            <li>Dámsky strih</li>
            <li>Fúkaná &amp; styling</li>
            <li>Umývanie vlasov</li>
            <li>Spoločenské účesy</li>
          </ul>
        </div>

        <div class="card">
          <b>Pánske</b>
          <ul class="list">
            <li>Pánsky strih</li>
            <li>Fade / kontúry</li>
            <li>Úprava brady</li>
          </ul>
        </div>

        <div class="card">
          <b>Farbenie</b>
          <ul class="list">
            <li>Farbenie / tónovanie</li>
            <li>Melír / balayage</li>
            <li>Preliv</li>
            <li>Farbenie vlastnou farbou</li>
          </ul>
        </div>
      </div>
    </div>
  </section>

  <!-- NÁŠ TÍM -->
  <section id="tim">
    <div class="wrap">
      <h3 class="section-title">Náš tím</h3>

      <div class="grid">
        <div class="card">
          <b>Kaderníčka Melinda</b>
          <div class="team-role">„Meli“</div>
          <p class="team-desc">
            - práca kaderníčky sa jej zapáčila hneď po škole<br>
            - roky praxe a skúseností<br>
            - táto práca ju robí šťastnou
          </p>
        </div>

        <div class="card">
          <b>Kaderníčka Marcela</b>
          <div class="team-role">„Marcelka“</div>
          <p class="team-desc">
            - profíčka s bohatými skúsenosťami<br>
            - zákazníkom vždy poradí s úsmevom na tvári najlepšie ako vie
          </p>
        </div>

        <div class="card">
          <b>Objednávky</b>
          <p class="team-desc">
            Objednávať sa môžete telefonicky, SMS správou alebo priamo v kaderníctve.
          </p>
        </div>
      </div>
    </div>
  </section>

  <!-- CENNÍK -->
  <section id="cennik">
    <div class="wrap">
      <h3 class="section-title">Cenník (orientačne)</h3>

      <div class="card">
        <div style="display:flex; justify-content:space-between; padding:10px 0; border-bottom:1px dashed var(--line); color:var(--muted);">
          <span>Dámsky strih</span> <b style="color:var(--text);">od 10–13 €</b>
        </div>
        <div style="display:flex; justify-content:space-between; padding:10px 0; border-bottom:1px dashed var(--line); color:var(--muted);">
          <span>Pánsky strih</span> <b style="color:var(--text);">od 9–13 €</b>
        </div>
        <div style="display:flex; justify-content:space-between; padding:10px 0; border-bottom:1px dashed var(--line); color:var(--muted);">
          <span>Farbenie</span> <b style="color:var(--text);">od 17–28 €</b>
        </div>
        <div style="display:flex; justify-content:space-between; padding:10px 0; color:var(--muted);">
          <span>Styling / fúkaná</span> <b style="color:var(--text);">od 22–32 €</b>
        </div>

        <p style="margin:12px 0 0; color:var(--muted); font-size:13px;">
          Ceny sa môžu líšiť podľa dĺžky vlasov a náročnosti úprav.
        </p>
      </div>
    </div>
  </section>

  <!-- GALÉRIA -->
  <section id="galeria">
    <div class="wrap">
      <h3 class="section-title">Galéria</h3>

      <div class="grid">
        <div class="card">
          <img src="foto1.jpeg" alt="Interiér kaderníctva" class="gallery-img">
        </div>
        <div class="card">
          <img src="foto2.png" alt="Kaderníctvo zvonku" class="gallery-img">
        </div>
        <div class="card">
          <img src="foto3.jpeg" alt="Interiér kaderníctva" class="gallery-img">
        </div>
      </div>
    </div>
  </section>

  <!-- KONTAKT -->
  <section id="kontakt">
    <div class="wrap">
      <h3 class="section-title">Kontakt</h3>

      <div class="contact-card">
        <div>
          <p><b>📍 Adresa:</b> Aténska 25, Košice</p>
          <p><b>📞 Telefón:</b> Melinda Pavlíková: 0908 985 971</p>
          <p><b>📞 Telefón:</b> Marcela Tkáčová: 0950 749 145</p>
          <p><b>🕒 Otváracie hodiny:</b> Podľa objednávok</p>
          <p><b>🌐 Instagram a Facebook:</b> @mm.kadernictvo</p>
        </div>

        <div class="card" style="margin:0; background:rgba(0,0,0,.02); box-shadow:none;">
          <b>Mapa:</b>
          <iframe
            src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d657.5394570486503!2d21.261048615971735!3d48.759782232396084!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x473ee100711fd923%3A0xd6a18fa7870f651b!2sKadern%C3%ADctvo%20M%26M!5e0!3m2!1ssk!2ssk!4v1769975428526!5m2!1ssk!2ssk"
            width="100%"
            height="260"
            style="border:0; border-radius:12px;"
            allowfullscreen=""
            loading="lazy"
            referrerpolicy="no-referrer-when-downgrade">
          </iframe>
        </div>
      </div>
    </div>
  </section>

  <!-- O NÁS (POD KONTAKTOM) -->
  <section id="onas">
    <div class="wrap">
      <h3 class="section-title">O nás</h3>

      <div class="contact-card">
        <div>
          <p><b>Sme novootvorené kaderníctvo, ktoré začalo fungovať začiatkom roka 2026.</b></p>
          <p>
            Prečo M&amp;M? Tento názov vznikol z iniciálov našich mien – Melinda a Marcela.<br>
            Dostanete sa k nám jednoducho, keďže sa nachádzame neďaleko konečnej autobusovej zastávky
            a parkovanie je možné priamo pred kaderníctvom.
          </p>
        </div>
      </div>
    </div>
  </section>

  <!-- ČIERNY BOX ÚPLNE NA KONCI (PRED ROKOM) -->
  <div class="bottom-message">
    <span>Zarezervujte si svoj termín včas a my ťa radi privítame v našom kaderníctve M&amp;M</span>
  </div>

  <div class="footer">
    © 2026 M&amp;M Kaderníctvo
  </div>

</body>
</html>

