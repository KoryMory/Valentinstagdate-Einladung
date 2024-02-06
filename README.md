<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Valentinstag Einladung</title>
  <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Montserrat:wght@400;700&display=swap">
  <style>
    body {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      background: linear-gradient(to right, #ff9a9e, #fecfef);
      margin: 0;
      font-family: 'Montserrat', sans-serif;
      overflow: hidden;
      position: relative;
    }

    .header_text {
      font-size: 32px;
      font-weight: bold;
      color: #fff;
      text-align: center;
      margin-top: 20px;
      margin-bottom: 0px;
      font-family: 'Dancing Script', cursive;
      z-index: 1;
    }

    .buttons {
      display: flex;
      flex-direction: row;
      justify-content: center;
      align-items: center;
      margin-top: 20px;
      z-index: 1;
    }

    .btn {
      background-color: #ff5e6c;
      color: white;
      padding: 12px 28px;
      text-align: center;
      display: inline-block;
      font-size: 16px;
      margin: 4px 2px;
      cursor: pointer;
      border: none;
      border-radius: 25px;
      transition: background-color 0.3s ease, transform 0.2s ease, box-shadow 0.2s ease;
      box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
      font-family: 'Montserrat', sans-serif;
    }

    .btn:hover {
      background-color: #ff2e50;
      transform: scale(1.05);
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    }

    .start_gif_container img,
    .ergebnis_gif_container img {
      width: 300px;
      height: auto;
      border-radius: 25px;
      z-index: 1;
    }

    .ergebnis_gif_container {
      display: none;
    }

    /* Hintergrund-Animation */
    @keyframes floatingHearts {
      0% { transform: translateY(0) scale(0.5); opacity: 1; }
      100% { transform: translateY(-1000px) scale(1.5); opacity: 0; }
    }

    .floating-hearts {
      position: absolute;
      bottom: 0;
      pointer-events: none;
      user-select: none;
      z-index: 0;
      width: 100%;
      height: 100%;
      overflow: hidden;
    }

    .heart {
      position: absolute;
      bottom: 0;
      background-image: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 32 29.6"><path fill="%23FF69B4" d="M23.6 0a9.4 9.4 0 0 0-6.6 2.74A9.4 9.4 0 0 0 10.4 0C4.65 0 0 4.65 0 10.4c0 11.2 16 19.2 16 19.2s16-8 16-19.2C32 4.65 27.35 0 23.6 0z"/></svg>');
      width: 32px;
      height: 29.6px;
      will-change: transform, opacity;
      animation: floatingHearts 5s linear infinite;
      animation-delay: var(--animation-delay, 0s);
      left: var(--left, 50%);
    }
  </style>
</head>
<body onclick="createHeart(event)">

<div class="header_text">Möchtest du mein Valentinstagdate sein? 🐼🐧🍪</div>

<div class="buttons">
  <button class="btn" onclick="antwort('Natürlich, Askim ♥️')">Natürlich, Askim ♥️</button>
  <button class="btn" id="hayir" onmouseover="moveButton()" onclick="antwort('Ich bin klein und lehne ab 🐥')">Ich bin klein und lehne ab 🐥</button>
</div>

<div class="start_gif_container" id="start_gif">
  <img src="https://media1.tenor.com/m/BpMuppPe_YUAAAAd/bhibatsam-cute-kid.gif" alt="Start-GIF">
</div>

<div class="ergebnis_gif_container" id="ergebnis_gif">
  <img src="https://media1.tenor.com/m/7cJG89IA1fEAAAAd/coreaninha.gif" alt="Ergebnis-GIF">
</div>

<div class="floating-hearts">
  <div class="heart" style="--animation-delay: 0s; --left: 10%;"></div>
  <div class="heart" style="--animation-delay: 1s; --left: 20%;"></div>
  <div class="heart" style="--animation-delay: 2s; --left: 30%;"></div>
  <div class="heart" style="--animation-delay: 3s; --left: 40%;"></div>
  <div class="heart" style="--animation-delay: 4s; --left: 50%;"></div>
  <div class="heart" style="--animation-delay: 5s; --left: 60%;"></div>
  <div class="heart" style="--animation-delay: 6s; --left: 70%;"></div>
  <div class="heart" style="--animation-delay: 7s; --left: 80%;"></div>
  <div class="heart" style="--animation-delay: 8s; --left: 90%;"></div>
</div>

<div class="interaktive-herzen"></div>

<script>
  function antwort(antwortText) {
    var headerText = document.querySelector('.header_text');
    var hayirButton = document.getElementById('hayir');
    var buttonsDiv = document.querySelector('.buttons');
    var startGifContainer = document.querySelector('.start_gif_container');
    var ergebnisGifContainer = document.querySelector('.ergebnis_gif_container');

    if (antwortText === 'Natürlich, Askim ♥️') {
      headerText.innerHTML = 'Wir treffen uns am Valentinstag, seni çok seviyorum 🐼🐐🧸♥️';
      hayirButton.style.pointerEvents = 'none';
      buttonsDiv.style.display = 'none';
      startGifContainer.style.display = 'none';
      ergebnisGifContainer.style.display = 'flex';
    }
  }

  function moveButton() {
    var hayirButton = document.getElementById('hayir');
    hayirButton.style.position = 'absolute';
    var randomX = Math.floor(Math.random() * (window.innerWidth - hayirButton.clientWidth));
    var randomY = Math.floor(Math.random() * (window.innerHeight - hayirButton.clientHeight));
    hayirButton.style.left = randomX + 'px';
    hayirButton.style.top = randomY + 'px';
  }

  function createHeart(event) {
    const heart = document.createElement('span');
    heart.style.left = `${event.clientX - 50}px`;
    heart.style.top = `${event.clientY - 50}px`;
    document.querySelector('.interaktive-herzen').appendChild(heart);
    setTimeout(() => heart.remove(), 5000);
  }
</script>

</body>
</html>
