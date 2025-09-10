# support
Support openxi
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <title>OpenXI — Техподдержка</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body { 
      font-family: Arial, sans-serif; 
      background: linear-gradient(135deg, #0b0c10, #1f2833); 
      color: #e6e6e6; 
      margin: 0; 
      padding: 0;
    }
    header {
      background: #e63946;
      padding: 20px;
      text-align: center;
      font-size: 22px;
      font-weight: bold;
      letter-spacing: 1px;
    }
    .container {
      max-width: 600px; 
      margin: 30px auto; 
      padding: 25px; 
      background: #111217; 
      border-radius: 16px; 
      box-shadow: 0 10px 40px rgba(0,0,0,0.6);
      text-align: center;
    }
    button {
      display: block; 
      width: 100%; 
      padding: 14px; 
      margin: 12px 0; 
      border: none; 
      border-radius: 8px; 
      font-size: 16px; 
      cursor: pointer; 
      font-weight: bold; 
      color: white;
      transition: transform 0.2s ease, opacity 0.2s ease;
    }
    button:hover { transform: scale(1.03); opacity: 0.9; }
    .btn-complaint { background: #e63946; }
    .btn-support { background: #28a745; }
    .btn-owner { background: #1f77b4; }
    .btn-admin { background: #8e44ad; }
    .hidden { display: none; }
    input, textarea {
      width: 100%; 
      padding: 12px; 
      margin: 8px 0; 
      border-radius: 8px; 
      border: 1px solid #444; 
      background: #1c1f24; 
      color: white; 
      font-size: 15px;
    }
    h2 { margin-top: 10px; color: #66fcf1; }

    /* Модальные окна */
    .modal {
      position: fixed;
      top: 0; left: 0; 
      width: 100%; height: 100%;
      background: rgba(0,0,0,0.7);
      display: none;
      align-items: center;
      justify-content: center;
      z-index: 1000;
    }
    .modal-content {
      background: #1c1f24;
      padding: 20px;
      border-radius: 12px;
      width: 90%;
      max-width: 400px;
      text-align: center;
      box-shadow: 0 5px 25px rgba(0,0,0,0.5);
    }
    .modal-content h3 {
      margin: 0 0 10px 0;
      color: #e63946;
    }
    .close-btn {
      background: #e63946;
      padding: 8px 14px;
      border-radius: 6px;
      cursor: pointer;
      border: none;
      color: white;
      font-weight: bold;
      margin-top: 15px;
    }
  </style>
</head>
<body>
  <header>🌐 OpenXI — Центр поддержки</header>

  <div class="container">
    <button class="btn-complaint" onclick="showComplaintForm()">📢 Подать жалобу</button>
    <button class="btn-support" onclick="openWhatsApp()">💬 Связаться с поддержкой</button>
    <button class="btn-owner" onclick="openModal('ownerModal')">👑 Владелец: Асадбек</button>
    <button class="btn-admin" onclick="openModal('adminModal')">🛡 Главный администратор: Абдурауфов Мухаммад Камол</button>

    <!-- Форма жалобы -->
    <div id="complaintForm" class="hidden">
      <h2>Форма жалобы</h2>
      <input type="text" id="username" placeholder="Ник игрока / пользователя">
      <textarea id="reason" placeholder="Причина жалобы"></textarea>
      <textarea id="details" placeholder="Опишите подробно ситуацию"></textarea>
      <button class="btn-complaint" onclick="sendComplaint()">Отправить жалобу</button>
    </div>
  </div>

  <!-- Модальное окно владельца -->
  <div id="ownerModal" class="modal">
    <div class="modal-content">
      <h3>👑 Владелец</h3>
      <p><b>Имя:</b> Асадбек</p>
      <p><b>Контакт:</b> Только через WhatsApp и почту поддержки</p>
      <button class="close-btn" onclick="closeModal('ownerModal')">Закрыть</button>
    </div>
  </div>

  <!-- Модальное окно администратора -->
  <div id="adminModal" class="modal">
    <div class="modal-content">
      <h3>🛡 Главный администратор</h3>
      <p><b>Имя:</b> Абдурауфов Мухаммад Камол</p>
      <p><b>Контакт:</b> Через систему поддержки OpenXI</p>
      <button class="close-btn" onclick="closeModal('adminModal')">Закрыть</button>
    </div>
  </div>

  <script>
    function showComplaintForm() {
      document.getElementById("complaintForm").classList.toggle("hidden");
    }

    function sendComplaint() {
      const username = document.getElementById("username").value;
      const reason = document.getElementById("reason").value;
      const details = document.getElementById("details").value;

      if (!username || !reason || !details) {
        alert("Заполните все поля!");
        return;
      }

      const subject = encodeURIComponent("Жалоба на игрока: " + username);
      const body = encodeURIComponent(
        "Игрок: " + username + "\nПричина: " + reason + "\nДетали: " + details
      );

      // Жалоба отправляется на твою почту
      window.open("mailto:abdumalikovasadbek401a@gmail.com?subject=" + subject + "&body=" + body, "_blank");
    }

    function openWhatsApp() {
      const phone = "99899100097"; // твой номер
      const message = encodeURIComponent("Здравствуйте, нужна помощь в OpenXI.");
      window.open("https://wa.me/" + phone + "?text=" + message, "_blank");
    }

    function openModal(id) {
      document.getElementById(id).style.display = "flex";
    }
    function closeModal(id) {
      document.getElementById(id).style.display = "none";
    }
  </script>
</body>
</html>
