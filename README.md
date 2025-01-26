<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Valentine Day</title>
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@700&display=swap" rel="stylesheet"> <!-- Added Cinzel font -->
    <style>
        body {
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background: var(--custom-background, url('https://img.freepik.com/free-vector/detailed-hand-painted-pink-watercolour-background_1048-17039.jpg')), linear-gradient(to bottom right, #ff9a9e, #fad0c4);
            font-family: 'Arial', sans-serif;
            text-align: center;
            overflow: hidden;
        }
        .envelope {
            position: relative;
            width: 90%;
            max-width: 300px;
            height: 200px;
            background: #fff;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
            overflow: hidden;
            transition: transform 0.5s;
        }
        .envelope:hover {
            transform: scale(1.05);
        }
        .flap {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 50%;
            background: #ff6b6b;
            border-bottom: 5px solid #e63946;
            clip-path: polygon(0 0, 100% 0, 50% 100%);
            transition: transform 0.5s;
            z-index: 2;
        }
        .flap::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(to bottom, rgba(255, 255, 255, 0.5), rgba(255, 255, 255, 0));
            clip-path: polygon(0 0, 100% 0, 50% 100%);
        }
        .wax-seal {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: #9e0a2d; /* Dark wax color */
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.2);
        }
        .letter {
            position: absolute;
            top: 50%;
            left: 10%;
            width: 80%;
            height: auto;
            background: url('https://img.freepik.com/free-vector/detailed-hand-painted-pink-watercolour-background_1048-17039.jpg');
            background-color: white;
            border-radius: 10px;
            padding: 20px;
            box-sizing: border-box;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            transform: translateY(200%);
            transition: transform 0.5s ease-out;
            z-index: 1;
        }
        .envelope.open .flap {
            transform: rotateX(180deg);
            transform-origin: top;
        }
        .envelope.open .letter {
            transform: translateY(-50%);
        }
        .letter h1 {
            margin: 0;
            font-size: 2rem;
            color: #ff6b6b;
            font-family: 'Cinzel', serif; /* Applied Victorian font */
        }
        .letter p {
            font-size: 1.2rem;
            color: #ffffff; /* Grayish white */
            margin-top: 10px;
        }
        .heart {
            position: absolute;
            width: 20px;
            height: 20px;
            background-color: #ff6b6b;
            clip-path: polygon(50% 0%, 100% 35%, 80% 100%, 50% 75%, 20% 100%, 0% 35%);
            animation: heart-float 6s ease-in infinite;
        }
        @keyframes heart-float {
            0% {
                opacity: 1;
                transform: translateY(0) scale(1);
            }
            50% {
                opacity: 0.8;
                transform: translateY(-200px) scale(1.2);
            }
            100% {
                opacity: 0;
                transform: translateY(500px) scale(0.8);
            }
        }

        @media (max-width: 600px) {
            .envelope {
                height: 180px;
            }
            .flap {
                height: 45%;
            }
            .letter {
                padding: 15px;
                font-size: 0.9rem;
            }
            .letter h1 {
                font-size: 1.2rem;
            }
            .letter p {
                font-size: 0.9rem;
            }
        }
    </style>
</head>
<body>
    <div class="envelope" onclick="openEnvelope(this)">
        <div class="flap"></div>
        <div class="letter">
            <h1>Happy Valentine's Day</h1>
            <p style="font-family: 'Script', cursive;">Happy Valentine's Day, Maygan❤</p>
        </div>
    </div>

    <script>
        function openEnvelope(envelope) {
            envelope.classList.toggle('open');
            if (envelope.classList.contains('open')) {
                releaseHearts();
            }
        }

        function releaseHearts() {
            for (let i = 0; i < 20; i++) {
                const heart = document.createElement('div');
                heart.classList.add('heart');
                heart.style.left = Math.random() * window.innerWidth + 'px';
                heart.style.top = Math.random() * window.innerHeight + 'px';
                document.body.appendChild(heart);
                setTimeout(() => heart.remove(), 6000); // Removes heart after it has floated out of view
            }
        }
    </script>

<audio controls autoplay>
    <source src="Blue-Yung-Kai.mp3" type="audio/mp3">
</audio>
</body>
</html>

