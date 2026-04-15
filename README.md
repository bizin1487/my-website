<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>🐎 КАКАЯ ТЫ ЛОШАДЬ? · полный тест</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Segoe UI', 'Roboto', system-ui, sans-serif;
            background: linear-gradient(145deg, #1b3b1b 0%, #2d5e2d 100%);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            margin: 0;
            padding: 20px;
            position: relative;
            overflow-x: hidden;
        }

        body::before {
            content: "🐎🐴🏇";
            position: absolute;
            bottom: 10px;
            left: 0;
            right: 0;
            text-align: center;
            font-size: 48px;
            opacity: 0.1;
            pointer-events: none;
            letter-spacing: 40px;
        }

        .card {
            max-width: 750px;
            width: 100%;
            background: #fdf8ed;
            border-radius: 60px 20px 60px 20px;
            box-shadow: 0 30px 40px rgba(0, 0, 0, 0.3), 0 0 0 8px #d4b483, 0 0 0 12px #6b3e1f;
            padding: 30px 28px 35px;
            text-align: center;
            border: 2px solid #ac7339;
        }

        h1 {
            font-size: 2.8rem;
            font-weight: 800;
            color: #3b220e;
            text-shadow: 4px 4px 0 #e0b87b;
            letter-spacing: 2px;
            margin-top: -5px;
            margin-bottom: 5px;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 15px;
            flex-wrap: wrap;
        }

        h1 span {
            font-size: 3rem;
        }

        .subhead {
            font-size: 1.2rem;
            color: #5a3a1c;
            font-style: italic;
            margin-bottom: 20px;
            border-bottom: 3px dashed #b8865b;
            padding-bottom: 12px;
            font-weight: 500;
        }

        .quiz-box {
            background: #efe1c6;
            border-radius: 40px 10px 40px 10px;
            padding: 25px 18px;
            box-shadow: inset 0 0 0 2px #b4915f, inset 0 0 15px #aa7e4e;
            margin-bottom: 15px;
        }

        .progress {
            font-size: 1.1rem;
            background: #6b4a2a;
            color: #f0ddc0;
            padding: 6px 15px;
            border-radius: 40px;
            display: inline-block;
            margin-bottom: 15px;
            font-weight: bold;
            border: 2px solid #d4a96a;
        }

        .question {
            font-size: 1.9rem;
            font-weight: 700;
            color: #2c1a06;
            margin-bottom: 20px;
            background: #f3e5d2;
            display: inline-block;
            padding: 10px 28px;
            border-radius: 50px;
            box-shadow: 0 4px 0 #6b4a2a;
            line-height: 1.3;
        }

        .options {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 18px 20px;
            margin: 20px 0 20px;
        }

        .option-btn {
            background: #faf3e4;
            border: 4px solid #5d3f1e;
            color: #2b1a09;
            padding: 16px 5px;
            font-size: 1.25rem;
            font-weight: bold;
            border-radius: 50px 15px 50px 15px;
            cursor: pointer;
            transition: 0.1s;
            box-shadow: 0 7px 0 #4a2f14;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            text-transform: uppercase;
            word-break: break-word;
        }

        .option-btn:hover {
            background: #ffe9c7;
            transform: translateY(-2px);
            box-shadow: 0 9px 0 #4a2f14;
        }

        .option-btn:active {
            transform: translateY(4px);
            box-shadow: 0 3px 0 #4a2f14;
        }

        .quote-box {
            background: #dac29c;
            margin: 15px 0 8px;
            padding: 12px 15px;
            border-radius: 30px 5px 30px 5px;
            border-left: 10px solid #7b4f24;
            font-style: italic;
            font-weight: 500;
            color: #1f2e0a;
            font-size: 1.2rem;
            box-shadow: inset 0 2px 6px rgba(0,0,0,0.1);
            min-height: 65px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .nav-buttons {
            display: flex;
            justify-content: space-between;
            gap: 15px;
            margin: 15px 0 5px;
        }

        .nav-btn {
            background: #b4915f;
            border: none;
            border-bottom: 6px solid #5a3a1c;
            font-size: 1.3rem;
            font-weight: bold;
            color: #231b0e;
            padding: 12px 22px;
            border-radius: 40px 10px 40px 10px;
            cursor: pointer;
            box-shadow: 0 4px 0 #3b2b19;
            transition: 0.05s linear;
            flex: 1;
            border: 2px solid #7a5a34;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .nav-btn:active {
            transform: translateY(3px);
            box-shadow: 0 1px 0 #3b2b19;
        }

        .nav-btn:disabled {
            opacity: 0.5;
            transform: none;
            box-shadow: 0 4px 0 #3b2b19;
            cursor: not-allowed;
        }

        .result-area {
            margin-top: 20px;
        }

        .result-btn {
            background: #c49a6c;
            border: none;
            border-bottom: 8px solid #5e2e0f;
            font-size: 2rem;
            font-weight: 900;
            color: #1e2f0c;
            padding: 16px 30px;
            border-radius: 60px 10px 60px 10px;
            cursor: pointer;
            box-shadow: 0 8px 0 #4b2a10, 0 10px 20px rgba(0,0,0,0.2);
            transition: 0.07s;
            text-transform: uppercase;
            letter-spacing: 4px;
            background: #e4b574;
            color: #231b0e;
            width: fit-content;
            margin: 10px auto 10px;
            border: 3px solid #b5722e;
        }

        .result-btn:hover {
            background: #f3ca91;
        }

        .result-btn:active {
            transform: translateY(5px);
            box-shadow: 0 3px 0 #4b2a10, 0 8px 12px rgba(0,0,0,0.2);
        }

        .result-btn:disabled {
            opacity: 0.45;
            transform: none;
            box-shadow: 0 8px 0 #4b2a10, 0 10px 20px rgba(0,0,0,0.2);
            cursor: not-allowed;
            background: #a58357;
            border-bottom-color: #4a2e14;
        }

        #horseResult {
            font-size: 2.2rem;
            font-weight: 800;
            margin: 20px 0 10px;
            padding: 18px 20px;
            background: #2d1c0b;
            border-radius: 30px 5px 30px 5px;
            color: #ffecb3;
            display: inline-block;
            border: 5px double #eebb77;
            box-shadow: 0 0 0 4px #5f3f1c;
            text-align: center;
            line-height: 1.4;
            word-break: break-word;
        }

        .answers-status {
            font-size: 1rem;
            margin: 5px 0 -5px;
            color: #4d2f14;
            font-weight: 600;
        }

        .signature {
            margin-top: 20px;
            color: #4e3116;
            font-weight: 600;
            font-size: 1rem;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 15px;
            opacity: 0.9;
            cursor: pointer;
        }

        @media (max-width: 550px) {
            .card { padding: 20px 12px; }
            h1 { font-size: 2rem; }
            .question { font-size: 1.5rem; }
            .options { grid-template-columns: 1fr; }
            .option-btn { padding: 14px; font-size: 1.1rem; }
            .result-btn { font-size: 1.7rem; padding: 14px 18px; }
            #horseResult { font-size: 1.8rem; }
        }

        @keyframes shake {
            0% { transform: translateX(0); }
            25% { transform: translateX(-8px); }
            50% { transform: translateX(8px); }
            75% { transform: translateX(-4px); }
            100% { transform: translateX(0); }
        }
    </style>
