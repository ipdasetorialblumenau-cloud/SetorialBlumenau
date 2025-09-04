<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Formulário com Temporizador</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }
    html, body {
      width: 100%;
      height: 100%;
      background-color: #f5f5f5;
      color: #333;
      line-height: 1.6;
    }
    .container {
      width: 100%;
      min-height: 100vh; /* ocupa toda a altura da tela */
      background-color: white;
      display: flex;
      flex-direction: column;
    }
    header {
      text-align: center;
      padding: 20px;
      border-bottom: 2px solid #f0f0f0;
    }
    h1 {
      color: #4285f4;
      margin-bottom: 10px;
    }
    .timer-container {
      background-color: #f8f9fa;
      border-radius: 8px;
      padding: 15px;
      text-align: center;
      margin: 15px;
      border: 1px solid #e8eaed;
    }
    .timer {
      font-size: 1.8rem;
      font-weight: bold;
      color: #d93025;
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      gap: 15px;
    }
    .time-unit {
      display: flex;
      flex-direction: column;
      align-items: center;
      min-width: 60px;
    }
    .time-value {
      font-size: 2.2rem;
      line-height: 1;
    }
    .time-label {
      font-size: 0.9rem;
      color: #5f6368;
      text-transform: uppercase;
    }
    .expired-message {
      color: #d93025;
      text-align: center;
      font-weight: bold;
      font-size: 1.5rem;
      padding: 20px;
      background-color: #fce8e6;
      border-radius: 8px;
      margin: 15px;
      display: none;
    }
    .form-container, .form-esgotado {
      flex: 1; /* ocupa o espaço restante da tela */
      display: flex;
      align-items: center;
      justify-content: center;
      margin: 0;
    }
    iframe {
      width: 100%;
      height: 100%; /* iframe expande toda a tela */
      border: none;
    }
    .form-esgotado {
      color: #d93025;
      text-align: center;
      font-weight: bold;
      font-size: 1.5rem;
      background-color: #fce8e6;
      border-radius: 8px;
      padding: 20px;
      display: none;
    }
    @media (max-width: 600px) {
      .timer {
        font-size: 1.4rem;
        gap: 10px;
      }
      .time-value {
        font-size: 1.8rem;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <header>
      <h1>Pesquisa de Satisfação</h1>
      <p>Participe da nossa pesquisa e ajude-nos a melhorar nossos serviços!</p>
    </header>
    
    <div class="timer-container" id="timer-container">
      <p>Tempo restante para responder:</p>
      <div class="timer">
        <div class="time-unit">
          <span id="days" class="time-value">00</span>
          <span class="time-label">Dias</span>
        </div>
        <div class="time-unit">
          <span id="hours" class="time-value">00</span>
          <span class="time-label">Horas</span>
        </div>
        <div class="time-unit">
          <span id="minutes" class="time-value">00</span>
          <span class="time-label">Minutos</span>
        </div>
        <div class="time-unit">
          <span id="seconds" class="time-value">00</span>
          <span class="time-label">Segundos</span>
        </div>
      </div>
    </div>
    
    <div id="expired-message" class="expired-message">
      Este formulário expirou!
    </div>
    
    <div class="form-container" id="form-container">
      <iframe id="form-iframe" 
        src="https://docs.google.com/forms/d/e/1FAIpQLSdK3E_h1ibAlLXrcOGcHmLV4G4O16siwrBT3r35827_Mpvijg/viewform?embedded=true">
      </iframe>
    </div>
    <div id="form-esgotado" class="form-esgotado">
      Formulário - Tempo esgotado.
    </div>
  </div>

  <script>
    const expiryDate = new Date(2025, 8, 7, 23, 59, 0);

    const daysElement = document.getElementById('days');
    const hoursElement = document.getElementById('hours');
    const minutesElement = document.getElementById('minutes');
    const secondsElement = document.getElementById('seconds');
    const expiredMessage = document.getElementById('expired-message');
    const timerContainer = document.getElementById('timer-container');
    const formContainer = document.getElementById('form-container');
    const formEsgotado = document.getElementById('form-esgotado');

    function updateTimer() {
      const now = new Date();
      const timeDifference = expiryDate - now;

      if (timeDifference <= 0) {
        clearInterval(timerInterval);
        timerContainer.style.display = 'none';
        expiredMessage.style.display = 'block';
        formContainer.style.display = 'none';
        formEsgotado.style.display = 'flex';
        return;
      }

      const days = Math.floor(timeDifference / (1000 * 60 * 60 * 24));
      const hours = Math.floor((timeDifference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      const minutes = Math.floor((timeDifference % (1000 * 60 * 60)) / (1000 * 60));
      const seconds = Math.floor((timeDifference % (1000 * 60)) / 1000);

      daysElement.textContent = days.toString().padStart(2, '0');
      hoursElement.textContent = hours.toString().padStart(2, '0');
      minutesElement.textContent = minutes.toString().padStart(2, '0');
      secondsElement.textContent = seconds.toString().padStart(2, '0');
    }

    updateTimer();
    const timerInterval = setInterval(updateTimer, 1000);
  </script>
</body>
</html>
