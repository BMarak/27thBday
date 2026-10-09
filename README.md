<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday!</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #fbeee0;
            font-family: 'Arial', sans-serif;
            overflow: hidden;
        }

        .container {
            text-align: center;
            padding: 20px;
        }

        .header_text {
            font-size: 2.5rem;
            color: #d32f2f;
            margin-bottom: 20px;
        }

        .gif_container img {
            max-width: 250px;
            height: auto;
            border-radius: 15px;
            margin-bottom: 20px;
        }

        .buttons {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 20px;
            flex-wrap: wrap;
            margin-top: 20px;
        }

        .yes-button {
            background-color: #4caf50;
            color: white;
            border: none;
            padding: 12px 24px;
            font-size: 18px;
            font-weight: bold;
            border-radius: 8px;
            cursor: pointer;
            transition: transform 0.2s ease-in-out;
            transform-origin: center;
        }

        .no-button {
            background-color: #f44336;
            color: white;
            border: none;
            padding: 12px 24px;
            font-size: 18px;
            font-weight: bold;
            border-radius: 8px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1 class="header_text" id="question">Will you celebrate your birthday with me?</h1>
        <div class="gif_container">
            <img id="main-gif" src="https://media1.giphy.com/media/v1.Y2lkPTc5MGI3NjExYjN4MjZzbGRyc3F2dzIydWV6dDkzcG1ndXpjd2RkOWtyeWZreTl1ciZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/cLS1cfxvGOPVpf9g3y/giphy.gif" alt="Cute GIF">
        </div>
        <div class="buttons" id="button-group">
            <button class="yes-button" id="yesBtn" onclick="handleYesClick()">Yes</button>
            <button class="no-button" id="noBtn" onclick="handleNoClick()">No</button>
        </div>
    </div>

    <script>
        const messages = [
            "Are you sure?",
            "Really sure??",
            "Are you positive?",
            "Pookie please...",
            "Just think about it!",
            "If you say no, I will be really sad...",
            "I will be very sad...",
            "I will be very very very sad..."
        ];

        let messageIndex = 0;
        let yesScale = 1;

        function handleNoClick() {
            const noButton = document.getElementById('noBtn');
            const yesButton = document.getElementById('yesBtn');

            // Change No button text
            noButton.textContent = messages[messageIndex];
            messageIndex = (messageIndex + 1) % messages.length;

            // Increase Yes button scale cleanly by 40% each click
            yesScale += 0.4;
            yesButton.style.transform = `scale(${yesScale})`;
        }

        function handleYesClick() {
            document.getElementById('question').textContent = "Knew you would say yes! Happy Birthday! ❤️";
            document.getElementById('main-gif').src = "https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExMHJuYzBsb3h3bzcxMDVpZzBncWc1MmlmbmFqdHF4dTFwdXR5ZmhhYyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/MDJ9IbxxvDUQM/giphy.gif";
            document.getElementById('button-group').style.display = "none";
        }
    </script>
</body>
</html>
