# CaigivayNPQ
<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Chào bạn!</title>
  <style>
    * { box-sizing: border-box; }
    body {
      margin: 0;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      font-family: "Segoe UI", Arial, sans-serif;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4, #a1c4fd);
      text-align: center;
      padding: 20px;
    }
    .card {
      background: rgba(255, 255, 255, 0.85);
      padding: 40px 30px;
      border-radius: 20px;
      max-width: 520px;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15);
    }
    h1 { margin: 0 0 15px; color: #e84393; font-size: 2rem; }
    p { font-size: 1.15rem; color: #333; line-height: 1.6; margin: 8px 0; }
    #loi { margin-top: 20px; font-style: italic; color: #6c5ce7; min-height: 3em; }
    button {
      margin-top: 20px;
      padding: 10px 22px;
      border: none;
      border-radius: 25px;
      background: #e84393;
      color: #fff;
      font-size: 1rem;
      cursor: pointer;
    }
    button:hover { background: #d63384; }
    #qua { font-size: 4rem; min-height: 5rem; margin-top: 10px; }
    .pop { animation: pop 0.6s ease; }
    @keyframes pop {
      0% { transform: scale(0); opacity: 0; }
      70% { transform: scale(1.3); }
      100% { transform: scale(1); opacity: 1; }
    }
    .roi {
      position: fixed;
      top: -50px;
      font-size: 2rem;
      pointer-events: none;
      animation: roi 3s linear forwards;
    }
    @keyframes roi {
      to { transform: translateY(110vh) rotate(360deg); }
    }
  </style>
</head>
<body>
  <div class="card">
    <h1>👋 Chào bạn!</h1>
    <p>Mình là <b>NPQ</b>.</p>
    <p>Chúc bạn một ngày vui vẻ, hạnh phúc! 🌸</p>
    <p id="loi">Chúc bạn luôn mỉm cười và gặp thật nhiều may mắn ✨</p>
    <button onclick="loiChucMoi()">Nhận thêm lời chúc 🎁</button>
    <div id="qua"></div>
  </div>

  <script>
    const loiChuc = [
      "Chúc bạn luôn mỉm cười và gặp thật nhiều may mắn ✨",
      "Mong hôm nay bạn gặp toàn điều tốt đẹp 🌈",
      "Chúc bạn học tập, làm việc thật hiệu quả 💪",
      "Cười lên nào, bạn tuyệt vời hơn bạn nghĩ đấy 😊",
      "Chúc bạn sức khỏe, bình an và nhiều niềm vui 🍀",
      "Mỗi ngày trôi qua đều là một cơ hội mới, cố lên nhé! 🌞",
      "Chúc mọi điều bạn mong muốn đều trở thành sự thật 🌟"
    ];

    function loiChucMoi() {
      const i = Math.floor(Math.random() * loiChuc.length);
      document.getElementById("loi").textContent = loiChuc[i];

      const hoa = ["💐", "🌹", "🌷", "🌻", "🌸"];
      const qua = document.getElementById("qua");
      qua.textContent = hoa[Math.floor(Math.random() * hoa.length)];
      qua.classList.remove("pop");
      void qua.offsetWidth;
      qua.classList.add("pop");

      for (let k = 0; k < 15; k++) {
        const b = document.createElement("span");
        b.className = "roi";
        b.textContent = hoa[Math.floor(Math.random() * hoa.length)];
        b.style.left = Math.random() * 100 + "vw";
        b.style.animationDelay = Math.random() * 1 + "s";
        document.body.appendChild(b);
        setTimeout(() => b.remove(), 4500);
      }
    }
  </script>
</body>
</html>
