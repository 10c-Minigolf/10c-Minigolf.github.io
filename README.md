<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tokyo Neon Schwarzlicht Minigolf – Klasse 10C</title>

    <!-- CSS einbinden -->
    <link rel="stylesheet" href="style.css">
</head>

<body>
<div class="page-wrapper">

<header class="header">
    <div class="logo">Tokyo MiniGolf 10C</div>
    <nav class="nav">
        <a href="#about">Über uns</a>
        <a href="#courses">Bahnen</a>
        <a href="#gallery">Galerie</a>
        <a href="#scoreboard">Scoreboard</a>
        <a href="#contact">Kontakt</a>
    </nav>
</header>

<section class="hero">
    <h2>Tokyo – Altes trifft Neon</h2>
    <p>Eine Schwarzlicht-MiniGolfbahn von der Klasse 10C</p>
    <div class="kanji">東京</div>
</section>

<section id="about" class="section">
    <h2>Über das Projekt</h2>
    <p>
        Wir, die Klasse <strong>10C</strong>, bauen eine eigene Schwarzlicht-Minigolfbahn
        zum Thema <strong>Tokyo</strong>.
    </p>
</section>

<section id="courses" class="section">
    <h2>Unsere Bahnen</h2>
    <div class="course-grid">
        <div class="course"><h3>❖ Name 1</h3><p>Beschreibung</p></div>
        <div class="course"><h3>❖ Name 2</h3><p>Beschreibung</p></div>
        <div class="course"><h3>❖ Name 3</h3><p>Beschreibung</p></div>
        <div class="course"><h3>❖ Name 4</h3><p>Beschreibung</p></div>
    </div>
</section>

<section id="scoreboard" class="section">
    <h2>Scoreboard</h2>
    <div class="scoreboard-container">
        <table class="scoreboard-table">
            <thead>
                <tr>
                    <th>Spieler</th>
                    <th>Punkte</th>
                    <th>R1</th><th>R2</th><th>R3</th><th>R4</th><th>R5</th>
                </tr>
            </thead>
            <tbody id="scoreBody">
                <tr>
                    <td contenteditable="true">Spieler 1</td>
                    <td contenteditable="true">0</td>
                    <td contenteditable="true">0</td>
                    <td contenteditable="true">0</td>
                    <td contenteditable="true">0</td>
                    <td contenteditable="true">0</td>
                    <td contenteditable="true">0</td>
                </tr>
            </tbody>
        </table>

        <button id="addRowBtn" class="neon-btn">➕ Spieler</button>
        <button id="saveScoreBtn" class="neon-btn">💾 Speichern</button>
        <button id="resetScoreBtn" class="neon-btn danger">✖ Reset</button>
    </div>
</section>

<section id="gallery" class="section">
    <h2>Galerie</h2>
    <div class="gallery-grid">
        <div class="img-placeholder">Bild 1</div>
        <div class="img-placeholder">Bild 2</div>
        <div class="img-placeholder">Bild 3</div>
        <div class="img-placeholder">Bild 4</div>
    </div>
</section>

<section id="contact" class="section">
    <h2>Kontakt</h2>
    <p><strong>Klasse 10C – Schulprojekt Tokyo Minigolf</strong></p>
</section>

<footer class="footer">
    <p>© 2025 – Klasse 10C</p>
</footer>

</div>

<script>
const scoreBody = document.getElementById("scoreBody");

document.getElementById("addRowBtn").onclick = () => {
    const row = document.createElement("tr");
    row.innerHTML = `
        <td contenteditable="true">Neuer Spieler</td>
        <td contenteditable="true">0</td>
        <td contenteditable="true">0</td>
        <td contenteditable="true">0</td>
        <td contenteditable="true">0</td>
        <td contenteditable="true">0</td>
        <td contenteditable="true">0</td>
    `;
    scoreBody.appendChild(row);
};

document.getElementById("saveScoreBtn").onclick = () => {
    localStorage.setItem("scoreboard", scoreBody.innerHTML);
    alert("Scoreboard gespeichert!");
};

window.onload = () => {
    const saved = localStorage.getItem("scoreboard");
    if (saved) scoreBody.innerHTML = saved;
};

document.getElementById("resetScoreBtn").onclick = () => {
    if (confirm("Scoreboard zurücksetzen?")) {
        localStorage.removeItem("scoreboard");
        location.reload();
    }
};
</script>

