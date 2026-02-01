# valentines-website
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Since you didn't have time to ask, i thought i'll do it. Will you be my Valentine? 😏❤️</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: linear-gradient(to bottom right, #ff9a9e, #fad0c4);
      text-align: center;
      color: white;
      height: 100vh;
      overflow-x: hidden;
    }

    canvas {
      position: fixed;
      top: 0;
      left: 0;
      pointer-events: none;
      z-index: 999;
    }

    .container {
      padding-top: 70px;
    }

    h1 {
      font-size: 42px;
    }

    p {
      font-size: 20px;
      margin: 20px auto;
      max-width: 600px;
    }

    .buttons {
      position: relative;
      height: 200px;
      margin-top: 30px;
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

    /* AFTER YES */
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
      box-shadow: 0 10px 20px rgba(0,0,0,0.25);
    }
  </style>
</head>

<body>

<canvas id="confetti"></canvas>

<div class="container">
  <h1>Since you didn't have time to ask, i thought i'll do it. Will you be my Valentine? 😏❤️</h1>
  <p>There is only one correct answer.</p>

  <div class="buttons" id="question">
    <button id="yesBtn" onclick="yesClicked()">YES 💖</button>
    <button id="noBtn">NO 🙄</button>
  </div>

  <div id="afterYes">
    <h1>🎉 YAYYY 🎉</h1>
    <p>
      Smart choice 😌  
      You’ve officially unlocked  
      *Us Being Cute™* 💕
    </p>

    <div class="photos">
      <img src="photo1.jpeg">
      <img src="photo2.jpeg">
      <img src="photo3.jpeg">
    </div>

    <p>
      No escape now.  
      You’re stuck with me ❤️😏
    </p>
  </div>
</div>

<script>
  /* NO BUTTON RUNS AWAY */
  const noBtn = document.getElementById("noBtn");

  noBtn.addEventListener("mouseover", moveNoButton);
  noBtn.addEventListener("click", moveNoButton);

  function moveNoButton() {
    const x = Math.random() * (window.innerWidth - 120);
    const y = Math.random() * (window.innerHeight - 60);
    noBtn.style.left = x + "px";
    noBtn.style.top = y + "px";
  }

  /* CONFETTI LOGIC */
  const canvas = document.getElementById("confetti");
  const ctx = canvas.getContext("2d");
  let confettiPieces = [];

  function resizeCanvas() {
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
  }
  window.addEventListener("resize", resizeCanvas);
  resizeCanvas();

  function createConfetti() {
    confettiPieces = [];
    for (let i = 0; i < 200; i++) {
      confettiPieces.push({
        x: Math.random() * canvas.width,
        y: Math.random() * canvas.height - canvas.height,
        r: Math.random() * 6 + 4,
        d: Math.random() * 200,
        color: `hsl(${Math.random() * 360}, 100%, 60%)`,
        tilt: Math.random() * 10 - 10
      });
    }
  }

  function drawConfetti() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    confettiPieces.forEach(p => {
      ctx.beginPath();
      ctx.fillStyle = p.color;
      ctx.arc(p.x, p.y, p.r, 0, Math.PI * 2);
      ctx.fill();
    });
    updateConfetti();
  }

  function updateConfetti() {
    confettiPieces.forEach(p => {
      p.y += Math.cos(p.d) + 4;
      p.x += Math.sin(p.d);
      if (p.y > canvas.height) {
        p.y = -10;
      }
    });
  }

  function startConfetti() {
    createConfetti();
    const interval = setInterval(drawConfetti, 20);
    setTimeout(() => {
      clearInterval(interval);
      ctx.clearRect(0, 0, canvas.width, canvas.height);
    }, 3000);
  }

  function yesClicked() {
    startConfetti();
    document.getElementById("question").style.display = "none";
    document.getElementById("afterYes").style.display = "block";
  }
</script>

</body>
</html>
