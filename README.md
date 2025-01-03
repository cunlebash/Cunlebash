<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.5">
    <title>Merged Floating Balls and Icons</title>
    <style>
        body {
            margin: 0;
            overflow: hidden;
            background-color: black;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            flex-direction: column;
        }

        .ball {
            position: absolute;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            color: white;
            font-weight: bold;
            font-family: Arial, sans-serif;
            text-align: center;
            transition: transform 0.2s;
        }

        .ball a {
            text-decoration: none;
            color: white;
        }

        .ball:nth-child(1) { background-color: red; }
        .ball:nth-child(2) { background-color: blue; }
        .ball:nth-child(3) { background-color: green; }
        .ball:nth-child(4) { background-color: yellow; }
        .ball:nth-child(5) { background-color: purple; }
        .ball:nth-child(6) { background-color: orange; }
        .ball:nth-child(7) { background-color: pink; }
        .ball:nth-child(8) { background-color: cyan; }
        .ball:nth-child(9) { background-color: lime; }
        .ball:nth-child(10) { background-color: teal; }
        .ball:nth-child(11) { background-color: magenta; }
        .ball:nth-child(12) { background-color: violet; }
        .ball:nth-child(13) { background-color: coral; }
        .ball:nth-child(14) { background-color: skyblue; }
        .ball:nth-child(15) { background-color: gold; }

        .ball:hover {
            transform: scale(1.1);
        }

        .bottom-icons {
            position: fixed;
            bottom: 0;
            left: 0;
            width: 100%;
            display: flex;
            justify-content: space-around;
            padding: 10px 0;
            background-color: transparent;
        }

        .bottom-icons a {
            color: #b21807;
            font-size: 40px;
            text-decoration: none;
            padding: 10px;
        }

        .bottom-icons a:hover {
            color: yellow;
        }

        .circle-plus {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background-color: #b21807;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .circle-plus i {
            color: white;
            font-size: 20px;
        }
       
        /* Existing styles... */
        
        .bottom-icons a {
        color: #b21807;
        font-size: 30px; /* Reduced from 40px to 30px */
        text-decoration: none;
        padding: 10px;
        }
        
        .circle-plus {
        width: 40px; /* Reduced from 50px */
        height: 40px; /* Reduced from 50px */
        border-radius: 50%;
        background-color: #b21807;
        display: flex;
        align-items: center;
        justify-content: center;
        }
        
        .circle-plus i {
        font-size: 16px; /* Reduced from 20px */
        }
        
    </style>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
</head>
<body>
    <!-- Floating Balls -->
    <div class="ball"><a href="go:S001">Wind</a></div>
    <div class="ball"><a href="go:S002">Flow</a></div>
    <div class="ball"><a href="go:S003">Cunle</a></div>
    <div class="ball"><a href="go:S004">Date</a></div>
    <div class="ball"><a href="go:S005">Elite</a></div>
    <div class="ball"><a href="go:S006">Cold</a></div>
    <div class="ball"><a href="go:S007">Hero</a></div>
    <div class="ball"><a href="go:S008">Noble</a></div>
    <div class="ball"><a href="go:S009">Gold</a></div>
    <div class="ball"><a href="go:S010">Best</a></div>
    <div class="ball"><a href="go:S011">Snow</a></div>
    <div class="ball"><a href="go:S012">Light</a></div>
    <div class="ball"><a href="go:S013">Gate</a></div>
    <div class="ball"><a href="go:S014">Zone</a></div>
    <div class="ball"><a href="go:S015">Hot</a></div>

    <!-- Bottom Icons -->
    <div class="bottom-icons">
        <a href="tel:914462626"><i class="fas fa-phone"></i></a>
        <a href="smsto:614462626?body=message_text"><i class="fas fa-sms"></i></a>
        <a href="mailto:example@example.com"><i class="fas fa-envelope"></i></a>
        <a href="#"><div class="circle-plus"><i class="fas fa-plus"></i></div></a>
    </div>

    <script>
        const balls = document.querySelectorAll('.ball');
        const initialSizes = [70, 60, 80, 50, 90, 75, 65, 55, 85, 60, 70, 50, 90, 65, 75];
        const speedFactors = [1.5, 2.0, 1.2, 1.8, 2.2, 1.6, 1.3, 2.1, 1.7, 2.3, 1.4, 2.4, 1.1, 2.5, 1.9];
        const screenWidth = window.innerWidth;
        const screenHeight = window.innerHeight;

        function getRandomSize() {
            return Math.floor(Math.random() * 50) + 50;
        }

        balls.forEach((ball, index) => {
            ball.style.left = Math.random() * (screenWidth - 100) + 'px';
            ball.style.top = (screenHeight - Math.random() * 100) + 'px';
            ball.style.width = initialSizes[index] + 'px';
            ball.style.height = initialSizes[index] + 'px';
        });

        function animateBall(ball, speedFactor) {
            let posY = parseInt(ball.style.top, 10);

            setInterval(() => {
                posY -= 2 * speedFactor;

                if (posY < -100) {
                    posY = screenHeight + Math.random() * 100;
                    ball.style.left = Math.random() * (screenWidth - 100) + 'px';
                    const newSize = getRandomSize();
                    ball.style.width = newSize + 'px';
                    ball.style.height = newSize + 'px';
                }

                ball.style.top = posY + 'px';
            }, 20);
        }

        balls.forEach((ball, index) => {
            animateBall(ball, speedFactors[index]);
        });
    </script>
</body>
</html>