</body>
</html>




/* -------------------------------- */
/* TOKYO NEON CYBERPUNK SCHWARZLICHT */
/* -------------------------------- */

:root {
    --neon-pink: #ff00e1;
    --neon-blue: #00eaff;
    --neon-purple: #b400ff;
    --neon-yellow: #ffe600;
    --dark-bg: #03010f;
    --font-main: 'Verdana', sans-serif;
}

body {
    margin: 0;
    background: var(--dark-bg);
    color: white;
    font-family: var(--font-main);
    display: flex;
    justify-content: center;
}

/* GitHub Pages Breiten-Fix */
.page-wrapper {
    width: 100%;
    max-width: 1400px;
}

/* Glitch Glow */
h1, h2, h3 {
    text-shadow:
        0 0 8px var(--neon-pink),
        0 0 15px var(--neon-blue),
        0 0 25px var(--neon-purple);
    letter-spacing: 2px;
}

/* Header */
.header {
    background: rgba(0,0,0,0.4);
    backdrop-filter: blur(6px);
    text-align: center;
    padding: 15px 0;
    border-bottom: 2px solid var(--neon-purple);
    box-shadow: 0 0 20px var(--neon-purple);
}

.logo {
    font-size: 2.5rem;
    color: var(--neon-pink);
    animation: pulse 2.5s infinite alternate;
}

@keyframes pulse {
    from { text-shadow: 0 0 10px var(--neon-pink); }
    to   { text-shadow: 0 0 25px var(--neon-blue); }
}

.nav a {
    margin: 0 15px;
    color: var(--neon-blue);
    text-decoration: none;
    font-weight: bold;
}

.nav a:hover {
    color: var(--neon-pink);
    text-shadow: 0 0 10px var(--neon-pink);
}

/* Hero */
.hero {
    text-align: center;
    padding: 120px 20px;
    min-height: 80vh;
    background: radial-gradient(circle at center,
        rgba(255,0,200,0.3),
        rgba(0,0,0,0.9)
    );
    display: flex;
    flex-direction: column;
    justify-content: center;
}

.hero h2 {
    font-size: 3rem;
    color: var(--neon-pink);
}

.kanji {
    font-size: 7rem;
    margin-top: 20px;
    color: var(--neon-blue);
    text-shadow:
        0 0 20px var(--neon-blue),
        0 0 40px var(--neon-yellow),
        0 0 60px var(--neon-purple);
}

/* Sections */
.section {
    padding: 80px clamp(20px, 6vw, 120px);
}

/* Courses */
.course-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 25px;
}

.course {
    background: rgba(10,0,30,0.7);
    border: 2px solid var(--neon-purple);
    padding: 20px;
    border-radius: 12px;
    box-shadow: 0 0 25px var(--neon-purple);
}

/* Scoreboard */
.scoreboard-container {
    background: rgba(10,0,30,0.7);
    padding: 30px;
    border-radius: 15px;
    border: 2px solid var(--neon-blue);
    box-shadow: 0 0 25px var(--neon-blue);
}

.scoreboard-table {
    width: 100%;
    border-collapse: collapse;
    color: var(--neon-yellow);
}

.scoreboard-table th,
.scoreboard-table td {
    padding: 12px;
    border-bottom: 1px solid rgba(255,255,255,0.2);
}

[contenteditable="true"]:focus {
    outline: 2px solid var(--neon-blue);
    background: rgba(0,255,255,0.15);
}

/* Buttons */
.neon-btn {
    margin-top: 20px;
    margin-right: 10px;
    padding: 10px 20px;
    background: black;
    border: 2px solid var(--neon-blue);
    color: var(--neon-blue);
    cursor: pointer;
    border-radius: 8px;
}

.neon-btn.danger {
    border-color: var(--neon-pink);
    color: var(--neon-pink);
}

/* Gallery */
.gallery-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 20px;
}

.img-placeholder {
    background: rgba(255,255,255,0.1);
    border: 2px dashed var(--neon-blue);
    text-align: center;
    padding: 60px 0;
}

/* Footer */
.footer {
    text-align: center;
    padding: 20px;
    border-top: 2px solid var(--neon-pink);
    box-shadow: 0 0 20px var(--neon-pink);
}











