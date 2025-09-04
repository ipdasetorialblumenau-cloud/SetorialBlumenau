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
        body {
            background-color: #f5f5f5;
            color: #333;
            line-height: 1.6;
            padding: 20px;
            max-width: 800px;
            margin: 0 auto;
        }
        .container {
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            padding: 20px;
            margin-bottom: 20px;
        }
        header {
            text-align: center;
            margin-bottom: 25px;
            padding-bottom: 15px;
            border-bottom: 2px solid #f0f0f0;
        }
        h1 {
            color: #4285f4;
            margin-bottom: 15px;
        }
        .timer-container {
            background-color: #f8f9fa;
            border-radius: 8px;
            padding: 15px;
            text-align: center;
            margin: 20px 0;
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
            min-width: 70px;
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
            margin: 20px 0;
        }
        .form-container {
            margin-top: 30px;
        }
        .form-esgotado {
            color: #d93025;
            text-align: center;
            font-weight: bold;
            font-size: 1.5rem;
            padding: 20px;
            background-color: #fce8e6;
            border-radius: 8px;
            margin: 20px 0;
            display: none;
        }
        iframe {
            width: 100%;
            border: none;
            border-radius: 8px;
            min-height: 500px;
        }
        @media (max-width: 600px) {
            .timer {
                font-size: 1.4rem;
                gap: 10px;
            }
            .time-value {
                font-size: 1.8rem;
            }
            .time-unit {
                min-width: 60px;
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
        
        <div class="timer-container">
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
        
        <div id="expired-message" class="expired-message" style="display: none;">
            Este formulário expirou!
        </div>
        
        <div class="form-container" id="form-container">
            <iframe id="form-iframe" src="https://docs.google.com/forms/d/e/1FAIpQLSdK3E_h1ibAlLXrcOGcHmLV4G4O16siwrBT3r35827_Mpvijg/viewform?embedded=true" height="3103" frameborder="0" marginheight="0" marginwidth="0">A carregar…</iframe>
        </div>
        <div id="form-esgotado" class="form-esgotado">
            Formulário - Tempo esgotado.
        </div>
    </div>

    <script>
        // Data de expiração: 07/09/2025 23:59
        // JavaScript usa meses de 0 (janeiro) a 11 (dezembro), então setembro é mês 8.
        const expiryDate = new Date(2025, 8, 7, 23, 59, 0); // Ano, Mês-1, Dia, Hora, Minuto, Segundo

        // Elementos do temporizador
        const daysElement = document.getElementById('days');
        const hoursElement = document.getElementById('hours');
        const minutesElement = document.getElementById('minutes');
        const secondsElement = document.getElementById('seconds');
        const expiredMessage = document.getElementById('expired-message');
        const timerContainer = document.querySelector('.timer-container');
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
                formEsgotado.style.display = 'block';
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
        formEsgotado.style.display = "none";
    </script>
</body>
</html>
