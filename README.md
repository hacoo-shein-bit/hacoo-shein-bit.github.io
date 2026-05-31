# HCO26.github.io
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>HCO26 — Affiliation</title>
  <link href="https://fonts.googleapis.com/css2?family=Barlow+Condensed:wght@300;400;600;700;900&family=Barlow:wght@300;400;500&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --black: #080808;
      --white: #f5f5f5;
      --grey1: #141414;
      --grey2: #1f1f1f;
      --grey3: #2e2e2e;
      --grey4: #555;
      --grey5: #888;
      --accent: #e8e8e8;
      --hacoo: #ff3c3c;
      --shein: #ffffff;
      --sidebar: 260px;
      --radius: 6px;
    }

    *, *::before, *::after { margin:0; padding:0; box-sizing:border-box; }

    html { scroll-behavior: smooth; }

    body {
      background: var(--black);
      color: var(--white);
      font-family: 'Barlow', sans-serif;
      font-weight: 300;
      display: flex;
      min-height: 100vh;
      overflow-x: hidden;
    }

    /* ═══════════════════════════════
       SIDEBAR
    ═══════════════════════════════ */
    .sidebar {
      width: var(--sidebar);
      background: var(--grey1);
      border-right: 1px solid var(--grey3);
      position: fixed;
      top: 0; left: 0; bottom: 0;
      display: flex;
      flex-direction: column;
      z-index: 50;
      overflow: hidden;
    }

    /* Top stripe */
    .sidebar::before {
      content: '';
      display: block;
      height: 3px;
      background: var(--white);
      flex-shrink: 0;
    }

    .brand {
      padding: 32px 28px 28px;
      border-bottom: 1px solid var(--grey3);
    }

    .brand-name {
      font-family: 'Barlow Condensed', sans-serif;
      font-weight: 900;
      font-size: 38px;
      letter-spacing: 6px;
      text-transform: uppercase;
      line-height: 1;
      color: var(--white);
    }

    .brand-sub {
      font-size: 11px;
      letter-spacing: 3px;
      text-transform: uppercase;
      color: var(--grey5);
      margin-top: 6px;
    }

    nav {
      flex: 1;
      padding: 24px 0;
      overflow-y: auto;
    }

    .nav-section-label {
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 10px;
      letter-spacing: 3px;
      text-transform: uppercase;
      color: var(--grey4);
      padding: 0 28px 10px;
    }

    .nav-item {
      display: flex;
      align-items: center;
      gap: 14px;
      padding: 13px 28px;
      cursor: pointer;
      border: none;
      background: transparent;
      width: 100%;
      text-align: left;
      color: var(--grey5);
      font-family: 'Barlow Condensed', sans-serif;
      font-weight: 600;
      font-size: 15px;
      letter-spacing: 2px;
      text-transform: uppercase;
      transition: color .2s, background .2s;
      position: relative;
    }

    .nav-item::before {
      content: '';
      position: absolute;
      left: 0; top: 0; bottom: 0;
      width: 2px;
      background: transparent;
      transition: background .2s;
    }

    .nav-item:hover { color: var(--white); background: rgba(255,255,255,.03); }
    .nav-item.active { color: var(--white); background: rgba(255,255,255,.05); }
    .nav-item.active::before { background: var(--white); }

    .nav-item .nav-icon {
      width: 20px; height: 20px;
      display: flex; align-items: center; justify-content: center;
      font-size: 14px; flex-shrink: 0;
    }

    .nav-item .nav-count {
      margin-left: auto;
      font-size: 11px;
      color: var(--grey4);
      background: var(--grey2);
      border-radius: 10px;
      padding: 2px 8px;
      font-weight: 400;
      letter-spacing: 0;
    }

    .sidebar-footer {
      padding: 20px 28px;
      border-top: 1px solid var(--grey3);
      font-size: 11px;
      color: var(--grey4);
      letter-spacing: 1px;
      line-height: 1.8;
    }

    /* ═══════════════════════════════
       MAIN
    ═══════════════════════════════ */
    .main {
      margin-left: var(--sidebar);
      flex: 1;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
    }

    /* Top bar */
    .topbar {
      padding: 20px 48px;
      border-bottom: 1px solid var(--grey3);
      display: flex;
      align-items: center;
      justify-content: space-between;
      position: sticky;
      top: 0;
      background: rgba(8,8,8,.92);
      backdrop-filter: blur(12px);
      z-index: 40;
    }

    .topbar-title {
      font-family: 'Barlow Condensed', sans-serif;
      font-weight: 700;
      font-size: 22px;
      letter-spacing: 4px;
      text-transform: uppercase;
    }

    .topbar-action button {
      display: flex; align-items: center; gap: 8px;
      background: var(--white); color: var(--black);
      border: none; border-radius: var(--radius);
      padding: 10px 20px;
      font-family: 'Barlow Condensed', sans-serif;
      font-weight: 700; font-size: 13px;
      letter-spacing: 2px; text-transform: uppercase;
      cursor: pointer;
      transition: background .2s, transform .15s;
    }
    .topbar-action button:hover { background: var(--accent); transform: scale(.98); }

    /* Content */
    .content {
      flex: 1;
      padding: 48px;
    }

    /* Pages */
    .page { display: none; }
    .page.active {
      display: block;
      animation: reveal .35s ease both;
    }

    @keyframes reveal {
      from { opacity: 0; transform: translateY(12px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    /* ═══════════════════════════════
       ARTICLES GRID
    ═══════════════════════════════ */
    .section-intro {
      margin-bottom: 36px;
    }

    .section-intro h2 {
      font-family: 'Barlow Condensed', sans-serif;
      font-weight: 900;
      font-size: clamp(36px, 5vw, 64px);
      letter-spacing: 5px;
      text-transform: uppercase;
      line-height: 1;
    }

    .section-intro p {
      color: var(--grey5);
      font-size: 13px;
      letter-spacing: 1.5px;
      text-transform: uppercase;
      margin-top: 10px;
    }

    .articles-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
      gap: 2px;
    }

    .article-card {
      background: var(--grey1);
      position: relative;
      overflow: hidden;
      display: block;
      text-decoration: none;
      color: var(--white);
      cursor: pointer;
      transition: background .2s;
      border: 1px solid var(--grey2);
    }

    .article-card:hover { background: var(--grey2); }

    .article-card:hover .card-overlay {
      opacity: 1;
    }

    .card-img-wrap {
      aspect-ratio: 3/4;
      overflow: hidden;
      background: var(--grey2);
      position: relative;
    }

    .card-img-wrap img {
      width: 100%; height: 100%;
      object-fit: cover;
      transition: transform .4s ease;
    }

    .article-card:hover .card-img-wrap img { transform: scale(1.04); }

    .card-placeholder {
      width: 100%; height: 100%;
      display: flex; align-items: center; justify-content: center;
      font-size: 40px;
      background: var(--grey2);
    }

    .card-overlay {
      position: absolute; inset: 0;
      background: rgba(0,0,0,.5);
      display: flex; align-items: center; justify-content: center;
      opacity: 0;
      transition: opacity .25s;
    }

    .card-overlay span {
      font-family: 'Barlow Condensed', sans-serif;
      font-weight: 700;
      font-size: 13px;
      letter-spacing: 3px;
      text-transform: uppercase;
      border: 1px solid var(--white);
      padding: 8px 18px;
    }

    .card-body { padding: 14px 16px; }

    .card-brand {
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 10px;
      letter-spacing: 2.5px;
      text-transform: uppercase;
      color: var(--grey5);
      margin-bottom: 4px;
    }

    .card-title {
      font-family: 'Barlow Condensed', sans-serif;
      font-weight: 600;
      font-size: 15px;
      letter-spacing: 0.5px;
      line-height: 1.3;
    }

    .card-delete {
      position: absolute; top: 8px; right: 8px;
      background: rgba(0,0,0,.7);
      border: 1px solid rgba(255,255,255,.15);
      color: var(--white);
      width: 28px; height: 28px;
      border-radius: 50%;
      display: none;
      align-items: center; justify-content: center;
      font-size: 13px;
      cursor: pointer;
      transition: background .2s;
    }

    .article-card:hover .card-delete { display: flex; }
    .card-delete:hover { background: rgba(255,60,60,.8) !important; }

    .empty-state {
      grid-column: 1 / -1;
      padding: 80px 20px;
      text-align: center;
      border: 1px dashed var(--grey3);
    }

    .empty-state .e-icon { font-size: 48px; margin-bottom: 16px; }
    .empty-state h3 {
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 20px; letter-spacing: 3px;
      text-transform: uppercase; color: var(--grey5);
    }
    .empty-state p { font-size: 13px; color: var(--grey4); margin-top: 6px; }

    /* ═══════════════════════════════
       CODES PROMO
    ═══════════════════════════════ */
    .codes-layout {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
      gap: 24px;
    }

    .code-block {
      border: 1px solid var(--grey3);
      border-radius: var(--radius);
      overflow: hidden;
    }

    .code-block-header {
      padding: 20px 24px;
      border-bottom: 1px solid var(--grey3);
      display: flex; align-items: center; gap: 16px;
    }

    .code-block-logo {
      font-family: 'Barlow Condensed', sans-serif;
      font-weight: 900;
      font-size: 13px;
      letter-spacing: 2px;
      padding: 6px 12px;
      border: 1px solid;
    }

    .code-block.hacoo .code-block-logo { color: var(--hacoo); border-color: var(--hacoo); }
    .code-block.shein .code-block-logo { color: var(--shein); border-color: var(--shein); }

    .code-block-name {
      font-family: 'Barlow Condensed', sans-serif;
      font-weight: 700;
      font-size: 22px;
      letter-spacing: 3px;
    }

    .code-block.hacoo .code-block-name { color: var(--hacoo); }
    .code-block.shein .code-block-name { color: var(--shein); }

    .codes-list { padding: 20px 24px; display: flex; flex-direction: column; gap: 12px; }

    .code-row {
      display: flex;
      align-items: center;
      justify-content: space-between;
      background: var(--grey2);
      border: 1px solid var(--grey3);
      padding: 14px 18px;
      cursor: pointer;
      transition: border-color .2s, background .2s;
      position: relative;
    }

    .code-row:hover { background: var(--grey3); border-color: var(--grey4); }

    .code-row-left { display: flex; flex-direction: column; gap: 3px; }

    .code-value {
      font-family: 'Barlow Condensed', sans-serif;
      font-weight: 700;
      font-size: 24px;
      letter-spacing: 3px;
    }

    .code-block.hacoo .code-value { color: var(--hacoo); }
    .code-block.shein .code-value { color: var(--shein); }

    .code-desc { font-size: 12px; color: var(--grey5); letter-spacing: 1px; }

    .copy-btn {
      font-family: 'Barlow Condensed', sans-serif;
      font-weight: 700;
      font-size: 11px;
      letter-spacing: 2px;
      text-transform: uppercase;
      padding: 6px 14px;
      border: 1px solid var(--grey4);
      background: transparent;
      color: var(--white);
      cursor: pointer;
      transition: all .2s;
    }

    .copy-btn:hover { background: var(--white); color: var(--black); border-color: var(--white); }
    .copy-btn.copied { background: var(--white); color: var(--black); border-color: var(--white); }

    .code-block-cta {
      padding: 16px 24px;
      border-top: 1px solid var(--grey3);
    }

    .code-block-cta a {
      display: block; text-align: center;
      text-decoration: none;
      padding: 14px;
      font-family: 'Barlow Condensed', sans-serif;
      font-weight: 700;
      font-size: 14px;
      letter-spacing: 3px;
      text-transform: uppercase;
      border: 1px solid;
      transition: background .2s, color .2s;
    }

    .code-block.hacoo .code-block-cta a { color: var(--hacoo); border-color: var(--hacoo); }
    .code-block.hacoo .code-block-cta a:hover { background: var(--hacoo); color: var(--black); }
    .code-block.shein .code-block-cta a { color: var(--shein); border-color: var(--shein); }
    .code-block.shein .code-block-cta a:hover { background: var(--shein); color: var(--black); }

    /* ═══════════════════════════════
       RÉSEAUX SOCIAUX
    ═══════════════════════════════ */
    .socials-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
      gap: 16px;
    }

    .social-card {
      background: var(--grey1);
      border: 1px solid var(--grey3);
      padding: 24px;
      display: flex;
      flex-direction: column;
      gap: 16px;
      position: relative;
    }

    .social-card-top {
      display: flex; align-items: center; gap: 14px;
    }

    .social-icon {
      width: 44px; height: 44px;
      border: 1px solid var(--grey3);
      display: flex; align-items: center; justify-content: center;
      font-size: 20px;
      flex-shrink: 0;
    }

    .social-name {
      font-family: 'Barlow Condensed', sans-serif;
      font-weight: 700;
      font-size: 18px;
      letter-spacing: 2px;
      text-transform: uppercase;
    }

    .social-handle {
      font-size: 12px;
      color: var(--grey5);
      margin-top: 2px;
      word-break: break-all;
    }

    .social-actions {
      display: flex; gap: 8px;
    }

    .social-btn {
      flex: 1; padding: 10px;
      border: 1px solid var(--grey3);
      background: transparent;
      color: var(--white);
      font-family: 'Barlow Condensed', sans-serif;
      font-weight: 600;
      font-size: 11px;
      letter-spacing: 2px;
      text-transform: uppercase;
      cursor: pointer;
      text-decoration: none;
      text-align: center;
      display: flex; align-items: center; justify-content: center; gap: 6px;
      transition: background .2s, border-color .2s;
    }

    .social-btn:hover { background: var(--grey3); border-color: var(--grey4); }
    .social-btn.primary { background: var(--white); color: var(--black); border-color: var(--white); }
    .social-btn.primary:hover { background: var(--accent); }

    .social-delete {
      position: absolute; top: 12px; right: 12px;
      background: transparent; border: none;
      color: var(--grey4); font-size: 16px;
      cursor: pointer; transition: color .2s;
    }
    .social-delete:hover { color: var(--hacoo); }

    /* ═══════════════════════════════
       MODAL
    ═══════════════════════════════ */
    .overlay {
      position: fixed; inset: 0;
      background: rgba(0,0,0,.85);
      backdrop-filter: blur(6px);
      z-index: 200;
      display: none;
      align-items: center; justify-content: center;
      padding: 20px;
    }

    .overlay.open { display: flex; }

    .modal {
      background: var(--grey1);
      border: 1px solid var(--grey3);
      width: 100%; max-width: 480px;
      padding: 40px;
      animation: reveal .25s ease both;
    }

    .modal-title {
      font-family: 'Barlow Condensed', sans-serif;
      font-weight: 900;
      font-size: 28px;
      letter-spacing: 4px;
      text-transform: uppercase;
      margin-bottom: 28px;
    }

    .form-row { margin-bottom: 18px; }

    .form-row label {
      display: block;
      font-size: 10px;
      letter-spacing: 2.5px;
      text-transform: uppercase;
      color: var(--grey5);
      margin-bottom: 8px;
    }

    .form-row input, .form-row select, .form-row textarea {
      width: 100%;
      background: var(--grey2);
      border: 1px solid var(--grey3);
      color: var(--white);
      padding: 12px 16px;
      font-family: 'Barlow', sans-serif;
      font-size: 14px;
      transition: border-color .2s;
      resize: vertical;
    }

    .form-row input:focus, .form-row select:focus, .form-row textarea:focus {
      outline: none;
      border-color: var(--white);
    }

    .form-row select option { background: var(--grey1); }

    .modal-btns { display: flex; gap: 10px; margin-top: 28px; }

    .btn-confirm {
      flex: 1; padding: 14px;
      background: var(--white); color: var(--black);
      border: none;
      font-family: 'Barlow Condensed', sans-serif;
      font-weight: 700; font-size: 14px;
      letter-spacing: 3px; text-transform: uppercase;
      cursor: pointer;
      transition: background .2s;
    }

    .btn-confirm:hover { background: var(--accent); }

    .btn-cancel-modal {
      padding: 14px 22px;
      background: transparent;
      border: 1px solid var(--grey3);
      color: var(--grey5);
      font-family: 'Barlow', sans-serif;
      font-size: 13px;
      cursor: pointer;
      transition: border-color .2s, color .2s;
    }

    .btn-cancel-modal:hover { border-color: var(--grey4); color: var(--white); }

    /* ═══════════════════════════════
       MOBILE
    ═══════════════════════════════ */
    @media (max-width: 700px) {
      .sidebar {
        width: 100%;
        height: auto;
        position: relative;
        flex-direction: column;
      }

      nav {
        display: flex;
        flex-direction: row;
        overflow-x: auto;
        padding: 8px 12px;
        gap: 4px;
      }

      .nav-section-label { display: none; }

      .nav-item {
        white-space: nowrap;
        padding: 8px 16px;
        font-size: 12px;
        flex-shrink: 0;
      }

      .nav-item::before { top: auto; bottom: 0; left: 0; right: 0; width: auto; height: 2px; }

      .sidebar-footer { display: none; }
      .brand { padding: 20px 20px 16px; }
      .brand-name { font-size: 28px; }

      body { flex-direction: column; }
      .main { margin-left: 0; }
      .topbar { padding: 14px 20px; }
      .content { padding: 24px 20px; }
      .articles-grid { grid-template-columns: repeat(2, 1fr); }
    }
  </style>
</head>
<body>

<!-- ── SIDEBAR ── -->
<aside class="sidebar">
  <div class="brand">
    <div class="brand-name">HCO26</div>
    <div class="brand-sub">Affiliation · Bons plans</div>
  </div>
  <nav>
    <p class="nav-section-label">Rubriques</p>
    <button class="nav-item active" data-page="hacoo" onclick="navigate(this)">
      <span class="nav-icon">🛍</span> Articles HACOO
      <span class="nav-count" id="count-hacoo">0</span>
    </button>
    <button class="nav-item" data-page="shein" onclick="navigate(this)">
      <span class="nav-icon">👗</span> Articles SHEIN
      <span class="nav-count" id="count-shein">0</span>
    </button>
    <button class="nav-item" data-page="codes" onclick="navigate(this)">
      <span class="nav-icon">🏷</span> Codes Promo
    </button>
    <button class="nav-item" data-page="socials" onclick="navigate(this)">
      <span class="nav-icon">📲</span> Réseaux Sociaux
      <span class="nav-count" id="count-socials">0</span>
    </button>
  </nav>
  <div class="sidebar-footer">
    © 2026 HCO26<br>
    Liens affiliés — aucun surcoût
  </div>
</aside>

<!-- ── MAIN ── -->
<div class="main">
  <div class="topbar">
    <div class="topbar-title" id="topbar-title">Articles HACOO</div>
    <div class="topbar-action" id="topbar-action">
      <button onclick="openModal('article','HACOO')">＋ Ajouter un article</button>
    </div>
  </div>

  <div class="content">

    <!-- PAGE HACOO -->
    <div class="page active" id="page-hacoo">
      <div class="section-intro">
        <h2>HACOO</h2>
        <p>Cliquez sur un article pour l'ouvrir directement</p>
      </div>
      <div class="articles-grid" id="grid-hacoo"></div>
    </div>

    <!-- PAGE SHEIN -->
    <div class="page" id="page-shein">
      <div class="section-intro">
        <h2>SHEIN</h2>
        <p>Cliquez sur un article pour l'ouvrir directement</p>
      </div>
      <div class="articles-grid" id="grid-shein"></div>
    </div>

    <!-- PAGE CODES -->
    <div class="page" id="page-codes">
      <div class="section-intro">
        <h2>Codes Promo</h2>
        <p>Copiez le code · Ouvrez l'app · Profitez</p>
      </div>
      <div class="codes-layout">

        <!-- HACOO -->
        <div class="code-block hacoo">
          <div class="code-block-header">
            <div class="code-block-logo">HAC</div>
            <div>
              <div class="code-block-name">HACOO</div>
              <div style="font-size:12px;color:var(--grey5);letter-spacing:1px">Application mobile</div>
            </div>
          </div>
          <div class="codes-list">
            <div class="code-row" onclick="copyCode('HCO26', this)">
              <div class="code-row-left">
                <div class="code-value">HCO26</div>
                <div class="code-desc">−14% sur votre commande</div>
              </div>
              <button class="copy-btn" tabindex="-1">Copier</button>
            </div>
            <div class="code-row" onclick="copyCode('HACOO28', this)">
              <div class="code-row-left">
                <div class="code-value">HACOO28</div>
                <div class="code-desc">−14% sur votre commande</div>
              </div>
              <button class="copy-btn" tabindex="-1">Copier</button>
            </div>
          </div>
          <div class="code-block-cta">
            <a href="https://hacoo.app" target="_blank" rel="noopener">Ouvrir HACOO →</a>
          </div>
        </div>

        <!-- SHEIN -->
        <div class="code-block shein">
          <div class="code-block-header">
            <div class="code-block-logo">SHE</div>
            <div>
              <div class="code-block-name">SHEIN</div>
              <div style="font-size:12px;color:var(--grey5);letter-spacing:1px">Application mobile</div>
            </div>
          </div>
          <div class="codes-list">
            <div class="code-row" onclick="copyCode('NQH59', this)">
              <div class="code-row-left">
                <div class="code-value">NQH59</div>
                <div class="code-desc">−60% sur votre commande</div>
              </div>
              <button class="copy-btn" tabindex="-1">Copier</button>
            </div>
          </div>
          <div class="code-block-cta">
            <a href="https://shein.com" target="_blank" rel="noopener">Ouvrir SHEIN →</a>
          </div>
        </div>

      </div>
    </div>

    <!-- PAGE RÉSEAUX -->
    <div class="page" id="page-socials">
      <div class="section-intro">
        <h2>Réseaux Sociaux</h2>
        <p>Suivez-moi · Lien direct ou copier l'identifiant</p>
      </div>
      <div class="socials-grid" id="grid-socials"></div>
    </div>

  </div><!-- /content -->
</div><!-- /main -->

<!-- ══ MODAL ══ -->
<div class="overlay" id="overlay" onclick="overlayClick(event)">
  <div class="modal" id="modal">
    <div class="modal-title" id="modal-title">Ajouter</div>

    <!-- Champs article -->
    <div id="fields-article">
      <div class="form-row">
        <label>Marque</label>
        <select id="f-brand">
          <option value="HACOO">HACOO</option>
          <option value="SHEIN">SHEIN</option>
        </select>
      </div>
      <div class="form-row">
        <label>Titre de l'article</label>
        <input type="text" id="f-title" placeholder="ex : Veste oversize noire"/>
      </div>
      <div class="form-row">
        <label>Lien affilié (URL)</label>
        <input type="url" id="f-url" placeholder="https://..."/>
      </div>
      <div class="form-row">
        <label>URL de l'image (optionnel)</label>
        <input type="url" id="f-img" placeholder="https://...jpg"/>
      </div>
    </div>

    <!-- Champs réseau social -->
    <div id="fields-social" style="display:none">
      <div class="form-row">
        <label>Réseau</label>
        <select id="f-snet">
          <option value="TikTok">TikTok</option>
          <option value="Instagram">Instagram</option>
          <option value="YouTube">YouTube</option>
          <option value="Facebook">Facebook</option>
          <option value="Snapchat">Snapchat</option>
          <option value="Twitter / X">Twitter / X</option>
          <option value="Pinterest">Pinterest</option>
          <option value="Autre">Autre</option>
        </select>
      </div>
      <div class="form-row">
        <label>Nom d'utilisateur / identifiant</label>
        <input type="text" id="f-shandle" placeholder="@votre_pseudo"/>
      </div>
      <div class="form-row">
        <label>Lien de votre profil (URL)</label>
        <input type="url" id="f-surl" placeholder="https://..."/>
      </div>
    </div>

    <div class="modal-btns">
      <button class="btn-cancel-modal" onclick="closeModal()">Annuler</button>
      <button class="btn-confirm" onclick="confirmAdd()">Ajouter</button>
    </div>
  </div>
</div>

<script>
// ─────────────────────────────────────────
//  STATE
// ─────────────────────────────────────────
const STORE_KEY = 'hco26_v2';

let state = JSON.parse(localStorage.getItem(STORE_KEY) || 'null') || {
  articles: [],
  socials: []
};

function save() { localStorage.setItem(STORE_KEY, JSON.stringify(state)); }

// ─────────────────────────────────────────
//  NAVIGATION
// ─────────────────────────────────────────
const PAGE_META = {
  hacoo:   { title: 'Articles HACOO',   action: () => `<button onclick="openModal('article','HACOO')">＋ Ajouter un article</button>` },
  shein:   { title: 'Articles SHEIN',   action: () => `<button onclick="openModal('article','SHEIN')">＋ Ajouter un article</button>` },
  codes:   { title: 'Codes Promo',      action: () => '' },
  socials: { title: 'Réseaux Sociaux',  action: () => `<button onclick="openModal('social')">＋ Ajouter un réseau</button>` },
};

function navigate(btn) {
  const id = btn.dataset.page;
  document.querySelectorAll('.nav-item').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  document.getElementById('page-' + id).classList.add('active');
  document.getElementById('topbar-title').textContent = PAGE_META[id].title;
  document.getElementById('topbar-action').innerHTML = PAGE_META[id].action();
}

// ─────────────────────────────────────────
//  COPY CODE
// ─────────────────────────────────────────
function copyCode(code, row) {
  navigator.clipboard.writeText(code).then(() => {
    const btn = row.querySelector('.copy-btn');
    btn.textContent = 'Copié ✓';
    btn.classList.add('copied');
    setTimeout(() => { btn.textContent = 'Copier'; btn.classList.remove('copied'); }, 2000);
  });
}

// ─────────────────────────────────────────
//  RENDER ARTICLES
// ─────────────────────────────────────────
const ICONS = { HACOO: '🛍️', SHEIN: '👗' };

function renderArticles() {
  ['HACOO','SHEIN'].forEach(brand => {
    const key = brand.toLowerCase();
    const grid = document.getElementById('grid-' + key);
    const items = state.articles.filter(a => a.brand === brand);
    document.getElementById('count-' + key).textContent = items.length;

    if (!items.length) {
      grid.innerHTML = `<div class="empty-state">
        <div class="e-icon">${ICONS[brand]}</div>
        <h3>Aucun article</h3>
        <p>Cliquez sur "＋ Ajouter" pour commencer</p>
      </div>`;
      return;
    }

    grid.innerHTML = items.map(a => {
      const idx = state.articles.indexOf(a);
      return `<div class="article-card" onclick="window.open('${escHtml(a.url)}','_blank')">
        <div class="card-img-wrap">
          ${a.img
            ? `<img src="${escHtml(a.img)}" alt="${escHtml(a.title)}" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'">`
            : ''}
          <div class="card-placeholder" style="${a.img ? 'display:none' : ''}">${ICONS[brand]}</div>
          <div class="card-overlay"><span>Voir l'article</span></div>
        </div>
        <div class="card-body">
          <div class="card-brand">${brand}</div>
          <div class="card-title">${escHtml(a.title)}</div>
        </div>
        <button class="card-delete" onclick="event.stopPropagation();deleteArticle(${idx})" title="Supprimer">✕</button>
      </div>`;
    }).join('');
  });
}

function deleteArticle(idx) {
  if (!confirm('Supprimer cet article ?')) return;
  state.articles.splice(idx, 1);
  save(); renderArticles();
}

// ─────────────────────────────────────────
//  RENDER SOCIALS
// ─────────────────────────────────────────
const SOCIAL_ICONS = {
  TikTok: '🎵', Instagram: '📸', YouTube: '▶️',
  Facebook: '👤', Snapchat: '👻', 'Twitter / X': '✖️',
  Pinterest: '📌', Autre: '🔗'
};

function renderSocials() {
  const grid = document.getElementById('grid-socials');
  document.getElementById('count-socials').textContent = state.socials.length;

  if (!state.socials.length) {
    grid.innerHTML = `<div class="empty-state" style="grid-column:1/-1">
      <div class="e-icon">📲</div>
      <h3>Aucun réseau</h3>
      <p>Ajoutez vos profils pour les partager</p>
    </div>`;
    return;
  }

  grid.innerHTML = state.socials.map((s, i) => `
    <div class="social-card">
      <div class="social-card-top">
        <div class="social-icon">${SOCIAL_ICONS[s.net] || '🔗'}</div>
        <div>
          <div class="social-name">${escHtml(s.net)}</div>
          <div class="social-handle">${escHtml(s.handle)}</div>
        </div>
      </div>
      <div class="social-actions">
        <a class="social-btn primary" href="${escHtml(s.url)}" target="_blank" rel="noopener">Ouvrir →</a>
        <button class="social-btn" onclick="navigator.clipboard.writeText('${escHtml(s.handle)}');this.textContent='Copié ✓';setTimeout(()=>this.textContent='Copier',2000)">Copier</button>
      </div>
      <button class="social-delete" onclick="deleteSocial(${i})">✕</button>
    </div>
  `).join('');
}

function deleteSocial(i) {
  if (!confirm('Supprimer ce réseau ?')) return;
  state.socials.splice(i, 1);
  save(); renderSocials();
}

// ─────────────────────────────────────────
//  MODAL
// ─────────────────────────────────────────
let modalMode = 'article';

function openModal(mode, brand) {
  modalMode = mode;
  document.getElementById('fields-article').style.display = mode === 'article' ? '' : 'none';
  document.getElementById('fields-social').style.display  = mode === 'social'  ? '' : 'none';
  if (mode === 'article') {
    document.getElementById('modal-title').textContent = 'Ajouter un article';
    if (brand) document.getElementById('f-brand').value = brand;
    document.getElementById('f-title').value = '';
    document.getElementById('f-url').value   = '';
    document.getElementById('f-img').value   = '';
  } else {
    document.getElementById('modal-title').textContent = 'Ajouter un réseau';
    document.getElementById('f-shandle').value = '';
    document.getElementById('f-surl').value    = '';
  }
  document.getElementById('overlay').classList.add('open');
}

function closeModal() { document.getElementById('overlay').classList.remove('open'); }

function overlayClick(e) { if (e.target === document.getElementById('overlay')) closeModal(); }

function confirmAdd() {
  if (modalMode === 'article') {
    const title = document.getElementById('f-title').value.trim();
    const url   = document.getElementById('f-url').value.trim();
    const img   = document.getElementById('f-img').value.trim();
    const brand = document.getElementById('f-brand').value;
    if (!title || !url) { alert('Remplissez le titre et le lien.'); return; }
    state.articles.push({ brand, title, url, img });
    save(); renderArticles();
    closeModal();
    document.querySelector(`[data-page="${brand.toLowerCase()}"]`).click();
  } else {
    const net    = document.getElementById('f-snet').value;
    const handle = document.getElementById('f-shandle').value.trim();
    const url    = document.getElementById('f-surl').value.trim();
    if (!handle || !url) { alert('Remplissez le nom et le lien.'); return; }
    state.socials.push({ net, handle, url });
    save(); renderSocials();
    closeModal();
    document.querySelector('[data-page="socials"]').click();
  }
}

// ─────────────────────────────────────────
//  UTILS
// ─────────────────────────────────────────
function escHtml(s) {
  return String(s)
    .replace(/&/g,'&amp;').replace(/"/g,'&quot;')
    .replace(/</g,'&lt;').replace(/>/g,'&gt;');
}

// ─────────────────────────────────────────
//  INIT
// ─────────────────────────────────────────
renderArticles();
renderSocials();
</script>
</body>
</html>
