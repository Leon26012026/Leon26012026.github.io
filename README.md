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
            --bg: #050816;
            --bg-light: #0f172a;
            --accent: #38bdf8;
            --accent-soft: rgba(56, 189, 248, 0.15);
            --text: #e5e7eb;
            --muted: #9ca3af;
            --card: #020617;
            --radius: 16px;
            --shadow: 0 18px 45px rgba(15, 23, 42, 0.7);
            --spacing: 18px;
        }

        * {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
            background: radial-gradient(circle at top, #1e293b 0, #020617 55%, #000 100%);
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
            background: radial-gradient(circle at 30% 20%, #38bdf8, #0369a1);
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 800;
            font-size: 20px;
            color: white;
            box-shadow: 0 10px 25px rgba(56, 189, 248, 0.45);
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
            color: var(--accent);
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
            background: rgba(15, 23, 42, 0.9);
            border: 1px solid rgba(148, 163, 184, 0.3);
            color: var(--muted);
            font-size: 11px;
            margin-bottom: 12px;
        }

        .hero-badge-dot {
            width: 20px;
            height: 20px;
            border-radius: 999px;
            background: radial-gradient(circle at 30% 20%, #22c55e, #16a34a);
            box-shadow: 0 0 16px rgba(34, 197, 94, 0.7);
        }

        .hero-title {
            font-size: clamp(30px, 4vw, 40px);
            font-weight: 800;
            line-height: 1.1;
            margin-bottom: 12px;
        }

        .hero-title span {
            background: linear-gradient(120deg, #38bdf8, #22c55e);
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
            background: rgba(15, 23, 42, 0.85);
            border: 1px solid rgba(148, 163, 184, 0.4);
            color: var(--muted);
        }

        .chip-strong {
            border-color: rgba(56, 189, 248, 0.7);
            background: var(--accent-soft);
            color: #e0f2fe;
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
            background: linear-gradient(135deg, #38bdf8, #0ea5e9);
            color: #0b1120;
            font-weight: 600;
            font-size: 14px;
            cursor: pointer;
            box-shadow: 0 12px 30px rgba(56, 189, 248, 0.55);
        }

        .btn-primary:hover {
            transform: translateY(-1px);
        }

        .btn-ghost {
            padding: 9px 16px;
            border-radius: 999px;
            background: rgba(15, 23, 42, 0.85);
            border: 1px solid rgba(148, 163, 184, 0.5);
            color: var(--muted);
            font-size: 14px;
            cursor: pointer;
        }

        .hero-note {
            font-size: 11px;
            color: var(--muted);
        }

        .hero-right {
            background: linear-gradient(145deg, rgba(15, 23, 42, 0.9), rgba(15, 23, 42, 0.2));
            border: 1px solid rgba(148, 163, 184, 0.25);
            border-radius: 24px;
            padding: 14px;
            box-shadow: var(--shadow);
        }

        .hero-card {
            border-radius: 18px;
            padding: 14px;
            background: radial-gradient(circle at top left, rgba(56, 189, 248, 0.14), #020617);
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
        }

        .map-placeholder {
            border-radius: 14px;
            background: conic-gradient(from 180deg at 50% 50%, #0f172a, #1d4ed8, #22c55e, #0f172a);
            padding: 2px;
            margin-bottom: 10px;
        }

        .map-inner {
            border-radius: 12px;
            background: radial-gradient(circle at top, #0b1120, #020617);
            padding: 10px;
            min-height: 150px;
            display: grid;
            grid-template-columns: repeat(3, minmax(0, 1fr));
            gap: 6px;
        }

        .map-slot {
            border-radius: 8px;
            background: rgba(15, 23, 42, 0.95);
            border: 1px dashed rgba(148, 163, 184, 0.5);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 11px;
            color: var(--muted);
        }

        .map-slot.free {
            border-style: solid;
            border-color: rgba(34, 197, 94, 0.9);
            background: radial-gradient(circle at top left, rgba(22, 163, 74, 0.3), rgba(15, 23, 42, 0.95));
            color: #bbf7d0;
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
            background: rgba(15, 23, 42, 0.95);
            border: 1px solid rgba(56, 189, 248, 0.6);
            color: #e0f2fe;
        }

        main {
            display: grid;
            grid-template-columns: minmax(0, 1.3fr) minmax(0, 1fr);
            gap: 26px;
        }

        section {
            background: rgba(15, 23, 42, 0.95);
            border-radius: var(--radius);
            padding: var(--spacing);
            border: 1px solid rgba(15, 23, 42, 0.95);
            box-shadow: 0 16px 40px rgba(15, 23, 42, 0.8);
        }

        h2 {
            font-size: 18px;
            margin: 0 0 10px;
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
            background: rgba(15, 23, 42, 0.9);
            border-radius: 12px;
            padding: 10px;
            border: 1px solid rgba(51, 65, 85, 0.9);
            font-size: 13px;
        }

        ul {
            padding-left: 18px;
            margin: 6px 0 0;
            font-size: 13px;
            color: var(--muted);
        }

        .video-wrapper {
            aspect-ratio: 16 / 9;
            border-radius: 14px;
            overflow: hidden;
            border: 1px solid rgba(148, 163, 184, 0.6);
            background: radial-gradient(circle at top, #020617, #020617);
            margin-top: 10px;
        }

        .cta-box {
            background: radial-gradient(circle at top left, rgba(56, 189, 248, 0.18), rgba(15, 23, 42, 0.98));
            border-radius: 12px;
            padding: 12px;
            border: 1px solid rgba(56, 189, 248, 0.7);
            margin-top: 10px;
            font-size: 13px;
        }

        .cta-button {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            margin-top: 8px;
            padding: 7px 14px;
            border-radius: 999px;
            border: none;
            background: white;
            color: #0f172a;
            font-weight: 600;
            font-size: 13px;
            cursor: pointer;
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
                        <div>ParkEase – App Mockup</div>
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
                Für Autofahrer ist ParkEase die schnellste Abkürzung zum Parkplatz. Für Besitzer wird der Stellplatz zur Einnahmequelle.
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
                Kurz und klar: So löst ParkEase das Parkplatzproblem.
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
