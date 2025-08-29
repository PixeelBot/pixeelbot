<!DOCTYPE html>
<html lang="pl">
<head>
  <meta charset="UTF-8">
  <title>Moja Strona</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    body {
      margin: 0;
      font-family: 'Poppins', sans-serif;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      min-height: 100vh;
      background: linear-gradient(270deg, #ff0080, #7928ca, #2af598);
      background-size: 600% 600%;
      animation: gradientBG 15s ease infinite;
      color: white;
      transition: background 0.5s, color 0.5s;
    }

    @keyframes gradientBG {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }

    .avatar {
      width: 130px;
      height: 130px;
      border-radius: 50%;
      border: 3px solid white;
      margin-bottom: 20px;
      box-shadow: 0px 4px 20px rgba(0,0,0,0.3);
    }

    h1 { font-size: 28px; margin: 10px 0; }
    p { font-size: 16px; opacity: 0.9; margin-bottom: 30px; }

    .links a {
      display: flex;
      align-items: center;
      justify-content: center;
      margin: 10px 0;
      padding: 14px 22px;
      background: rgba(0,0,0,0.4);
      border-radius: 12px;
      color: white;
      text-decoration: none;
      font-size: 18px;
      transition: all 0.3s;
      width: 220px;
    }
    .links a i {
      margin-right: 10px;
    }
    .links a:hover {
      background: rgba(255,255,255,0.2);
      transform: scale(1.05);
    }

    .counter {
      margin-top: 25px;
      font-size: 14px;
      opacity: 0.8;
    }

    .toggle-theme {
      position: absolute;
      top: 20px;
      right: 20px;
      background: rgba(0,0,0,0.5);
      border: none;
      color: white;
      padding: 10px;
      border-radius: 50%;
      cursor: pointer;
    }

    body.light {
      background: #f2f2f2;
      color: #111;
    }
    body.light .links a {
      background: #ddd;
      color: #111;
    }
    body.light .links a:hover {
      background: #bbb;
    }
    body.light .toggle-theme {
      background: #ccc;
      color: black;
    }
  </style>
</head>
<body>
  <button class="toggle-theme"><i class="fas fa-moon"></i></button>

  <img src="https://placekitten.com/200/200" alt="Avatar" class="avatar">
  <h1>Twoja Nazwa</h1>
  <p>Twój opis / bio 🔥</p>

  <div class="links">
    <a href="https://instagram.com"><i class="fab fa-instagram"></i> Instagram</a>
    <a href="https://tiktok.com"><i class="fab fa-tiktok"></i> TikTok</a>
    <a href="https://youtube.com"><i class="fab fa-youtube"></i> YouTube</a>
    <a href="https://twitter.com"><i class="fab fa-twitter"></i> Twitter</a>
  </div>

  <div class="counter">Odwiedziny: <span id="count">0</span></div>

  <script>
    // Dark / Light mode
    const toggleBtn = document.querySelector('.toggle-theme');
    toggleBtn.addEventListener('click', () => {
      document.body.classList.toggle('light');
      toggleBtn.innerHTML = document.body.classList.contains('light') ? '<i class="fas fa-sun"></i>' : '<i class="fas fa-moon"></i>';
    });

    // Licznik odwiedzin (localStorage)
    let count = localStorage.getItem('visits') || 0;
    count++;
    localStorage.setItem('visits', count);
    document.getElementById('count').textContent = count;
  </script>
</body>
</html>
