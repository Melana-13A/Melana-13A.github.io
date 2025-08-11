<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Will You Be My Valentine?</title>
<style>
    body {
        font-family: 'Arial', sans-serif;
        background-color: #ffe4ec;
        text-align: center;
        padding: 20px;
        overflow: hidden;
        transition: background 1s;
    }
    h1 {
        color: #d81b60;
        margin-bottom: 30px;
        text-shadow: 0 0 10px #ff80ab;
    }
    .container {
        max-width: 600px;
        margin: 0 auto;
        background-color: white;
        padding: 30px;
        border-radius: 15px;
        box-shadow: 0 4px 8px rgba(0,0,0,0.1);
        position: relative;
        z-index: 2;
    }
    .buttons {
        margin-top: 20px;
    }
    button {
        padding: 10px 20px;
        margin: 0 10px;
        font-size: 16px;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        transition: transform 0.3s;
    }
    #yes {
        background-color: #4caf50;
        color: white;
    }
    #yes:hover {
        transform: scale(1.1);
        box-shadow: 0 0 10px #4caf50;
    }
    #no {
        background-color: #f44336;
        color: white;
        position: relative;
    }
    .hidden {
        display: none;
    }
    #response {
        margin-top: 20px;
        font-size: 24px;
        color: #d81b60;
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
        font-size: 20px;
        animation: floatUp 6s linear infinite;
        z-index: 1;
    }
    @keyframes floatUp {
        0% { transform: translateY(100vh) scale(1); opacity: 1; }
        100% { transform: translateY(-10vh) scale(1.5); opacity: 0; }
    }
</style>
</head>
<body>

<div class="container">
    <h1>Will You Be My Valentine? ❤️</h1>
    <div id="question">
        <p>I really like you! Will you be my Valentine?</p>
        <div class="buttons">
            <button id="yes">Yes! 💕</button>
            <button id="no">No 😢</button>
        </div>
    </div>
    <div id="response" class="hidden">
        <div class="heart">❤️</div>
        <p id="love-message"></p>
    </div>
</div>

<audio id="love-music" src="https://www.computerhope.com/jargon/m/example.mp3"></audio> <!-- Replace with your own MP3 -->

<script>
let escapeSpeed = 20; // button escape speed

// Floating hearts generator
function createHeart() {
    const heart = document.createElement("div");
    heart.classList.add("floating-heart");
    heart.textContent = "💖";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.fontSize = Math.random() * 20 + 10 + "px";
    heart.style.animationDuration = Math.random() * 3 + 3 + "s";
    document.body.appendChild(heart);
    setTimeout(() => { heart.remove(); }, 6000);
}
setInterval(createHeart, 300);

// Typing effect for love message
function typeText(text, element) {
    let i = 0;
    function typing() {
        if (i < text.length) {
            element.innerHTML += text.charAt(i);
            i++;
            setTimeout(typing, 80);
        }
    }
    typing();
}

document.getElementById('yes').addEventListener('click', function() {
    document.getElementById('question').classList.add('hidden');
    document.getElementById('response').classList.remove('hidden');
    document.body.style.background = "linear-gradient(to top right, #ff9a9e, #fad0c4)";
    const msg = document.getElementById('love-message');
    msg.innerHTML = "";
    typeText("Yay! You made me the happiest person alive! ❤️", msg);
    document.getElementById("love-music").play();
});

// No button escape
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

    escapeSpeed -= 1; // gets faster
});
</script>
</body>
</html>
