<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Be My Valentine?</title>
<style>
  body {
    margin: 0;
    font-family: "Poppins", sans-serif;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background: linear-gradient(135deg, #ffd6e8, #ffc2e2, #ffe6f2);
    overflow: hidden;
  }

  .card {
    background: white;
    padding: 40px 30px;
    border-radius: 20px;
    box-shadow: 0 15px 40px rgba(0,0,0,0.1);
    text-align: center;
    max-width: 400px;
    width: 90%;
    position: relative;
  }

  .cat {
    font-size: 60px;
  }

  h1 {
    font-size: 22px;
    margin: 20px 0 30px;
  }

  .buttons {
    position: relative;
    height: 100px;
  }

  button {
    border: none;
    padding: 12px 26px;
    border-radius: 30px;
    font-size: 16px;
    cursor: pointer;
    transition: transform 0.2s ease;
  }

  #yesBtn {
    background: #ff4d88;
    color: white;
    font-weight: bold;
    box-shadow: 0 8px 20px rgba(255, 77, 136, 0.4);
  }

  #yesBtn:hover {
    transform: scale(1.1);
  }

  #noBtn {
    background: #eee;
    color: #333;
    position: absolute;
  }

  .hint {
    margin-top: 20px;
    font-size: 12px;
    color: #777;
  }

  .celebration {
    display: none;
    margin-top: 20px;
  }

  .celebration h2 {
    font-size: 26px;
    margin-bottom: 15px;
  }

  .celebration img {
    width: 100%;
    border-radius: 15px;
  }
</style>
</head>
<body>

<div class="card" id="card">
  <div class="cat">🐱💖</div>
  <h1>Hyy Maluzz will you be my valentine?</h1>

  <div class="buttons">
    <button id="yesBtn">Yes</button>
    <button id="noBtn">No</button>
  </div>

  <div class="hint">"No" seems a bit shy 😈</div>

  <div class="celebration" id="celebration">
    <h2>YAY! 🎉</h2>
    <img src="https://media.giphy.com/media/MDJ9IbxxvDUQM/giphy.gif" alt="Celebration">
  </div>
</div>

<script>
  const noBtn = document.getElementById("noBtn");
  const yesBtn = document.getElementById("yesBtn");
  const celebration = document.getElementById("celebration");

  function moveNoButton() {
    const card = document.querySelector(".card");
    const maxX = card.clientWidth - noBtn.offsetWidth - 20;
    const maxY = 80;

    const randomX = Math.random() * maxX;
    const randomY = Math.random() * maxY;

    noBtn.style.left = randomX + "px";
    noBtn.style.top = randomY + "px";
  }

  noBtn.addEventListener("mouseover", moveNoButton);
  noBtn.addEventListener("click", moveNoButton);

  yesBtn.addEventListener("click", () => {
    celebration.style.display = "block";
    yesBtn.style.display = "none";
    noBtn.style.display = "none";
    document.querySelector(".hint").style.display = "none";
  });

  // Initial position for No button
  moveNoButton();
</script>

</body>
</html>
