<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>Yay!</title>
	<style>
		body {
			display: flex;
			justify-content: center;
			align-items: center;
			height: 100vh;
			margin: 0;
			background-color: #fbeee0;
			font-family: 'Arial', sans-serif;
		}

		.container {
			text-align: center;
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
		}

		.yes-button {
			background-color: #4caf50;
			color: white;
			border: none;
			padding: 10px 20px;
			font-size: 18px;
			font-weight: bold;
			border-radius: 8px;
			cursor: pointer;
			transition: all 0.2s ease-in-out;
		}

		.no-button {
			background-color: #f44336;
			color: white;
			border: none;
			padding: 10px 20px;
			font-size: 18px;
			font-weight: bold;
			border-radius: 8px;
			cursor: pointer;
		}
	</style>
</head>
<body>
	<div class="container">
		<h1 class="header_text">Knew you would say yes! Happy Birthday! ❤️</h1>
		<div class="gif_container">
			<img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExMHJuYzBsb3h3bzcxMDVpZzBncWc1MmlmbmFqdHF4dTFwdXR5ZmhhYyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/MDJ9IbxxvDUQM/giphy.gif" alt="Celebration GIF">
		</div>
		<div class="buttons">
			<button class="yes-button" onclick="handleYesClick()">Yes</button>
			<button class="no-button" onclick="handleNoClick()">No</button>
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

		function handleNoClick() {
			const noButton = document.querySelector('.no-button');
			const yesButton = document.querySelector('.yes-button');

			noButton.textContent = messages[messageIndex];
			messageIndex = (messageIndex + 1) % messages.length;

			const currentSize = parseFloat(window.getComputedStyle(yesButton).fontSize);
			yesButton.style.fontSize = `${currentSize * 1.5}px`;
			yesButton.style.padding = `${10 * (currentSize / 18 * 1.2)}px ${20 * (currentSize / 18 * 1.2)}px`;
		}

		function handleYesClick() {
			window.location.href = "yes_page.html";
		}
	</script>
</body>
</html>