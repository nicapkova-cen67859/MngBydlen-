<!doctype html>
<html lang="cs">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>MngBydlení – manuál pro manažery</title>
  <style>
    :root{
      --bg:#0b1220; --panel:#111a2e; --text:#e8eefc; --muted:#a8b3cf;
      --accent:#6aa6ff; --accent2:#65d6ad; --border:rgba(255,255,255,.10);
      --shadow:0 10px 30px rgba(0,0,0,.35);
      --radius:16px;
      --max:1100px;
    }
    *{box-sizing:border-box}
    body{
      margin:0;
      font-family: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Arial, "Noto Sans", "Liberation Sans", sans-serif;
      background: radial-gradient(1200px 700px at 20% -10%, rgba(106,166,255,.35), transparent 55%),
                  radial-gradient(900px 600px at 90% 0%, rgba(101,214,173,.25), transparent 50%),
                  var(--bg);
      color:var(--text);
      line-height:1.55;
    }
    a{color:inherit}
    .wrap{max-width:var(--max); margin:0 auto; padding:24px}
    header{
      position:sticky; top:0; z-index:10;
      backdrop-filter: blur(10px);
      background: linear-gradient(to bottom, rgba(11,18,32,.92), rgba(11,18,32,.65));
      border-bottom:1px solid var(--border);
    }
    .topbar{display:flex; gap:16px; align-items:center; justify-content:space-between}
    .brand{display:flex; gap:12px; align-items:center; text-decoration:none}
    .logo{
      width:40px; height:40px; border-radius:12px;
      background: linear-gradient(135deg, var(--accent), var(--accent2));
      box-shadow: var(--shadow);
    }
    .brand strong{display:block; font-size:14px; letter-spacing:.3px}
    .brand span{display:block; font-size:12px; color:var(--muted)}
    nav{display:flex; flex-wrap:wrap; gap:10px; justify-content:flex-end}
    nav a{
      text-decoration:none;
      padding:10px 12px;
      border:1px solid var(--border);
      border-radius:999px;
      color:var(--muted);
    }
    nav a:hover{color:var(--text); border-color:rgba(255,255,255,.22)}
    .hero{padding:32px 0 10px}
    .hero h1{margin:0 0 10px; font-size:34px}
    .hero p{margin:0; color:var(--muted); max-width:75ch}
    .grid{
      display:grid;
      grid-template-columns: 280px 1fr;
      gap:18px;
      padding:18px 0 26px;
    }
    @media (max-width: 900px){
      .grid{grid-template-columns:1fr}
    }
    .panel{
      background:rgba(17,26,46,.75);
      border:1px solid var(--border);
      border-radius:var(--radius);
      box-shadow: var(--shadow);
    }
    .side{padding:14px}
    .side h2{margin:8px 8px 10px; font-size:14px; color:var(--muted); letter-spacing:.3px; text-transform:uppercase}
    .menu{list-style:none; padding:0; margin:0}
    .menu li{margin:8px 0}
    .menu a{
      display:block; text-decoration:none;
      padding:10px 12px;
      border-radius:12px;
      border:1px solid transparent;
      color:var(--text);
    }
    .menu a small{display:block; color:var(--muted); margin-top:2px}
    .menu a:hover{border-color:rgba(255,255,255,.18); background:rgba(255,255,255,.04)}
    main{padding:16px}
    .cards{
      display:grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap:14px;
    }
    @media (max-width: 900px){
      .cards{grid-template-columns:1fr}
    }
    .card{
      padding:14px;
      border:1px solid var(--border);
      border-radius:var(--radius);
      background:rgba(255,255,255,.03);
    }
    .card h3{margin:0 0 6px; font-size:16px}
    .card p{margin:0; color:var(--muted); font-size:13px}
    .card a.btn{
      display:inline-block; margin-top:10px;
      text-decoration:none;
      padding:10px 12px;
      border-radius:12px;
      border:1px solid rgba(255,255,255,.16);
      color:var(--text);
    }
    .card a.btn:hover{border-color:rgba(255,255,255,.28)}
    .section{margin-top:16px; padding:14px; border-top:1px solid var(--border)}
    .section h2{margin:0 0 6px; font-size:16px}
    .section p{margin:0; color:var(--muted)}
    footer{color:var(--muted); padding:24px 0 40px; font-size:12px}
    .kbd{
      font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", monospace;
      border:1px solid var(--border);
      background:rgba(255,255,255,.04);
      padding:2px 6px; border-radius:8px;
    }
  </style>