</head>
<body>

<div class="card">
    <h1>
        <span>🏇</span> КАКАЯ ТЫ ЛОШАДЬ? <span>🏇</span>
    </h1>
    <div class="subhead">5 вопросов — узнай свою лошадиную сущность</div>

    <div class="quiz-box">
        <div class="progress" id="progressIndicator">Вопрос 1 / 5</div>
        <div class="question" id="questionText">Загрузка...</div>

        <div class="options" id="optionsContainer"></div>

        <div class="quote-box" id="quoteBox">🐴 «Выбери ответ, и мудрость копыт откроется»</div>

        <div class="nav-buttons">
            <button class="nav-btn" id="prevBtn" disabled>◀ Назад</button>
            <button class="nav-btn" id="nextBtn">Далее ▶</button>
        </div>

        <!-- Статус ответов -->
        <div class="answers-status" id="answersStatus">✅ Отвечено: 0 / 5</div>

        <div class="result-area">
            <button class="result-btn" id="revealBtn" disabled>🔮 Узнать результат</button>
            <div id="horseResult"></div>
        </div>
    </div>

    <div class="signature" id="resetTrigger">
        <span>🐎</span> кликни сюда, чтобы начать заново <span>🐎</span>
    </div>
</div>

<script>
    (function(){
        // ----- БАЗА ВОПРОСОВ И ЦИТАТ -----
        const questions = [
            {
                text: "🥣 Что ты выберешь на завтрак?",
                options: ["🌾 Овёс с солью", "🍎 Сладкое яблоко", "🥕 Морковка-гигант", "🍞 Бутерброд с колбасой"],
                quotes: [
                    "«Овёс — топливо чемпионов, но ты явно не скакун» 🐴",
                    "«Яблоко от яблони... но лошадь не оценит компот» 🍏",
                    "«Морковка для зрения, а ты и так видишь, что ты не лошадь» 🥕👀",
                    "«Бутерброд? Это по-человечески. Лошади так не едят, Семен» 🥪"
                ]
            },
            {
                text: "🏁 Твой любимый вид спорта?",
                options: ["🏇 Скачки", "🐎 Конкур", "🚴 Велоспорт", "🛋️ Лежание на диване"],
                quotes: [
                    "«Скачки — для быстрых, но ты скорее комментатор» 🎤",
                    "«Конкур — прыжки через барьеры, а ты через лужи» 🌧️",
                    "«Велосипед — железный конь, но ты не ковбой» 🚲",
                    "«Диван — не конюшня, но тебе идёт» 🛌"
                ]
            },
            {
                text: "🎵 Какую музыку предпочитаешь?",
                options: ["🎺 Цыганские романсы", "🤠 Кантри", "🎸 Рок", "🎹 Классика"],
                quotes: [
                    "«Цыгане лошадей любят, а ты им кто?» 🎻",
                    "«Кантри — музыка ковбоев, но ты без шляпы» 🤠",
                    "«Рок — это мощно, почти как топот табуна» 🎸🐎",
                    "«Моцарт для ушей, а не для копыт» 🎼"
                ]
            },
            {
                text: "🌳 Где бы ты хотел жить?",
                options: ["🏞️ В конюшне", "🏰 В замке", "🏙️ В мегаполисе", "🏝️ На острове"],
                quotes: [
                    "«Конюшня пахнет сеном, но у тебя аллергия на труд» 🤧",
                    "«Замок — для принцесс, а ты скорее конюх» 👑",
                    "«В городе лошадям скучно, а тебе норм» 🏙️",
                    "«Остров — мечта, но плавать как конь ты не умеешь» 🏊"
                ]
            },
            {
                text: "🤔 Кем ты видишь себя через 10 лет?",
                options: ["🏆 Чемпионом скачек", "🌾 Фермером", "👑 Боссом", "🤷 Тем же Семеном"],
                quotes: [
                    "«Чемпионом? Только если по поеданию овса» 🥇",
                    "«Фермер — хорошо, лошадям нужен уход» 🚜",
                    "«Босс — да, но лошади начальников не уважают» 💼",
                    "«Семен — это судьба. И это не лошадь» 😎"
                ]
            }
        ];

        // ----- СОСТОЯНИЕ -----
        let currentIndex = 0;
        const answers = new Array(questions.length).fill(null);
        
        // DOM-элементы
        const progressEl = document.getElementById('progressIndicator');
        const questionEl = document.getElementById('questionText');
        const optionsContainer = document.getElementById('optionsContainer');
        const quoteBox = document.getElementById('quoteBox');
        const prevBtn = document.getElementById('prevBtn');
        const nextBtn = document.getElementById('nextBtn');
        const revealBtn = document.getElementById('revealBtn');
        const horseResultDiv = document.getElementById('horseResult');
        const resetTrigger = document.getElementById('resetTrigger');
        const answersStatus = document.getElementById('answersStatus');

        // ----- ВСПОМОГАТЕЛЬНЫЕ ФУНКЦИИ -----
        function countAnswered() {
            return answers.filter(a => a !== null).length;
        }

        function updateAnswersStatus() {
            const answered = countAnswered();
            answersStatus.textContent = `✅ Отвечено: ${answered} / ${questions.length}`;
            
            // Кнопка "Узнать результат" активна только если отвечены ВСЕ вопросы
            if (answered === questions.length) {
                revealBtn.disabled = false;
            } else {
                revealBtn.disabled = true;
            }
        }

        function renderCurrentQuestion() {
            const q = questions[currentIndex];
            questionEl.textContent = q.text;
            progressEl.textContent = `Вопрос ${currentIndex + 1} / ${questions.length}`;

            optionsContainer.innerHTML = '';
            q.options.forEach((optText, idx) => {
                const btn = document.createElement('button');
                btn.className = 'option-btn';
                btn.innerHTML = optText;
                btn.setAttribute('data-option-index', idx);
                
                if (answers[currentIndex] === idx) {
                    btn.style.background = '#ffe0a3';
                    btn.style.borderColor = '#b35400';
                    btn.style.transform = 'scale(1.02)';
                } else {
                    btn.style.background = '#faf3e4';
                    btn.style.borderColor = '#5d3f1e';
                    btn.style.transform = 'scale(1)';
                }

                btn.addEventListener('click', function(e) {
                    const selectedIdx = parseInt(this.getAttribute('data-option-index'));
                    answers[currentIndex] = selectedIdx;
                    
                    // Обновляем стили
                    document.querySelectorAll('.option-btn').forEach((b, i) => {
                        if (i === selectedIdx) {
                            b.style.background = '#ffe0a3';
                            b.style.borderColor = '#b35400';
                            b.style.transform = 'scale(1.02)';
                        } else {
                            b.style.background = '#faf3e4';
                            b.style.borderColor = '#5d3f1e';
                            b.style.transform = 'scale(1)';
                        }
                    });

                    // Цитата
                    quoteBox.innerHTML = `🐎 ${q.quotes[selectedIdx]}`;
                    
                    // Обновляем статус ответов и кнопку результата
                    updateAnswersStatus();
                    
                    // Очищаем финальный результат, если меняем ответы
                    horseResultDiv.innerHTML = '';
                });

                optionsContainer.appendChild(btn);
            });

            // Установка цитаты, если ответ уже есть
            const savedAnswer = answers[currentIndex];
            if (savedAnswer !== null) {
                quoteBox.innerHTML = `🐎 ${q.quotes[savedAnswer]}`;
            } else {
                quoteBox.innerHTML = `🐴 «Вопрос ждёт твоего решения, наездник»`;
            }

            prevBtn.disabled = (currentIndex === 0);
            
            if (currentIndex === questions.length - 1) {
                nextBtn.textContent = '🏁 Завершить';
            } else {
                nextBtn.textContent = 'Далее ▶';
            }

            updateAnswersStatus(); // актуализируем счетчик и кнопку
        }

        function goToQuestion(newIndex) {
            if (newIndex < 0 || newIndex >= questions.length) return;
            currentIndex = newIndex;
            renderCurrentQuestion();
            horseResultDiv.innerHTML = '';
        }

        function resetQuiz() {
            currentIndex = 0;
            for (let i = 0; i < answers.length; i++) answers[i] = null;
            renderCurrentQuestion();
            horseResultDiv.innerHTML = '';
            quoteBox.innerHTML = `🐴 «Выбери ответ, и мудрость копыт откроется»`;
            updateAnswersStatus();
        }

        function handleReveal() {
            // Дополнительная проверка (хотя кнопка disabled, но на всякий)
            if (countAnswered() !== questions.length) {
                horseResultDiv.innerHTML = '⚠️ Ответь на все вопросы, Семен!';
                return;
            }
            
            const finalPhrase = '😤 Семен, ты ботяра, а не лошадь! 🐗💨';
            horseResultDiv.innerHTML = finalPhrase;
            horseResultDiv.style.animation = 'shake 0.4s ease-in-out';
            setTimeout(() => horseResultDiv.style.animation = '', 400);
            quoteBox.innerHTML = '🏇 «Ржать можешь, но ботярой останешься. С уважением, табун.» 🏇';
        }

        // ----- ПОДПИСКА НА СОБЫТИЯ -----
        prevBtn.addEventListener('click', () => {
            if (currentIndex > 0) goToQuestion(currentIndex - 1);
        });

        nextBtn.addEventListener('click', () => {
            if (currentIndex < questions.length - 1) {
                goToQuestion(currentIndex + 1);
            } else {
                // На последнем вопросе кнопка "Завершить" — просто напоминание
                if (countAnswered() === questions.length) {
                    quoteBox.innerHTML = '🎯 «Все ответы даны! Жми "Узнать результат" и узри истину.»';
                } else {
                    quoteBox.innerHTML = '⚠️ «Остались вопросы без ответа, Семен. Не ленись!»';
                }
            }
        });

        revealBtn.addEventListener('click', handleReveal);
        resetTrigger.addEventListener('click', resetQuiz);
        document.querySelector('h1').addEventListener('dblclick', resetQuiz);

        // Инициализация
        renderCurrentQuestion();

        console.log('%c🐎 «Конь о четырех ногах, и тот спотыкается, а Семен — ботяра!»', 'font-size:16px; background:#6b4a2a; color:#f5e1be; padding:6px; border-radius:12px;');
    })();
</script>
</body>
</html># my-website
