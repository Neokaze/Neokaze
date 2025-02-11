- <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Will You Be My Valentine? 💖</title>
    <style>
        body {
            text-align: center;
            background: url('/mnt/data/WhatsApp%20Image%202025-02-11%20at%2023.23.38.jpeg') no-repeat center center fixed; background-size: cover; background-color: #ffccdc;
            font-family: 'Arial', sans-serif;
            color: #fff;
        }
        h1 {
            font-size: 3.5rem;
            margin-top: 20px;
        }
        .container {
            width: 80%;
            margin: auto;
            background: rgba(255, 192, 203, 0.9);
            padding: 20px;
            border-radius: 15px;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
            color: #6a0572;
        }
        .question {
            font-size: 2rem;
            margin: 30px 0;
        }
        .btn {
            background-color: #ff4d6d;
            color: white;
            border: none;
            padding: 15px 30px;
            font-size: 1.5rem;
            cursor: pointer;
            border-radius: 30px;
            margin: 10px;
            transition: transform 0.3s ease-in-out;
        }
        .btn:hover {
            background-color: #d63384;
            transform: scale(1.1);
        }
        .message {
            font-size: 1.8rem;
            font-weight: bold;
            margin-top: 20px;
            color: #ff0054;
        }
        .hidden {
            display: none;
        }
    </style>
</head>
<body>
    <audio autoplay loop>
        <source src="/mnt/data/Steam Powered Giraffe - Honeybee.mp3" type="audio/mpeg">
        Your browser does not support the audio element.
    </audio>

    <h1>Will You Be My Valentine, My Love? 💕</h1>
    <div class="container" id="quiz">
        <p class="question" id="question-text">Do you know how much I love you? 😘</p>
        <div id="options"></div>
        <p id="feedback" class="message hidden"></p>
    </div>

    <script>
        const questions = [
            {
                text: "Do you know how much I love you? 😘",
                options: ["More than anything in the world ❤️", "A little bit 😆", "More than pizza 🍕 ✅", "Not sure 🤔"],
                correct: 2
            },
            {
                text: "Which song reminds me of you the most? 🎶",
                options: ["Honeybee - Steam Powered Giraffe 🎶", "Three Ducks 🦆🦆🦆", "Video Games - Lana Del Rey 🎮", "3 Daqat (Our Little Secret Song) 🎵 ✅"],
                correct: 3
            },
            {
                text: "Where was our most special moment together? 💖",
                options: ["Your birthday celebration 🎂", "IMG Worlds adventure 🎢", "The time I gave you the ring 💍", "Watching Minions at the cinema 🍿 ✅"],
                correct: 3
            },
            {
                text: "Do you want to be my Valentine? 💘",
                options: ["YES, OF COURSE! 💕 ✅"],
                correct: 0
            }
        ];

        let currentQuestion = 0;
        const questionText = document.getElementById("question-text");
        const optionsContainer = document.getElementById("options");
        const feedback = document.getElementById("feedback");

        function loadQuestion(index) {
            if (index >= questions.length) {
                showLoveLetter();
                return;
            }

            currentQuestion = index;
            questionText.innerText = questions[index].text;
            optionsContainer.innerHTML = "";
            feedback.classList.add("hidden");

            questions[index].options.forEach((option, i) => {
                const btn = document.createElement("button");
                btn.className = "btn";
                btn.innerText = option;
                btn.onclick = () => checkAnswer(i === questions[index].correct, index + 1);
                optionsContainer.appendChild(btn);
            });
        }

        function checkAnswer(isCorrect, nextIndex) {
            feedback.innerText = isCorrect ? "Correct, sunshine! ☀️" : "Wrong, stinky winky! 😜 Try again!";
            feedback.style.color = isCorrect ? "#28a745" : "#ff0054";
            feedback.classList.remove("hidden");
            
            if (isCorrect) {
                setTimeout(() => loadQuestion(nextIndex), 1500);
            }
        }

        function showLoveLetter() {
            document.body.innerHTML = `
                <div class="container">
                    <h1>My Love, My Everything ❤️</h1>
                    <p>
                        I can’t even begin to tell you how incredibly lucky I feel to have you in my life. 
                        You are the most beautiful, kind, and special person I have ever met. Every moment with you feels like magic, 
                        and I wouldn’t trade it for the world. 
                    </p>
                    <p>
                        From the little things you do to the way you light up a room, you make my life so much better. 
                        I hope you know that you are loved, cherished, and absolutely perfect just as you are. 
                    </p>
                    <p>
                        I am so happy you said yes! You are my Valentine today, tomorrow, and forever. ❤️
                    </p>
                    <p><b>I love you endlessly.</b></p>
                </div>
            `;
        }

        loadQuestion(0);
    </script>
</body>
</html>
