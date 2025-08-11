<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>You Are My Forever ❤️</title>
<style>
    body {
        font-family: 'Segoe UI', sans-serif;
        background-color: #fff0f5;
        text-align: center;
        padding: 20px;
        overflow: hidden;
        transition: background-color 0.5s;
    }
    h1 {
        color: #c2185b;
        margin-bottom: 20px;
    }
    .container {
        max-width: 600px;
        margin: 0 auto;
        background-color: white;
        padding: 30px;
        border-radius: 20px;
        box-shadow: 0 6px 15px rgba(0,0,0,0.1);
        position: relative;
        z-index: 1;
    }
    .buttons {
        margin-top: 20px;
    }
    button {
        padding: 10px 20px;
        margin: 0 10px;
        font-size: 16px;
        border: none;
        border-radius: 8px;
        cursor: pointer;
        transition: transform 0.3s;
    }
    #yes {
        background-color: #e91e63;
        color: white;
    }
    #no {
        background-color: #9e9e9e;
        color: white;
        position: relative;
    }
    .hidden {
        display: none;
    }
    #response {
        margin-top: 20px;
        font-size: 24px;
        color: #c2185b;
        font-weight: bold;
    }
    .heart {
        font-size: 100px;
        color: red;
        animation: beat 1s infinite alternate;
    }
    @keyframes beat {
        to { transform: scale(1.2); }
    }
    /* Floating hearts background */
    .floating-heart {
        position: fixed;
        bottom: -50px;
        font-size: 24px;
        animation: floatUp 5s linear infinite;
        color: rgba(255,0,0,0.7);
        z-index: 0;
    }
    @keyframes floatUp {
        0% { transform: translateY(0); opacity: 1; }
        100% { transform: translateY(-800px); opacity: 0; }
    }
</style>
</head>
<body>
<div class="container">
    <h1>You Are My Forever ❤️</h1>
    
    <div id="question">
        <p>From the moment I met you, my heart knew you were the one.<br>
        Will you walk beside me in every tomorrow?</p>
        <div class="buttons">
            <button id="yes">Yes, My Love 💖</button>
            <button id="no">Maybe... Not 😏</button>
        </div>
    </div>
    
    <div id="response" class="hidden">
        <div class="heart">❤️</div>
        <p>You just made my soul dance in joy! 💕<br>
        I promise to love you endlessly.</p>
    </div>
</div>

<!-- Background music -->
<audio id="bg-music" src="https://cdn.pixabay.com/download/audio/2022/03/15/audio_32f44fdb77.mp3" preload="auto"></audio>

<script>
    // Yes button function
    document.getElementById('yes').addEventListener('click', function() {
        document.getElementById('question').classList.add('hidden');
        document.getElementById('response').classList.remove('hidden');
        document.body.style.backgroundColor = "#ffe4ec";

        // Play music
        document.getElementById('bg-music').play();

        // Confetti
        for (let i = 0; i < 30; i++) {
            let heart = document.createElement("div");
            heart.classList.add("floating-heart");
            heart.style.left = Math.random() * window.innerWidth + "px";
            heart.style.animationDuration = (3 + Math.random() * 2) + "s";
            heart.innerHTML = "💖";
            document.body.appendChild(heart);
            setTimeout(() => heart.remove(), 5000);
        }
    });

    // No button runaway
    document.getElementById('no').addEventListener('mouseover', function() {
        const button = this;
        const container = document.querySelector('.container');
        const containerRect = container.getBoundingClientRect();
        
        const maxX = containerRect.width - button.offsetWidth;
        const maxY = containerRect.height - button.offsetHeight;
        
        const randomX = Math.floor(Math.random() * maxX);
        const randomY = Math.floor(Math.random() * maxY);
        
        button.style.position = 'absolute';
        button.style.left = randomX + 'px';
        button.style.top = randomY + 'px';
    });
</script>
</body>
</html>
