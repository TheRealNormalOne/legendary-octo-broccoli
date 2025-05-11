<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Telegram Mini App</title>
    <script src="https://telegram.org/js/telegram-web-app.js"></script>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; padding: 20px; }
        button { padding: 10px 15px; background: #0088cc; color: white; border: none; border-radius: 5px; }
    </style>
</head>
<body>
    <h1>Привет, Telegram!</h1>
    <p>Это мини-приложение внутри Telegram.</p>
    <button onclick="sendData()">Отправить данные боту</button>
    <br><br>
    <button onclick="openClubSite()">Открыть сайт клуба</button>

    <script>
        const tg = window.Telegram.WebApp;

        tg.expand(); // Развернуть приложение на весь экран
        tg.MainButton.setText("Готово").show(); // Показать кнопку снизу

        function sendData() {
            tg.sendData(JSON.stringify({ action: "hello" }));
            tg.close(); // Закрыть мини-апп
        }

        function openClubSite() {
            window.open('https://underdog.outsourcers.ru/', '_blank');
            // Если не работает в Telegram, используйте:
            // window.location.href = 'https://underdog.outsourcers.ru/';
        }
    </script>
</body>
</html>
