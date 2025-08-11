<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Will You Be Mine?</title>
<style>
    body {
        font-family: 'Segoe UI', sans-serif;
        background: linear-gradient(135deg, #fdfbfb, #ebedee);
        text-align: center;
        padding: 20px;
        overflow: hidden;
        transition: background 1s ease;
    }
    h1 {
        color: #ff7b89;
        margin-bottom: 20px;
        font-size: 2em;
        text-shadow: 0 0 10px rgba(255, 182, 193, 0.4);
    }
    p {
        color: #555;
        font-size: 1.1em;
    }
    .container {
        max-width: 600px;
        margin: 0 auto;
        background-color: rgba(255, 255, 255, 0.9);
        padding: 30px;
        border-radius: 20px;
        box-shadow: 0 4px 20px rgba(0,0,0,0.05);
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
        border-radius: 25px;
        cursor: pointer;
        transition: transform 0.3s, box-shadow 0.3s;
    }
    #yes {
        background-color: #ffb3c1;
        color: white;
        box-shadow: 0 4px 10px rgba(255, 182, 193, 0.4);
    }
    #yes:hover {
        transform: scale(1.1);
        box-shadow: 0 6px 15px rgba(255, 182, 193, 0.6);
    }
    #no {
        background-color: #bdbdbd;
        color: white;
        position: relative;
    }
    .hidden {
        display: none;
    }
    #response {
        margin-top: 20px;
        font-size: 24px;
        color: #ff7b89;
        font-weight: bold;
    }
    .heart {
        font-size: 90px;
        color: #ff7b89;
        animation: beat 1s infinite alternate;
    }
    @keyframes beat {
        to { transform: scale(1.2); }
    }
    /* Floating petals */
    .petal {
        position: fixed;
        font-size: 18px;
        animation: floatDown 8s linear infinite;
        z-index: 1;
    }
    @keyframes floatDown {
        0% { transform: translateY(-10vh) rotate(0deg); opacity: 1; }
        100% { transform: translateY(110vh) rotate(360deg); opacity: 0; }
    }
</style>
</head>
<body>

<div class="container">
    <h1>Will You Be Mine? 🌸</h1>
    <div id="question">
        <p>From the moment I met you, my world began to bloom — will you let me hold your heart forever?</p>
        <div class="buttons">
            <button id="yes">Yes 💖</button>
            <button id="no">No 😅</button>
        </div>
    </div>
    <div id="response" class="hidden">
        <div class="heart">💗</div>
        <p id="love-message"></p>
    </div>
</div>

<audio id="love-music" src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3"></audio> <!-- replace wit
