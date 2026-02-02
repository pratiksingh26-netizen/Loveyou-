
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>My Heart Chooses You 💖</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
* { box-sizing: border-box; }

body {
  margin: 0;
  height: 100vh;
  font-family: 'Poppins', sans-serif;
  background: linear-gradient(180deg, #ff9a9e, #fad0c4);
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
}

.glow {
  position: absolute;
  width: 300px;
  height: 300px;
  background: rgba(255,255,255,0.25);
  filter: blur(80px);
  animation: pulse 4s infinite;
}

@keyframes pulse {
  0% {transform: scale(1);}
  50% {transform: scale(1.2);}
  100% {transform: scale(1);}
}

.card {
  position: relative;
  background: rgba(255,255,255,0.18);
  backdrop-filter: blur(18px);
  border-radius: 30px;
  padding: 35px 25px;
  width: 90%;
  max-width: 400px;
  text-align: center;
  color: white;
  box-shadow: 0 30px 60px rgba(0,0,0,0.25);
  animation: fadeUp 1.8s ease;
}

@keyframes fadeUp {
  from {opacity:0; transform: translateY(40px);}
  to {opacity:1; transform: translateY(0);}
}

h1 {
  font-size: 2.2em;
  margin-bottom: 10px;
}

#typing {
  font-size: 1.05em;
  line-height: 1.6;
  min-height: 110px;
  margin-top: 10px;
}

.buttons {
  position: relative;
  height: 90px;
  margin-top: 25px;
}

button {
  padding: 14px 28px;
  border-radius: 40px;
  border: none;
  font-size: 1em;
  cursor: pointer;
  transition: 0.4s;
}

#yes {
  background: #ff2e63;
  color: white;
}

#no {
  background: rgba(255,255,255,0.85);
  color: #444;
  position: absolute;
  right: 0;
}

button:hover {
  transform: scale(1.12);
}

#convince {
  margin-top: 18px;
  font-size: 0.95em;
  opacity: 0.9;
}

/* Hearts */
.heart {
  position: absolute;
  font-size: 22px;
  animation: floatUp 5s linear infinite;
}

@keyframes floatUp {
  from {transform: translateY(0); opacity: 1;}
  to {transform: translateY(-700px); opacity: 0;}
}
</style>
</head>

<body>

<div class="glow"></div>

<div class="card" id="card">
  <h1>Muskan Mahi 💕</h1>

  <div id="typing"></div>

  <div class="buttons">
    <button id="yes">YES 💖</button>
    <button id="no">NO 🙈</button>
  </div>

  <div id="convince"></div>
</div>

<script>
// Romantic typing message
const confession = [
  "Some people come into our lives unexpectedly…",
  "and slowly, without realizing it,",
  "they become our favorite thought.",
  "",
  "Muskan, you are that person for me.",
  "Will you be my Valentine? 💘"
].join(" ");

let i = 0;
function typeConfession() {
  if (i < confession.length) {
    document.getElementById("typing").innerHTML += confession.charAt(i);
    i++;
    setTimeout(typeConfession, 45);
  }
}
typeConfession();

// NO button destiny logic
const noBtn = document.getElementById("no");
const convince = document.getElementById("convince");

const softLines = [
  "My heart already belongs to you 🥺",
  "Even destiny is smiling right now 💞",
  "You feel it too, don’t you? 😌",
  "Some choices are made by the heart 💓",
  "NO just means you’re teasing me 😉"
];

let idx = 0;

noBtn.addEventListener("click", () => {
  const x = Math.random() * 220;
  const y = Math.random() * 50;
  noBtn.style.transform = `translate(-${x}px, ${y}px)`;

  convince.innerText = softLines[idx];
  idx = (idx + 1) % softLines.length;
});

// YES — final love screen
document.getElementById("yes").addEventListener("click", () => {
  document.body.innerHTML = `
    <div class="glow"></div>
    <div class="card">
      <h1>✨ Best Decision Ever ✨</h1>
      <p style="font-size:1.5em; line-height:1.6; margin-top:15px;">
        Muskan 💖<br>
        You are my Valentine,<br>
        today and always.<br><br>
        I Love You ❤️
      </p>
    </div>
  `;
  setInterval(createHeart, 180);
});

function createHeart() {
  const heart = document.createElement("div");
  heart.className = "heart";
  heart.innerHTML = "❤️";
  heart.style.left = Math.random() * window.innerWidth + "px";
  heart.style.bottom = "0px";
  document.body.appendChild(heart);
  setTimeout(() => heart.remove(), 5000);
}
</script>

</body>
</html>
