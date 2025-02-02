<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Will You Be My Valentine?</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: pink;
            font-family: Arial, sans-serif;
            overflow: hidden;
            flex-direction: column;
            margin: 0;
        }
        .container {
            text-align: center;
            background: white;
            padding: 20px;
            border-radius: 15px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
            margin-bottom: 30px;
            width: 80%;
            max-width: 500px;
        }
        h1 {
            color: red;
            font-size: 1.5em;
            margin-bottom: 20px;
        }
        .buttons {
            margin-top: 20px;
        }
        .btn {
            padding: 12px 25px;
            font-size: 18px;
            border: none;
            cursor: pointer;
            border-radius: 10px;
            margin: 5px;
        }
        .yes {
            background-color: red;
            color: white;
        }
        .no {
            background-color: gray;
            color: white;
        }
        .hearts {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
        }
        .heart {
            position: absolute;
            color: red;
            font-size: 30px;
            animation: float 5s linear infinite;
        }
        @keyframes float {
            from {
                transform: translateY(100vh);
                opacity: 1;
            }
            to {
                transform: translateY(-10vh);
                opacity: 0;
            }
        }
        .pompompurin-image {
            margin-top: 20px;
            width: 100%;
            height: auto;
            max-width: 150px;
        }
        .footer {
            font-size: 14px;
            color: gray;
            margin-top: 20px;
        }

        /* Responsive design for smaller screens */
        @media (max-width: 600px) {
            h1 {
                font-size: 1.3em;
            }
            .btn {
                font-size: 16px;
                padding: 10px 20px;
            }
            .pompompurin-image {
                width: 80%;
                max-width: 120px;
            }
        }

    </style>
</head>
<body>
    <div class="hearts"></div>
    <div class="container">
        <h1>Will You Be My Valentine?</h1>
        <div class="buttons">
            <button class="btn yes" onclick="acceptLove()">Yes</button>
            <button class="btn no" onmouseover="moveNo()">No</button>
        </div>
        <img class="pompompurin-image" id="pompompurinImg" src="https://media.tenor.com/ZhNxfL0GmoMAAAAj/mocha-bear-hearts.gif" alt="mocha-bear-hearts">
    </div>
    <div class="footer">
        Created by Michael :3
    </div>

    <script>
        function acceptLove() {
            alert("YIPPEEE thy highness u have made my heart bloom with joy! (●'◡'●)");
            // Change the Pompompurin image
            const img = document.getElementById('pompompurinImg');
            img.src = "https://i.pinimg.com/originals/5a/c2/27/5ac2275ba30265fb4053623741bebc22.gif"; // New image source
        }
        
        function moveNo() {
            const btnNo = document.querySelector('.no');
            btnNo.style.top = Math.random() * window.innerHeight + 'px';
            btnNo.style.left = Math.random() * window.innerWidth + 'px';
        }

        function createHeart() {
            const heart = document.createElement("div");
            heart.innerHTML = "❤️";
            heart.classList.add("heart");
            heart.style.left = Math.random() * 100 + "vw";
            heart.style.animationDuration = Math.random() * 3 + 2 + "s";
            document.querySelector(".hearts").appendChild(heart);
            setTimeout(() => heart.remove(), 5000);
        }

        setInterval(createHeart, 300);
    </script>
</body>
</html>
