<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>OKM INDUSTRIES</title>
  <style>
    body {
      font-family: 'Arial', sans-serif;
      background: #f0f0f0;
      text-align: center;
      padding: 20px;
      overflow: hidden;
    }
    h1 {
      color: #444;
    }
    .game-container {
      display: grid;
      grid-template-columns: repeat(7, 100px); /* 7 kolom */
      grid-template-rows: repeat(6, 150px);  /* 6 baris */
      gap: 20px;
      justify-content: center;
      margin-top: 30px;
    }
    .card {
      width: 100px;
      height: 150px;
      background: #ff6f61;
      border-radius: 10px;
      display: flex;
      justify-content: center;
      align-items: center;
      cursor: pointer;
      transform: perspective(600px) rotateY(0deg);
      transform-style: preserve-3d;
      transition: transform 0.6s;
    }
    .card.flipped {
      transform: perspective(600px) rotateY(180deg);
    }
    .card .front,
    .card .back {
      position: absolute;
      width: 100%;
      height: 100%;
      border-radius: 10px;
      backface-visibility: hidden;
    }
    .card .front {
      background: #ff6f61;
      color: white;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 24px;
    }
    .card .back {
      background: #fff;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 16px;
      transform: rotateY(180deg);
    }
    .card img {
      width: 100%;
      border-radius: 10px;
    }
    footer {
      margin-top: 40px;
      font-size: 14px;
      color: #777;
    }
    .music-embed {
      display: none;
    }
    .start-button {
      margin-top: 20px;
      padding: 10px 20px;
      background-color: #ff5500;
      color: white;
      border: none;
      font-size: 18px;
      cursor: pointer;
    }
    .start-button:hover {
      background-color: #ff3300;
    }
    /* Menambahkan style untuk tampilan jumlah salah pilih */
    .wrong-count {
      font-size: 24px;
      color: #ff5500;
      font-weight: bold;
      position: absolute;
      top: 20px;
      left: 20px;
    }
    /* Animasi meriah saat memilih kartu yang benar */
    .celebrate {
      position: relative;
    }
    .celebrate::before {
      content: "🌸";
      position: absolute;
      top: -50px;
      left: 50%;
      transform: translateX(-50%);
      font-size: 30px;
      animation: flowerRain 2s ease-out forwards;
    }

    /* Banyak bunga yang berhamburan */
    .celebrate .flower {
      position: absolute;
      top: -50px;
      left: 50%;
      transform: translateX(-50%);
      font-size: 20px;
      opacity: 1;
      animation: flowerFall 3s ease-out infinite;
    }

    @keyframes flowerRain {
      0% {
        top: -50px;
        opacity: 1;
      }
      100% {
        top: 80%;
        opacity: 0;
      }
    }

    /* Animasi jatuhnya bunga */
    @keyframes flowerFall {
      0% {
        transform: translateX(0) translateY(0);
        opacity: 1;
      }
      100% {
        transform: translateX(var(--random-x)) translateY(100vh);
        opacity: 0;
      }
    }
  </style>
