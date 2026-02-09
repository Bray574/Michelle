<html lang="de">
<head>
    <meta charset="UTF-8">
    <title>Be My Valentine?</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #fff0f3;
            text-align: center;
            overflow: hidden; /* Verhindert Scrollbalken */
        }

        h1 {
            color: #ff4d6d;
            font-size: 2.5rem;
            margin-bottom: 30px;
            user-select: none;
        }

        .container {
            position: relative;
            width: 400px;
            height: 100px;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        /* Gemeinsame feste Größe für beide Buttons */
        .btn {
            width: 130px;
            height: 55px;
            font-size: 1.2rem;
            font-weight: bold;
            border-radius: 50px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            box-sizing: border-box;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            position: absolute; /* Beide absolut im Container */
        }

        #yesBtn {
            background-color: #ff4d6d;
            color: white;
            border: none;
            left: 50px; /* Startposition Ja */
        }

        #noBtn {
            background-color: #ffffff;
            color: #ff4d6d;
            border: 2px solid #ff4d6d;
            right: 50px; /* Startposition Nein */
            z-index: 999;
            transition: none; /* Kein gleiten, sondern sofortiger Sprung */
        }
    </style>
</head>
<body>

    <h1>Hola Bebé, quieres ser mi Valentín? ❤️</h1>
    
    <div class="container">
        <button id="yesBtn" class="btn" onclick="celebrate()">Si!</button>
        <button id="noBtn" class="btn">No</button>
    </div>

    <script>
        const noBtn = document.getElementById('noBtn');

        function moveButton() {
            // Berechnet den verfügbaren Platz im Fenster
            // Wir ziehen die Button-Größe ab, damit er nicht aus dem Rand ragt
            const maxX = window.innerWidth - 130; 
            const maxY = window.innerHeight - 55;

            // Erzeugt komplett neue Zufallspositionen
            const randomX = Math.floor(Math.random() * maxX);
            const randomY = Math.floor(Math.random() * maxY);

            // Ändert die Position auf 'fixed', damit er überall hinspringen kann
            noBtn.style.position = 'fixed';
            noBtn.style.left = randomX + 'px';
            noBtn.style.top = randomY + 'px';
        }

        // Event-Listener für Maus und Klickversuche
        noBtn.addEventListener('mouseenter', moveButton);
        noBtn.addEventListener('click', moveButton);
    </script>

    <script>
        function celebrate() {
            document.body.innerHTML = `
                <h1 style="color: #ff4d6d;">❤️ Lo sabía!😋 Te amo mi Amorcito! ❤️</h1>
                <p style="font-size: 60px;">🌹✨🥂🥰</p>
                <p style="font-family: sans-serif; color: #ff4d6d;">Tengo muchas ganas de verte!</p>
            `;
        }
    </script>
</body>
</html>
