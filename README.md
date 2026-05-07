# questionario-grazie
Thank-you page with confetti animation for questionnaire completion.
<!DOCTYPE html>
<html lang="it">
<head>
  <meta charset="UTF-8">
  <title>Grazie!</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(135deg, #6dd5ed, #2193b0);
      font-family: Arial, sans-serif;
      overflow: hidden;
      color: white;
      text-align: center;
    }

    h1 {
      font-size: 3em;
      z-index: 2;
    }

    p {
      font-size: 1.5em;
      z-index: 2;
    }

    .confetti {
      position: fixed;
      width: 10px;
      height: 10px;
      background-color: red;
      top: -10px;
      animation: fall linear infinite;
      opacity: 0.8;
    }

    @keyframes fall {
      to {
        transform: translateY(100vh) rotate(720deg);
      }
    }
  </style>
</head>
<body>

  <div>
    <h1>🎉 GRAZIE! 🎉</h1>
    <p>Il questionario è stato completato con successo</p>
  </div>

  <script>
    const colors = ["#ff0a54", "#ff477e", "#ff85a1", "#fbb1bd", "#f9bec7", "#ffd6e0"];

    function createConfetti() {
      const confetti = document.createElement("div");
      confetti.classList.add("confetti");

      confetti.style.left = Math.random() * window.innerWidth + "px";
      confetti.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
      confetti.style.animationDuration = (2 + Math.random() * 3) + "s";
      confetti.style.opacity = Math.random();

      document.body.appendChild(confetti);

      setTimeout(() => {
        confetti.remove();
      }, 5000);
    }

    setInterval(createConfetti, 100);
  </script>

</body>
</html>
