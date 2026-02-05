<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <title>Tokyo Neon Schwarzlicht Minigolf – Klasse 10C</title>
    <link rel="stylesheet" href="10c-minigolf.css">
</head>

<body>

Projekt Logo
Tokyo MiniGolf 10C
Über uns Bahnen Galerie Scoreboard Kontakt

<section class="hero">
    <h2>Tokyo – Altes trifft Neon</h2>
    <p>Eine Schwarzlicht-MiniGolfbahn von der Klasse 10C</p>
    <div class="kanji">東京</div>
</section>

<section id="about" class="section">
    <h2>Über das Projekt</h2>
    <p>
        Wir, die Klasse <strong>10C</strong>, bauen eine eigene Schwarzlicht-Minigolfbahn zum Thema 
        <strong>„Tokyo“</strong>.  
        Neon, Cyberpunk, alte Tempel, moderne Stadt – alles vereint in einem leuchtenden Erlebnis.
    </p>
</section>

<section id="courses" class="section">
    <h2>Unsere Bahnen</h2>

    <div class="course-grid">
        <div class="course">
            <h3>❖ Name 1 </h3>
            <p>Beschreibung 1.</p>
        </div>

        <div class="course">
            <h3>❖ Name 2 </h3>
            <p>Beschreibung 2.</p>
        </div>

        <div class="course">
            <h3>❖ Name 3 </h3>
            <p>Beschreibung 3.</p>
        </div>

        <div class="course">
            <h3>❖ Name 4</h3>
            <p>Beschreibung 4.</p>
        </div>
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
                    <th>R1</th>
                    <th>R2</th>
                    <th>R3</th>
                    <th>R4</th>
                    <th>R5</th>
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
                <tr>
                    <td contenteditable="true">Spieler 2</td>
                    <td contenteditable="true">0</td>
                    <td contenteditable="true">0</td>
                    <td contenteditable="true">0</td>
                    <td contenteditable="true">0</td>
                    <td contenteditable="true">0</td>
                    <td contenteditable="true">0</td>
                </tr>
                <tr>
                    <td contenteditable="true">Spieler 3</td>
                    <td contenteditable="true">0</td>
                    <td contenteditable="true">0</td>
                    <td contenteditable="true">0</td>
                    <td contenteditable="true">0</td>
                    <td contenteditable="true">0</td>
                    <td contenteditable="true">0</td>
                </tr>
                <tr>
                    <td contenteditable="true">Spieler 4</td>
                    <td contenteditable="true">0</td>
                    <td contenteditable="true">0</td>
                    <td contenteditable="true">0</td>
                    <td contenteditable="true">0</td>
                    <td contenteditable="true">0</td>
                    <td contenteditable="true">0</td>
                </tr>
            </tbody>
        </table>

        <button id="addRowBtn" class="neon-btn">➕ Spieler hinzufügen</button>
        <button id="saveScoreBtn" class="neon-btn">💾 Speichern</button>
        <button id="resetScoreBtn" class="neon-btn danger">✖ Zurücksetzen</button>
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
    <p>Bei Fragen zum Projekt oder zur Präsentation:</p>
    <p><strong>Klasse 10C – Schulprojekt Tokyo Minigolf</strong></p>
</section>

<footer class="footer">
    <p>© 2025 – Klasse 10C </p>
</footer>

<script>
document.getElementById("addRowBtn").onclick = () => {
    const row = document.createElement("tr");
    row.innerHTML = `
        <td contenteditable="true">Neuer Spieler</td>
        <td contenteditable="true">0</td>
        <td contenteditable="true">0</td>
        <td contenteditable="true">0</td>
        <td contenteditable="true">0</td>
    `;
    document.getElementById("scoreBody").appendChild(row);
};

document.getElementById("saveScoreBtn").onclick = () => {
    localStorage.setItem("scoreboard", document.getElementById("scoreBody").innerHTML);
    alert("Scoreboard gespeichert!");
};

window.onload = () => {
    const saved = localStorage.getItem("scoreboard");
    if (saved) document.getElementById("scoreBody").innerHTML = saved;
};

document.getElementById("resetScoreBtn").onclick = () => {
    if (confirm("Scoreboard wirklich zurücksetzen?")) {
        localStorage.removeItem("scoreboard");
        location.reload();
    }
};
</script>

</body>
</html>
