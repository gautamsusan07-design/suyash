# suyash
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>For My Only One 🌹</title>
    <style>
        :root { --main-red: #8a0e0e; --glow: #ff4d6d; }
        body {
            margin: 0; background: #000; color: white;
            font-family: 'Georgia', serif;
            display: flex; justify-content: center; align-items: center;
            height: 100vh; overflow: hidden;
        }
        #canvas { position: absolute; top: 0; left: 0; }
        .card {
            position: relative; z-index: 2;
            text-align: center; background: rgba(0,0,0,0.8);
            padding: 40px; border-radius: 15px;
            border: 1px solid var(--main-red);
            box-shadow: 0 0 20px var(--main-red);
            max-width: 400px;
        }
        h1 { font-style: italic; color: var(--glow); text-shadow: 0 0 10px var(--glow); }
        #typewriter { height: 50px; font-size: 1.2rem; line-height: 1.5; }
        .rose-icon { font-size: 50px; cursor: pointer; transition: 0.5s; }
        .rose-icon:hover { transform: scale(1.2) rotate(10deg); }
    </style>
</head>
<body>
    <canvas id="canvas"></canvas>
    <div class="card">
        <div class="rose-icon" onclick="playMusic()">🌹</div>
        <h1>Happy Rose Day</h1>
        <div id="typewriter"></div>
        <p style="font-size: 0.8rem; margin-top: 20px; color: #666;">(Click the rose for a surprise)</p>
    </div>

    <script>
        // Typewriter Effect
        const text = "In a garden full of flowers, my eyes will always look for you. You are my forever rose.";
        let i = 0;
        function type() {
            if (i < text.length) {
                document.getElementById("typewriter").innerHTML += text.charAt(i);
                i++;
                setTimeout(type, 100);
            }
        }
        window.onload = type;

        function playMusic() {
            alert("❤️ You are the most beautiful flower in my life! ❤️");
        }

        // Simple Background Animation
        const canvas = document.getElementById('canvas');
        const ctx = canvas.getContext('2d');
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;
        
        function draw() {
            ctx.fillStyle = 'rgba(0, 0, 0, 0.05)';
            ctx.fillRect(0, 0, canvas.width, canvas.height);
            ctx.fillStyle = '#400';
            for(let j=0; j<5; j++) {
                ctx.beginPath();
                ctx.arc(Math.random()*canvas.width, Math.random()*canvas.height, 1, 0, Math.PI*2);
                ctx.fill();
            }
            requestAnimationFrame(draw);
        }
        draw();
    </script>
</body>
</html>
