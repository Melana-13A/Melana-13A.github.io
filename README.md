<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Will You Join My Cosmic Journey?</title>
    <style>
        body {
            font-family: 'Trebuchet MS', sans-serif;
            background: radial-gradient(circle at center, #0d1b2a, #000000);
            color: #e0eaff;
            text-align: center;
            padding: 20px;
            overflow: hidden;
            transition: background 1s;
        }

        h1 {
            color: #89c2d9;
            margin-bottom: 20px;
            text-shadow: 0 0 10px #89c2d9;
        }

        .container {
            max-width: 600px;
            margin: 0 auto;
            background: rgba(13, 27, 42, 0.8);
            padding: 30px;
            border-radius: 20px;
            box-shadow: 0 0 20px rgba(173, 216, 230, 0.3);
            position: relative;
        }

        .buttons {
            margin-top: 20px;
        }

        button {
            padding: 12px 24px;
            margin: 0 10px;
            font-size: 16px;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            transition: transform 0.3s, box-shadow 0.3s;
        }

        #yes {
            background-color: #4cafef;
            color: white;
            box-shadow: 0 0 10px #4cafef;
        }

        #yes:hover {
            transform: scale(1.1);
            box-shadow: 0 0 20px #4cafef;
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
            font-weight: bold;
            color: #ffd700;
            text-shadow: 0 0 15px #ffd700;
        }

        .planet {
            font-size: 80px;
            animation: spin 8s linear infinite;
        }

        @keyframes spin {
            100% { transform: rotate(360deg); }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Will You Join My Cosmic Journey?</h1>
        
        <div id="question">
            <p>Let’s travel the stars together 🌌</p>
            <div class="buttons">
                <button id="yes">Yes! 🚀</button>
                <button id="no">No 👽</button>
            </div>
        </div>
        
        <div id="response" class="hidden">
            <div class="planet">🪐</div>
            <p>Yay! Let’s explore the galaxy together! 🌠</p>
        </div>
    </div>

    <script>
        document.getElementById('yes').addEventListener('click', function() {
            document.getElementById('question').classList.add('hidden');
            document.getElementById('response').classList.remove('hidden');
            document.body.style.background = "radial-gradient(circle at center, #1b263b, #000)";
        });

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
