# Chocosopresa-de-galleta
<!-- end list -->
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Para mi San Valentín 🐥</title>
    <link href="https://fonts.googleapis.com/css2?family=Varela+Round&display=swap" rel="stylesheet">
    <style>
        :root {
            --yellow-duck: #FFD93D;
            --orange-beak: #FF8E3C;
            --pink-bg: #FFE5EC;
            --pink-dark: #FF8FAB;
            --white: #FFFFFF;
            --text-color: #594A4E;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            user-select: none; /* Evita que seleccionen el texto al hacer click rápido */
        }

        body {
            font-family: 'Varela Round', sans-serif;
            background: linear-gradient(135deg, #FFF0F3 0%, #FFE5EC 100%);
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden; /* Para que el confetti no estire la pantalla */
            color: var(--text-color);
            position: relative;
        }

        /* --- Fondo Animado --- */
        .bg-hearts {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            z-index: 0;
            pointer-events: none;
            overflow: hidden;
        }

        .bg-heart {
            position: absolute;
            color: rgba(255, 143, 171, 0.2);
            font-size: 2rem;
            animation: floatBackground 10s infinite linear;
        }

        @keyframes floatBackground {
            0% { transform: translateY(110vh) rotate(0deg); opacity: 0; }
            20% { opacity: 1; }
            80% { opacity: 1; }
            100% { transform: translateY(-10vh) rotate(360deg); opacity: 0; }
        }

        /* --- Contenedor Principal --- */
        .container {
            position: relative;
            z-index: 10;
            text-align: center;
            max-width: 90%;
            width: 400px;
        }

        /* --- Pantallas --- */
        .screen {
            transition: opacity 0.5s ease, transform 0.5s ease;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            width: 100%;
        }

        .hidden {
            display: none !important;
            opacity: 0;
            transform: scale(0.9);
        }

        /* --- Arte SVG (Patitos) --- */
        .duck-svg {
            width: 200px;
            height: 200px;
            margin-bottom: 20px;
            filter: drop-shadow(0 4px 6px rgba(0,0,0,0.1));
            animation: bounceDuck 3s infinite ease-in-out;
        }

        @keyframes bounceDuck {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        /* --- Textos --- */
        h1 {
            font-size: 1.8rem;
            color: var(--pink-dark);
            margin-bottom: 30px;
            line-height: 1.4;
        }

        /* --- Botones --- */
        .btn-container {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn {
            background-color: var(--white);
            color: var(--pink-dark);
            border: 2px solid var(--pink-dark);
            padding: 15px 40px;
            font-size: 1.2rem;
            border-radius: 50px;
            cursor: pointer;
            font-family: inherit;
            font-weight: bold;
            box-shadow: 0 4px 10px rgba(255, 143, 171, 0.3);
            transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            outline: none;
            min-width: 120px;
        }

        .btn:hover {
            background-color: var(--pink-dark);
            color: var(--white);
            transform: scale(1.1) rotate(-3deg);
            box-shadow: 0 8px 20px rgba(255, 143, 171, 0.5);
        }

        .btn:nth-child(2):hover {
            transform: scale(1.1) rotate(3deg); /* El otro botón rota al otro lado */
        }

        .btn:active {
            transform: scale(0.95);
        }

        .btn-restart {
            margin-top: 20px;
            font-size: 1rem;
            padding: 10px 25px;
            opacity: 0.8;
        }

        /* --- Animación Confetti (CSS puro + JS trigger) --- */
        .confetti {
            position: absolute;
            top: -10px;
            z-index: 20;
            width: 10px;
            height: 10px;
            background-color: var(--pink-dark);
            animation: fall linear forwards;
        }

        @keyframes fall {
            to { transform: translateY(110vh) rotate(720deg); }
        }

    </style>
</head>
<body>

    <div class="bg-hearts" id="bgHearts"></div>

    <div class="container">
        
        <div id="screen1" class="screen">
            <svg class="duck-svg" viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
                <ellipse cx="100" cy="120" rx="50" ry="45" fill="#FFD93D"/>
                <circle cx="100" cy="85" r="35" fill="#FFD93D"/>
                <circle cx="88" cy="80" r="4" fill="#333"/>
                <circle cx="112" cy="80" r="4" fill="#333"/>
                <circle cx="90" cy="78" r="1.5" fill="#FFF"/> <circle cx="114" cy="78" r="1.5" fill="#FFF"/> <circle cx="75" cy="90" r="5" fill="#FFB7B2" opacity="0.6"/>
                <circle cx="125" cy="90" r="5" fill="#FFB7B2" opacity="0.6"/>
                <ellipse cx="100" cy="95" rx="10" ry="6" fill="#FF8E3C"/>
                <ellipse cx="60" cy="115" rx="15" ry="10" fill="#FFD93D" transform="rotate(-20 60 115)"/>
                <ellipse cx="140" cy="115" rx="15" ry="10" fill="#FFD93D" transform="rotate(20 140 115)"/>
                
                <line x1="135" y1="120" x2="135" y2="150" stroke="#8B4513" stroke-width="3"/>
                <rect x="95" y="30" width="80" height="50" rx="5" fill="#FFF" stroke="#FF8FAB" stroke-width="2" transform="rotate(5 135 55)"/>
                <text x="135" y="55" font-family="arial, sans-serif" font-size="10" fill="#FF8FAB" text-anchor="middle" transform="rotate(5 135 55)">¿Serías mi</text>
                <text x="135" y="70" font-family="arial, sans-serif" font-size="10" fill="#FF8FAB" text-anchor="middle" transform="rotate(5 135 55)">San Valentín?</text>
            </svg>

            <h1>¿Quieres ser mi<br>San Valentín?</h1>
            
            <div class="btn-container">
                <button class="btn" onclick="sayYes()">Sí</button>
                <button class="btn" onclick="sayYes()">Sí</button>
            </div>
        </div>

        <div id="screen2" class="screen hidden">
            <svg class="duck-svg" viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
                <g id="floatingHearts">
                    <path d="M10,10 C10,5 15,5 15,10 C15,5 20,5 20,10 L15,18 L10,10" fill="#FF8FAB">
                        <animateTransform attributeName="transform" type="translate" values="50 50; 50 30; 50 50" dur="2s" repeatCount="indefinite"/>
                    </path>
                    <path d="M170,30 C170,25 175,25 175,30 C175,25 180,25 180,30 L175,38 L170,30" fill="#FF8FAB">
                        <animateTransform attributeName="transform" type="translate" values="0 0; 0 -20; 0 0" dur="2.5s" repeatCount="indefinite"/>
                    </path>
                </g>

                <ellipse cx="100" cy="110" rx="50" ry="45" fill="#FFD93D"/>
                <circle cx="100" cy="75" r="35" fill="#FFD93D"/>
                <path d="M82,75 Q88,68 94,75" stroke="#333" stroke-width="2" fill="none"/>
                <path d="M106,75 Q112,68 118,75" stroke="#333" stroke-width="2" fill="none"/>
                <circle cx="75" cy="85" r="5" fill="#FFB7B2" opacity="0.6"/>
                <circle cx="125" cy="85" r="5" fill="#FFB7B2" opacity="0.6"/>
                <path d="M95,85 Q100,95 105,85" fill="#FF8E3C"/>
                
                <ellipse cx="70" cy="100" rx="15" ry="10" fill="#FFD93D" transform="rotate(-30 70 100)"/>
                <ellipse cx="130" cy="100" rx="15" ry="10" fill="#FFD93D" transform="rotate(30 130 100)"/>
                
                <path d="M100,105 C80,90 70,110 100,140 C130,110 120,90 100,105" fill="#FF5D8F"/>
            </svg>

            <h1>¡Sabía que dirías que sí! 💛</h1>
            
            <button class="btn btn-restart" onclick="restart()">Repetir</button>
        </div>

    </div>

    <script>
        // --- Generar fondo animado ---
        function createBackgroundHearts() {
            const container = document.getElementById('bgHearts');
            const hearts = ['❤', '💛', '💗', '💕'];
            
            for(let i = 0; i < 15; i++) {
                const heart = document.createElement('div');
                heart.classList.add('bg-heart');
                heart.innerHTML = hearts[Math.floor(Math.random() * hearts.length)];
                heart.style.left = Math.random() * 100 + 'vw';
                heart.style.animationDuration = (Math.random() * 5 + 10) + 's'; // Entre 10 y 15s
                heart.style.animationDelay = (Math.random() * 5) + 's';
                container.appendChild(heart);
            }
        }

        createBackgroundHearts();

        // --- Lógica del botón "Sí" ---
        function sayYes() {
            const screen1 = document.getElementById('screen1');
            const screen2 = document.getElementById('screen2');

            // 1. Ocultar pantalla 1
            screen1.style.opacity = '0';
            screen1.style.transform = 'translateY(-20px)';

            setTimeout(() => {
                screen1.classList.add('hidden');
                
                // 2. Mostrar pantalla 2
                screen2.classList.remove('hidden');
                // Pequeño hack para reiniciar la animación CSS
                void screen2.offsetWidth; 
                screen2.style.opacity = '1';
                screen2.style.transform = 'translateY(0)';
                
                // 3. Lanzar confetti
                throwConfetti();
            }, 500);
        }

        // --- Lógica de Reinicio ---
        function restart() {
            const screen1 = document.getElementById('screen1');
            const screen2 = document.getElementById('screen2');

            screen2.style.opacity = '0';
            screen2.style.transform = 'translateY(20px)';

            setTimeout(() => {
                screen2.classList.add('hidden');
                
                screen1.classList.remove('hidden');
                void screen1.offsetWidth;
                screen1.style.opacity = '1';
                screen1.style.transform = 'translateY(0)';
            }, 500);
        }

        // --- Sistema de Confetti ---
        function throwConfetti() {
            const colors = ['#FFD93D', '#FF8FAB', '#FF5D8F', '#FFFFFF'];
            
            for (let i = 0; i < 50; i++) {
                const confetti = document.createElement('div');
                confetti.classList.add('confetti');
                
                // Posición aleatoria
                confetti.style.left = Math.random() * 100 + 'vw';
                
                // Color aleatorio
                confetti.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
                
                // Velocidad aleatoria
                const duration = Math.random() * 2 + 2; // entre 2 y 4s
                confetti.style.animationDuration = duration + 's';
                
                document.body.appendChild(confetti);

                // Limpiar DOM después de la animación
                setTimeout(() => {
                    confetti.remove();
                }, duration * 1000);
            }
        }
    </script>
</body>
</html>
