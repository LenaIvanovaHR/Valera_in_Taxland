<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Валера в Стране Налогов</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            background-color: #1a1a1a;
            color: white;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            overflow: hidden;
        }
        #game-container {
            position: relative;
            width: 100%;
            max-width: 1280px;
            height: 100vh;
            max-height: 720px;
            background-size: cover;
            background-position: center;
            box-shadow: 0 0 20px rgba(0,0,0,0.8);
            transition: background-image 0.5s ease-in-out;
        }
        #character-sprite {
            position: absolute;
            bottom: 180px;
            left: 50%;
            transform: translateX(-50%);
            height: 60%;
            display: none;
            filter: drop-shadow(0 0 10px rgba(0,0,0,0.5));
            border-radius: 20px;
        }
        #dialogue-box {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 180px;
            background: linear-gradient(to top, rgba(0,0,0,0.95), rgba(0,0,0,0.7));
            border-top: 3px solid #ff8c00;
            box-sizing: border-box;
            padding: 20px 40px;
            cursor: pointer;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }
        #speaker {
            font-size: 24px;
            font-weight: bold;
            color: #ff8c00;
            margin-bottom: 10px;
            text-shadow: 1px 1px 3px rgba(0,0,0,0.8);
        }
        #text {
            font-size: 20px;
            line-height: 1.5;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.8);
            margin: 0;
        }
        #hint {
            position: absolute;
            bottom: 10px;
            right: 20px;
            font-size: 14px;
            color: #aaa;
            animation: blink 1.5s infinite;
        }
        @keyframes blink {
            0%, 100% { opacity: 0.5; }
            50% { opacity: 1; }
        }
        #choices {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            display: flex;
            flex-direction: column;
            gap: 15px;
            width: 60%;
            display: none;
            z-index: 10;
        }
        .choice-btn {
            background: rgba(20, 20, 20, 0.95);
            border: 2px solid #ff8c00;
            color: white;
            padding: 15px;
            font-size: 18px;
            cursor: pointer;
            border-radius: 8px;
            transition: all 0.3s;
            font-family: inherit;
        }
        .choice-btn:hover {
            background: #ff8c00;
            color: black;
            transform: scale(1.02);
        }
        #coins-display {
            position: absolute;
            top: 20px;
            right: 20px;
            font-size: 20px;
            background: rgba(0,0,0,0.7);
            padding: 10px 20px;
            border-radius: 20px;
            border: 1px solid #ff8c00;
            display: none;
        }
    </style>
</head>
<body>

<div id="game-container">
    <div id="coins-display">🪙 Монеты: <span id="coin-count">0</span></div>
    <img id="character-sprite" src="" alt="Персонаж">
    
    <div id="choices"></div>

    <div id="dialogue-box" onclick="nextSlide()">
        <div id="speaker">Система</div>
        <p id="text">Загрузка...</p>
        <div id="hint">Нажмите, чтобы продолжить...</div>
    </div>
</div>

