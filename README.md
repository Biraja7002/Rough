
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kyuutuverse 🐱💗</title>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

:root {
  --pink: #ff80b5;
  --dark-pink: #e84393;
  --white: #ffffff;
}

body {
  min-height: 100vh;
  font-family: "Trebuchet MS", Arial, sans-serif;
  color: white;
  text-align: center;
  overflow-x: hidden;

  /* Replace cat-background.jpg with your image filename */
  background:
    linear-gradient(
      rgba(49, 15, 55, 0.48),
      rgba(92, 24, 76, 0.58)
    ),
    url("cat-background.jpg");

  background-size: cover;
  background-position: center;
  background-attachment: fixed;
  background-repeat: no-repeat;
}

.container {
  position: relative;
  z-index: 2;
  width: min(900px, 92%);
  margin: auto;
  padding: 35px 0 60px;
}

.card {
  margin: 22px auto;
  padding: 25px 18px;
  border: 1px solid rgba(255,255,255,.4);
  border-radius: 25px;
  background: rgba(255, 240, 249, 0.14);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  box-shadow: 0 8px 35px rgba(0,0,0,.15);
}

h1 {
  font-size: clamp(2.3rem, 8vw, 4.5rem);
  margin: 12px 0;
  text-shadow: 0 4px 20px #ff69b4;
}

h2 {
  margin-bottom: 15px;
}

p {
  line-height: 1.8;
}

.cat {
  position: fixed;
  bottom: -100px;
  z-index: 1;
  pointer-events: none;
  animation: floatUp linear forwards;
  filter: drop-shadow(0 3px 8px rgba(0,0,0,.2));
}

@keyframes floatUp {
  0% {
    transform: translateY(0) rotate(-10deg);
    opacity: 0;
  }
  15% {
    opacity: .95;
  }
  85% {
    opacity: .85;
  }
  100% {
    transform: translateY(-120vh) rotate(15deg);
    opacity: 0;
  }
}

button {
  border: none;
  border-radius: 30px;
  padding: 13px 22px;
  margin: 8px;
  background: linear-gradient(135deg, #ff91c8, #ff5ca8);
  color: white;
  font-size: 1rem;
  font-weight: bold;
  cursor: pointer;
  box-shadow: 0 5px 18px rgba(255, 80, 160, .3);
  transition: transform .2s;
}

button:hover {
  transform: translateY(-3px) scale(1.03);
}

#countdown {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 12px;
  margin: 20px 0;
}

.time-box {
  min-width: 75px;
  padding: 15px 10px;
  border-radius: 16px;
  background: rgba(255,255,255,.2);
}

.time-box strong {
  display: block;
  font-size: 1.8rem;
}

.time-box span {
  font-size: .8rem;
}

#message {
  min-height: 55px;
  margin-top: 15px;
  font-size: 1.1rem;
}

footer {
  padding: 20px;
  font-size: .9rem;
}

@media (max-width: 600px) {
  .container {
    padding-top: 20px;
  }

  .card {
    padding: 22px 14px;
  }

  body {
    background-attachment: scroll;
  }
}

@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
</style>
</head>

<body>

<main class="container">

  <header class="card">
    <div style="font-size:4rem" aria-hidden="true">🐱🎀🐾</div>
    <p>WELCOME TO A LITTLE WORLD MADE FOR</p>
    <h1>Anuska 💗</h1>
    <p>Also known as my adorable Kyuutu 🐈</p>
    <p>A tiny universe filled with cats, hearts and memories.</p>
    <button id="surpriseBtn">Open your surprise 💌</button>
    <p id="message" aria-live="polite"></p>
  </header>

  <section class="card">
    <h2>🎂 Birthday Countdown 🎂</h2>
    <p>Counting down to your special day!</p>

    <div id="countdown" aria-live="polite">
      <div class="time-box">
        <strong id="days">--</strong>
        <span>Days</span>
      </div>
      <div class="time-box">
        <strong id="hours">--</strong>
        <span>Hours</span>
      </div>
      <div class="time-box">
        <strong id="minutes">--</strong>
        <span>Minutes</span>
      </div>
      <div class="time-box">
        <strong id="seconds">--</strong>
        <span>Seconds</span>
      </div>
    </div>

    <p>📅 5 October 2026</p>
  </section>

  <section class="card">
    <h2>🐾 Cat Paradise 🐾</h2>
    <p>
      Every little cat in this universe carries a tiny heart
      and a little reminder that you are special. 💕
    </p>
    <button id="catBtn">Send me a kitty! 🐈</button>
    <button id="heartBtn">Make it rain hearts 💗</button>
    <p id="catMessage" aria-live="polite"></p>
  </section>

  <section class="card">
    <h2>💌 A Little Message For You</h2>
    <p>
      Dear Anuska,
      <br>
      May your days be filled with laughter, peaceful moments,
      cute little surprises and countless reasons to smile.
      <br>
      This little website is made especially for you.
      <br><br>
      Happy Birthday, Kyuutu! 🎂🐱💗
      <br>
      With love,<br>
      Biraja ❤️
    </p>
  </section>

  <footer>
    Made with 💗 by Biraja, just for Anuska 🐈
  </footer>

</main>

<script>
const birthday = new Date("2026-10-05T00:00:00+05:30");

function updateCountdown() {
  const now = Date.now();
  const distance = birthday.getTime() - now;

  if (distance <= 0) {
    document.getElementById("countdown").innerHTML =
      "<h2>Happy Birthday, Anuska! 🎂💗🐱</h2>";
    return;
  }

  document.getElementById("days").textContent =
    Math.floor(distance / 86400000);

  document.getElementById("hours").textContent =
    Math.floor((distance % 86400000) / 3600000);

  document.getElementById("minutes").textContent =
    Math.floor((distance % 3600000) / 60000);

  document.getElementById("seconds").textContent =
    Math.floor((distance % 60000) / 1000);
}

updateCountdown();
setInterval(updateCountdown, 1000);

const floatingEmojis = ["🐱", "🐈", "💗", "💕", "🐾", "🎀", "✨"];

function createFloatingEmoji(emoji) {
  const item = document.createElement("span");

  item.className = "cat";
  item.textContent = emoji;
  item.style.left = Math.random() * 94 + "vw";
  item.style.fontSize = (22 + Math.random() * 25) + "px";
  item.style.animationDuration = (6 + Math.random() * 5) + "s";

  document.body.appendChild(item);

  item.addEventListener("animationend", () => item.remove());
}

setInterval(() => {
  const emoji = floatingEmojis[
    Math.floor(Math.random() * floatingEmojis.length)
  ];
  createFloatingEmoji(emoji);
}, 650);

document.getElementById("surpriseBtn").addEventListener("click", () => {
  document.getElementById("message").textContent =
    "Surprise, Kyuutu! 🐱💗 You deserve all the smiles, hugs and happiness in the world! 🎀";
  burst("💗", 18);
});

document.getElementById("catBtn").addEventListener("click", () => {
  document.getElementById("catMessage").textContent =
    "Meowww! A tiny kitty has arrived just for you! 🐈💕";
  burst("🐱", 8);
});

document.getElementById("heartBtn").addEventListener("click", () => {
  burst("💗", 25);
});

function burst(emoji, amount) {
  for (let i = 0; i < amount; i++) {
    setTimeout(() => createFloatingEmoji(emoji), i * 90);
  }
}
</script>

</body>
</html>