</head>
<body>
  <h1>Temukan Monyet di bawah ini</h1>
  <p>Coba klik salah satu kartu untuk membaliknya!</p>

  <!-- Tombol Start Game yang akan memulai permainan dan musik -->
  <button class="start-button" onclick="startGame()">Start Game</button>

  <!-- Menambahkan musik latar dari SoundCloud, disembunyikan terlebih dahulu -->
  <iframe class="music-embed" width="100%" height="300" scrolling="no" frameborder="no" allow="autoplay" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/310640631&color=%23ff5500&auto_play=true&hide_related=false&show_comments=false&show_user=true&show_reposts=false&show_teaser=true&visual=true"></iframe>

  <!-- Menampilkan jumlah salah pilih -->
  <div class="wrong-count">Salah Pilih: <span id="wrongCount">0</span></div>

  <div class="game-container">
    <!-- Kartu-kartu yang akan dibalik -->
    <div class="card" onclick="flipCard(this)">
      <div class="front">?</div>
      <div class="back">😜 Salah!</div>
    </div>
    <div class="card" onclick="flipCard(this)">
        <div class="front">?</div>
        <div class="back">😜 Salah!</div>
      </div><div class="card" onclick="flipCard(this)">
        <div class="front">?</div>
        <div class="back">😜 Salah!</div>
      </div><div class="card" onclick="flipCard(this)">
        <div class="front">?</div>
        <div class="back">😜 Salah!</div>
      </div><div class="card" onclick="flipCard(this)">
        <div class="front">?</div>
        <div class="back">😜 Salah!</div>
      </div><div class="card" onclick="flipCard(this)">
        <div class="front">?</div>
        <div class="back">😜 Salah!</div>
      </div><div class="card" onclick="flipCard(this)">
        <div class="front">?</div>
        <div class="back">😜 Salah!</div>
      </div><div class="card" onclick="flipCard(this)">
        <div class="front">?</div>
        <div class="back">😜 Salah!</div>
      </div><div class="card" onclick="flipCard(this)">
        <div class="front">?</div>
        <div class="back">😜 Salah!</div>
      </div><div class="card" onclick="flipCard(this)">
        <div class="front">?</div>
        <div class="back">😜 Salah!</div>
      </div><div class="card" onclick="flipCard(this)">
        <div class="front">?</div>
        <div class="back">😜 Salah!</div>
      </div><div class="card" onclick="flipCard(this)">
        <div class="front">?</div>
        <div class="back">😜 Salah!</div>
      </div>
      <div class="card" onclick="flipCard(this)">
        <div class="front">?</div>
        <div class="back">😜 Salah!</div>
      </div><div class="card" onclick="flipCard(this)">
        <div class="front">?</div>
        <div class="back">😜 Salah!</div>
      </div><div class="card" onclick="flipCard(this)">
        <div class="front">?</div>
        <div class="back">😜 Salah!</div>
      </div><div class="card" onclick="flipCard(this)">
        <div class="front">?</div>
        <div class="back">😜 Salah!</div>
      </div><div class="card" onclick="flipCard(this)">
        <div class="front">?</div>
        <div class="back">😜 Salah!</div>
      </div>
    <div class="card" onclick="flipCard(this)">
      <div class="front">?</div>
      <div class="back">😜 Salah!</div>
    </div>
    <!-- Tambahkan lebih banyak kartu di sini sesuai kebutuhan -->
    
    <!-- Foto dia di baris 4 kolom 7 -->
    <div class="card" onclick="flipCard(this)">
      <div class="front">?</div>
      <div class="back">
        <img src="foto-dia.jpg" alt="Foto Dia">
      </div>
    </div>
    <div class="card" onclick="flipCard(this)">
        <div class="front">?</div>
        <div class="back">😜 Salah!</div>
      </div>
      <div class="card" onclick="flipCard(this)">
        <div class="front">?</div>
        <div class="back">😜 Salah!</div>
      </div>
  </div>
  
  <footer>&copy; 2024 - Game Buatan Khusus 😏</footer>

  <script>
    let wrongCount = 0;

    function flipCard(card) {
      card.classList.toggle('flipped');
      
      // Periksa apakah kartu yang dibalik benar atau salah
      if (card.querySelector('.back').textContent === '😜 Salah!') {
        // Menambah jumlah kesalahan
        wrongCount++;
        document.getElementById('wrongCount').textContent = wrongCount;
      } else {
        // Menambahkan banyak bunga yang berhamburan
        let flowers = '';
        for (let i = 0; i < 20; i++) {
          flowers += `<span class="flower" style="--random-x: ${Math.random() * 200 - 100}px;">🌸</span>`;
        }
        card.innerHTML += `<div class="celebrate">${flowers}</div>`;
        
        // Menghapus animasi setelah selesai
        setTimeout(() => {
          card.querySelector('.celebrate').remove();
        }, 3000);
      }
    }

    function startGame() {
      const musicEmbed = document.querySelector('.music-embed');
      musicEmbed.style.display = 'none';  // Pastikan tetap tersembunyi

      const startButton = document.querySelector('.start-button');
      startButton.style.display = 'none';

      const iframe = musicEmbed.contentWindow;
      iframe.postMessage('{"method":"play"}', '*');
    }
  </script>
</body>
</html>
