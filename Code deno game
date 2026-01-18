<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<title>Jump Runner</title>

<style>
body {
  margin: 0;
  font-family: Arial, Tahoma;
  background: linear-gradient(135deg, #1e3c72, #2a5298);
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.game-box {
  background: #ffffff;
  border-radius: 16px;
  padding: 20px;
  width: 700px;
  box-shadow: 0 10px 30px rgba(0,0,0,0.3);
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 10px;
}

.header h2 {
  margin: 0;
}

#score {
  font-weight: bold;
}

#game {
  position: relative;
  height: 220px;
  background: linear-gradient(#e3f2fd, #ffffff);
  border-radius: 12px;
  overflow: hidden;
  border: 2px solid #ddd;
}

#player {
  position: absolute;
  bottom: 20px;
  left: 60px;
  width: 40px;
  height: 40px;
  background: radial-gradient(circle at top left, #00e5ff, #006064);
  border-radius: 50%;
}

.jump {
  animation: jump 0.55s ease-out;
}

@keyframes jump {
  0% { bottom: 20px; }
  50% { bottom: 120px; }
  100% { bottom: 20px; }
}

.obstacle {
  position: absolute;
  bottom: 20px;
  right: -30px;
  width: 30px;
  height: 50px;
  background: linear-gradient(#ff7043, #bf360c);
  border-radius: 6px;
}

.shop {
  margin-top: 15px;
  padding-top: 10px;
  border-top: 1px solid #eee;
}

.product {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 6px 0;
}

.product button {
  background: #2a5298;
  color: #fff;
  border: none;
  padding: 6px 12px;
  border-radius: 6px;
  cursor: pointer;
}

.product button:hover {
  background: #1e3c72;
}
</style>
</head>

<body>

<div class="game-box">
  <div class="header">
    <h2>Jump Runner</h2>
    <div>النقاط: <span id="score">0</span></div>
  </div>

  <div id="game">
    <div id="player"></div>
    <div class="obstacle" id="obstacle"></div>
  </div>

  <div class="shop">
    <strong>منتجات مقترحة</strong>

    <div class="product">
      🎮 يد تحكم ألعاب
      <button onclick="window.open('PUT_LINK_HERE')">عرض</button>
    </div>

    <div class="product">
      ⌨️ كيبورد ألعاب
      <button onclick="window.open('PUT_LINK_HERE')">عرض</button>
    </div>
  </div>
</div>

<script>
const player = document.getElementById("player");
const obstacle = document.getElementById("obstacle");
const scoreEl = document.getElementById("score");

let score = 0;
let pos = 700;

document.addEventListener("keydown", e => {
  if (e.code === "Space" && !player.classList.contains("jump")) {
    player.classList.add("jump");
    setTimeout(() => player.classList.remove("jump"), 550);
  }
});

setInterval(() => {
  pos -= 6;
  obstacle.style.right = pos + "px";

  if (pos < -30) {
    pos = 700;
    score++;
    scoreEl.textContent = score;
  }

  const playerBottom = parseInt(getComputedStyle(player).bottom);
  if (pos < 100 && pos > 60 && playerBottom < 60) {
    alert("انتهت اللعبة! نقاطك: " + score);
    score = 0;
    scoreEl.textContent = score;
    pos = 700;
  }
}, 20);
</script>

</body>
</html>
