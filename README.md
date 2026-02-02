# valentines-website

<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Since you did NOT have time to ask, i thought i'll only do it. Will you be my V-A-L-E-N-T-I-N-E? 😏❤️ (huh) </title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <style>

    .tiny-heart {
  font-size: 40px;
  margin-bottom: 15px;
}
    .question-box {
  background: white;
  color: #ff4d6d;
  max-width: 800px;
  margin: 40px auto;
  padding: 40px 30px;
  border-radius: 25px;
  box-shadow: 0 15px 30px rgba(0,0,0,0.15);
}
    #yesBtn {
  animation: yesPulse 1.8s infinite;
}

@keyframes yesPulse {
  0% { transform: scale(1); box-shadow: 0 0 0 rgba(255,77,109,0.4); }
  50% { transform: scale(1.08); box-shadow: 0 0 20px rgba(255,77,109,0.6); }
  100% { transform: scale(1); box-shadow: 0 0 0 rgba(255,77,109,0.4); }
}
.tiny-text {
  font-size: 14px;
  color: #777;
  margin-top: 15px;
}

    .surprise-link {
  display: inline-block;
  margin-top: 25px;
  padding: 14px 28px;
  background: #ff4d6d;
  color: white;
  text-decoration: none;
  border-radius: 30px;
  font-size: 16px;
}

.surprise-link:hover {
  background: #e63b5f;
}
.question-box h1 {
  color: #ff4d6d;
}

.question-box p {
  color: #555;
  margin-top: 15px;
}
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: linear-gradient(to bottom right, #ff9a9e, #cbe3e5);
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

<!-- MUSIC -->
<audio id="loveSong">
  <source src="Espresso.mp3" type="audio/mpeg">
</audio>

<div class="question-box">
  <div class="tiny-heart">❤️</div>
  <h1>Since you did NOT have time to ask, i thought i'll only do it. Will you be my V-A-L-E-N-T-I-N-E? 😏❤️ (huh) </h1>
  <p>There is only one correct answer.</p>

  <div class="buttons" id="question">
    <button id="yesBtn" onclick="yesClicked()">YES 💖</button>
    <button id="noBtn">NO 🙄</button>
  </div>
<p class="tiny-text">Wrong answers will be ignored 😌</p>

  <div id="afterYes">
    <h1>🎉 YAYYY 🎉</h1>
    <p>
      Look at you making great life choices 😌  
      Now do not expect a gift because,
      I am your biggest gift 💕
    </p>

    <div class="photos">
      <img src="photo1.jpeg">
      <img src="photo2.jpeg">
      <img src="photo3.jpeg">
      <img src="photo4.jpeg">
      <img src="photo5.jpeg">
      <img src="photo6.jpeg">
    </div>

    <p>
      You better be happy because this took me 3 hours to build❤️😏
    </p>
    <a href="letter.html" class="surprise-link">
  Click here for a surprise 💌
</a>
  </div>
</div>


<script>
  /* NO BUTTON RUNS */
  const noBtn = document.getElementById("noBtn");

  noBtn.addEventListener("mouseover", moveNoButton);
  noBtn.addEventListener("click", moveNoButton);

  function moveNoButton() {
    const noTexts = ["NO 😭", "WAIT 😳", "OKAY STOP", "WHY THO", "NOT FAIR"];
noBtn.innerText = noTexts[Math.floor(Math.random() * noTexts.length)];
    
    const x = Math.random() * (window.innerWidth - 120);
    const y = Math.random() * (window.innerHeight - 60);
    noBtn.style.left = x + "px";
    noBtn.style.top = y + "px";
  }

  /* CONFETTI */
  const canvas = document.getElementById("confetti");
  const ctx = canvas.getContext("2d");
  let confetti = [];

  function resize() {
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
  }
  window.addEventListener("resize", resize);
  resize();

  function createConfetti() {
    confetti = [];
    for (let i = 0; i < 200; i++) {
      confetti.push({
        x: Math.random() * canvas.width,
        y: Math.random() * canvas.height - canvas.height,
        r: Math.random() * 6 + 4,
        color: `hsl(${Math.random() * 360}, 100%, 60%)`,
        speed: Math.random() * 3 + 2
      });
    }
  }

  function drawConfetti() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    confetti.forEach(p => {
      ctx.beginPath();
      ctx.fillStyle = p.color;
      ctx.arc(p.x, p.y, p.r, 0, Math.PI * 2);
      ctx.fill();
      p.y += p.speed;
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

    const song = document.getElementById("loveSong");
    song.play();

    document.getElementById("question").style.display = "none";
    document.getElementById("afterYes").style.display = "block";
  }
</script>

</body>
</html>
