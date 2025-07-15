<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CC's Love Letter</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Pacifico&family=Poppins&display=swap');

    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      font-family: 'Poppins', sans-serif;
      background: linear-gradient(135deg, #ffe6e6, #fff0f5);
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      overflow: hidden;
      position: relative;
    }

    .container, .letter {
      background: rgba(255, 255, 255, 0.8);
      padding: 30px;
      border-radius: 15px;
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
      max-width: 600px;
      width: 90%;
      text-align: center;
      animation: fadeIn 1s ease-in-out;
      z-index: 2;
    }

    h1 {
      font-family: 'Pacifico', cursive;
      color: #ff5e7e;
    }

    input {
      padding: 12px;
      width: 80%;
      border-radius: 10px;
      border: none;
      margin: 15px 0;
      font-size: 1rem;
    }

    button {
      background: #ff5e7e;
      color: white;
      padding: 10px 20px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      font-size: 1rem;
      transition: transform 0.3s;
    }

    button:hover {
      transform: scale(1.05);
    }

    .letter {
      display: none;
      font-family: 'Poppins', sans-serif;
      color: #444;
      text-align: left;
      animation: pageTurn 1s ease forwards;
    }

    .letter h2 {
      font-family: 'Pacifico', cursive;
      color: #d94f70;
    }

    .qr {
      margin-top: 20px;
      text-align: center;
    }

    .qr img {
      width: 120px;
      height: 120px;
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }

    @keyframes pageTurn {
      0% { transform: rotateY(90deg); opacity: 0; }
      100% { transform: rotateY(0deg); opacity: 1; }
    }

    .hearts {
      position: absolute;
      width: 100%;
      height: 100%;
      top: 0;
      left: 0;
      overflow: hidden;
      z-index: 1;
      pointer-events: none;
    }

    .heart {
      position: absolute;
      width: 20px;
      height: 20px;
      background: red;
      transform: rotate(45deg);
      animation: float 6s linear infinite;
    }

    .heart::before,
    .heart::after {
      content: '';
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
      left: -10px;
      top: 0;
    }

    @keyframes float {
      0% {
        bottom: -10%;
        left: calc(100% * var(--pos));
        opacity: 1;
        transform: scale(1) rotate(45deg);
      }
      100% {
        bottom: 100%;
        left: calc(100% * var(--pos) + 20px);
        opacity: 0;
        transform: scale(0.5) rotate(45deg);
      }
    }
  </style>
</head>
<body>
  <div class="hearts">
    <!-- Floating hearts -->
    <div class="heart" style="--pos:0.1;"></div>
    <div class="heart" style="--pos:0.3;"></div>
    <div class="heart" style="--pos:0.5;"></div>
    <div class="heart" style="--pos:0.7;"></div>
    <div class="heart" style="--pos:0.9;"></div>
  </div>

  <div class="container" id="inputPage">
    <h1>💌 CC's Love Letter 💌</h1>
    <p>Hey love, before you open this letter, tell me your name.</p>
    <input type="text" id="partnerName" placeholder="Your name here...">
    <br>
    <button onclick="openLetter()">Open Letter</button>
  </div>

  <div class="letter" id="letterPage">
    <h2 id="greeting"></h2>
    <p>
      This letter wasn’t planned at all. It’s completely impromptu, straight from my heart to yours. But after you surprised me with flowers and snacks for our 3-month mark (seriously, how do you keep outdoing yourself?), I figured it’s my turn to give you something from me.
    </p>
    <p>
      So here it is, my gift to you. Words. Raw and unfiltered. Because in this little journey we’re on—<em>our</em> journey—I’ve decided that I’m going to be more affectionate than you. I <strong>will</strong> win this. You hear me? I’m competitive like that. You bring snacks, I bring soul. <strong>Mother fucker.</strong>
    </p>
    <p>
      Thank you for being the person you are—patient with me even when I’m chaotic and impulsive. You’ve seen my rough edges and stayed, and that’s a kind of love that feels rare. Please never lose faith in yourself, especially when life throws you off course. I’ll always be here to remind you of your strength, even when you can’t see it.
    </p>
    <p>
      I still think about the little moments that made me fall for you harder. That time you held my hand when everything felt like it was spinning? I knew then—you were my calm in the storm. And yes, I’ll <em>never</em> forget the Asador moment. Every ride, every touch, every weird little laugh, it’s all part of this beautiful, strange, and exciting thing we’re building together.
    </p>
    <p>
      The future’s uncertain, sure. But my heart’s made its choice. I’m in this. Fully. I want to keep learning you, laughing with you, fighting for us—even when it’s not easy. Especially then.
    </p>
    <p>
      You see something in me, and I see something extraordinary in you too. So let’s keep showing up, lifting each other up, loving hard, even when the road gets bumpy. And just so you know, this affectionate war isn’t over. I’m just getting started.
    </p>
    <p style="margin-top: 30px;">With all my chaotic, stubborn, competitive love, <br><strong>CC</strong></p>
    <div class="qr">
      <p>Scan this for a lil' surprise 🎶</p>
      <img src="https://api.qrserver.com/v1/create-qr-code/?size=120x120&data=https://video-link-generator.replit.app/v/wrqmj860v9isc1974csc4n" alt="QR Code">
    </div>
  </div>

  <script>
    function openLetter() {
      const name = document.getElementById("partnerName").value.trim().toLowerCase();
      if(name === "javier") {
        document.getElementById("greeting").innerHTML = `Dear Javier,`;
        document.getElementById("inputPage").style.display = "none";
        document.getElementById("letterPage").style.display = "block";
      } else {
        alert("Nice try, but this isn't for you 💌");
      }
    }
  </script>
</body>
</html>
