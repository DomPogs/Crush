<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Page</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f0f0f0;
        }
        .container {
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        .box {
            border: 2px solid pink;
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            background-color: white;
            width: 300px;
            position: relative;
        }
        .credit {
            font-size: 12px;
            color: gray;
            margin-top: 10px;
        }
        button {
            margin: 10px;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        .yes-button {
            border: 2px solid blue;
            background-color: white;
            color: blue;
        }
        .no-button {
            border: 2px solid red;
            background-color: white;
            color: red;
        }
        .what-button {
            border: 2px solid pink;
            background-color: white;
            color: pink;
        }
        .image {
            width: 100%;
            max-width: 300px;
            margin-bottom: 20px;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="box" id="content">
            <!-- Dynamic content will be inserted here -->
        </div>
        <div class="credit">
            Created by Dominique E.<br>
        </div>
    </div>

    <script>
        function showContent(page) {
            const content = document.getElementById('content');
            content.innerHTML = '';

            if (page === 'start') {
                content.innerHTML = `
                    <p>Hi crush ok kalang?</p>
                    <button class="yes-button" onclick="showContent('yesPage')">Yes</button>
                    <button class="no-button" onclick="showContent('noPage')">No</button>
                `;
            } else if (page === 'yesPage') {
                content.innerHTML = `
                    <p>Ohh great</p>
                    <p>May gusto kasi akong sabihin</p>
                    <button class="what-button" onclick="showContent('whatPage')">What</button>
                `;
            } else if (page === 'whatPage') {
                content.innerHTML = `
                    <p>Crush kasi kita</p>
                    <button class="what-button" onclick="showContent('finalQuestion')">OK</button>
                `;
            } else if (page === 'finalQuestion') {
                content.innerHTML = `
                    <p>May gusto din kasi akong tanungin</p>
                    <button class="what-button" onclick="showContent('askCrush')">What</button>
                `;
            } else if (page === 'askCrush') {
                content.innerHTML = `
                    <p>Crush mo rin ba ako?</p>
                    <button class="yes-button" onclick="showContent('loveMusic')">Yes</button>
                    <button class="no-button" onclick="showContent('sadMusic')">No</button>
                `;
            } else if (page === 'loveMusic') {
                content.innerHTML = `
                    <img src="cute.jpg" alt="Love Image" class="image">
                    <p>Akoy kinikilig yiee</p>
                    <audio autoplay>
                        <source src="Kilig1.mp3" type="audio/mpeg">
                        Your browser does not support the audio element.
                    </audio>
                `;
            } else if (page === 'sadMusic') {
                content.innerHTML = `
                    <img src="kermit.jpg" alt="Sad Image" class="image">
                    <p>Ay :(</p>
                    <audio autoplay>
                        <source src="Same Ground.mp3" type="audio/mpeg">
                        Your browser does not support the audio element.
                    </audio>
                `;
            } else if (page === 'noPage') {
                content.innerHTML = `
                    <p>May gusto kasi akong sabihin sayo</p>
                    <button class="what-button" onclick="showContent('noWhatPage')">What</button>
                `;
            } else if (page === 'noWhatPage') {
                content.innerHTML = `
                    <p>Crush kasi kita</p>
                    <button class="what-button" onclick="showContent('noFinalQuestion')">OK</button>
                `;
            } else if (page === 'noFinalQuestion') {
                content.innerHTML = `
                    <p>May gusto din kasi akong tanungin</p>
                    <button class="what-button" onclick="showContent('noAskCrush')">What</button>
                `;
            } else if (page === 'noAskCrush') {
                content.innerHTML = `
                    <p>Crush mo rin ba ako?</p>
                    <button class="yes-button" onclick="showContent('loveMusic')">Yes</button>
                    <button class="no-button" onclick="showContent('sadMusic')">No</button>
                `;
            }
        }

        // Initial content
        showContent('start');
    </script>
</body>
</html>
