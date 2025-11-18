# Leon26012026.github.io
<!DOCTYPE html>
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
            --accent-blue: #0ea5e9;
            --text: #0f172a;
            --muted: #6b7280;
            --card: #ffffff;
            --border-soft: #d1d5db;
            --radius: 16px;
            --shadow: 0 18px 40px rgba(0,0,0,0.08);
            --max-box: 880px; /* gleiche Größe für Video und CTA */
        }

        * { box-sizing: border-box; }
        body {
            margin: 0;
            font-family: system-ui, sans-serif;
            background: radial-gradient(circle at top, #e0efff 0, #f2f7f5 40%, #ecfdf3 100%);
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
            margin-bottom: 32px;
        }

        .logo { display: flex; align-items: center; gap: 10px; }

        .logo-icon {
            width: 42px; height: 42px;
            border-radius: 12px;
            background: radial-gradient(circle at 30% 20%, #22c55e, #15803d);
            display: flex; justify-content: center; align-items: center;
            color: white; font-size: 20px; font-weight: 800;
            box-shadow: 0 10px 25px rgba(22, 163, 74, 0.3);
        }

        nav { display: flex; gap: 18px; color: var(--muted); }
        nav a:hover { color: var(--accent-blue); }

        /* HERO */
        .hero {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 32px;
            margin-bottom: 30px;
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
            width: 18px; height: 18px;
            border-radius: 50%;
            background: radial-gradient(circle, #22c55e, #15803d);
        }

        .hero-title {
            font-size: clamp(32px, 4vw, 44px);
            font-weight: 800;
            margin: 10px 0;
        }

        .hero-title span {
            background: linear-gradient(120deg, #16a34a, #0ea5e9);
            -webkit-background-clip: text;
            color: transparent;
        }

        .hero-subtitle { color: var(--muted); max-width: 520px; }

        .hero-highlight { display: flex; gap: 10px; margin: 16px 0; }
        .chip {
            padding: 6px 12px;
            border-radius: 999px;
            background: #ecfdf3;
            border: 1px solid #bbf7d0;
            color: #166534;
            font-size: 12px;
        }
        .chip-strong {
            background: #16a34a; border-color: #16a34a; color: #ecfdf3;
        }

        .btn-primary {
            padding: 10px 18px;
            background: linear-gradient(135deg, #16a34a, #22c55e);
            border-radius: 999px;
            border: none;
            color: #ecfdf3;
            font-weight: 600;
            cursor: pointer;
        }

        .btn-ghost {
            padding: 9px 16px;
            border-radius: 999px;
            border: 1px solid var(--border-soft);
            background: white;
            color: var(--muted);
            cursor: pointer;
        }
        .btn-ghost:hover { border-color: #0ea5e9; }

        .hero-right {
            background: white;
            padding: 16px;
            border-radius: 20px;
            border: 1px solid #d1fae5;
            box-shadow: var(--shadow);
        }

        /* HAUPTTEIL */
        main { margin-top: 20px; display: block; }

        section {
            background: var(--card);
            border-radius: var(--radius);
            padding: 22px;
            margin-bottom: 22px;
            border: 1px solid var(--border-soft);
            box-shadow: var(--shadow);
        }

        h2 { margin: 0 0 12px; font-size: 20px; }
        .section-subtitle { color: var(--muted); margin-bottom: 14px; }

        /* VIDEO — exakt so groß wie CTA → 880px */
        .video-wrapper {
            width: 100%;
            max-width: var(--max-box);
            aspect-ratio: 16 / 9;
            margin: 16px auto;
            background: black;
            border-radius: 18px;
            overflow: hidden;
            border: 1px solid #d1d5db;
        }

        .video-wrapper iframe {
            width: 100%; height: 100%; border: none;
        }

        /* CTA BOX */
        .cta-box {
            max-width: var(--max-box);
            margin: 16px auto 0;
            background: linear-gradient(135deg, #ecfdf3, #ffffff);
            border: 1px solid #bbf7d0;
            border-radius: 14px;
            padding: 16px;
            box-shadow: var(--shadow);
        }

        .cta-button {
            margin-top: 10px;
            padding: 8px 16px;
            background: #16a34a;
            border-radius: 999px;
            border: none;
            color: white;
            font-weight: 600;
            cursor: pointer;
        }

        footer {
            margin-top: 30px;
            text-align: center;
            color: var(--muted);
            font-size: 12px;
        }

        @media (max-width: 880px) {
            .hero { grid-template-columns: 1fr; text-align: center; }
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
            <a href="#termin">Termin</a>
        </nav>
    </header>

    <!-- HERO -->
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
                ParkEase verbindet Autofahrer mit privaten Stellplatzanbietern.
                Schnell, effizient und nachhaltig.
            </p>

            <div class="hero-highlight">
                <div class="chip chip-strong">Weniger CO₂</div>
                <div class="chip">Einnahmen für Vermieter</div>
                <div class="chip">Sichere Bezahlung</div>
            </div>

            <a href="#termin"><button class="btn-primary">Termin mit dem Team buchen</button></a>
        </div>

        <div class="hero-right">
            <strong>App-Mockup · Konzeptvorschau</strong>
            <p style="color: var(--muted); font-size: 13px; margin-top: 6px;">
                Reservieren, buchen & bezahlen – alles in einer App.
            </p>
        </div>
    </section>

    <!-- VIDEO – groß und mittig -->
    <main>
        <section id="video">
            <h2 style="text-align:center;">Pitch-Video</h2>
            <p class="section-subtitle" style="text-align:center;">
                Unser Projekt in nur 30 Sekunden erklärt.
            </p>

            <div class="video-wrapper">
                <iframe
                    src="https://www.youtube.com/embed/il_ueri6y8s?autoplay=1&mute=1&controls=0&modestbranding=1&loop=1&rel=0&playsinline=1&playlist=il_ueri6y8s"
                    allow="autoplay; encrypted-media"
                    allowfullscreen>
                </iframe>
            </div>

            <!-- CTA BOX -->
            <div class="cta-box" id="termin">
                <strong>Möchtest du mit uns sprechen?</strong><br>
                Buche gerne einen kurzen Termin über Calendly.<br>

                <a href="https://calendly.com/leonbritz0" target="_blank">
                    <button class="cta-button">Termin buchen →</button>
                </a>

                <p style="font-size:11px; color:var(--muted); margin-top:6px;">
                    Der Link führt zu unserem öffentlichen Kalender.
                </p>
            </div>
        </section>

        <!-- FUNKTION -->
        <section id="funktion">
            <h2>Wie ParkEase funktioniert</h2>
            <p class="section-subtitle">
                Einfach für Fahrer – transparent für Vermieter.
            </p>

            <ul>
                <li>Fahrer finden freie Parkplätze in Echtzeit.</li>
                <li>Vermieter stellen Stellplätze flexibel zur Verfügung.</li>
                <li>Navigation & Zahlung direkt in der App.</li>
            </ul>
        </section>
    </main>

    <footer>
        ParkEase – Hochschulprojekt (MVP). Bereitgestellt über GitHub Pages.
    </footer>

</div>
</body>
</html>

