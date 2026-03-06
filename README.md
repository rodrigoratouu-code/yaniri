<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Invitación de Cumpleaños - Yaniris </title>

    <!-- Open Graph / WhatsApp -->
    <meta property="og:title" content="🎉 Invitación de Cumpleaños - YANIRI" />
    <meta property="og:description" content="¡Estás invitado! 📅 Sábado 27 de Febrero - 18:00 hs - Barcelona" />
    <meta property="og:image" content="https://rodrigoratouu-code.github.io/yaniri/imagen.webp" />
    <meta property="og:type" content="website" />
    <meta property="og:url" content="https://rodrigoratouu-code.github.io/yaniri/" />

    <!-- Twitter Card -->
    <meta name="twitter:card" content="summary_large_image" />
    <meta name="twitter:title" content="🎉 Invitación de Cumpleaños - YANIRI" />
    <meta name="twitter:description" content="¡Estás invitado! 📅 Sábado 27 de Febrero - 18:00 hs - Barcelona" />
    <meta name="twitter:image" content="https://TU-USUARIO.github.io/YANIRI/imagen.webp" />

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 20px;
            overflow-x: hidden;
            background: linear-gradient(135deg, #0f0c29, #302b63, #24243e);
            background-size: 400% 400%;
            animation: gradientShift 15s ease infinite;
            position: relative;
        }

        /* Fondo animado con partículas */
        body::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 20% 50%, rgba(120, 0, 255, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 80%, rgba(255, 0, 150, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 40% 20%, rgba(0, 200, 255, 0.1) 0%, transparent 50%);
            animation: particleMove 20s ease infinite;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        @keyframes particleMove {
            0%, 100% { transform: translate(0, 0) scale(1); }
            33% { transform: translate(30px, -30px) scale(1.1); }
            66% { transform: translate(-20px, 20px) scale(0.9); }
        }

        /* Estrellas flotantes */
        .stars {
            position: absolute;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: 0;
        }

        .star {
            position: absolute;
            width: 6px;
            height: 6px;
            background: white;
            border-radius: 50%;
            animation: twinkle 2s infinite;
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0; transform: scale(1); }
            50% { opacity: 1; transform: scale(1.5); }
        }

        /* Tarjeta de invitación */
        .card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            padding: 2.5rem;
            border-radius: 30px;
            box-shadow: 
                0 8px 32px rgba(0, 0, 0, 0.3),
                0 0 100px rgba(138, 43, 226, 0.2),
                inset 0 0 50px rgba(255, 255, 255, 0.02);
            text-align: center;
            max-width: 450px;
            width: 100%;
            position: relative;
            z-index: 1;
            animation: cardFloat 6s ease-in-out infinite;
            transition: transform 0.3s ease;
        }

        .card:hover {
            transform: translateY(-10px);
        }

        @keyframes cardFloat {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        .card-img {
            width: 100%;
            max-width: 300px;
            border-radius: 20px;
            margin-bottom: 1.5rem;
            border: 3px solid rgba(255, 255, 255, 0.2);
            box-shadow: 
                0 10px 30px rgba(0, 0, 0, 0.5),
                0 0 40px rgba(138, 43, 226, 0.3);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .card-img:hover {
            transform: scale(1.05);
            box-shadow: 
                0 15px 40px rgba(0, 0, 0, 0.6),
                0 0 60px rgba(138, 43, 226, 0.5);
        }

        h1 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 50%, #f093fb 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: titleGlow 3s ease-in-out infinite;
            text-shadow: 0 0 30px rgba(138, 43, 226, 0.5);
        }

        @keyframes titleGlow {
            0%, 100% { filter: brightness(1); }
            50% { filter: brightness(1.3); }
        }

        .subtitle {
            color: rgba(255, 255, 255, 0.7);
            font-size: 1.1rem;
            margin-bottom: 0.5rem;
            letter-spacing: 1px;
        }

        .name {
            font-size: 3rem;
            margin: 1rem 0;
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            font-weight: bold;
            text-shadow: 0 0 40px rgba(245, 87, 108, 0.6);
            animation: nameFloat 4s ease-in-out infinite;
        }

        @keyframes nameFloat {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        .details {
            color: rgba(255, 255, 255, 0.9);
            margin: 2rem 0;
            line-height: 2;
            font-size: 1.2rem;
            background: rgba(255, 255, 255, 0.05);
            padding: 1.5rem;
            border-radius: 15px;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .details strong {
            color: #f093fb;
            font-size: 1.3rem;
        }

        .btn {
            display: inline-block;
            padding: 1rem 2.5rem;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #fff;
            border-radius: 50px;
            text-decoration: none;
            font-weight: bold;
            font-size: 1.2rem;
            transition: all 0.3s ease;
            box-shadow: 
                0 10px 30px rgba(138, 43, 226, 0.4),
                0 0 40px rgba(138, 43, 226, 0.2);
            border: 2px solid rgba(255, 255, 255, 0.2);
            position: relative;
            overflow: hidden;
            margin-top: 1rem;
        }

        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
            transition: left 0.5s;
        }

        .btn:hover::before {
            left: 100%;
        }

        .btn:hover {
            background: linear-gradient(135deg, #764ba2 0%, #f093fb 100%);
            transform: translateY(-5px);
            box-shadow: 
                0 15px 40px rgba(138, 43, 226, 0.6),
                0 0 60px rgba(138, 43, 226, 0.4);
        }

        .btn:active {
            transform: translateY(-2px);
        }

        .mini-link {
            font-size: 0.85rem;
            margin-top: 2rem;
            color: rgba(255, 255, 255, 0.5);
            position: relative;
            z-index: 1;
        }

        .mini-link a {
            color: #f093fb;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s ease;
        }

        .mini-link a:hover {
            color: #ffffff;
            text-shadow: 0 0 10px rgba(240, 147, 251, 0.8);
        }

        /* Confeti animado */
        .confetti {
            position: absolute;
            width: 10px;
            height: 10px;
            background: #f093fb;
            opacity: 0;
            animation: confettiFall 5s linear infinite;
        }

        @keyframes confettiFall {
            0% {
                opacity: 1;
                transform: translateY(-100vh) rotate(0deg);
            }
            100% {
                opacity: 0;
                transform: translateY(100vh) rotate(720deg);
            }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .card {
                padding: 2rem 1.5rem;
                margin: 1rem;
            }

            h1 {
                font-size: 2rem;
            }

            .name {
                font-size: 2.2rem;
            }

            .details {
                font-size: 1.1rem;
                padding: 1.2rem;
            }

            .btn {
                padding: 0.9rem 2rem;
                font-size: 1.1rem;
            }
        }

        @media (max-width: 480px) {
            h1 {
                font-size: 1.8rem;
            }

            .name {
                font-size: 2rem;
            }

            .details {
                font-size: 1rem;
            }
        }
    </style>
</head>
<body>
    <!-- Estrellas de fondo -->
    <div class="stars" id="stars"></div>

    <!-- Tarjeta de invitación -->
    <section class="card">
        <img src="radioRD.webp" alt="Cumpleaños de Aangelica" class="card-img">

        <h1> ¡Estás invitado! </h1>
        <p class="subtitle">Celebramos el cumpleaños de</p>
        <h2 class="name">yaniris</h2>

        <div class="details">
            <strong>📅</strong> Sábado 27 de Febrero<br>
            <strong>🕒</strong> 18:00 hs<br>
            <strong>📍</strong> Barcelona
        </div>

        <a href="https://wa.me/34655549219?text=¡Confirmo%20mi%20asistencia%20al%20cumpleaños%20de%20Yaniris!" 
           target="_blank" 
           id="btn-confirmar" 
           class="btn">
            ✨ Confirmar asistencia ✨
        </a>
    </section>

    <p class="mini-link">
        ¿Quieres una tarjeta digital como esta?
        <a href="https://wa.me/34617615732?text=Hola%2C%20quiero%20una%20tarjeta%20digital%20personalizada" target="_blank">
            Pídela aquí
        </a>
    </p>

    <!-- Audio que sonará al confirmar -->
    <audio id="sonido-confirmacion">
        <source src="confirmacion.mp3" type="audio/mpeg">
    </audio>

    <script>
        // Crear estrellas en el fondo
        const starsContainer = document.getElementById('stars');
        for (let i = 0; i < 100; i++) {
            const star = document.createElement('div');
            star.className = 'star';
            star.style.left = Math.random() * 100 + '%';
            star.style.top = Math.random() * 100 + '%';
            star.style.animationDelay = Math.random() * 3 + 's';
            starsContainer.appendChild(star);
        }

        // Crear confeti
        for (let i = 0; i < 50; i++) {
            const confetti = document.createElement('div');
            confetti.className = 'confetti';
            confetti.style.left = Math.random() * 100 + '%';
            confetti.style.animationDelay = Math.random() * 5 + 's';
            confetti.style.animationDuration = (Math.random() * 3 + 3) + 's';
            
            const colors = ['#667eea', '#764ba2', '#f093fb', '#f5576c', '#4facfe'];
            confetti.style.background = colors[Math.floor(Math.random() * colors.length)];
            
            document.body.appendChild(confetti);
        }

        // Reproducir sonido al confirmar
        const boton = document.getElementById("btn-confirmar");
        const sonido = document.getElementById("sonido-confirmacion");

        boton.addEventListener("click", () => {
            sonido.currentTime = 0;
            sonido.play().catch(e => console.log('Audio no disponible'));
        });
    </script>
</body>
</html>

 
