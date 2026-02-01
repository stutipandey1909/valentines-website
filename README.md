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
      Congratulations 🎉  
      You’re officially stuck with me as your Valentine ❤️😌  
      No take-backs 😌
    </div>
  </div>

#afterYes {
      display: none;
      margin-top: 40px;
    }

    .photos {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 15px;
      margin-top: 30px;
    }

    .photos img {
      width: 220px;
      height: 220px;
      object-fit: cover;
      border-radius: 20px;
      box-shadow: 0 10px 20px rgba(0,0,0,0.2);
    }
  </style>
</head>

<body>

  <div class="container">
    <h1>Be My Valentine 😌❤️</h1>
    <p>Choose wisely. There is only one correct answer.</p>

    <div class="buttons" id="question">
      <button id="yesBtn" onclick="yesClicked()">YES 💖</button>
      <button id="noBtn">NO 🙄</button>
    </div>
    <div id="afterYes">
      <h1>🥰 KNEW IT</h1>
      <p>
        Congratulations 🎉  
        You just unlocked exclusive access to  
        *Us Being Cute™* 💕
      </p>

      <div class="photos">
        <img src="photo1.jpg" alt="You❤️">
        <img src="photo2.jpg" alt="My favorite sketch">
        <img src="photo3.jpg" alt="Dangerously cute">
      </div>

      <p>
        Sorry, no refunds.  
        You’re officially stuck with me now 😌❤️
      </p>
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
      document.getElementById("question").style.display = "none";
      document.getElementById("afterYes").style.display = "block";
    }
  </script>

</body>
</html>
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
