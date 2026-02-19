<html lang="te">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ugadi 2026 Greetings</title>
    <style>
        :root {
            --primary-gold: #FFD700;
            --deep-red: #8B0000;
            --leaf-green: #228B22;
        }

        body {
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: #fff9e6;
            overflow-x: hidden;
            text-align: center;
        }

        .page {
            display: none;
            height: 100vh;
            width: 100vw;
            position: relative;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }

        .active { display: flex; }

        /* --- Page 1 --- */
        .big-symbol { font-size: 120px; margin-bottom: 20px; }
        .telugu-text { font-size: 2.5rem; color: var(--deep-red); font-weight: bold; margin: 20px; }

        /* --- Page 2: Ugadi Wishes --- */
        .temple { font-size: 100px; z-index: 5; margin: 20px 0; }
        
        .falling {
            position: absolute;
            top: -50px;
            font-size: 30px;
            animation: fall linear infinite;
        }

        @keyframes fall {
            to { transform: translateY(110vh) rotate(360deg); }
        }

        .bird {
            position: absolute;
            font-size: 40px;
            top: 20%;
            animation: fly 6s linear infinite;
        }

        @keyframes fly {
            from { left: -10%; }
            to { left: 110%; }
        }

        /* --- Page 3: Horoscope --- */
        .horoscope-wheel {
            width: 300px;
            height: 300px;
            border-radius: 50%;
            border: 5px solid var(--primary-gold);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 80px;
            cursor: pointer;
            animation: rotate 10s linear infinite;
            background: white;
            box-shadow: 0 0 20px rgba(0,0,0,0.1);
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .wish-popup {
            display: none;
            font-size: 1.5rem;
            color: var(--leaf-green);
            margin-top: 30px;
            font-weight: bold;
            padding: 20px;
            border: 2px dashed var(--primary-gold);
        }

        button {
            padding: 15px 30px;
            font-size: 1.2rem;
            background-color: var(--deep-red);
            color: white;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            box-shadow: 0 4px 10px rgba(0,0,0,0.2);
            transition: 0.3s;
            z-index: 10;
        }

        button:hover { transform: scale(1.1); background-color: #b30000; }
    </style>
</head>
<body>

    <div id="page1" class="page active">
        <div class="big-symbol">🪔</div>
        <div class="telugu-text">విశ్వావసు నామ సంవత్సర శుభాకాంక్షలు</div>
        <button onclick="showPage('page2')">Enter Celebrations</button>
    </div>

    <div id="page2" class="page">
        <div class="big-symbol" style="position: absolute; top: 20px;">🌸</div>
        <div class="bird">🐦‍⬛</div>
        <div class="temple">🛕</div>
        <div class="telugu-text">ఉగాది శుభాకాంక్షలు!</div>
        <button onclick="showPage('page3')">Check Horoscope</button>
    </div>

    <div id="page3" class="page">
        <h2>Click the Wheel for Your Blessing</h2>
        <div class="horoscope-wheel" onclick="revealWish()">
            ♈
        </div>
        <div id="finalWish" class="wish-popup">
            2026 ఉగాది మీకు సకల శుభాలను చేకూర్చాలని కోరుకుంటున్నాము!
        </div>
    </div>

    <script>
        function showPage(pageId) {
            document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
            document.getElementById(pageId).classList.add('active');
            
            if(pageId === 'page2') {
                createFallingItems();
            }
        }

        function createFallingItems() {
            const symbols = ['🥭', '🍃', '🥭', '🍃'];
            for (let i = 0; i < 20; i++) {
                setTimeout(() => {
                    const item = document.createElement('div');
                    item.className = 'falling';
                    item.innerText = symbols[Math.floor(Math.random() * symbols.length)];
                    item.style.left = Math.random() * 100 + 'vw';
                    item.style.animationDuration = (Math.random() * 3 + 2) + 's';
                    document.getElementById('page2').appendChild(item);
                }, i * 300);
            }
        }

        function revealWish() {
            const wheel = document.querySelector('.horoscope-wheel');
            wheel.style.animationPlayState = 'paused';
            document.getElementById('finalWish').style.display = 'block';
        }
    </script>
</body>
</html>
