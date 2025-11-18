<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ParkEase – Intelligente Parkplatz-Sharing-App</title>
    <meta name="description" content="ParkEase ist eine App, mit der private Parkplatzbesitzer freie Stellplätze mit Autofahrern teilen können – flexibel, effizient und nachhaltig.">

    <style>
        :root {
            --bg: #020617;
            --accent: #16a34a;
            --accent-blue: #2563eb;
            --accent-blue-soft: #1d4ed8;
            --accent-soft: #bbf7d0;
            --text: #0f172a;
            --muted: #6b7280;
            --card: #ffffff;
            --border-soft: #d1d5db;
            --radius: 18px;
            --shadow: 0 24px 60px rgba(15, 23, 42, 0.45);
            --max-box: 880px;
        }

        * { box-sizing: border-box; }

        body {
            margin: 0;
            font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
            color: var(--text);
            line-height: 1.6;
            background: radial-gradient(circle at top, #0f172a 0, #020617 55%, #000 100%);
            position: relative;
            overflow-x: hidden;
        }

        /* Animierter Hintergrund */
        body::before {
            content: "";
            position: fixed;
            inset: -20%;
            background:
                radial-gradient(circle at 10% 20%, rgba(59,130,246,0.18), transparent 55%),
                radial-gradient(circle at 90% 10%, rgba(34,197,94,0.18), transparent 55%),
                radial-gradient(circle at 50% 90%, rgba(59,130,246,0.22), transparent 55%);
            opacity: 0.9;
            z-index: -2;
            animation: bgFloat 35s ease-in-out infinite alternate;
        }

        @keyframes bgFloat {
            0% { transform: translate3d(0, 0, 0) scale(1); }
            50% { transform: translate3d(-3%, 1%, 0) scale(1.05); }
            100% { transform: translate3d(2%, -2%, 0) scale(1.02); }
        }

        .noise-overlay {
            position: fixed;
            inset: 0;
            pointer-events: none;
            opacity: 0.32;
            z-index: -1;
            background-image: linear-gradient(to right, rgba(148,163,184,0.06) 1px, transparent 1px),
                              linear-gradient(to bottom, rgba(148,163,184,0.06) 1px, transparent 1px);
            background-size: 18px 18px;
        }

        a { color: inherit; text-decoration: none; }

        .container {
            max-width: 1080px;
            margin: 0 auto;
            padding: 24px 18px 72px;
        }

        /* HEADER */
        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 18px;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .logo-icon {
            width: 44px;
            height: 44px;
            border-radius: 14px;
            background: radial-gradient(circle at 30% 20%, #3b82f6, #1d4ed8);
            display: flex;
            justify-content: center;
            align-items: center;
            color: white;
            font-size: 20px;
            font-weight: 800;
            box-shadow: 0 16px 35px rgba(37, 99, 235, 0.6);
        }

        .logo-text-title {
            font-weight: 700;
            font-size: 18px;
            letter-spacing: 0.04em;
            color: #e5e7eb;
        }

        /* Neuer, großer Slogan neben dem Icon */
        .logo-slogan {
            font-size: 17px;
            font-weight: 900;
            color: #facc15;
            letter-spacing: 0.06em;
            text-transform: uppercase;
        }

        nav {
            display: flex;
            gap: 18px;
            font-size: 14px;
            color: #9ca3af;
        }

        nav a {
            position: relative;
            padding-bottom: 2px;
        }

        nav a::after {
            content: "";
            position: absolute;
            left: 0;
            bottom: -3px;
            width: 0;
            height: 2px;
            border-radius: 999px;
            background: linear-gradient(90deg, #3b82f6, #22c55e);
            transition: width 0.2s ease;
        }

        nav a:hover::after {
            width: 100%;
        }

        nav a:hover {
            color: #e5e7eb;
        }

        main {
            margin-top: 10px;
            display: block;
        }

        /* GENERISCHE SECTION-KARTEN */
        section {
            background: radial-gradient(circle at top left, rgba(59,130,246,0.16), rgba(15,23,42,0.98));
            border-radius: var(--radius);
            padding: 22px;
            margin-bottom: 22px;
            border: 1px solid rgba(148,163,184,0.3);
            box-shadow: var(--shadow);
            backdrop-filter: blur(12px);
        }

        h2 {
            margin: 0 0 12px;
            font-size: 20px;
            color: #e5e7eb;
        }

        .section-subtitle {
            color: #9ca3af;
            margin-bottom: 14px;
            font-size: 14px;
        }

        /* VIDEOBLOCK */
        .video-wrapper {
            width: 100%;
            max-width: var(--max-box);
            aspect-ratio: 16 / 9;
            margin: 18px auto 10px;
            background: #020617;
            border-radius: 20px;
            overflow: hidden;
            border: 1px solid rgba(148,163,184,0.5);
            box-shadow: 0 18px 45px rgba(15,23,42,0.8);
            position: relative;
        }

        .video-wrapper iframe {
            width: 100%;
            height: 100%;
            border: none;
            display: block;
        }

        .info-block {
            max-width: var(--max-box);
            margin: 14px auto 0;
            font-size: 14px;
            color: #e5e7eb;
            font-weight: 700; /* wichtiger Block */
            background: linear-gradient(135deg, rgba(15,23,42,0.95), rgba(15,23,42,0.85));
            border-radius: 14px;
            padding: 14px 16px;
            border: 1px solid rgba(148,163,184,0.45);
            position: relative;
        }

        .info-block::before {
            content: "i";
            position: absolute;
            left: 14px;
            top: 14px;
            width: 22px;
            height: 22px;
            border-radius: 999px;
            border: 1px solid rgba(59,130,246,0.8);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 13px;
            color: #bfdbfe;
            background: rgba(15,23,42,0.9);
        }

        .info-block-inner {
            padding-left: 32px;
        }

        .info-block ul {
            margin-top: 8px;
            padding-left: 20px;
        }

        .info-block li + li {
            margin-top: 4px;
        }

        /* HERO / IDEE */
        .hero {
            display: grid;
            grid-template-columns: 1.2fr 1fr;
            gap: 32px;
        }

        .hero-badge {
            background: rgba(22,163,74,0.12);
            border: 1px solid rgba(74,222,128,0.6);
            padding: 4px 10px;
            border-radius: 999px;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            font-size: 11px;
            color: #bbf7d0;
        }

        .hero-badge-dot {
            width: 18px;
            height: 18px;
            border-radius: 50%;
            background: radial-gradient(circle, #22c55e, #15803d);
            box-shadow: 0 0 12px rgba(34,197,94,0.8);
        }

        .hero-title {
            font-size: clamp(32px, 4vw, 44px);
            font-weight: 800;
            margin: 10px 0 8px;
            color: #f9fafb;
        }

        .hero-subtitle {
            color: #cbd5f5;
            max-width: 520px;
            font-size: 14px;
            margin-top: 4px;
        }

        .hero-highlight {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin: 16px 0;
        }

        .chip {
            padding: 6px 12px;
            border-radius: 999px;
            background: rgba(15,23,42,0.9);
            border: 1px solid rgba(148,163,184,0.6);
            color: #e5e7eb;
            font-size: 12px;
        }

        .chip-strong {
            background: rgba(22,163,74,0.2);
            border-color: rgba(74,222,128,0.9);
            color: #bbf7d0;
        }

        .btn-row {
            display: flex;
            gap: 10px;
            margin: 10px 0 8px;
            flex-wrap: wrap;
        }

        .btn-primary {
            padding: 10px 18px;
            background: linear-gradient(135deg, #3b82f6, #1d4ed8);
            border-radius: 999px;
            border: none;
            color: #eff6ff;
            font-weight: 600;
            cursor: pointer;
            box-shadow: 0 14px 30px rgba(15,23,42,0.8);
            transition: transform 0.15s ease, box-shadow 0.15s ease, filter 0.15s ease;
        }

        .btn-primary:hover {
            transform: translateY(-1px);
            box-shadow: 0 18px 40px rgba(15,23,42,0.9);
            filter: brightness(1.05);
        }

        .hero-note {
            font-size: 11px;
            color: #9ca3af;
        }

        .hero-right {
            background: radial-gradient(circle at top left, rgba(37,99,235,0.16), rgba(15,23,42,0.96));
            padding: 18px;
            border-radius: 18px;
            border: 1px solid rgba(148,163,184,0.45);
            box-shadow: 0 18px 45px rgba(15,23,42,0.9);
        }

        .hero-right h3 {
            margin-top: 0;
            font-size: 18px;
            font-weight: 800;
            color: #e5e7eb;
            display: flex;
            align-items: center;
            gap: 6px;
        }

        .hero-right h3::before {
            content: "ⓘ";
            font-size: 16px;
            color: #93c5fd;
        }

        .hero-right p {
            font-size: 15px;
            font-weight: 600;
            color: #e5e7eb;
        }

        .hero-image {
            width: 100%;
            border-radius: 12px;
            margin: 10px 0 14px;
            border: 1px solid rgba(148,163,184,0.7);
            box-shadow: 0 12px 30px rgba(15,23,42,0.9);
            display: block;
        }

        /* FUNKTION */
        .funktion-list {
            margin-top: 6px;
            padding-left: 18px;
            color: #e5e7eb;
            font-size: 14px;
        }

        .funktion-list li + li {
            margin-top: 4px;
        }

        .funktion-list li::marker {
            color: #38bdf8;
        }

        footer {
            margin-top: 30px;
            text-align: center;
            color: #9ca3af;
            font-size: 12px;
        }

        @media (max-width: 880px) {
            .hero {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 640px) {
            header {
                flex-direction: column;
                align-items: flex-start;
                gap: 12px;
            }
        }
    </style>
</head>

<body>
<div class="noise-overlay"></div>

<div class="container">

    <!-- HEADER -->
    <header>
        <div class="logo">
            <div class="logo-icon">P</div>
            <div>
                <div class="logo-text-title">ParkEase</div>
                <div class="logo-slogan">Parkplätze teilen. Stress sparen.</div>
            </div>
        </div>

        <nav>
            <a href="#idee">Idee</a>
            <a href="#video">Pitch-Video</a>
            <a href="#funktion">Funktion</a>
            <a href="https://calendly.com/leonbritz0" target="_blank" rel="noopener noreferrer">Termin</a>
        </nav>
    </header>

    <main>
        <!-- VIDEO DIREKT UNTER NAV -->
        <section id="video">
            <h2 style="text-align:center;">Pitch-Video</h2>
            <p class="section-subtitle" style="text-align:center;">
                In diesem kurzen Video zeigen wir, wie ParkEase das Parken einfacher, schneller und nachhaltiger macht.
            </p>

            <div class="video-wrapper">
                <iframe
                    src="https://www.youtube.com/embed/il_ueri6y8s?controls=1&modestbranding=1&rel=0&playsinline=1"
                    allow="encrypted-media"
                    allowfullscreen>
                </iframe>
            </div>

            <div class="info-block">
                <div class="info-block-inner">
                    <p>
                        Das Video richtet sich an alle, die regelmäßig Zeit durch Parkplatzsuche verlieren, sowie an Menschen,
                        die ungenutzte Stellplätze besitzen und daraus eine flexible Einnahmequelle machen möchten.
                    </p>

                    <ul>
                        <li><strong>Zielgruppe:</strong> Pendler, Studierende, Innenstadtbewohner und private Stellplatzbesitzer.</li>
                        <li><strong>Mehrwert:</strong> Weniger Suchverkehr, weniger Stress und effizientere Nutzung vorhandener Parkflächen.</li>
                        <li><strong>Vorteile der App:</strong> Transparente Preise, schnelle Buchung, sichere Bezahlung und klare Bewertungen.</li>
                    </ul>

                    <p style="margin-top:10px;">
                        Wenn du Interesse am Projekt hast oder Feedback geben möchtest, kannst du oben über <strong>„Termin“</strong>
                        direkt einen Gesprächstermin mit dem ParkEase-Team über Calendly buchen.
                    </p>
                </div>
            </div>
        </section>

        <!-- HERO / IDEE -->
        <section class="hero" id="idee">
            <div>
                <div class="hero-badge">
                    <div class="hero-badge-dot"></div>
                    MVP · Hochschulprojekt
                </div>

                <h1 class="hero-title">
                    Finde deinen Parkplatz in <span>Sekunden</span>.
                </h1>

                <p class="hero-subtitle">
                    ParkEase verbindet Autofahrer mit privaten Stellplatzanbietern – so wird aus ungenutzten
                    Parkflächen ein flexibles, digitales Sharing-Angebot.
                </p>

                <div class="hero-highlight">
                    <div class="chip chip-strong">Weniger CO₂ & Stau</div>
                    <div class="chip">Einnahmen für Vermieter</div>
                    <div class="chip">Transparente Buchung</div>
                </div>

                <div class="btn-row">
                    <!-- Button führt DIREKT zu Calendly -->
                    <a href="https://calendly.com/leonbritz0" target="_blank" rel="noopener noreferrer">
                        <button class="btn-primary">Termin mit dem Team buchen</button>
                    </a>
                </div>

                <div class="hero-note">
                    Geplanter Launch (MVP): Januar 2026 · Projektkontext: Hochschule / Studienprojekt
                </div>
            </div>

            <div class="hero-right">
                <h3>Was ist ParkEase?</h3>

                <!-- Bild mit deinem externen Link -->
                <img
                    src="https://www.abendzeitung-muenchen.de/storage/image/4/4/7/3/1153744_woehr-bauer_mehrzumthema_1ACZQZ_L0Z1n0.jpg"
                    alt="Leeres, großes Parkhaus mit vielen Stellplätzen"
                    class="hero-image">

                <p>
                    ParkEase ist eine Konzept-App, die freien Parkraum sichtbar macht. Stellplätze, Einfahrten oder private
                    Parkflächen können kurzfristig freigegeben und von Autofahrern gebucht werden.
                </p>
                <p>
                    So entsteht ein smarter, gemeinschaftlich genutzter Parkplatzpool – mit Vorteil für Fahrer, Vermieter
                    und die Umwelt. Genau solche Bilder von leeren, anonymen Parkhäusern wie oben sollen durch eine
                    bessere Auslastung und Planung in Zukunft verhindert werden.
                </p>
            </div>
        </section>

        <!-- FUNKTION -->
        <section id="funktion">
            <h2>Wie ParkEase funktioniert</h2>
            <p class="section-subtitle">
                Einfach in der Nutzung – klar in der Struktur.
            </p>

            <ul class="funktion-list">
                <li><strong>Für Fahrer:</strong> App öffnen, Zielgebiet wählen, freien Stellplatz auswählen und direkt buchen.</li>
                <li><strong>Für Vermieter:</strong> Stellplatz anlegen, Zeiten & Preise festlegen, Buchungen im Überblick behalten.</li>
                <li><strong>Bezahlung:</strong> Läuft digital über integrierte Zahlungsdienste (z. B. Karten- oder Wallet-Anbieter).</li>
                <li><strong>Nachhaltigkeit:</strong> Weniger Suchverkehr bedeutet weniger Emissionen und weniger Stress im Stadtverkehr.</li>
            </ul>
        </section>
    </main>

    <footer>
        ParkEase – Konzept im Rahmen eines Hochschulprojekts (MVP).<br>
        Bereitgestellt über GitHub Pages.
    </footer>

</div>
</body>
</html>
