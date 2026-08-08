hi<!DOCTYPE html>
<html>
<head>
  <title>Clap for Medhansh</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin: 0;
      padding-top: 100px;
      height: 100vh;
      background-image: url('medhansh.png.png');
      background-size: cover;
      background-position: center;
      background-attachment: fixed;
    }
    .button-container {
      display: inline-block;
      background-color: rgba(255, 255, 255, 0.9); 
      padding: 20px 40px;
      border-radius: 16px;
      box-shadow: 0 4px 20px rgba(0,0,0,0.3);
    }
    h1 {
      cursor: pointer;
      margin: 0 0 10px 0;
      font-size: 32px;
      -webkit-user-select: none;
      -moz-user-select: none;
      user-select: none;
    }
    h1:active {
      transform: scale(0.98); /* Makes the button look physically pressed */
    }
    .counter-text {
      font-size: 20px;
      font-weight: bold;
      color: #333;
      margin: 0;
      -webkit-user-select: none;
      -moz-user-select: none;
      user-select: none;
    }
    .emoji {
      position: absolute;
      font-size: 40px;
      animation: floatUp 1.5s ease-out forwards;
      pointer-events: none;
    }
    @keyframes floatUp {
      0% { transform: translateY(0) scale(1); opacity: 1; }
      100% { transform: translateY(-250px) scale(1.8); opacity: 0; }
    }
  </style>
</head>
<body>

  <!-- Box containing both the button and the live counter -->
  <div class="button-container">
    <h1 onclick="createClap(event)">👏 Clap for Medhansh 👏</h1>
    <p class="counter-text">Total Claps: <span id="clapCount">0</span></p>
  </div>

  <script>
    // Start the clap counter at 0
    let count = 0;

    function createClap(event) {
      // 1. Increase the count and update the screen
      count = count + 1;
      document.getElementById('clapCount').innerText = count;

      // 2. Create the floating emoji
      const emoji = document.createElement('div');
      emoji.innerText = '👏';
      emoji.className = 'emoji';
      
      emoji.style.left = (event.clientX - 20) + 'px';
      emoji.style.top = (event.clientY - 20) + 'px';
      
      document.body.appendChild(emoji);
      
      setTimeout(() => {
        emoji.remove();
      }, 1500);
    }
  </script>

</body>
</html>
