<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Какой ты демон из тиктока? 🔥</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap');
        body {
            background: #0a0a0a;
            color: #ff00ff;
            font-family: 'Press Start 2P', system-ui;
            text-align: center;
            padding: 40px 20px;
            line-height: 1.6;
        }
        h1 { font-size: 2.2rem; text-shadow: 0 0 20px #00ffff; }
        .question { margin: 40px 0; font-size: 1.1rem; }
        label { display: block; margin: 15px 0; cursor: pointer; }
        input[type="radio"] { margin-right: 10px; accent-color: #ff00ff; }
        button, .result-btn {
            background: #ff00ff;
            color: #000;
            border: none;
            padding: 20px 40px;
            font-size: 1.3rem;
            cursor: pointer;
            margin-top: 30px;
            box-shadow: 0 0 30px #00ffff;
            transition: all 0.3s;
        }
        button:hover, .result-btn:hover { transform: scale(1.05); background: #00ffff; color: #ff00ff; }
        .result { display: none; margin: 50px auto; max-width: 600px; padding: 30px; background: #1a0033; border: 3px dashed #00ffff; }
    </style>
</head>
<body>
    <h1>КАКОЙ ТЫ ДЕМОН ИЗ ТИКТОКА?</h1>
    <p style="color:#00ffff; font-size:1rem;">Пройди 3 вопроса и получи разбор в Telegram-боте 🔥</p>

    <form id="quizForm">
        <div class="question">
            <h3>1. Когда все вокруг в истерике, ты:</h3>
            <label><input type="radio" name="q1" value="1"> Снимаешь тикток «это мой момент»</label>
            <label><input type="radio" name="q1" value="2"> Молча наливаешь всем по стакану и говоришь «расслабьтесь»</label>
            <label><input type="radio" name="q1" value="3"> Уходишь в темноту и пишешь в заметки «все умрут»</label>
        </div>

        <div class="question">
            <h3>2. Твой идеальный плейлист для саморазрушения:</h3>
            <label><input type="radio" name="q2" value="1"> Hyperpop и крики</label>
            <label><input type="radio" name="q2" value="2"> Тяжёлый металл + rain sounds</label>
            <label><input type="radio" name="q2" value="3"> Lo-fi + матерные подкасты</label>
        </div>

        <div class="question">
            <h3>3. Если бы твоя жизнь была мемом, то:</h3>
            <label><input type="radio" name="q3" value="1"> «This is fine» в горящей комнате</label>
            <label><input type="radio" name="q3" value="2"> «Distracted boyfriend» с самим собой</label>
            <label><input type="radio" name="q3" value="3"> «Change my mind» с подписью «я нормальный»</label>
        </div>

        <button type="button" onclick="submitTest()">Пройти тест и получить результат в боте</button>
    </form>

    <div id="resultScreen" class="result">
        <h2>ГОТОВО, ДЕМОН! 🔥</h2>
        <p id="codeText" style="font-size:1.5rem; color:#00ffff;"></p>
        <p style="color:#ff00ff;">Результат сохранён. Теперь жми кнопку и бот расскажет тебе всю правду (без цензуры).</p>
        <a id="botLink" href="#" class="result-btn" target="_blank">➡️ ДОБАВИТЬ БОТА И УЗНАТЬ, КТО Я НА САМОМ ДЕЛЕ</a>
        <p style="margin-top:30px; font-size:0.9rem; color:#666;">(для теста код одноразовый, потом заменим на реальную БД)</p>
    </div>

    <script>
        function submitTest() {
            const q1 = document.querySelector('input[name="q1"]:checked');
            const q2 = document.querySelector('input[name="q2"]:checked');
            const q3 = document.querySelector('input[name="q3"]:checked');

            if (!q1 || !q2 || !q3) {
                alert('Эй, демон, ответь на все вопросы, не ленись 😏');
                return;
            }

            const score = parseInt(q1.value) + parseInt(q2.value) + parseInt(q3.value);
            
            // Генерируем код
            const code = 'demo-' + Math.random().toString(36).substring(2, 10).toUpperCase();
            
            // Показываем экран результата
            document.getElementById('quizForm').style.display = 'none';
            const resultScreen = document.getElementById('resultScreen');
            resultScreen.style.display = 'block';
            
            document.getElementById('codeText').innerHTML = `ТВОЙ СЕКРЕТНЫЙ КОД:<br><b style="color:#ffff00; font-size:2rem;">${code}</b>`;
            
            // ССЫЛКА НА БОТА — ЗАМЕНИ НА СВОЙ ЮЗЕРНЕЙМ!!!
            const botUsername = 'Psyho12345Bot'; // ←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←
            const link = `https://t.me/${botUsername}?start=${code}`;
            document.getElementById('botLink').href = link;
        }
    </script>
</body>
</html>
