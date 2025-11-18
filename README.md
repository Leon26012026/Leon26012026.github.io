# Leon26012026.github.io
<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ParkEase – Intelligente Parkplatz-Sharing-App</title>
    <meta name="description" content="ParkEase ist eine App, mit der private Parkplatzbesitzer ihre freien Stellplätze an Autofahrer vermieten können – effizient, flexibel und nachhaltig.">

    <style>
        :root {
            --bg: #f3f7f4;
            --bg-soft: #e5f3ea;
            --accent: #22c55e;      /* Grün – nachhaltig */
            --accent-soft: #bbf7d0;
            --accent-dark: #15803d;
            --text: #111827;
            --muted: #6b7280;
            --card: #ffffff;
            --border-soft: #d1d5db;
            --radius: 16px;
            --shadow: 0 18px 40px rgba(15, 23, 42, 0.08);
            --spacing: 18px;
        }

        * {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
            background: radial-gradient(circle at top, #e0f7ec 0, #f9fafb 55%, #eef2ff 100%);
            color: var(--text);
            line-height: 1.5;
        }

        a {
            color: inherit;
            text-decoration: none;
        }

        .container {
            max-width: 1080px;
            margin: 0 auto;
            padding: 24px 18px 72px;
        }

        header {
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 16px;
            margin-bottom: 32px;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo-icon {
            width: 40px;
            height: 40px;
            border-radius: 12px;
            background: radial-gradient(circle at 30% 20%, #22c55e, #16a34a);
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 800;
            font-size: 20px;
            color: white;
            box-shadow: 0 10px 25px rgba(22, 163, 74, 0.35);
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
            color: var(--accent-dark);
        }

        .hero {
            display: grid;
            grid-template-columns: minmax(0, 1.2fr) minmax(0, 1fr);
            align-items: center;
            gap: 32px;
            margin-bottom: 40px;
        }

        .hero-badge {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            padding: 4px 10px 4px 4px;
            border-radius: 999px;
            background: #ecfdf3;
            border: 1px solid #bbf7d0;
            color: #15803d;
            font-size: 11px;
            margin-bottom: 12px;
        }

        .hero-badge-dot {
            width: 20px;
            height: 20px;
            border-radius: 999px;
            background: radial-gradient(circle at 30% 20%, #22c55e, #16a34a);
            box-shadow: 0 0 12px rgba(34, 197, 94, 0.7);
        }

        .hero-title {
            font-size: clamp(30px, 4vw, 40px);
            font-weight: 800;
            line-height: 1.1;
            margin-bottom: 12px;
        }

        .hero-title span {
            background: linear-gradient(120deg, #22c55e, #0ea5e9);
            -webkit-background-clip: text;
            color: transparent;
        }

        .hero-subtitle {
            font-size: 15px;
            color: var(--muted);
            max-width: 520px;
            margin-bottom: 20px;
        }

        .hero-highlight {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            font-size: 12px;
            margin-bottom: 22px;
        }

        .chip {
            padding: 5px 11px;
            border-radius: 999px;
            background: #ecfdf3;
            border: 1px solid #bbf7d0;
            color: #15803d;
        }

        .chip-strong {
            background: #22c55e;
            border-color: #22c55e;
            color: #ecfdf3;
        }

        .hero-actions {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-bottom: 16px;
        }

        .btn-primary {
            padding: 10px 18px;
            border-radius: 999px;
            border: none;
            background: linear-gradient(135deg, #22c55e, #16a34a);
            color: #ecfdf3;
            font-weight: 600;
            font-size: 14px;
            cursor: pointer;
            box-shadow: 0 12px 30px rgba(22, 163, 74, 0.45);
        }

        .btn-primary:hover {
            transform: translateY(-1px);
        }

        .btn-ghost {
            padding: 9px 16px;
            border-radius: 999px;
            background: #ffffff;
            border: 1px solid var(--border-soft);
            color: var(--muted);
            font-size: 14px;
            cursor: pointer;
        }

        .btn-ghost:hover {
            border-color: #22c55e;
            color: #15803d;
        }

        .hero-note {
            font-size: 11px;
            color: var(--muted);
        }

        .hero-right {
            background: #ffffff;
            border: 1px solid #d1fae5;
            border-radius: 24px;
            padding: 14px;
            box-shadow: var(--shadow);
        }

        .hero-card {
            border-radius: 18px;
            padding: 14px;
            background: linear-gradient(160deg, #ecfdf3, #ffffff);
        }

        .hero-card-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 11px;
            color: var(--muted);
            margin-bottom: 10px;
        }

        .hero-card-title {
            font-size: 13px;
            font-weight: 600;
            color: var(--text);
        }

        .map-placeholder {
            border-radius: 14px;
            background: linear-gradient(135deg, #bbf7d0, #22c55e);
            padding: 2px;
            margin-bottom: 10px;
        }

        .map-inner {
            border-radius: 12px;
            background: #ffffff;
            padding: 10px;
            min-height: 150px;
            display: grid;
            grid-template-columns: repeat(3, minmax(0, 1fr));
            gap: 6px;
        }

        .map-slot {
            border-radius: 8px;
            background: #f3f4f6;
            border: 1px dashed #d1d5db;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 11px;
            color: var(--muted);
        }

        .map-slot.free {
            border-style: solid;
            border-color: #22c55e;
            background: #ecfdf3;
            color: #166534;
        }

        .hero-card-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 11px;
            color: var(--muted);
        }

        .hero-card-badge {
            padding: 4px 8px;
            border-radius: 999px;
            background: #ecfdf3;
            border: 1px solid #22c55e;
            color: #166534;
            font-weight: 500;
        }

        main {
            display: grid;
            grid-template-columns: minmax(0, 1.3fr) minmax(0, 1fr);
            gap: 26px;
        }

        section {
            background: var(--card);
            border-radius: var(--radius);
            padding: var(--spacing);
            border: 1px solid var(--border-soft);
            box-shadow: var(--shadow);
        }

        h2 {
            font-size: 18px;
            margin: 0 0 10px;
            color: var(--text);
        }

        .section-subtitle {
            font-size: 13px;
            color: var(--muted);
            margin-bottom: 12px;
        }

        .grid-two {
            display: grid;
            grid-template-columns: repeat(2, minmax(0, 1fr));
            gap: 10px;
        }

        .card-soft {
            background: #f9fafb;
            border-radius: 12px;
            padding: 10px;
            border: 1px solid #e5e7eb;
            font-size: 13px;
        }

        .card-soft h3 {
            font-size: 13px;
            margin: 0 0 6px;
            color: var(--text);
        }

        ul {
            padding-left: 18px;
            margin: 6px 0 0;
            font-size: 13px;
            color: var(--muted);
        }

        li {
            margin-bottom: 4px;
        }

        .video-wrapper {
            aspect-ratio: 16 / 9;
            border-radius: 14px;
            overflow: hidden;
            border: 1px solid #e5e7eb;
            background: #000;
            margin-top: 10px;
        }

        .video-wrapper iframe {
            width: 100%;
            height: 100%;
            border: 0;
        }

        .cta-box {
            background: linear-gradient(135deg, #ecfdf3, #ffffff);
            border-radius: 12px;
            padding: 12px;
            border: 1px solid #bbf7d0;
            margin-top: 10px;
            font-size: 13px;
        }

        .cta-box strong {
            color: #166534;
        }

        .cta-button {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            margin-top: 8px;
            padding: 7px 14px;
            border-radius: 999px;
            border: none;
            background: #22c55e;
            color: #ecfdf3;
            font-weight: 600;
            font-size: 13px;
            cursor: pointer;
        }

        .cta-button span {
            margin-left: 6px;
        }

        .cta-button:hover {
            background: #16a34a;
        }

        footer {
            margin-top: 26px;
            font-size: 11px;
            color: var(--muted);
            text-align: center;
        }

        @media (max-width: 880px) {
            .hero, main {
                grid-template-columns: minmax(0, 1fr);
            }
        }

        @media (max-width: 640px) {
            header {
                flex-direction: column;
                align-items: flex-start;
            }
        }
    </style>
</head>

<body>
<div class="container">
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
            <a href="#funktion">Wie es funktioniert</a>
            <a href="#video">Pitch-Video</a>
            <a href="#termin">Termin buchen</a>
        </nav>
    </header>

    <section class="hero" id="idee">
        <div>
            <div class="hero-badge">
                <div class="hero-badge-dot"></div>
                <span>Startup-Projekt · MVP-Phase</span>
            </div>

            <h1 class="hero-title">
                Finde deinen Parkplatz in <span>Sekunden</span> – statt in Runden.
            </h1>

            <p class="hero-subtitle">
                ParkEase verbindet Autofahrer mit privaten Parkplatzbesitzern. So wird aus leeren Stellplätzen
                ein smartes Sharing-Netzwerk – für weniger Suchverkehr, mehr Zeit und ein entspanntes Ankommen.
            </p>

            <div class="hero-highlight">
                <div class="chip chip-strong">Weniger Stau & CO₂</div>
                <div class="chip">Zusatzeinnahmen für Vermieter</div>
                <div class="chip">Sichere Buchung & Bezahlung</div>
            </div>

            <div class="hero-actions">
                <a href="#termin">
                    <button class="btn-primary">Jetzt Termin mit dem Projektteam buchen</button>
                </a>
                <a href="#video">
                    <button class="btn-ghost">Pitch-Video ansehen</button>
                </a>
            </div>

            <div class="hero-note">
                MVP-Umsetzung im Rahmen eines Hochschulprojekts · Geplanter Launch: Januar 2026
            </div>
        </div>

        <div class="hero-right">
            <div class="hero-card">
                <div class="hero-card-header">
                    <div>
                        <div class="hero-card-title">Live-Parkplätze in deiner Stadt</div>
                        <div>ParkEase – App-Mockup (Konzept)</div>
                    </div>
                    <div class="hero-card-badge">Beta</div>
                </div>

                <div class="map-placeholder">
                    <div class="map-inner">
                        <div class="map-slot">Belegt</div>
                        <div class="map-slot free">Frei • 3,50 €</div>
                        <div class="map-slot">Belegt</div>
                        <div class="map-slot free">Frei • 2 Min.</div>
                        <div class="map-slot">Belegt</div>
                        <div class="map-slot free">Frei • privat</div>
                    </div>
                </div>

                <div class="hero-card-footer">
                    <span>Suche · Reservieren · Bezahlen – alles in einer App</span>
                    <span>ParkEase · v0.1 MVP</span>
                </div>
            </div>
        </div>
    </section>

    <main>
        <section id="funktion">
            <h2>Wie ParkEase funktioniert</h2>
            <p class="section-subtitle">
                Für Autofahrer ist ParkEase die schnellste Abkürzung zum Parkplatz. Für Besitzer wird der Stellplatz zur nachhaltigen Einnahmequelle.
            </p>

            <div class="grid-two">
                <div class="card-soft">
                    <h3>Für Autofahrer</h3>
                    <ul>
                        <li>Freie Parkplätze in Echtzeit finden.</li>
                        <li>Preis & Entfernung vergleichen.</li>
                        <li>Reservieren & Navigieren mit einem Klick.</li>
                        <li>Bezahlung direkt per App.</li>
                    </ul>
                </div>

                <div class="card-soft">
                    <h3>Für Vermieter</h3>
                    <ul>
                        <li>Stellplatz stundenweise freigeben.</li>
                        <li>Eigene Preise wählen.</li>
                        <li>Buchungen & Einnahmen im Dashboard.</li>
                        <li>Bewertungen für Vertrauen.</li>
                    </ul>
                </div>
            </div>
        </section>

        <section id="video">
            <h2>Pitch-Video</h2>
            <p class="section-subtitle">
                Kurz und klar: So löst ParkEase das Parkplatzproblem – effizient und nachhaltig.
            </p>

            <div class="video-wrapper">
                <iframe 
                    src="https://www.youtube.com/embed/il_ueri6y8s?autoplay=1&mute=1&controls=0&rel=0&modestbranding=1&playsinline=1&loop=1&playlist=il_ueri6y8s"
                    title="ParkEase Pitch Video"
                    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                    referrerpolicy="strict-origin-when-cross-origin"
                    allow="autoplay; encrypted-media"
                    allowfullscreen>
                </iframe>
            </div>

            <div class="cta-box" id="termin">
                <strong>Direkt mit dem Projektteam sprechen?</strong><br>
                Buche ein kurzes Gespräch über Calendly.
                <br>

                <a href="https://calendly.com/leonbritz0" target="_blank" rel="noopener noreferrer">
                    <button class="cta-button">
                        Termin buchen <span>→</span>
                    </button>
                </a>

                <div style="margin-top: 4px; font-size: 11px; color: var(--muted);">
                    Der Link führt zu unserem öffentlichen Calendly-Kalender.
                </div>
            </div>
        </section>
    </main>

    <footer>
        ParkEase – Konzept im Rahmen eines Hochschulprojekts (MVP).<br>
        Bereitgestellt über <strong>GitHub Pages</strong>.
    </footer>

</div>
</body>
</html>
