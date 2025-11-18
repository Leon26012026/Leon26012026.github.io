# Leon26012026.github.io
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ParkEase – Intelligente Parkplatz-Sharing-App</title>
    <meta name="description" content="ParkEase ist eine App, mit der private Parkplatzbesitzer freie Stellplätze mit Autofahrern teilen können – flexibel, effizient und nachhaltig.">

    <style>
        :root {
            --bg: #f2f7f5;
            --bg-soft: #e3f6ec;
            --accent: #16a34a;
            --accent-soft: #bbf7d0;
            --accent-blue: #2563eb;
            --accent-blue-soft: #dbeafe;
            --text: #0f172a;
            --muted: #6b7280;
            --card: #ffffff;
            --border-soft: #d1d5db;
            --radius: 16px;
            --shadow: 0 18px 40px rgba(0,0,0,0.08);
            --max-box: 880px;
        }

        * { box-sizing: border-box; }

        body {
            margin: 0;
            font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
            background: radial-gradient(circle at top, #dbeafe 0, #f2f7f5 45%, #ecfdf3 100%);
            color: var(--text);
            line-height: 1.55;
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
            gap: 10px;
        }

        .logo-icon {
            width: 42px;
            height: 42px;
            border-radius: 12px;
            background: radial-gradient(circle at 30% 20%, #3b82f6, #1d4ed8); /* blau */
            display: flex;
            justify-content: center;
            align-items: center;
            color: white;
            font-size: 20px;
            font-weight: 800;
            box-shadow: 0 10px 25px rgba(37, 99, 235, 0.4);
        }

        .logo-text-title {
            font-weight: 700;
            font-size: 18px;
            letter-spacing: 0.03em;
        }

        .logo-text-sub {
            font-size: 12px;
            color: var(--muted);
        }

        nav {
            display: flex;
            gap: 18px;
            font-size: 14px;
            color: var(--muted);
        }

        nav a:hover {
            color: var(--accent-blue);
        }

        /* VIDEO OBEN */
        main {
            margin-top: 10px;
            display: block;
        }

        section {
            background: var(--card);
            border-radius: var(--radius);
            padding: 22px;
            margin-bottom: 22px;
            border: 1px solid var(--border-soft);
            box-shadow: var(--shadow);
        }

        h2 {
            margin: 0 0 12px;
            font-size: 20px;
        }

        .section-subtitle {
            color: var(--muted);
            margin-bottom: 14px;
        }

        .video-wrapper {
            width: 100%;
            max-width: var(--max-box);
            aspect-ratio: 16 / 9;
            margin: 16px auto;
            background: #000;
            border-radius: 18px;
            overflow: hidden;
            border: 1px solid #d1d5db;
        }

        .video-wrapper iframe {
            width: 100%;
            height: 100%;
            border: none;
            display: block;
        }

        .info-block {
            max-width: var(--max-box);
            margin: 12px auto 0;
            font-size: 14px;
            color: var(--muted);
        }

        .info-block ul {
            margin-top: 8px;
            padding-left: 18px;
        }

        /* HERO */
        .hero {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 32px;
        }

        .hero-badge {
            background: #ecfdf3;
            border: 1px solid #bbf7d0;
            padding: 4px 10px;
            border-radius: 999px;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            font-size: 11px;
            color: #166534;
        }

        .hero-badge-dot {
            width: 18px;
            height: 18px;
            border-radius: 50%;
            background: radial-gradient(circle, #22c55e, #15803d);
        }

        .hero-title {
            font-size: clamp(32px, 4vw, 44px);
            font-weight: 800;
            margin: 10px 0;
        }

        .hero-title span {
            background: linear-gradient(120deg, #16a34a, #2563eb);
            -webkit-background-clip: text;
            color: transparent;
        }

        .hero-subtitle {
            color: var(--muted);
            max-width: 520px;
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
            background: #ecfdf3;
            border: 1px solid #bbf7d0;
            color: #166534;
            font-size: 12px;
        }

        .chip-strong {
            background: #16a34a;
            border-color: #16a34a;
            color: #ecfdf3;
        }

        .btn-row {
            display: flex;
            gap: 10px;
            margin: 8px 0 6px;
            flex-wrap: wrap;
        }

        .btn-primary {
            padding: 10px 18px;
            background: linear-gradient(135deg, #2563eb, #1d4ed8);
            border-radius: 999px;
            border: none;
            color: #eff6ff;
            font-weight: 600;
            cursor: pointer;
        }

        .btn-primary:hover {
            transform: translateY(-1px);
        }

        .hero-note {
            font-size: 11px;
            color: var(--muted);
        }

        .hero-right {
            background: white;
            padding: 16px;
            border-radius: 20px;
            border: 1px solid var(--border-soft);
            box-shadow: var(--shadow);
        }

        .hero-right h3 {
            margin-top: 0;
            font-size: 15px;
        }

        .hero-right p {
            font-size: 13px;
            color: var(--muted);
        }

        /* FUNKTIONS-SECTION */
        .funktion-list {
            margin-top: 6px;
            padding-left: 18px;
            color: var(--muted);
            font-size: 14px;
        }

        footer {
            margin-top: 30px;
            text-align: center;
            color: var(--muted);
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
<div class="container">

    <!-- HEADER -->
    <header>
        <div class="logo">
            <div class="logo-icon">P</div>
            <div>
                <div class="logo-text-title">ParkEase</div>
                <div class="logo-text-sub">Parkplätze teilen. Stress sparen.</div>
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
                    src="https://youtu.be/il_ueri6y8s"
                    allow="autoplay; encrypted-media"
                    allowfullscreen>
                </iframe>
            </div>

            <div class="info-block">
                <p>
                    Das Video richtet sich an alle, die in der Stadt unterwegs sind und regelmäßig Zeit mit der Parkplatzsuche verlieren –
                    sowie an Menschen, die ungenutzte Stellplätze haben und daraus eine kleine Einnahmequelle machen möchten.
                </p>
                <ul>
                    <li><strong>Zielgruppe:</strong> Pendler, Studierende, Innenstadtbewohner und private Stellplatzbesitzer.</li>
                    <li><strong>Mehrwert:</strong> Weniger Suchverkehr, weniger Stress, besser genutzter Parkraum.</li>
                    <li><strong>Call-to-Action:</strong> Wer Interesse an der Idee oder am Projekt hat, kann direkt einen Termin mit dem Team vereinbaren.</li>
                </ul>
                <p style="margin-top:8px;">
                    Wenn du Fragen zum Konzept, zur Umsetzung oder zu möglichen Erweiterungen hast, kannst du oben rechts im Menü
                    über <strong>„Termin“</strong> direkt einen Slot über Calendly buchen.
                </p>
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
                    <!-- Button führt jetzt DIREKT zu Calendly -->
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
                <p>
                    ParkEase ist eine Konzept-App, die freien Parkraum sichtbar macht. Stellplätze, Einfahrten oder private
                    Parkflächen können kurzfristig freigegeben und von Autofahrern gebucht werden. So entsteht ein
                    smarter, gemeinschaftlich genutzter Parkplatzpool.
                </p>
                <p>
                    Im nächsten Schritt arbeiten wir an Prototyp, Nutzer-Feedback-Runden und einer möglichen Testphase
                    in ausgewählten Stadtvierteln.
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
                <li><strong>Für Vermieter:</strong> Stellplatz anlegen, Zeiten & Preise festlegen, Buchungen verwalten.</li>
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


