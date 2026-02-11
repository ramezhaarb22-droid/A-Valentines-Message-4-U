<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>عيد حب لملوكه 💖</title>
<style>
  body {
    margin: 0;
    padding: 0;
    font-family: 'Arial', sans-serif;
    overflow: hidden;
    background: linear-gradient(to bottom, #ff9a9e, #fad0c4);
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    color: white;
    text-align: center;
  }

  .container {
    z-index: 10;
  }

  input[type="password"] {
    padding: 15px;
    border-radius: 10px;
    border: none;
    font-size: 1.2em;
    margin-bottom: 20px;
    outline: none;
  }

  button {
    padding: 15px 30px;
    border: none;
    border-radius: 15px;
    background-color: #ff4b5c;
    color: white;
    font-size: 1.2em;
    cursor: pointer;
    transition: transform 0.2s;
  }

  button:active {
    animation: shake 0.3s;
  }

  @keyframes shake {
    0% { transform: translate(1px, 1px) rotate(0deg); }
    20% { transform: translate(-2px, -1px) rotate(-1deg); }
    40% { transform: translate(-1px, 2px) rotate(1deg); }
    60% { transform: translate(2px, -1px) rotate(0deg); }
    80% { transform: translate(-1px, 1px) rotate(1deg); }
    100% { transform: translate(1px, -1px) rotate(0deg); }
  }

  .heart {
    position: absolute;
    width: 20px;
    height: 20px;
    background: red;
    transform: rotate(-45deg);
    animation: float 6s linear infinite;
  }

  .heart::before,
  .heart::after {
    content: "";
    position: absolute;
    width: 20px;
    height: 20px;
    background: red;
    border-radius: 50%;
  }

  .heart::before {
    top: -10px;
    left: 0;
  }

  .heart::after {
    left: 10px;
    top: 0;
  }

  @keyframes float {
    0% { transform: translateY(100vh) scale(0.5) rotate(0deg); opacity: 0.7; }
    50% { opacity: 1; }
    100% { transform: translateY(-100vh) scale(1) rotate(360deg); opacity: 0; }
  }

  .hidden {
    display: none;
  }

  .love-message {
    font-size: 2em;
    animation: heartbeat 1s infinite;
  }

  @keyframes heartbeat {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.2); }
  }
</style>
</head>
<body>

<div class="container" id="loginScreen">
  <h1>💖 عيد حب 💖</h1>
  <input type="password" id="password" placeholder="ادخلي الباسور يحبيبتي 🥹💗">
  <br>
  <button onclick="checkPassword()">دخلي 💕</button>
</div>

<div class="container hidden" id="loveScreen">
  <h1 class="love-message">ملوكه يا حبيبتي، أنا بحبك ومقدرش أعيش من غيرك 💖</h1>
</div>

<!-- موسيقى هادئة -->
<audio autoplay loop>
  <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
</audio>

<script>
  const correctPassword = "292009"; // كلمة السر الجديدة

  function checkPassword() {
    const input = document.getElementById('password').value;
    if(input === correctPassword) {
      document.getElementById('loginScreen').classList.add('hidden');
      document.getElementById('loveScreen').classList.remove('hidden');
    } else {
      alert("الباسورد خطأ 😢 جربي تاني!");
    }
  }

  // توليد قلوب عائمة
  function createHeart() {
    const heart = document.createElement('div');
    heart.classList.add('heart');
    heart.style.left = Math.random() * window.innerWidth + 'px';
    heart.style.animationDuration = 4 + Math.random() * 3 + 's';
    heart.style.width = 10 + Math.random() * 30 + 'px';
    heart.style.height = heart.style.width;
    document.body.appendChild(heart);
    setTimeout(() => {
      heart.remove();
    }, 7000);
  }

  setInterval(createHeart, 500);
</script>

</body>
</html>
