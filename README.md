<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Valentine's Day</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f7c0c0;
            color: #fff;
            text-align: center;
            padding: 20px;
            margin: 0;
            position: relative;
        }

        h1 {
            font-size: 50px;
            margin-top: 50px;
            color: #d40000;
            text-shadow: 3px 3px 5px rgba(0, 0, 0, 0.3);
        }

        .heart {
            font-size: 100px;
            color: #ff1a1a;
            animation: bounce 1s infinite alternate;
        }

        .message {
            font-size: 24px;
            color: #fff;
            margin-top: 20px;
        }

        @keyframes bounce {
            0% {
                transform: translateY(0);
            }
            100% {
                transform: translateY(-20px);
            }
        }

        .gift-box {
            margin-top: 30px;
            font-size: 50px;
            color: #ff6699;
            cursor: pointer;
        }

        .gift-box:hover {
            transform: scale(1.1);
        }

        .popup {
            display: none;
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background-color: #ff1a1a;
            padding: 30px;
            border-radius: 10px;
            color: white;
            box-shadow: 0px 0px 20px rgba(0, 0, 0, 0.4);
            font-size: 20px;
            text-align: center;
        }

        .popup button {
            margin-top: 20px;
            padding: 10px 20px;
            background-color: #fff;
            color: #ff1a1a;
            border: none;
            font-size: 16px;
            cursor: pointer;
        }

        .popup button:hover {
            background-color: #ff6699;
        }

        .name-input {
            font-size: 20px;
            padding: 10px;
            margin-top: 20px;
            background-color: white;
            border: none;
            color: #ff1a1a;
            border-radius: 5px;
            text-align: center;
        }

        .submit-btn {
            font-size: 18px;
            padding: 10px 20px;
            margin-top: 10px;
            background-color: #ff1a1a;
            color: white;
            border: none;
            cursor: pointer;
            border-radius: 5px;
        }

        .submit-btn:hover {
            background-color: #ff6699;
        }

        .quote {
            font-size: 18px;
            margin-top: 20px;
            color: #fff;
            font-style: italic;
        }

        .quote-author {
            margin-top: 5px;
            font-size: 16px;
            color: #ffccff;
        }

    </style>
</head>
<body>
    <h1>Happy Valentine's Day!</h1>
    <div class="heart">💖</div>
    <div class="message">Please enter your name to receive a special Valentine's message:</div>
    
    <input type="text" id="name" class="name-input" placeholder="Enter your name" />
    <button class="submit-btn" onclick="showMessage()">Submit</button>

    <div id="personalizedMessage" class="message" style="display: none;"></div>
    
    <div class="gift-box" onclick="showPopup()">🎁</div>

    <div id="popup" class="popup">
        <p>Here's a special Valentine's Day message just for you! 💌</p>
        <button onclick="closePopup()">Close</button>
    </div>

    <div id="quote" class="quote" style="display: none;"></div>
    <div id="quoteAuthor" class="quote-author" style="display: none;"></div>

    <!-- Add Isq Bulaava Song -->
    <audio id="bgMusic" loop autoplay>
        <!-- Replace this URL with the correct audio file URL for Isq Bulaava -->
        <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mp3">
        Your browser does not support the audio element.
    </audio>

    <script>
        const quotes = [
            { text: "Love is not about how many days, months, or years you have been together. Love is about how much you love each other every single day.", author: "Anonymous" },
            { text: "Love is composed of a single soul inhabiting two bodies.", author: "Aristotle" },
            { text: "You are my sun, my moon, and all my stars.", author: "E.E. Cummings" },
            { text: "In all the world, there is no heart for me like yours. In all the world, there is no love for you like mine.", author: "Maya Angelou" }
        ];

        function getRandomQuote() {
            const randomIndex = Math.floor(Math.random() * quotes.length);
            return quotes[randomIndex];
        }

        function showMessage() {
            const name = document.getElementById('name').value;
            if (name) {
                const quote = getRandomQuote();
                document.getElementById('personalizedMessage').style.display = 'block';
                document.getElementById('personalizedMessage').innerText = `Happy Valentine's Day, ${name}! 💖 May your day be filled with love and happiness!`;

                document.querySelector('.name-input').style.display = 'none';
                document.querySelector('.submit-btn').style.display = 'none';

                const randomQuote = getRandomQuote();
                document.getElementById('quote').style.display = 'block';
                document.getElementById('quote').innerText = `"${randomQuote.text}"`;
                document.getElementById('quoteAuthor').style.display = 'block';
                document.getElementById('quoteAuthor').innerText = `- ${randomQuote.author}`;
            } else {
                alert("Please enter your name!");
            }
        }

        function showPopup() {
            document.getElementById('popup').style.display = 'block';
        }

        function closePopup() {
            document.getElementById('popup').style.display = 'none';
        }
    </script>
</body>
</html>
