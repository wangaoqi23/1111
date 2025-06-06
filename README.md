# 1111
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0">
    <title>母亲节快乐</title>
    <style>
        /* 基础样式 */
        body {
            margin: 0;
            padding: 0;
            font-family: 'Microsoft YaHei', 'PingFang SC', sans-serif;
            background: linear-gradient(135deg, #ff9a9e, #fad0c4);
            min-height: 100vh;
            overflow-x: hidden;
        }

        .container {
            padding: 20px;
            text-align: center;
            color: #6d3d2f;
        }

        /* 标题样式 */
        .title {
            font-size: 2.2rem;
            margin: 20px 0;
            animation: fadeInUp 1s ease;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
        }

        /* 祝福内容 */
        .content {
            font-size: 1.1rem;
            line-height: 1.8;
            margin: 20px 0;
            animation: fadeIn 2s ease;
        }

        /* 心形动画 */
        .heart {
            color: #ff4081;
            font-size: 3rem;
            animation: heartbeat 1.5s infinite;
            margin: 20px 0;
        }

        /* 花瓣动画 */
        .petal {
            position: absolute;
            width: 15px;
            height: 15px;
            background: rgba(255, 192, 203, 0.7);
            border-radius: 50% 50% 0 50%;
            transform: rotate(-45deg);
            animation: fall linear infinite;
        }

        /* 动画定义 */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes heartbeat {
            0% { transform: scale(1); }
            50% { transform: scale(1.2); }
            100% { transform: scale(1); }
        }

        @keyframes fall {
            to {
                transform: translateY(100vh) rotate(360deg);
                opacity: 0;
            }
        }
    </style>
</head>
<body>
    <!-- 花瓣容器 -->
    <div id="petals"></div>

    <div class="container">
        <div class="heart">❤</div>
        <h1 class="title">妈妈，母亲节快乐！</h1>
        
        <div class="content">
            <p>感谢您多年的辛勤付出，</p >
            <p>您的爱如同春天的阳光温暖我心，</p >
            <p>愿时光慢些走，愿您永远健康美丽！</p >
        </div>

        <div class="heart">❤</div>
    </div>

    <script>
        // 创建花瓣动画
        function createPetals() {
            const petalsContainer = document.getElementById('petals');
            const petalCount = 15;

            for (let i = 0; i < petalCount; i++) {
                const petal = document.createElement('div');
                petal.className = 'petal';
                
                // 随机设置位置和动画时长
                petal.style.left = Math.random() * 100 + 'vw';
                petal.style.animationDuration = Math.random() * 3 + 2 + 's';
                petal.style.animationDelay = Math.random() * 2 + 's';
                
                petalsContainer.appendChild(petal);
            }
        }

        // 初始化
        window.onload = function() {
            createPetals();
            
            // 添加点击祝福语特效
            document.querySelector('.title').addEventListener('click', function() {
                this.style.transform = 'scale(1.1)';
                setTimeout(() => {
                    this.style.transform = 'scale(1)';
                }, 200);
            });
        }
    </script>
</body>
</html>
