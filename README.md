<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Ayiwa Express — Livraison rapide au Bénin</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&display=swap" rel="stylesheet" />
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@latest/tabler-icons.min.css" />
  <style>
    *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

    :root {
      --blue: #1B3F8B;
      --blue-light: #E8EDF8;
      --blue-mid: #2E5CB8;
      --gold: #D4A017;
      --gold-light: #FBF3DC;
      --gold-mid: #E8B820;
      --dark: #0D1F3C;
      --text: #2C3E5A;
      --bg: #F7F9FC;
      --white: #ffffff;
    }

    html { scroll-behavior: smooth; }
    body { font-family: 'Inter', sans-serif; color: var(--text); background: var(--white); }

    /* NAV */
    nav {
      position: sticky; top: 0; z-index: 100;
      display: flex; align-items: center; justify-content: space-between;
      padding: 0.9rem 3rem;
      background: var(--white);
      border-bottom: 2px solid var(--gold);
      box-shadow: 0 1px 12px rgba(27,63,139,0.07);
    }
    .logo { font-size: 22px; font-weight: 600; letter-spacing: -0.5px; display: flex; align-items: center; gap: 3px; text-decoration: none; }
    .logo .l1 { color: var(--blue); }
    .logo .l2 { color: var(--gold); }
    .nav-links { display: flex; gap: 2rem; list-style: none; }
    .nav-links a { font-size: 14px; color: var(--text); text-decoration: none; opacity: 0.75; transition: opacity 0.2s; }
    .nav-links a:hover { opacity: 1; color: var(--blue); }
    .nav-cta {
      background: var(--blue); color: #fff; border: none;
      padding: 9px 20px; border-radius: 7px; font-size: 14px; cursor: pointer;
      font-weight: 500; display: flex; align-items: center; gap: 7px;
      text-decoration: none; transition: background 0.2s;
    }
    .nav-cta:hover { background: var(--blue-mid); }
    .hamburger { display: none; background: none; border: none; cursor: pointer; font-size: 24px; color: var(--blue); }

    /* HERO */
    .hero {
      background: linear-gradient(135deg, #EEF2FA 0%, #F7F9FC 60%, #FBF3DC 100%);
      padding: 5rem 3rem 4rem;
      display: grid; grid-template-columns: 1.1fr 0.9fr; gap: 3rem; align-items: center;
    }
    .hero-badge {
      display: inline-flex; align-items: center; gap: 8px;
      background: var(--blue-light); color: var(--blue);
      font-size: 12px; padding: 5px 14px; border-radius: 20px; margin-bottom: 1.5rem;
      border: 0.5px solid #BFC9E0;
    }
    .live-dot { width: 8px; height: 8px; background: #22C55E; border-radius: 50%; display: inline-block; animation: pulse 2s infinite; }
    @keyframes pulse { 0%,100%{opacity:1} 50%{opacity:0.4} }
    .hero h1 { font-size: 42px; font-weight: 600; line-height: 1.15; color: var(--dark); margin-bottom: 1.25rem; letter-spacing: -1.5px; }
    .hero h1 em { font-style: normal; color: var(--blue); }
    .hero h1 .accent { color: var(--gold); }
    .hero p { font-size: 16px; line-height: 1.8; color: var(--text); opacity: 0.85; margin-bottom: 2.25rem; max-width: 480px; }
    .hero-btns { display: flex; gap: 1rem; flex-wrap: wrap; }
    .btn-gold {
      background: var(--gold); color: var(--dark); border: none;
      padding: 13px 24px; border-radius: 8px; font-size: 15px; cursor: pointer;
      display: inline-flex; align-items: center; gap: 8px; font-weight: 500;
      text-decoration: none; transition: background 0.2s;
    }
    .btn-gold:hover { background: #C4920F; }
    .btn-outline {
      background: transparent; color: var(--blue);
      border: 1.5px solid var(--blue);
      padding: 13px 24px; border-radius: 8px; font-size: 15px; cursor: pointer;
      text-decoration: none; display: inline-flex; align-items: center; gap: 7px;
      transition: background 0.2s;
    }
    .btn-outline:hover { background: var(--blue-light); }

    /* CONTACT CARD */
    .hero-card {
      background: var(--white); border-radius: 16px; padding: 1.75rem;
      border: 0.5px solid #D0DAEE; box-shadow: 0 4px 24px rgba(27,63,139,0.1);
    }
    .card-title {
      font-size: 13px; color: var(--blue); font-weight: 500;
      display: flex; align-items: center; gap: 8px; margin-bottom: 1.25rem;
    }
    .quick-info { display: flex; flex-direction: column; gap: 0.75rem; margin-bottom: 1.5rem; }
    .info-row {
      display: flex; align-items: center; gap: 12px;
      padding: 11px 14px; border-radius: 8px;
      background: var(--bg); border: 0.5px solid #E2EAF5;
    }
    .info-row i { color: var(--blue); font-size: 18px; flex-shrink: 0; }
    .info-row span, .info-row a { font-size: 14px; color: var(--text); text-decoration: none; }
    .info-row a:hover { color: var(--blue); }
    .wa-btn {
      width: 100%; background: #25D366; color: #fff; border: none;
      padding: 13px; border-radius: 9px; font-size: 15px; cursor: pointer;
      display: flex; align-items: center; justify-content: center; gap: 9px;
      font-weight: 500; text-decoration: none; transition: background 0.2s;
    }
    .wa-btn:hover { background: #1DAE58; }

    /* STATS */
    .stats {
      background: var(--blue); padding: 1.75rem 3rem;
      display: grid; grid-template-columns: repeat(4, 1fr);
    }
    .stat { text-align: center; padding: 0.5rem; }
    .stat .n { font-size: 28px; font-weight: 600; color: var(--gold-mid); }
    .stat .l { font-size: 13px; color: rgba(255,255,255,0.7); margin-top: 3px; }

    /* SECTIONS */
    section { padding: 4rem 3rem; }
    section.alt { background: var(--bg); }
    .eyebrow { font-size: 11px; color: var(--gold); letter-spacing: 2px; text-transform: uppercase; margin-bottom: 5px; }
    .sec-title { font-size: 30px; font-weight: 600; color: var(--dark); letter-spacing: -0.5px; margin-bottom: 2.5rem; }

    /* SERVICES */
    .svc-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.25rem; }
    .svc {
      border: 0.5px solid #D0DAEE; border-radius: 12px; padding: 1.5rem;
      background: var(--white); transition: border-color 0.2s, box-shadow 0.2s;
    }
    .svc:hover { border-color: var(--blue); box-shadow: 0 4px 16px rgba(27,63,139,0.08); }
    .svc-ico {
      width: 46px; height: 46px; border-radius: 11px;
      background: var(--blue-light);
      display: flex; align-items: center; justify-content: center;
      font-size: 22px; color: var(--blue); margin-bottom: 1rem;
    }
    .svc h3 { font-size: 15px; font-weight: 600; color: var(--dark); margin-bottom: 6px; }
    .svc p { font-size: 13px; color: var(--text); opacity: 0.8; line-height: 1.65; }

    /* STEPS */
    .steps-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 1.25rem; }
    .step { text-align: center; padding: 1.5rem 1rem; }
    .step-n {
      width: 42px; height: 42px; border-radius: 50%;
      background: var(--gold); color: var(--dark);
      display: flex; align-items: center; justify-content: center;
      font-size: 16px; font-weight: 600; margin: 0 auto 1rem;
    }
    .step h3 { font-size: 15px; font-weight: 600; color: var(--dark); margin-bottom: 6px; }
    .step p { font-size: 13px; color: var(--text); opacity: 0.8; line-height: 1.65; }

    /* TESTIMONIALS */
    .testi-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.25rem; }
    .testi { border: 0.5px solid #D0DAEE; border-radius: 12px; padding: 1.5rem; background: var(--white); }
    .stars { color: var(--gold); font-size: 15px; margin-bottom: 12px; }
    .testi p { font-size: 14px; line-height: 1.75; color: var(--text); margin-bottom: 1.25rem; }
    .tauth { display: flex; align-items: center; gap: 10px; }
    .av {
      width: 36px; height: 36px; border-radius: 50%;
      background: var(--blue-light); color: var(--blue);
      display: flex; align-items: center; justify-content: center;
      font-size: 12px; font-weight: 600; flex-shrink: 0;
    }
    .tauth strong { font-size: 13px; font-weight: 600; color: var(--dark); display: block; }
    .tauth span { font-size: 12px; color: var(--text); opacity: 0.65; }

    /* CONTACT SECTION */
    .contact-sec {
      background: var(--dark); padding: 4rem 3rem; text-align: center;
    }
    .contact-sec h2 { font-size: 32px; font-weight: 600; color: #fff; letter-spacing: -0.5px; margin-bottom: 0.75rem; }
    .contact-sec > p { font-size: 16px; color: rgba(255,255,255,0.6); margin-bottom: 2.5rem; }
    .contact-cards { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.25rem; max-width: 700px; margin: 0 auto 2.5rem; }
    .contact-card {
      background: rgba(255,255,255,0.06); border-radius: 12px;
      padding: 1.5rem 1rem; border: 0.5px solid rgba(255,255,255,0.12);
      display: flex; flex-direction: column; align-items: center; gap: 10px;
      transition: background 0.2s;
    }
    .contact-card:hover { background: rgba(255,255,255,0.1); }
    .contact-card i { font-size: 28px; color: var(--gold-mid); }
    .contact-card .clbl { font-size: 11px; color: rgba(255,255,255,0.5); text-transform: uppercase; letter-spacing: 1.5px; }
    .contact-card .cval { font-size: 15px; color: #fff; font-weight: 500; }
    .contact-card a { color: var(--gold-mid); text-decoration: none; font-size: 13px; text-align: center; line-height: 1.5; }
    .wa-big {
      background: #25D366; color: #fff; border: none;
      padding: 14px 36px; border-radius: 10px; font-size: 16px; cursor: pointer;
      display: inline-flex; align-items: center; gap: 10px; font-weight: 500;
      text-decoration: none; transition: background 0.2s;
    }
    .wa-big:hover { background: #1DAE58; }

    /* FOOTER */
    footer {
      background: #070F1E; padding: 2rem 3rem;
      display: flex; align-items: center; justify-content: space-between; flex-wrap: wrap; gap: 1rem;
    }
    .flogo { font-size: 18px; font-weight: 600; }
    .flogo .l1 { color: #B5C6E8; }
    .flogo .l2 { color: var(--gold); }
    footer p { font-size: 12px; color: rgba(255,255,255,0.35); }
    .flinks { display: flex; gap: 2rem; }
    .flinks a { font-size: 13px; color: rgba(255,255,255,0.45); text-decoration: none; }
    .flinks a:hover { color: var(--gold-mid); }

    /* RESPONSIVE */
    @media (max-width: 900px) {
      nav { padding: 0.9rem 1.5rem; }
      .nav-links { display: none; }
      .hamburger { display: block; }
      .hero { grid-template-columns: 1fr; padding: 3rem 1.5rem; }
      .hero h1 { font-size: 32px; }
      .hero-card { display: none; }
      .stats { grid-template-columns: repeat(2, 1fr); padding: 1.5rem; gap: 1rem; }
      section { padding: 3rem 1.5rem; }
      .svc-grid { grid-template-columns: 1fr 1fr; }
      .steps-grid { grid-template-columns: 1fr 1fr; }
      .testi-grid { grid-template-columns: 1fr; }
      .contact-cards { grid-template-columns: 1fr; max-width: 360px; }
      .contact-sec { padding: 3rem 1.5rem; }
      footer { padding: 1.5rem; flex-direction: column; text-align: center; }
      .flinks { justify-content: center; }
    }

    @media (max-width: 600px) {
      .hero h1 { font-size: 26px; }
      .svc-grid { grid-template-columns: 1fr; }
      .steps-grid { grid-template-columns: 1fr; }
    }
  </style>
</head>
<body>

  <nav>
    <a href="#" class="logo">
      <span class="l1">Ayiwa</span>
      <span class="l2">Express</span>
    </a>
    <ul class="nav-links">
      <li><a href="#services">Services</a></li>
      <li><a href="#comment">Comment ça marche</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
    <a href="https://wa.me/22960169655041" target="_blank" class="nav-cta">
      <i class="ti ti-brand-whatsapp"></i> WhatsApp
    </a>
    <button class="hamburger" aria-label="Menu">&#9776;</button>
  </nav>

  <!-- HERO -->
  <div class="hero">
    <div>
      <div class="hero-badge">
        <span class="live-dot"></span>
        Livraison disponible maintenant au Bénin
      </div>
      <h1>Votre livraison,<br><em>rapide</em> et <span class="accent">fiable</span>.</h1>
      <p>Colis, repas, documents, courses — Ayiwa Express prend en charge tous vos envois au Bénin, 7 jours sur 7, avec rapidité et sérieux.</p>
      <div class="hero-btns">
        <a href="https://wa.me/22960169655041" target="_blank" class="btn-gold">
          <i class="ti ti-brand-whatsapp"></i> Commander sur WhatsApp
        </a>
        <a href="#services" class="btn-outline">
          Nos services <i class="ti ti-arrow-down"></i>
        </a>
      </div>
    </div>
    <div class="hero-card">
      <div class="card-title">
        <span class="live-dot"></span> Contactez-nous directement
      </div>
      <div class="quick-info">
        <div class="info-row">
          <i class="ti ti-phone"></i>
          <a href="tel:+22960169655041">+229 60 169 655 041</a>
        </div>
        <div class="info-row">
          <i class="ti ti-brand-whatsapp"></i>
          <a href="https://wa.me/22960169655041" target="_blank">WhatsApp : 0169655041</a>
        </div>
        <div class="info-row">
          <i class="ti ti-mail"></i>
          <a href="mailto:ayiwaexpressbenin@gmail.com">ayiwaexpressbenin@gmail.com</a>
        </div>
        <div class="info-row">
          <i class="ti ti-clock"></i>
          <span>Disponible 7j/7 — délai moyen 30 min</span>
        </div>
      </div>
      <a href="https://wa.me/22960169655041" target="_blank" class="wa-btn">
        <i class="ti ti-brand-whatsapp" style="font-size:20px;"></i>
        Écrire sur WhatsApp maintenant
      </a>
    </div>
  </div>

  <!-- STATS -->
  <div class="stats">
    <div class="stat"><div class="n">2 000+</div><div class="l">Livraisons réalisées</div></div>
    <div class="stat"><div class="n">98%</div><div class="l">Clients satisfaits</div></div>
    <div class="stat"><div class="n">30 min</div><div class="l">Délai moyen</div></div>
    <div class="stat"><div class="n">7j/7</div><div class="l">Disponibilité</div></div>
  </div>

  <!-- SERVICES -->
  <section id="services">
    <div class="eyebrow">Nos services</div>
    <div class="sec-title">On livre tout, partout au Bénin.</div>
    <div class="svc-grid">
      <div class="svc">
        <div class="svc-ico"><i class="ti ti-package"></i></div>
        <h3>Colis & e-commerce</h3>
        <p>Achats en ligne ou envois personnels livrés directement à domicile, en toute sécurité.</p>
      </div>
      <div class="svc">
        <div class="svc-ico"><i class="ti ti-tools-kitchen-2"></i></div>
        <h3>Repas & restauration</h3>
        <p>Partenaire des restaurants locaux, on apporte vos plats chauds avant qu'ils refroidissent.</p>
      </div>
      <div class="svc">
        <div class="svc-ico"><i class="ti ti-file-text"></i></div>
        <h3>Documents & courriers</h3>
        <p>Contrats, factures, enveloppes urgentes — remis en main propre avec confirmation.</p>
      </div>
      <div class="svc">
        <div class="svc-ico"><i class="ti ti-building-store"></i></div>
        <h3>Courses & commissions</h3>
        <p>Vous n'avez pas le temps ? On fait vos courses et on vous les livre où vous êtes.</p>
      </div>
      <div class="svc">
        <div class="svc-ico"><i class="ti ti-truck"></i></div>
        <h3>Livraison en gros</h3>
        <p>Pour entreprises et commerçants, on gère des volumes importants avec ponctualité.</p>
      </div>
      <div class="svc">
        <div class="svc-ico"><i class="ti ti-clock-bolt"></i></div>
        <h3>Livraison urgente</h3>
        <p>Besoin immédiat ? Notre flotte disponible 7j/7 répond en moins de 5 minutes.</p>
      </div>
    </div>
  </section>

  <!-- HOW IT WORKS -->
  <section id="comment" class="alt">
    <div class="eyebrow">Processus</div>
    <div class="sec-title">Simple en 4 étapes.</div>
    <div class="steps-grid">
      <div class="step">
        <div class="step-n">1</div>
        <h3>Passez commande</h3>
        <p>Par WhatsApp, appel ou e-mail — en quelques secondes seulement.</p>
      </div>
      <div class="step">
        <div class="step-n">2</div>
        <h3>On récupère</h3>
        <p>Un livreur Ayiwa se déplace chez vous ou chez le vendeur.</p>
      </div>
      <div class="step">
        <div class="step-n">3</div>
        <h3>Suivi en direct</h3>
        <p>Vous recevez des notifications à chaque étape de la livraison.</p>
      </div>
      <div class="step">
        <div class="step-n">4</div>
        <h3>Livré !</h3>
        <p>Votre envoi arrive à destination, vous confirmez la réception.</p>
      </div>
    </div>
  </section>

  <!-- TESTIMONIALS -->
  <section>
    <div class="eyebrow">Témoignages</div>
    <div class="sec-title">Ce que disent nos clients.</div>
    <div class="testi-grid">
      <div class="testi">
        <div class="stars">★★★★★</div>
        <p>Service impeccable ! Mon colis est arrivé en moins de 25 minutes, bien emballé et en parfait état. Je recommande vivement Ayiwa Express.</p>
        <div class="tauth">
          <div class="av">AK</div>
          <div><strong>Adeola K.</strong><span>Cliente particulière, Cotonou</span></div>
        </div>
      </div>
      <div class="testi">
        <div class="stars">★★★★★</div>
        <p>On utilise Ayiwa Express pour toutes nos livraisons boutique. Fiables, ponctuels et très professionnels. Un vrai partenaire de confiance.</p>
        <div class="tauth">
          <div class="av">MS</div>
          <div><strong>Moussa S.</strong><span>Gérant boutique, Porto-Novo</span></div>
        </div>
      </div>
      <div class="testi">
        <div class="stars">★★★★☆</div>
        <p>Pratique et rapide. J'ai pu envoyer des documents urgents sans me déplacer. Le livreur était très courtois et professionnel.</p>
        <div class="tauth">
          <div class="av">FD</div>
          <div><strong>Fatima D.</strong><span>Professionnelle, Abomey-Calavi</span></div>
        </div>
      </div>
    </div>
  </section>

  <!-- CONTACT -->
  <section id="contact" class="contact-sec">
    <h2>Prêt à envoyer quelque chose ?</h2>
    <p>Contactez-nous maintenant — un livreur peut être chez vous en moins de 10 minutes.</p>
    <div class="contact-cards">
      <div class="contact-card">
        <i class="ti ti-phone"></i>
        <div class="clbl">Appel</div>
        <div class="cval">0169 655 041</div>
      </div>
      <div class="contact-card">
        <i class="ti ti-brand-whatsapp"></i>
        <div class="clbl">WhatsApp</div>
        <div class="cval">0169 655 041</div>
      </div>
      <div class="contact-card">
        <i class="ti ti-mail"></i>
        <div class="clbl">Email</div>
        <a href="mailto:ayiwaexpressbenin@gmail.com">ayiwaexpressbenin@gmail.com</a>
      </div>
    </div>
    <a href="https://wa.me/22960169655041" target="_blank" class="wa-big">
      <i class="ti ti-brand-whatsapp" style="font-size:22px;"></i>
      Écrire sur WhatsApp maintenant
    </a>
  </section>

  <footer>
    <div class="flogo"><span class="l1">Ayiwa</span><span class="l2">Express</span></div>
    <p>© 2025 Ayiwa Express Bénin — Tous droits réservés</p>
    <div class="flinks">
      <a href="mailto:ayiwaexpressbenin@gmail.com">ayiwaexpressbenin@gmail.com</a>
      <a href="tel:+22960169655041">0169 655 041</a>
    </div>
  </footer>

</body>
