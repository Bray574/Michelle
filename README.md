<html lang="de">
<head>
    <meta charset="UTF-8">
    <title>Quieres ser mi Valentin?</title>
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
            overflow: hidden;
        }

        h1 {
            color: #ff4d6d;
            font-size: 2.2rem;
            margin-bottom: 40px;
            padding: 0 20px;
        }

        .container {
            position: relative;
            width: 300px; /* Begrenzt den Startbereich */
            height: 100px;
        }

        .btn {
            /* Fixiert die Größe für beide Buttons identisch */
            width: 100px;
            height: 50px;
            font-size: 1.1rem;
            font-weight: bold;
            border-radius: 25px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            box-sizing: border-box; /* Wichtig für die Rahmengröße */
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            position: absolute;
            transition: none; /* Sofortiger Sprung */
        }

        #yesBtn {
            background-color: #ff4d6d;
            color: white;
            border: none;
            left: 20px;
        }

        #noBtn {
            background-color: #ffffff;
            color: #ff4d6d;
            border: 2px solid #ff4d6d;
            right: 20px;
            z-index: 999;
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
            // Definiert die Button-Größe fest für die Berechnung
            const btnWidth = 100;
            const btnHeight = 50;
            const padding = 20;

            const maxX = window.innerWidth - btnWidth - padding;
            const maxY = window.innerHeight - btnHeight - padding;

            const randomX = Math.max(padding, Math.floor(Math.random() * maxX));
            const randomY = Math.max(padding, Math.floor(Math.random() * maxY));

            // Setzt feste Breite/Höhe direkt im Style, um das "Rechteck-Problem" zu killen
            noBtn.style.position = 'fixed';
            noBtn.style.width = btnWidth + 'px'; 
            noBtn.style.height = btnHeight + 'px';
            noBtn.style.left = randomX + 'px';
            noBtn.style.top = randomY + 'px';
        }

        noBtn.addEventListener('mouseover', moveButton);
        noBtn.addEventListener('touchstart', (e) => {
            e.preventDefault();
            moveButton();
        });
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
