# valentines-website
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>You've to make the right choice. Be My Valentine 😏❤️</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: linear-gradient(to bottom right, #ff9a9e, #fad0c4);
      text-align: center;
      color: white;
      height: 100vh;
      overflow: hidden;
    }

    .container {
      padding-top: 80px;
    }

    h1 {
      font-size: 42px;
      margin-bottom: 10px;
    }

    p {
      font-size: 20px;
      margin-bottom: 30px;
    }

    .buttons {
      position: relative;
      height: 200px;
    }

    button {
      padding: 14px 30px;
      font-size: 16px;
      border-radius: 30px;
      border: none;
      cursor: pointer;
    }

    #yesBtn {
      background: white;
      color: #ff4d6d;
      margin-right: 20px;
    }

    #noBtn {
      background: #ff4d6d;
      color: white;
      position: absolute;
    }

    #result {
      font-size: 24px;
      margin-top: 40px;
      display: none;
    }
  </style>
</head>

<body>

  <div class="container">
    <h1>You've to make the right choice. Be My Valentine 😏❤️</h1>
    <p>Important question. Think carefully.</p>

    <div class="buttons">
      <button id="yesBtn" onclick="yesClicked()">YES 💖</button>
      <button id="noBtn">NO 🙄</button>
    </div>

    <div id="result">
      🥰 Knew it.  
      You’re officially my Valentine now ❤️  
      No take-backs 😌
    </div>
  </div>

  <script>
    const noBtn = document.getElementById("noBtn");

    noBtn.addEventListener("mouseover", moveNoButton);
    noBtn.addEventListener("click", moveNoButton);

    function moveNoButton() {
      const x = Math.random() * (window.innerWidth - 120);
      const y = Math.random() * (window.innerHeight - 60);

      noBtn.style.left = x + "px";
      noBtn.style.top = y + "px";
    }

    function yesClicked() {
      document.querySelector(".buttons").style.display = "none";
      document.getElementById("result").style.display = "block";
    }
  </script>

</body>
</html>
