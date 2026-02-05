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