<script>
    // ==========================================
    // СЦЕНАРИЙ ИГРЫ (Данные)
    // ==========================================
    let state = {
        coins: 0,
        currentLabel: "start"
    };

    const story = {
        // ПРОЛОГ
        "start": {
            bg: "images/bg_office.png", speaker: "Валера",
            text: "Хм, что это ещё за файл? Я такой не сохранял...", sprite: null,
            next: "prologue_fall"
        },
        "prologue_fall": {
            bg: "images/bg_documents.png", speaker: "Голос сверху",
            text: "Падать вечно нельзя, дружок. Рано или поздно долетишь до сути.", sprite: null,
            next: "prologue_cat"
        },
        "prologue_cat": {
            bg: "images/bg_documents.png", speaker: "Рыжий Кот",
            text: "Добро пожаловать в Страну Налогов, Валера. Тут всё как у вас, только выгоднее — если знать, куда смотреть.", sprite: "images/cat_smile.png",
            next: "prologue_choice"
        },
        "prologue_choice": {
            speaker: "Выбор", text: "Что спросит Валера?",
            choices: [
                { text: "А зачем мне вообще это надо, я и так неплохо живу", next: "prologue_A" },
                { text: "А можно получить вычет, если я вообще ничего не тратил?", next: "prologue_C" },
                { text: "Хорошо, показывай дорогу", next: "prologue_B", coins: 10 }
            ]
        },
        "prologue_A": {
            speaker: "Рыжий Кот", text: "Неплохо — не значит по максимуму. Тысячи рублей просто лежат там, где ты их не забираешь.",
            next: "prologue_choice"
        },
        "prologue_C": {
            speaker: "Рыжий Кот", text: "Вычет — это возврат уже уплаченного налога с твоих трат. Не потратил — нечего возвращать. Но ты наверняка тратился — на детей, лечение, учёбу...",
            next: "prologue_choice"
        },
        "prologue_B": {
            bg: "images/bg_road.png", speaker: "Рыжий Кот",
            text: "Тогда за мной. Первая остановка — Родительский лес.", sprite: "images/cat_full.png",
            next: "prologue_rule"
        },
        "prologue_rule": {
            bg: "images/bg_road.png", speaker: "Рыжий Кот",
            text: "Погоди-ка, прежде чем мы пойдём глубже — запомни одну вещь, а то потом собьёшься со счёта. Из каждого рубля твоей зарплаты налоговая забирает 13 копеек. Вычет — это не деньги, которые тебе дарят сверху. Это сумма, с которой налоговая обещает не забирать свои 13 копеек.", sprite: "images/cat_full.png",
            next: "prologue_rule_caterpillar"
        },
        "prologue_rule_caterpillar": {
            bg: "images/bg_road.png", speaker: "Гусеница Bugatti",
            text: "Проще говоря: вычет 100 000 ₽ — вернётся 13 000 ₽. Вычет 150 000 ₽ — вернётся 19 500 ₽. Всегда 13% от вычета, а не сам вычет целиком. Получить вычет может только тот, кто платит НДФЛ 13%.", sprite: "images/caterpillar.png",
            next: "prologue_math"
        },
        "prologue_math": {
            speaker: "Выбор", text: "Валере положен вычет 150 000 ₽ на лечение. Сколько реально вернётся ему на счёт?",
            choices: [
                { text: "150 000 ₽", next: "prologue_math_A" },
                { text: "13 000 ₽", next: "prologue_math_C" },
                { text: "19 500 ₽", next: "prologue_math_B", coins: 15 }
            ]
        },
        "prologue_math_A": { speaker: "Рыжий Кот", text: "Это база, а не возврат. Пересчитай через 13%.", next: "prologue_math" },
        "prologue_math_C": { speaker: "Гусеница Bugatti", text: "Это 13% от 100 000, а у нас 150 000.", next: "prologue_math" },
        "prologue_math_B": {
            speaker: "Рыжий Кот", text: "Вот теперь считаешь правильно. 150 000 × 13% = 19 500 ₽.",
            next: "prologue_end"
        },
        "prologue_end": {
            bg: "images/bg_road.png", speaker: "Рыжий Кот",
            text: "И да — с 2025 года ставка НДФЛ не всегда ровно 13%. При высоком доходе она растёт по прогрессивной шкале, до 22%. Так что у некоторых счастливчиков реальный возврат может быть даже больше стандартных 13% от вычета.", sprite: "images/cat_full.png",
            next: "block1_start"
        },

        // БЛОК 1. ЯРМАРКА
        "block1_start": {
            bg: "images/bg_fair.png", speaker: "Рыжий Кот",
            text: "Добро пожаловать на Ярмарку НДФЛ. Это главный налог, который касается тебя каждый месяц, даже если ты о нём не думаешь. Зарплата, премии, доход от сдачи квартиры в аренду, продажа имущества, выигрыши — всё это доход, а с дохода физлица берут НДФЛ.", sprite: "images/cat_full.png",
            next: "block1_choice1"
        },
        "block1_choice1": {
            speaker: "Выбор", text: "Валера в отпуске выиграл в лотерею 50 000 ₽. Нужно ли платить с этого НДФЛ?",
            choices: [
                { text: "Нет, это же не зарплата", next: "block1_ch1_A" },
                { text: "Только если выигрыш больше 1 000 000 ₽", next: "block1_ch1_C" },
                { text: "Да, это тоже доход — и с него тоже удерживается налог", next: "block1_ch1_B", coins: 15 }
            ]
        },
        "block1_ch1_A": { speaker: "Рыжий Кот", text: "Прилавок с выигрышами тоже кидает монетку в мешок, не сомневайся.", next: "block1_choice1" },
        "block1_ch1_C": { speaker: "Гусеница Bugatti", text: "Не совсем так работает порог, дружочек. Выигрыш облагается налогом почти всегда.", next: "block1_choice1" },
        "block1_ch1_B": {
            speaker: "Гусеница Bugatti", text: "Именно. Доход есть доход, откуда бы он ни пришёл.",
            next: "block1_scene2"
        },
        "block1_scene2": {
            bg: "images/bg_booth.png", speaker: "Рыжий Кот",
            text: "Видишь эту будку? Это твой работодатель — он тут называется налоговым агентом. С зарплаты всё происходит автоматически. А вот с другими доходами — не так. Придётся подавать декларацию 3-НДФЛ самостоятельно.", sprite: "images/cat_full.png",
            next: "block1_choice2"
        },
        "block1_choice2": {
            speaker: "Выбор", text: "Валера сдаёт квартиру в аренду, деньги приходят напрямую ему на карту. Что делать с налогом?",
            choices: [
                { text: "Ничего, раз с зарплаты уже всё удержали", next: "block1_ch2_A" },
                { text: "Попросить своего работодателя удержать и с этого дохода тоже", next: "block1_ch2_C" },
                { text: "Самому подать декларацию 3-НДФЛ по итогам года и заплатить налог", next: "block1_ch2_B", coins: 15 }
            ]
        },
        "block1_ch2_A": { speaker: "Рыжий Кот", text: "Зарплата и аренда — два разных источника дохода, будка тут ни при чём.", next: "block1_choice2" },
        "block1_ch2_C": { speaker: "Гусеница Bugatti", text: "Работодатель отвечает только за то, что платит сам, дружочек.", next: "block1_choice2" },
        "block1_ch2_B": { speaker: "Рыжий Кот", text: "Именно так — без декларации в этом случае никак.", next: "block1_scene3" },
        
        "block1_scene3": {
            bg: "images/bg_stairs.png", speaker: "Гусеница Bugatti",
            text: "С 2025 года у нас не одна ставка НДФЛ, а целая лестница — пять ступеней: до 2,4 млн — 13%, от 2,4 до 5 млн — 15% с превышения, от 5 до 20 млн — 18% с превышения, от 20 до 50 млн — 20% с превышения, свыше 50 млн — 22% с превышения.", sprite: "images/caterpillar.png",
            next: "block1_choice3"
        },
        "block1_choice3": {
            speaker: "Выбор", text: "Доход Валеры за год — 3 000 000 ₽. Как считается его НДФЛ?",
            choices: [
                { text: "15% на всю сумму сразу", next: "block1_ch3_A" },
                { text: "13% на всё, раз доход меньше 5 000 000 ₽", next: "block1_ch3_C" },
                { text: "13% на первые 2 400 000 ₽ и 15% на оставшиеся 600 000 ₽", next: "block1_ch3_B", coins: 20 }
            ]
        },
        "block1_ch3_A": { speaker: "Рыжий Кот", text: "Лестница ступенчатая — с этой ступеньки платят не все сразу, а только та часть, что до неё дотянулась.", next: "block1_choice3" },
        "block1_ch3_C": { speaker: "Гусеница Bugatti", text: "Порог для 13% — это 2 400 000, а не 5 000 000, дружочек.", next: "block1_choice3" },
        "block1_ch3_B": { speaker: "Гусеница Bugatti", text: "Точно! 2 400 000 × 13% + 600 000 × 15% = 312 000 + 90 000 = 402 000 ₽ налога.", next: "block1_scene4" },

        "block1_scene4": {
            bg: "images/bg_cabinet.png", speaker: "Рыжий Кот",
            text: "Запомни этот павильон — сюда мы будем возвращаться в каждой следующей главе. Все заявления и справки приходят именно туда, на сайт ФНС России. А ещё все правила действуют для налоговых резидентов РФ, которые провели в России больше 183 дней за последние 12 месяцев.", sprite: "images/cat_full.png",
            next: "block2_start"
        },

        // БЛОК 2. НЕДВИЖИМОСТЬ
        "block2_start": {
            bg: "images/bg_realty.png", speaker: "Рыжий Кот",
            text: "Здесь живут те, кто купил своё жильё. И тут государству тоже есть что тебе вернуть.", sprite: "images/cat_full.png",
            next: "block2_scene1"
        },
        "block2_scene1": {
            bg: "images/bg_realty.png", speaker: "Гусеница Bugatti",
            text: "На два отдельных вычета сразу! Первый — за саму покупку: база 2 000 000 ₽, максимальный возврат 260 000 ₽. Второй — за уплаченные проценты по ипотеке: база уже 3 000 000 ₽, максимальный возврат 390 000 ₽. А если вы в браке — оба супруга могут заявить вычет.", sprite: "images/caterpillar.png",
            next: "block2_choice1"
        },
        "block2_choice1": {
            speaker: "Выбор", text: "Валера и его жена купили квартиру в ипотеку за 6 000 000 ₽. Как выгоднее оформить вычет?",
            choices: [
                { text: "Вычет заявляет только Валера один", next: "block2_ch1_A" },
                { text: "Вычет не положен, раз квартира дороже 2 000 000 ₽", next: "block2_ch1_C" },
                { text: "Вычет заявляют оба супруга — так семейный лимит по процентам увеличивается", next: "block2_ch1_B", coins: 20 }
            ]
        },
        "block2_ch1_A": { speaker: "Рыжий Кот", text: "Можно и так, но тогда вторая половина лимита просто сгорит зря.", next: "block2_choice1" },
        "block2_ch1_C": { speaker: "Гусеница Bugatti", text: "Лимит — это потолок для расчёта, а не запрет на вычет при более дорогой покупке.", next: "block2_choice1" },
        "block2_ch1_B": { speaker: "Гусеница Bugatti", text: "Именно! Вдвоём вы используете куда больше положенного лимита, чем поодиночке.", next: "block2_scene2" },

        "block2_scene2": {
            bg: "images/bg_garage.png", speaker: "Рыжий Кот",
            text: "А вот тут — наоборот, о продаже. Здесь важно не прогадать со временем. Для недвижимости минимальный срок владения — 5 лет, для машины — 3 года. А налог можно уменьшить вычетом: 1 000 000 ₽ для недвижимости, 250 000 ₽ для прочего имущества.", sprite: "images/cat_full.png",
            next: "block2_choice2"
        },
        "block2_choice2": {
            speaker: "Выбор", text: "У Валеры квартира не единственная, он владеет ей 4 года и хочет продать. Нужно ли платить налог?",
            choices: [
                { text: "Нет, 4 года — вполне достаточно", next: "block2_ch2_A" },
                { text: "Срок владения тут вообще не имеет значения", next: "block2_ch2_C" },
                { text: "Да, минимальный срок — 5 лет, значит налог платить придётся", next: "block2_ch2_B", coins: 20 }
            ]
        },
        "block2_ch2_A": { speaker: "Рыжий Кот", text: "Пять лет — это пять лет, дружок.", next: "block2_choice2" },
        "block2_ch2_C": { speaker: "Рыжий Кот", text: "Пять лет — это пять лет, дружок.", next: "block2_choice2" },
        "block2_ch2_B": { speaker: "Гусеница Bugatti", text: "Всё верно. Раньше пяти лет для не единственного жилья — налог с разницы между продажей и вычетом или расходами на покупку.", next: "block2_scene3" },
        
        "block2_scene3": {
            bg: "images/bg_garage.png", speaker: "Гусеница Bugatti",
            text: "И ещё одно, прежде чем идти дальше. Помнишь лестницу из пяти ступеней? С 2025 года ставка НДФЛ не всегда ровно 13% — у тех, кто зарабатывает существенно больше, часть дохода облагается уже по 15–22%. Так что если коллега говорит, что вернул больше 13% — не спеши считать его хвастуном.", sprite: "images/caterpillar.png",
            next: "block4_start" // Переход к Блоку 4, так как Блок 3 в разработке
        },

        // БЛОК 4. СОЦИАЛЬНЫЕ БОНУСЫ
        "block4_start": {
            bg: "images/bg_forest.png", speaker: "Рыжий Кот",
            text: "У тебя есть дети, Валера? Тогда этот лес шумит для тебя. Каждый месяц, пока твой доход с начала года не перевалит за 450 000 рублей, тебе полагается вычет на каждого.", sprite: "images/cat_smile.png",
            next: "block4_scene1"
        },
        "block4_scene1": {
            bg: "images/bg_forest.png", speaker: "Гусеница Bugatti",
            text: "Ах, молодой человек... До 2025 года на второго ребёнка давали всего 1400 рублей в месяц. Теперь — 2800. На третьего и последующих было 3000, стало 6000. На первую — 1400, на второго — 2800. Итого 4200 рублей вычета.", sprite: "images/caterpillar.png",
            next: "block4_choice1"
        },
        "block4_choice1": {
            speaker: "Выбор", text: "Как Валере получить этот вычет?",
            choices: [
                { text: "Пойти в налоговую и подать декларацию 3-НДФЛ", next: "block4_ch1_A" },
                { text: "Ждать, пока налоговая сама пришлёт вычет", next: "block4_ch1_C" },
                { text: "Обратиться в бухгалтерию/отдел кадров на работе", next: "block4_ch1_B", coins: 20 }
            ]
        },
        "block4_ch1_A": { speaker: "Рыжий Кот", text: "Можно и так, но зачем усложнять? Есть путь короче.", next: "block4_choice1" },
        "block4_ch1_C": { speaker: "Рыжий Кот", text: "Этот вычет сам себя не найдёт — его получают через работодателя, а не ждут у моря погоды.", next: "block4_choice1" },
        "block4_ch1_B": { speaker: "Гусеница Bugatti", text: "Именно так. Принеси в бухгалтерию копию свидетельства о рождении, для дочери — справку из вуза об очной форме, и заявление. Дальше зарплата сама станет немного больше.", next: "block4_scene2" },

        "block4_scene2": {
            bg: "images/bg_gto.png", speaker: "Рыжий Кот",
            text: "А вот и моё любимое нововведение. С 2025 года государство платит тебе за заботу о себе. Сдай нормы ГТО, получи знак отличия — и пройди диспансеризацию в том же году. Вот тогда вычет твой. 18 000 рублей в год.", sprite: "images/cat_full.png",
            next: "block4_choice2"
        },
        "block4_choice2": {
            speaker: "Выбор", text: "Валера в этом году сдал ГТО в марте, а диспансеризацию прошёл в декабре прошлого года. Получит он вычет?",
            choices: [
                { text: "Да, оба события были", next: "block4_ch2_A" },
                { text: "Да, если попросит по-хорошему", next: "block4_ch2_C" },
                { text: "Нет, годы должны совпадать", next: "block4_ch2_B", coins: 20 }
            ]
        },
        "block4_ch2_A": { speaker: "Гусеница Bugatti", text: "Увы. Правило простое — оба события в одном календарном году.", next: "block4_choice2" },
        "block4_ch2_C": { speaker: "Гусеница Bugatti", text: "Увы. Правило простое — оба события в одном календарном году.", next: "block4_choice2" },
        "block4_ch2_B": { speaker: "Рыжий Кот", text: "Соображаешь. Получить этот вычет можно у работодателя, единовременно, в любом месяце — просто принеси документы.", next: "block4_scene3" },

        "block4_scene3": {
            bg: "images/bg_social_forest.png", speaker: "Рыжий Кот",
            text: "Здесь всё, на что ты обычно тратишься сам. Учёба, лечение, фитнес — общий лимит вычета 150 000 рублей в год. А вот обучение детей считается отдельно — до 110 000 рублей на каждого ребёнка. Дорогостоящее лечение вообще не ограничено лимитом.", sprite: "images/cat_full.png",
            next: "block4_choice3"
        },
        "block4_choice3": {
            speaker: "Выбор", text: "Валера потратил: 40 000 ₽ на обучение, 90 000 ₽ на фитнес, и 80 000 ₽ на обучение сына. Сколько войдёт в общий лимит?",
            choices: [
                { text: "Все 210 000 войдут в общий лимит", next: "block4_ch3_A" },
                { text: "Всё войдёт в лимит на ребёнка", next: "block4_ch3_C" },
                { text: "130 000 — в общий лимит, а 80 000 за сына — отдельно", next: "block4_ch3_B", coins: 30 }
            ]
        },
        "block4_ch3_A": { speaker: "Рыжий Кот", text: "Не совсем. Обучение и лечение за себя — это один котёл, а за детей — отдельный.", next: "block4_choice3" },
        "block4_ch3_C": { speaker: "Рыжий Кот", text: "Не совсем. Обучение и лечение за себя — это один котёл, а за детей — отдельный.", next: "block4_choice3" },
        "block4_ch3_B": { speaker: "Гусеница Bugatti", text: "Прекрасно! Именно так — траты Валеры на себя (130 000) укладываются в общий лимит 150 000, а 80 000 за сына — отдельно.", next: "block4_scene4" },

        "block4_scene4": {
            bg: "images/bg_archive.png", speaker: "Рыжий Кот",
            text: "Раньше здесь был хаос — договоры, чеки, лицензии для каждого вычета отдельно. Теперь порядок: одна справка на всё. Но это только для трат после 1 января 2024 года.", sprite: "images/cat_full.png",
            next: "block4_choice4"
        },
        "block4_choice4": {
            speaker: "Выбор", text: "Что нужно сделать, чтобы получить вычет в упрощённом порядке?",
            choices: [
                { text: "Собрать справки, чеки и лично отнести их в налоговую", next: "block4_ch4_A" },
                { text: "Ничего, вычет придёт сам собой без всяких действий", next: "block4_ch4_C" },
                { text: "Дождаться предзаполненного заявления в Личном кабинете и просто подписать его", next: "block4_ch4_B", coins: 25 }
            ]
        },
        "block4_ch4_A": { speaker: "Рыжий Кот", text: "Это как раз то, от чего мы избавились. Не в этот раз.", next: "block4_choice4" },
        "block4_ch4_C": { speaker: "Гусеница Bugatti", text: "Подписать заявление всё же придётся — само оно не подтвердится.", next: "block4_choice4" },
        "block4_ch4_B": { speaker: "Рыжий Кот", text: "Организация сама передаст данные — с твоего согласия. В марте следующего года жди сообщение в Личном кабинете.", next: "block4_scene5" },

        "block4_scene5": {
            bg: "images/bg_palace.png", speaker: "Рыжий Кот",
            text: "Добро пожаловать в самое новое крыло Страны Налогов. С 2026 года здесь раздают кешбэк. Если в семье двое и более детей, и средний доход на человека ниже 1,5 прожиточного минимума — налог пересчитывается по ставке 6% вместо 13%.", sprite: "images/cat_full.png",
            next: "block4_choice5"
        },
        "block4_choice5": {
            speaker: "Выбор", text: "У Гены трое детей, доход 1 450 000 ₽, прожиточный минимум 17 733 ₽. Подходит ли Гена под кешбэк?",
            choices: [
                { text: "Не подходит, доход слишком большой", next: "block4_ch5_A" },
                { text: "Невозможно посчитать без дополнительных данных", next: "block4_ch5_C" },
                { text: "Подходит, доход ниже порога", next: "block4_ch5_B", coins: 30 }
            ]
        },
        "block4_ch5_A": { speaker: "Рыжий Кот", text: "Кот качает головой, показывает лапой на цифры выше.", next: "block4_choice5" },
        "block4_ch5_C": { speaker: "Рыжий Кот", text: "Кот качает головой, показывает лапой на цифры выше.", next: "block4_choice5" },
        "block4_ch5_B": { speaker: "Гусеница Bugatti", text: "Верно! И сумма кешбэка — это разница между налогом по 13% и по 6% — то есть 101 500 ₽ в год!", next: "final" },

        // ФИНАЛ
        "final": {
            bg: "images/bg_final.png", speaker: "Рыжий Кот",
            text: "Ну что, Валера, готов открыть сундук? Помни: вычет сам не придёт, если ты сам не протянешь руку. Увидимся в другой раз!", sprite: "images/cat_smile.png",
            next: "end_game"
        },
        "end_game": {
            speaker: "Система", text: "Конец игры! Вы собрали " + state.coins + " монет любопытства. Спасибо за игру!",
            next: null
        }
    };

    // ==========================================
    // ЛОГИКА ИГРЫ (JS)
    // ==========================================
    const bgElement = document.getElementById('game-container');
    const speakerElement = document.getElementById('speaker');
    const textElement = document.getElementById('text');
    const spriteElement = document.getElementById('character-sprite');
    const choicesElement = document.getElementById('choices');
    const dialogueBox = document.getElementById('dialogue-box');
    const coinDisplay = document.getElementById('coins-display');
    const coinCount = document.getElementById('coin-count');

    function updateScene() {
        const scene = story[state.currentLabel];
        if (!scene) {
            console.error("Сцена не найдена: " + state.currentLabel);
            return;
        }

        // Обновляем монеты
        coinCount.innerText = state.coins;
        if (state.coins > 0) coinDisplay.style.display = 'block';

        // Если это слайд с выбором
        if (scene.choices) {
            dialogueBox.style.display = 'none';
            choicesElement.style.display = 'flex';
            choicesElement.innerHTML = '';
            
            scene.choices.forEach(choice => {
                const btn = document.createElement('button');
                btn.className = 'choice-btn';
                btn.innerText = choice.text;
                btn.onclick = () => {
                    if (choice.coins) state.coins += choice.coins;
                    state.currentLabel = choice.next;
                    choicesElement.style.display = 'none';
                    dialogueBox.style.display = 'flex';
                    updateScene();
                };
                choicesElement.appendChild(btn);
            });
            return;
        }

        // Обычный слайд
        dialogueBox.style.display = 'flex';
        
        // Меняем фон
        if (scene.bg) {
            bgElement.style.backgroundImage = `url('${scene.bg}')`;
        }
        
        // Меняем текст и говорящего
        speakerElement.innerText = scene.speaker || "Система";
        textElement.innerText = scene.text || "";
        
        // Показываем/скрываем спрайт
        if (scene.sprite) {
            spriteElement.src = scene.sprite;
            spriteElement.style.display = 'block';
        } else {
            spriteElement.style.display = 'none';
        }
    }

    function nextSlide() {
        const scene = story[state.currentLabel];
        if (scene.choices || !scene.next) return; // Если выбор или конец игры

        state.currentLabel = scene.next;
        updateScene();
    }

    // Запуск игры
    updateScene();
</script>

</body>
</html>
```
