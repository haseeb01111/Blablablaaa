<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Twinkle Stars</title>
    <style>
        body {
            margin: 0;
            height: 100vh;
            background-color: black;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            color: white;
            font-family: Arial, sans-serif;
        }

        .stars {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
        }

        .star {
            position: absolute;
            width: 2px;
            height: 2px;
            background-color: white;
            border-radius: 50%;
            animation: twinkle 1.5s infinite ease-in-out;
        }

        @keyframes twinkle {
            0%, 100% {
                opacity: 0.2;
            }
            50% {
                opacity: 1;
            }
        }

        .message {
            z-index: 2;
            font-size: 3rem;
            text-align: center;
            animation: glow 1.5s infinite alternate;
        }

        @keyframes glow {
            from {
                text-shadow: 0 0 10px white, 0 0 20px white;
            }
            to {
                text-shadow: 0 0 20px white, 0 0 30px white;
            }
        }
    </style>
</head>
<body>
    <div class="stars" id="stars"></div>
    <div class="message">Isi tarha baap ki baat maanty reh</div>

    <script>
        const starsContainer = document.getElementById('stars');
        const numStars = 150; // Number of stars

        for (let i = 0; i < numStars; i++) {
            const star = document.createElement('div');
            star.classList.add('star');
            star.style.top = `${Math.random() * 100}vh`;
            star.style.left = `${Math.random() * 100}vw`;
            star.style.animationDelay = `${Math.random() * 2}s`;
            starsContainer.appendChild(star);
        }
    </script>
</body>
</html>
