- 👋 Hi, I’m @Arjunrayhod
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
Arjunrayhod/Arjunrayhod is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Subway Princess Game</title>
    <style>
        body {
            font-family: Arial, sans-serif;
        }

        #gameArea {
            width: 100%;
            height: 400px;
            background-color: #87CEEB;
            position: relative;
            overflow: hidden;
        }

        .character {
            width: 50px;
            height: 50px;
            position: absolute;
            bottom: 10px;
            background-color: #FF6347;
        }

        .boy {
            background-color: #00BFFF;
        }

        #startScreen {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 24px;
            text-align: center;
            color: #FFFFFF;
        }
    </style>
</head>
<body>

    <div id="startScreen">
        <h1>Welcome to Subway Princess Game!</h1>
        <h2>Arjun Rathod</h2>
        <p>Click anywhere to start the game!</p>
    </div>

    <div id="gameArea">
        <div id="player" class="character"></div>
        <div id="boy1" class="character boy"></div>
        <div id="boy2" class="character boy"></div>
    </div>

    <script>
        const gameArea = document.getElementById('gameArea');
        const player = document.getElementById('player');
        const boy1 = document.getElementById('boy1');
        const boy2 = document.getElementById('boy2');
        const startScreen = document.getElementById('startScreen');

        // Position the player and boys before the game starts
        function setInitialPositions() {
            player.style.left = '50px'; // Start position of Arjun
            boy1.style.left = '120px'; // Position of first boy
            boy2.style.left = '190px'; // Position of second boy
        }

        // Start the game when the user clicks
        document.addEventListener('click', () => {
            startScreen.style.display = 'none'; // Hide start screen
            setInitialPositions();
            startGame();
        });

        function startGame() {
            let playerPosX = 50;
            let boy1PosX = 120;
            let boy2PosX = 190;

            const speed = 5; // Speed of the game

            // Game loop
            setInterval(() => {
                playerPosX += speed;
                boy1PosX += speed;
                boy2PosX += speed;

                player.style.left = playerPosX + 'px';
                boy1.style.left = boy1PosX + 'px';
                boy2.style.left = boy2PosX + 'px';

                // Reset positions when they go out of screen
                if (playerPosX > gameArea.offsetWidth) {
                    playerPosX = -50; // Reset to the left
                }

                if (boy1PosX > gameArea.offsetWidth) {
                    boy1PosX = -50; // Reset to the left
                }

                if (boy2PosX > gameArea.offsetWidth) {
                    boy2PosX = -50; // Reset to the left
                }
            }, 100); // Refresh game every 100ms
        }
    </script>

</body>
</html>
