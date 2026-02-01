# valentines-website
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Valentine’s ❤️</title>
    <style>
        body {
            margin: 0;
            font-family: 'Arial', sans-serif;
            background: linear-gradient(to bottom right, #ff9a9e, #fad0c4);
            color: #fff;
            text-align: center;
        }
        .container {
            padding: 60px 20px;
        }
        h1 {
            font-size: 48px;
        }
        p {
            font-size: 20px;
            max-width: 600px;
            margin: 20px auto;
        }
        button {
            background-color: #fff;
            color: #ff4d6d;
            border: none;
            padding: 14px 24px;
            font-size: 16px;
            border-radius: 30px;
            cursor: pointer;
            margin-top: 20px;
        }
        button:hover {
            background-color: #ffe6eb;
        }
        .heart {
            font-size: 40px;
            animation: pulse 1.5s infinite;
        }
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.2); }
            100% { transform: scale(1); }
        }
    </style>
</head>
<body>

    <div class="container">
        <div class="heart">❤️</div>
        <h1>Happy Valentine’s Day</h1>
        <p>
            From the moment you came into my life, everything felt warmer,
            happier, and a little more magical. This is just a small way to
            say how much you mean to me 💕
        </p>
        <button onclick="showLove()">Click for a surprise 💌</button>
        <p id="message"></p>
    </div>

    <script>
        function showLove() {
            document.getElementById("message").innerText =
            "I choose you. Today, tomorrow, and always ❤️";
        }
    </script>

</body>
</html>
