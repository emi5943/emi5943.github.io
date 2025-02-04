
<html lang="bg">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Игра: Уцели квадрата</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }
        #square {
            width: 50px;
            height: 50px;
            background-color: red;
            position: absolute;
            top: 100px;
            left: 100px;
            cursor: pointer;
        }
    </style>
</head>
<body>

<h1>Уцели квадрата!</h1>
<p>Кликни върху червения квадрат възможно най-бързо.</p>
<p>Време за реакция: <span id="time">0</span> секунди</p>

<div id="square"></div>

<script>
    let square = document.getElementById("square");
    let timeDisplay = document.getElementById("time");
    let startTime;

    function moveSquare() {
        let x = Math.random() * (window.innerWidth - 50);
        let y = Math.random() * (window.innerHeight - 50);
        square.style.left = x + "px";
        square.style.top = y + "px";
        startTime = Date.now();
    }

    square.addEventListener("click", function () {
        let reactionTime = (Date.now() - startTime) / 1000;
        timeDisplay.textContent = reactionTime.toFixed(2);
        moveSquare();
    });

    moveSquare();
</script>

</body>
</html>
