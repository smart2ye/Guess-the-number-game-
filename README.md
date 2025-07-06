<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>لعبة تخمين الرقم</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f8ff;
            text-align: center;
            padding: 20px;
        }
        input {
            padding: 10px;
            font-size: 16px;
            margin-top: 10px;
            width: 100px;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            margin-top: 10px;
            background-color: #4CAF50;
            color: white;
            border: none;
            cursor: pointer;
        }
        button:hover {
            background-color: #45a049;
        }
        p {
            font-size: 18px;
            color: #333;
        }
        #message {
            font-size: 20px;
            font-weight: bold;
            color: #d9534f;
        }
    </style>
</head>
<body>
    <h1>لعبة تخمين الرقم</h1>
    <p>تخمين الرقم بين 1 و 10!</p>
    <input type="number" id="guess" min="1" max="10" placeholder="أدخل رقمًا" />
    <button onclick="checkGuess()">تخمين</button>
    <p id="message"></p>

    <script>
        const randomNumber = Math.floor(Math.random() * 10) + 1;

        function checkGuess() {
            const guess = document.getElementById('guess').value;
            const message = document.getElementById('message');
            if (guess == randomNumber) {
                message.textContent = "تهانينا! لقد خمنت الرقم بشكل صحيح.";
                message.style.color = "#5bc0de";  // تغيير اللون عند الفوز
            } else if (guess < 1 || guess > 10) {
                message.textContent = "الرجاء إدخال رقم بين 1 و 10.";
                message.style.color = "#d9534f";  // لون التحذير
            } else {
                message.textContent = "خطأ! حاول مرة أخرى.";
                message.style.color = "#d9534f";  // لون الخطأ
            }
        }
    </script>
</body>
</html>
