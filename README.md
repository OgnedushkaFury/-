<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>КОНКУРС с призами </title>
    <link href="https://fonts.googleapis.com/css2?family=Russo+One&family=Comfortaa:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Comfortaa', sans-serif;
            background: #1a0a00;
            color: #fff;
            overflow-x: hidden;
        }

        /* Animated fire particles */
        .fire-particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
        }

        .particle {
            position: absolute;
            width: 4px;
            height: 4px;
            border-radius: 50%;
            animation: floatUp linear infinite;
            opacity: 0;
        }

        @keyframes floatUp {
            0% {
                opacity: 0;
                transform: translateY(100vh) scale(0);
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 0.6;
            }
            100% {
                opacity: 0;
                transform: translateY(-20vh) scale(1);
            }
        }

        .wrapper {
            position: relative;
            z-index: 1;
        }

        /* Hero Banner */
        .hero {
            position: relative;
            width: 100%;
            max-width: 800px;
            margin: 0 auto;
            overflow: hidden;
        }

        .hero img {
            width: 100%;
            display: block;
        }

        .hero-overlay {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            height: 60%;
            background: linear-gradient(to top, #1a0a00 0%, transparent 100%);
        }

        /* Title Section */
        .title-section {
            text-align: center;
            padding: 30px 20px 20px;
            position: relative;
        }

        .title-section h1 {
            font-family: 'Russo One', sans-serif;
            font-size: 2.8em;
            color: #ff6a00;
            text-shadow: 0 0 20px rgba(255, 106, 0, 0.8),
                         0 0 40px rgba(255, 106, 0, 0.4),
                         0 0 60px rgba(255, 68, 0, 0.3);
            animation: fireGlow 2s ease-in-out infinite alternate;
            letter-spacing: 3px;
        }

        @keyframes fireGlow {
            0% {
                text-shadow: 0 0 20px rgba(255, 106, 0, 0.8),
                             0 0 40px rgba(255, 106, 0, 0.4);
                color: #ff8c00;
            }
            100% {
                text-shadow: 0 0 30px rgba(255, 68, 0, 1),
                             0 0 60px rgba(255, 68, 0, 0.6),
                             0 0 80px rgba(255, 0, 0, 0.3);
                color: #ffaa00;
            }
        }

        .subtitle {
            font-family: 'Russo One', sans-serif;
            font-size: 1.4em;
            color: #ffaa00;
            text-shadow: 0 0 15px rgba(255, 170, 0, 0.6);
            margin-top: 5px;
        }

        .date-badge {
            display: inline-block;
            margin-top: 15px;
            padding: 10px 30px;
            background: linear-gradient(135deg, #ff6a00, #ff2200);
            border-radius: 50px;
            font-weight: 700;
            font-size: 1.1em;
            color: #fff;
            box-shadow: 0 4px 25px rgba(255, 68, 0, 0.5);
            animation: pulse 2s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); box-shadow: 0 4px 25px rgba(255, 68, 0, 0.5); }
            50% { transform: scale(1.05); box-shadow: 0 4px 35px rgba(255, 68, 0, 0.8); }
        }

        /* Divider */
        .divider {
            width: 100%;
            max-width: 800px;
            margin: 0 auto;
            text-align: center;
            padding: 10px 20px;
        }

        .divider .line {
            height: 2px;
            background: linear-gradient(to right, transparent, #ff6a00, #ffaa00, #ff6a00, transparent);
            margin: 20px 0;
            border-radius: 2px;
        }

        .divider .stars {
            font-size: 1.2em;
            color: #ffaa00;
            letter-spacing: 8px;
            animation: twinkle 1.5s ease-in-out infinite alternate;
        }

        @keyframes twinkle {
            0% { opacity: 0.6; }
            100% { opacity: 1; }
        }

        /* Content */
        .content {
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
        }

        .section {
            background: linear-gradient(135deg, rgba(255, 106, 0, 0.08) 0%, rgba(255, 34, 0, 0.05) 100%);
            border: 1px solid rgba(255, 106, 0, 0.2);
            border-radius: 20px;
            padding: 30px;
            margin-bottom: 25px;
            backdrop-filter: blur(10px);
            animation: fadeInUp 0.8s ease-out;
            position: relative;
            overflow: hidden;
        }

        .section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: linear-gradient(to right, #ff6a00, #ffaa00, #ff6a00);
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .section-title {
            font-family: 'Russo One', sans-serif;
            font-size: 1.8em;
            color: #ffaa00;
            text-shadow: 0 0 15px rgba(255, 170, 0, 0.5);
            margin-bottom: 20px;
            text-align: center;
        }

        .section-title .emoji {
            margin: 0 8px;
        }

        /* Task Section */
        .task-text {
            font-size: 1.1em;
            line-height: 1.8;
            color: #ffe0b2;
            text-align: center;
        }

        .dragon-names {
            color: #ff6a00;
            font-weight: 700;
            font-size: 1.2em;
            text-shadow: 0 0 10px rgba(255, 106, 0, 0.4);
        }

        /* Prizes */
        .prizes-grid {
            display: grid;
            gap: 12px;
        }

        .prize-item {
            display: flex;
            align-items: flex-start;
            gap: 15px;
            padding: 15px 20px;
            background: rgba(255, 106, 0, 0.08);
            border-radius: 12px;
            border-left: 4px solid;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .prize-item:hover {
            transform: translateX(8px);
            box-shadow: 0 4px 20px rgba(255, 106, 0, 0.2);
        }

        .prize-item:nth-child(1) {
            border-left-color: #ffd700;
            background: rgba(255, 215, 0, 0.08);
        }
        .prize-item:nth-child(2) {
            border-left-color: #c0c0c0;
            background: rgba(192, 192, 192, 0.08);
        }
        .prize-item:nth-child(3) {
            border-left-color: #cd7f32;
            background: rgba(205, 127, 50, 0.08);
        }
        .prize-item:nth-child(4),
        .prize-item:nth-child(5) {
            border-left-color: #ff6a00;
        }

        .prize-place {
            font-weight: 700;
            font-size: 1.3em;
            min-width: 80px;
            white-space: nowrap;
        }

        .prize-item:nth-child(1) .prize-place { color: #ffd700; }
        .prize-item:nth-child(2) .prize-place { color: #c0c0c0; }
        .prize-item:nth-child(3) .prize-place { color: #cd7f32; }
        .prize-item:nth-child(4) .prize-place,
        .prize-item:nth-child(5) .prize-place { color: #ff6a00; }

        .prize-desc {
            color: #ffe0b2;
            line-height: 1.5;
            font-size: 1em;
        }

        /* References */
        .refs-list {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 12px;
        }

        .ref-chip {
            padding: 10px 24px;
            background: linear-gradient(135deg, rgba(255, 106, 0, 0.2), rgba(255, 34, 0, 0.1));
            border: 1px solid rgba(255, 106, 0, 0.3);
            border-radius: 50px;
            color: #ffaa00;
            font-weight: 600;
            font-size: 1.05em;
            transition: all 0.3s ease;
        }

        .ref-chip:hover {
            background: linear-gradient(135deg, rgba(255, 106, 0, 0.4), rgba(255, 34, 0, 0.2));
            transform: scale(1.08);
            box-shadow: 0 0 20px rgba(255, 106, 0, 0.3);
        }

        /* Dates */
        .dates-box {
            text-align: center;
            padding: 25px;
            background: linear-gradient(135deg, rgba(255, 68, 0, 0.15), rgba(255, 106, 0, 0.08));
            border-radius: 15px;
            border: 1px solid rgba(255, 106, 0, 0.3);
        }

        .dates-box .date-text {
            font-family: 'Russo One', sans-serif;
            font-size: 1.6em;
            color: #ffaa00;
            text-shadow: 0 0 15px rgba(255, 170, 0, 0.4);
        }

        .dates-box .date-sub {
            color: #ffcc80;
            margin-top: 8px;
            font-size: 1em;
        }

        /* Rules */
        .rules-list {
            list-style: none;
            display: grid;
            gap: 10px;
        }

        .rules-list li {
            display: flex;
            align-items: flex-start;
            gap: 12px;
            padding: 12px 18px;
            background: rgba(255, 255, 255, 0.03);
            border-radius: 10px;
            color: #ffe0b2;
            line-height: 1.5;
            font-size: 0.95em;
            transition: background 0.3s ease;
        }

        .rules-list li:hover {
            background: rgba(255, 106, 0, 0.1);
        }

        .rules-list li .icon {
            color: #ff6a00;
            font-size: 1.2em;
            flex-shrink: 0;
            margin-top: 2px;
        }

        /* CTA Button */
        .cta-section {
            text-align: center;
            padding: 40px 20px 60px;
        }

        .cta-button {
            display: inline-flex;
            align-items: center;
            gap: 12px;
            padding: 20px 50px;
            background: linear-gradient(135deg, #2AABEE, #1E8FD2);
            color: #fff;
            text-decoration: none;
            font-family: 'Russo One', sans-serif;
            font-size: 1.4em;
            border-radius: 60px;
            box-shadow: 0 8px 30px rgba(42, 171, 238, 0.4);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .cta-button::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255,255,255,0.1), transparent);
            transform: rotate(45deg);
            animation: shimmer 3s infinite;
        }

        @keyframes shimmer {
            0% { transform: translateX(-100%) rotate(45deg); }
            100% { transform: translateX(100%) rotate(45deg); }
        }

        .cta-button:hover {
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 12px 40px rgba(42, 171, 238, 0.6);
        }

        .cta-button:active {
            transform: translateY(0) scale(0.98);
        }

        .cta-button .tg-icon {
            font-size: 1.3em;
        }

        /* Decorative dragon */
        .dragon-deco {
            text-align: center;
            font-size: 3em;
            margin: 15px 0;
            animation: dragonFloat 3s ease-in-out infinite;
        }

        @keyframes dragonFloat {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        /* Footer */
        .footer {
            text-align: center;
            padding: 20px;
            color: rgba(255, 255, 255, 0.3);
            font-size: 0.8em;
        }

        /* Responsive */
        @media (max-width: 600px) {
            .title-section h1 {
                font-size: 2em;
            }
            .section {
                padding: 20px;
            }
            .section-title {
                font-size: 1.4em;
            }
            .prize-item {
                flex-direction: column;
                gap: 5px;
            }
            .cta-button {
                padding: 16px 35px;
                font-size: 1.1em;
            }
            .dragon-names {
                font-size: 1.05em;
            }
        }

        /* Scroll reveal animation */
        .reveal {
            opacity: 0;
            transform: translateY(40px);
            transition: all 0.8s ease-out;
        }
        .reveal.visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>

    <!-- Fire Particles Background -->
    <div class="fire-particles" id="particles"></div>

    <div class="wrapper">
        <!-- Hero Banner -->
        <div class="hero">
            <img src="https://i.postimg.cc/sXCH0sm4/IMG-20260416-135105-120.jpg" alt="Конкурс с призами">
            <div class="hero-overlay"></div>
        </div>

        <!-- Title -->
        <div class="title-section">
            <h1>🔥 КОНКУРС 🔥</h1>
            <div class="subtitle">с призами</div>
            <div class="date-badge">📅 с 12 апреля по 12 июня</div>
        </div>

        <!-- Divider -->
        <div class="divider">
            <div class="line"></div>
            <div class="stars"> ★ ✧ ★ ✦</div>
            <div class="line"></div>
        </div>

        <!-- Content -->
        <div class="content">

            <!-- ЗАДАНИЕ -->
            <div class="section reveal">
                <div class="section-title">
                    <span class="emoji">🎨</span> ЗАДАНИЕ <span class="emoji">🎨</span>
                </div>
                <div class="dragon-deco">🐉</div>
                <p class="task-text">
                    Нарисовать <strong>3 моих дракончиков</strong> в одном арте!<br><br>
                    <span class="dragon-names">
                        Огнев, Огнедушка и Игница
                    </span>
                </p>
                <div class="dragon-deco">🐉🐉</div>
            </div>

            <!-- ПРИЗЫ -->
            <div class="section reveal">
                <div class="section-title">
                    <span class="emoji"></span> ПРИЗЫ <span class="emoji">🏆</span>
                </div>
                <div class="prizes-grid">
                    <div class="prize-item">
                        <span class="prize-place">🥇 1. Место</span>
                        <span class="prize-desc">Коллаб видео со мной и с победителем</span>
                    </div>
                    <div class="prize-item">
                        <span class="prize-place">🥈 2. Место</span>
                        <span class="prize-desc">Коллаб Арт со мной и с вторым победителем конкурса</span>
                    </div>
                    <div class="prize-item">
                        <span class="prize-place">🥉 3. Место</span>
                        <span class="prize-desc">Пиар пост в ТГК</span>
                    </div>
                    <div class="prize-item">
                        <span class="prize-place">4. Место</span>
                        <span class="prize-desc">Арт</span>
                    </div>
                    <div class="prize-item">
                        <span class="prize-place">5. Место</span>
                        <span class="prize-desc">Арт</span>
                    </div>
                </div>
            </div>

            <!-- РЕФЕРЕНСЫ -->
            <div class="section reveal">
                <div class="section-title">
                    <span class="emoji">📎</span> РЕФЕРЕНСЫ <span class="emoji">📎</span>
                </div>
                <div class="refs-list">
                    <div class="ref-chip">🔥 Огнедушка</div>
                    <div class="ref-chip"> Игница</div>
                    <div class="ref-chip">🔥 Огнев</div>
                </div>
            </div>

            <!-- ДАТЫ -->
            <div class="section reveal">
                <div class="section-title">
                    <span class="emoji">📅</span> ДАТЫ <span class="emoji">📅</span>
                </div>
                <div class="dates-box">
                    <div class="date-text">12 Апреля — 12 Июня</div>
                    <div class="date-sub">Не пропустите дедлайн! ⏰</div>
                </div>
            </div>

            <!-- ПРАВИЛА -->
            <div class="section reveal">
                <div class="section-title">
                    <span class="emoji"></span> ПРАВИЛА <span class="emoji">📜</span>
                </div>
                <ul class="rules-list">
                    <li>
                        <span class="icon">🚫</span>
                        <span>Не срисовывать</span>
                    </li>
                    <li>
                        <span class="icon">🎬</span>
                        <span>Скинуть спидпеинт</span>
                    </li>
                    <li>
                        <span class="icon">️</span>
                        <span>Скинуть в одном арте</span>
                    </li>
                    <li>
                        <span class="icon">⏰</span>
                        <span>Присылать до дедлайна</span>
                    </li>
                    <li>
                        <span class="icon">📵</span>
                        <span>Не присылать в огненнтарию / ролку чат</span>
                    </li>
                    <li>
                        <span class="icon">✍️</span>
                        <span>Рисовать от начала до конца самим</span>
                    </li>
                    <li>
                        <span class="icon">🤖</span>
                        <span>Не используйте ИИ для создания позы / обработки</span>
                    </li>
                </ul>
            </div>

        </div>

        <!-- Divider -->
        <div class="divider">
            <div class="line"></div>
            <div class="stars">✦ ★ ✧ ★ ✦</div>
            <div class="line"></div>
        </div>

        <!-- CTA -->
        <div class="cta-section reveal">
            <a href="https://t.me/ognedushka822" target="_blank" class="cta-button">
                <span class="tg-icon">📲</span>
                ПОДПИСАТЬСЯ НА ТГК
            </a>
        </div>

        <!-- Footer -->
        <div class="footer">
            🐉 Конкурс Огнедушка 🐉
        </div>
    </div>

    <script>
        // Create fire particles
        const particlesContainer = document.getElementById('particles');
        const particleCount = 30;

        for (let i = 0; i < particleCount; i++) {
            const particle = document.createElement('div');
            particle.classList.add('particle');

            const hue = Math.random() * 40 + 10; // orange-red range
            const size = Math.random() * 4 + 2;
            const left = Math.random() * 100;
            const duration = Math.random() * 6 + 4;
            const delay = Math.random() * 8;

            particle.style.cssText = `
                left: ${left}%;
                width: ${size}px;
                height: ${size}px;
                background: hsl(${hue}, 100%, ${50 + Math.random() * 20}%);
                box-shadow: 0 0 ${size * 2}px hsl($# -
Конкурс на 5 мест
