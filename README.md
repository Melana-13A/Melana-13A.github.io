<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Will You Be My Valentine?</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #ffebee;
            text-align: center;
            padding: 20px;
            transition: background-color 0.5s;
        }
        
        h1 {
            color: #d81b60;
            margin-bottom: 30px;
        }
        
        .container {
            max-width: 600px;
            margin: 0 auto;
            background-color: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
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
        
        #no {
            background-color: #f44336;
            color: white;
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
            to {
                transform: scale(1.2);
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Will You Be My Valentine?</h1>
        
        <div id="question">
            <p>I really like you! Would you be my Valentine?</p>
            <div class="buttons">
                <button id="yes">Yes!</button>
                <button id="no">No</button>
            </div>
        </div>
        
        <div id="response" class="hidden">
            <div class="heart">❤️</div>
            <p>Yay! You made me the happiest person! ❤️</p>
        </div>
    </div>

    <script>
        document.getElementById('yes').addEventListener('click', function() {
            document.getElementById('question').classList.add('hidden');
            document.getElementById('response').classList.remove('hidden');
            document.body.style.backgroundColor = "#fce4ec";
        });
        
        document.getElementById('no').addEventListener('mouseover', function() {
            const button = this;
            const container = document.querySelector('.container');
            const containerRect = container.getBoundingClientRect();
            
            // Random position within container
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
