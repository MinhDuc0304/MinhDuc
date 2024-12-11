<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;500&display=swap" rel="stylesheet">
  <title>Tràn bộ nhớ</title> 
  <link rel="stylesheet" href="./style.css">

</head>

<body>

  <h1>MĐ có điều muốn nói</h1>
  <button onclick="generateRandomNotifications()">Nhấn đây nè</button>
  <script src="./script.js"></script>
</body>

</html>
const messages = [
  "MĐ nhớ nghan quá 😭😭"
];

function generateRandomNotifications() {
  const notificationCount = 100;

  for (let i = 0; i < notificationCount; i++) {
    setTimeout(() => {
      const notification = document.createElement('div');
      notification.className = 'notification';

      const randomMessage = messages[Math.floor(Math.random() * messages.length)];
      notification.innerHTML = `
        <div class="notification-header">
          <button class="minimize-btn" onclick="minimizeNotification(this)">–</button>
          <span>Tràn ngập bộ</span>
        </div>
        <p>${randomMessage}</p>
      `;

      const x = Math.random() * (window.innerWidth - 240);
      const y = Math.random() * (window.innerHeight - 160);
      notification.style.left = `${x}px`;
      notification.style.top = `${y}px`;

      document.body.appendChild(notification);
    }, i * 200);
  }
}

function minimizeNotification(button) {
  const notification = button.closest('.notification');
  notification.style.display = 'none'; 
}

document.addEventListener("DOMContentLoaded", function () {
  var encodedText = '&#68;&#101;&#115;&#105;&#103;&#110;&#32;&#98;&#121;&#32;&#80;&#97;&#110;&#98;&#97;&#112;';
  var footer = document.createElement("a");
  footer.innerHTML = encodedText; 
  document.body.appendChild(footer); 
  body {
  margin: 0;
  padding: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: #eeeeee;
  font-family: Arial, sans-serif;
  overflow: hidden;
}

h1 {
  position: fixed;
  top: 30px;
  left: 50%;
  font-size: 50px;
  transform: translateX(-50%);
}
a {
  position: fixed;
  bottom: 0;
  text-align: center;
  font-size: 14px;
  color: #333;
}
button {
  position: absolute;
  z-index: 1;
  padding: 15px 30px;
  font-size: 18px;
  font-family: 'Arial', 'Helvetica', sans-serif;
  background-color: #0a2b57;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background-color: #1b53a7;
}

.notification {
  position: absolute;
  width: 240px;
  height: 160px;
  background-color: #FFB6C1;
  color: rgb(0, 0, 0);
  font-size: 16px;
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  box-sizing: border-box;
  z-index: 2;
  border: 4px solid #ffffff;
}

.notification-header {
  display: flex;
  justify-content: flex-end;
  align-items: center;
  width: 100%;
  padding: 5px;
  background-color: #ffffff;
  border-radius: 5px 5px 0 0;
  color: white;
  font-weight: bold;
  box-sizing: border-box;
}

.notification-header span {
  color: rgb(0, 0, 0);
  font-family: 'Arial', 'Helvetica', sans-serif;
  text-align: center;
  flex-grow: 1;
}

.notification p {
  margin: 0;
  text-align: center;
  padding: 10px;
  flex-grow: 1;
  display: flex;
  font-family: 'Arial', 'Helvetica', sans-serif;
  font-style: normal;
  justify-content: center;
  align-items: center;
  height: 100%;
}

.minimize-btn {
  font-size: 20px;
  cursor: pointer;
  padding: 5px;
  background-color: transparent;
  border: none;
  color: rgb(0, 0, 0);
  margin-left: auto;
}

.minimize-btn:hover {
  background-color: rgba(255, 255, 255, 0.3);
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: scale(0.5);
  }

  to {
    opacity: 1;
    transform: scale(1);
  }
}
});
