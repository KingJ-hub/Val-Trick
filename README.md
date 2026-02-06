<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Be My Valentine 💘</title>

  <style>
    body {
      margin: 0;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(135deg, #ff4d6d, #ff8fa3);
      font-family: Arial, sans-serif;
      color: white;
      text-align: center;
    }

    .card {
      background: rgba(0,0,0,0.25);
      padding: 25px;
      border-radius: 20px;
      width: 90%;
      max-width: 420px;
    }

    .intro-media {
      width: 100%;
      border-radius: 15px;
      margin-bottom: 15px;
    }

    h1 {
      margin-bottom: 10px;
    }

    .buttons {
      display: flex;
      justify-content: center;
      gap: 15px;
      margin-top: 20px;
      flex-wrap: wrap;
    }

    button {
      border: none;
      border-radius: 12px;
      cursor: pointer;
      font-size: 18px;
      padding: 12px 26px;
      transition: all 0.3s ease;
    }

    #yesBtn {
      background: #2ecc71;
      color: white;
      transform: scale(1);
    }

    #noBtn {
      background: #e74c3c;
      color: white;
      transform: scale(1);
    }
  </style>
</head>
<body>

  <!-- Background Music -->
  <audio autoplay loop>
    <!-- Replace this with your own music file -->
    <source src="music.mp3" type="audio/mpeg">
  </audio>

  <div class="card">
    <!-- INTRO IMAGE (replace src) -->
    <img 
      src="intro.jpg" 
      alt="Valentine Intro" 
      class="intro-media"
    >

    <!-- OR VIDEO (use instead of image if you want)
    <video class="intro-media" autoplay loop muted>
      <source src="intro.mp4" type="video/mp4">
    </video>
    -->

    <h1>Will you be my Valentine? 💖</h1>
    <p>Read my Valentine message 💌</p>

    <div class="buttons">
      <button id="yesBtn">Yes 💕</button>
      <button id="noBtn">No 🙃</button>
    </div>
  </div>

  <script>
    let yesScale = 1;
    let noScale = 1;

    const yesBtn = document.getElementById("yesBtn");
    const noBtn = document.getElementById("noBtn");

    noBtn.addEventListener("click", () => {
      yesScale += 0.25;
      noScale -= 0.15;

      if (noScale <= 0.2) {
        noBtn.style.display = "none";
      }

      yesBtn.style.transform = `scale(${yesScale})`;
      noBtn.style.transform = `scale(${noScale})`;
    });

    yesBtn.addEventListener("click", () => {
      document.body.innerHTML = `
        <div style="
          display:flex;
          justify-content:center;
          align-items:center;
          height:100vh;
          text-align:center;
          background: linear-gradient(135deg, #ff4d6d, #ff8fa3);
          color:white;
          font-family: Arial;
          padding:20px;
        ">
          <h1>Yayyy!! 💘🥰<br>You’re my Valentine ❤️</h1>
        </div>
      `;
    });
  </script>

</body>
</html>