</head>
<body>
  <header>
    <div class="wrap topbar">
      <a class="brand" href="#uvod">
        <div class="logo" aria-hidden="true"></div>
        <div>
          <strong>MngBydlení</strong>
          <span>Manuál pro manažery – bydlení</span>
        </div>
      </a>

      <nav aria-label="Rychlá navigace">
        <a href="#postupy">Postupy</a>
        <a href="#dokumenty">Dokumenty</a>
        <a href="#kontakty">Kontakty</a>
      </nav>
    </div>
  </header>

  <div class="wrap hero" id="uvod">
    <h1>Centrální místo pro správu bydlení</h1>
    <p>
      Stránka slouží jako veřejně dostupný „manual“ pro manažery. Může obsahovat postupy,
      checklisty, šablony a odkazy na interní materiály (pokud něco nemá být veřejné, nedávej to sem).
    </p>
  </div>

  <div class="wrap grid">
    <aside class="panel side">
      <h2>Obsah</h2>
      <ul class="menu">
        <li><a href="#postupy">Postupy <small>kroky, checklisty, eskalace</small></a></li>
        <li><a href="#dokumenty">Dokumenty <small>šablony, formuláře, odkazy</small></a></li>
        <li><a href="#kontakty">Kontakty <small>role, odpovědnosti, komu psát</small></a></li>
      </ul>

      <h2>Tip</h2>
      <div style="padding:0 8px 8px; color:var(--muted); font-size:13px">
        Až zapneš GitHub Pages, URL bude typicky:
        <div style="margin-top:8px">
          <span class="kbd">https://nicapkova-cen67859.github.io/MngBydlen-/</span>
        </div>
      </div>
    </aside>

    <main class="panel">
      <div class="cards" id="postupy">
        <div class="card">
          <h3>Onboarding bytu</h3>
          <p>Kontrola dokumentů, převzetí, zápis stavu, předání klíčů.</p>
          <a class="btn" href="#" onclick="alert('Sem doplň odkaz na konkrétní stránku nebo PDF.');return false;">Otevřít</a>
        </div>
        <div class="card">
          <h3>Řešení závad</h3>
          <p>Prioritizace, komunikace s dodavatelem, SLA a eskalace.</p>
          <a class="btn" href="#" onclick="alert('Sem doplň odkaz na konkrétní stránku nebo PDF.');return false;">Otevřít</a>
        </div>
        <div class="card">
          <h3>Ukončení nájmu</h3>
          <p>Checklist, protokol, vyúčtování, předání.</p>
          <a class="btn" href="#" onclick="alert('Sem doplň odkaz na konkrétní stránku nebo PDF.');return false;">Otevřít</a>
        </div>
      </div>

      <div class="section" id="dokumenty">
        <h2>Dokumenty</h2>
        <p>
          Sem dej odkazy na veřejné šablony (např. PDF v repozitáři) nebo na další stránky.
          Doporučení: vytvořit složku <span class="kbd">docs/</span> a do ní ukládat soubory.
        </p>
      </div>

      <div class="section" id="kontakty">
        <h2>Kontakty</h2>
        <p>
          Doplň role (Manažer bydlení, Údržba, Finance) + e-mail/Slack. Pokud to má být veřejné,
          nedávej osobní údaje – raději obecné mailboxy.
        </p>
      </div>
    </main>
  </div>

  <footer class="wrap">
    © 2026 MngBydlení. Poslední aktualizace: 2026-04-17.
  </footer>
</body>
</html>
