<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>پرام می‌ریزه! 💥</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(135deg, #0f0f23 0%, #1a1a2e 50%, #16213e 100%);
            color: #00ff88;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            position: relative;
        }

        /* ستاره‌های درحال حرکت */
        .stars {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
        }

        .star {
            position: absolute;
            background: white;
            border-radius: 50%;
            animation: twinkle var(--duration) infinite ease-in-out;
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0.2; }
            50% { opacity: 1; }
        }

        .container {
            text-align: center;
            z-index: 10;
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(20px);
            border-radius: 20px;
            padding: 3rem;
            border: 1px solid rgba(0, 255, 136, 0.3);
            box-shadow: 0 0 50px rgba(0, 255, 136, 0.2);
            position: relative;
            overflow: hidden;
        }

        .container::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: conic-gradient(
                transparent,
                rgba(0, 255, 136, 0.3),
                transparent 30%
            );
            animation: rotate 6s linear infinite;
        }

        @keyframes rotate {
            100% {
                transform: rotate(360deg);
            }
        }

        .content {
            position: relative;
            z-index: 2;
            background: rgba(15, 15, 35, 0.9);
            border-radius: 15px;
            padding: 2rem;
        }

        .main-title {
            font-size: 3.5rem;
            margin-bottom: 2rem;
            background: linear-gradient(45deg, #00ff88, #00ccff, #ff00ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-shadow: 0 0 30px rgba(0, 255, 136, 0.5);
            animation: glow 2s ease-in-out infinite alternate;
        }

        @keyframes glow {
            from {
                text-shadow: 0 0 20px rgba(0, 255, 136, 0.5);
            }
            to {
                text-shadow: 0 0 30px rgba(0, 255, 136, 0.8), 
                           0 0 40px rgba(0, 204, 255, 0.6);
            }
        }

        .typing-container {
            height: 120px;
            margin-bottom: 2rem;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .typing-text {
            font-size: 2.5rem;
            font-weight: bold;
            border-right: 3px solid #00ff88;
            padding-right: 10px;
            animation: blink 0.7s infinite;
        }

        @keyframes blink {
            0%, 100% { border-color: #00ff88; }
            50% { border-color: transparent; }
        }

        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 1rem;
            margin-top: 2rem;
        }

        .skill {
            background: rgba(0, 255, 136, 0.1);
            padding: 1rem;
            border-radius: 10px;
            border: 1px solid rgba(0, 255, 136, 0.3);
            transform: scale(0);
            animation: popIn 0.5s ease forwards;
            position: relative;
            overflow: hidden;
            transition: all 0.3s ease;
        }

        .skill:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 5px 20px rgba(0, 255, 136, 0.4);
            background: rgba(0, 255, 136, 0.2);
        }

        .skill::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(
                90deg,
                transparent,
                rgba(255, 255, 255, 0.2),
                transparent
            );
            transition: left 0.5s;
        }

        .skill:hover::before {
            left: 100%;
        }

        @keyframes popIn {
            to {
                transform: scale(1);
            }
        }

        .skill:nth-child(1) { animation-delay: 0.1s; }
        .skill:nth-child(2) { animation-delay: 0.2s; }
        .skill:nth-child(3) { animation-delay: 0.3s; }
        .skill:nth-child(4) { animation-delay: 0.4s; }
        .skill:nth-child(5) { animation-delay: 0.5s; }
        .skill:nth-child(6) { animation-delay: 0.6s; }
        .skill:nth-child(7) { animation-delay: 0.7s; }
        .skill:nth-child(8) { animation-delay: 0.8s; }
        .skill:nth-child(9) { animation-delay: 0.9s; }

        .pulse {
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        /* انیمیشن‌های ویژه */
        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        .floating {
            animation: float 3s ease-in-out infinite;
        }
    </style>
</head>
<body>
    <div class="stars" id="stars"></div>
    
    <div class="container floating">
        <div class="content">
            <h1 class="main-title pulse">🚀 پروفایل حرفه‌ای</h1>
            
            <div class="typing-container">
                <div class="typing-text" id="typing-text"></div>
            </div>

            <h2 style="margin-bottom: 1rem; color: #00ccff;">🛠 مهارت‌های من</h2>
            
            <div class="skills-container">
                <div class="skill">🐍 Django</div>
                <div class="skill">🐳 Docker</div>
                <div class="skill">🐧 Linux</div>
                <div class="skill">📚 Git</div>
                <div class="skill">🐍 Python</div>
                <div class="skill">🐘 PHP</div>
                <div class="skill">⚡ JavaScript</div>
                <div class="skill">💙 Dart</div>
                <div class="skill">🎨 HTML/CSS</div>
                <div class="skill">🔧 WordPress</div>
            </div>
        </div>
    </div>

    <script>
        // ایجاد ستاره‌ها
        function createStars() {
            const starsContainer = document.getElementById('stars');
            const starCount = 150;
            
            for (let i = 0; i < starCount; i++) {
                const star = document.createElement('div');
                star.className = 'star';
                
                const size = Math.random() * 3;
                star.style.width = `${size}px`;
                star.style.height = `${size}px`;
                
                star.style.left = `${Math.random() * 100}%`;
                star.style.top = `${Math.random() * 100}%`;
                
                star.style.setProperty('--duration', `${Math.random() * 3 + 2}s`);
                star.style.animationDelay = `${Math.random() * 5}s`;
                
                starsContainer.appendChild(star);
            }
        }

        // انیمیشن تایپ کردن
        function typeWriter(element, text, speed, callback) {
            let i = 0;
            element.innerHTML = '';
            
            function type() {
                if (i < text.length) {
                    element.innerHTML += text.charAt(i);
                    i++;
                    setTimeout(type, speed);
                } else if (callback) {
                    setTimeout(callback, 1000);
                }
            }
            type();
        }

        // انیمیشن پاک کردن
        function deleteText(element, speed, callback) {
            let text = element.innerHTML;
            let i = text.length;
            
            function deleteChar() {
                if (i > 0) {
                    element.innerHTML = text.substring(0, i - 1);
                    i--;
                    setTimeout(deleteChar, speed);
                } else if (callback) {
                    setTimeout(callback, 500);
                }
            }
            deleteChar();
        }

        // توالی انیمیشن‌ها
        function startAnimation() {
            const typingElement = document.getElementById('typing-text');
            const texts = [
                "نام شما",
                "Backend Developer"
            ];
            let textIndex = 0;

            function nextAnimation() {
                if (textIndex < texts.length) {
                    typeWriter(typingElement, texts[textIndex], 100, () => {
                        deleteText(typingElement, 50, () => {
                            textIndex++;
                            if (textIndex < texts.length) {
                                setTimeout(nextAnimation, 500);
                            }
                        });
                    });
                }
            }
            
            nextAnimation();
        }

        // راه‌اندازی
        document.addEventListener('DOMContentLoaded', function() {
            createStars();
            setTimeout(startAnimation, 1000);
            
            // افکت‌های تعاملی
            const skills = document.querySelectorAll('.skill');
            skills.forEach(skill => {
                skill.addEventListener('mouseenter', function() {
                    this.style.animation = 'none';
                    setTimeout(() => {
                        this.style.animation = '';
                    }, 10);
                });
            });
        });
    </script>
</body>
</html>
