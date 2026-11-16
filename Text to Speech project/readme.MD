<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>

    <style>
        * {
            box-sizing: border-box;
        }

        body {
            min-height: 100vh;
            margin: 0;
            display: grid;
            place-items: center;
            font-family: Arial, sans-serif;
            background: #f3f4f6;
        }

        #container1 {
            width: min(90%, 420px);
            padding: 28px;
            background: white;
            border-radius: 12px;
            box-shadow: 0 4px 16px #0000001a;
        }

        #text {
            margin: 0 0 20px;
            text-align: center;
            font-size: 24px;
        }

        #texttospeak {
            width: 100%;
            min-height: 120px;
            padding: 12px;
            border: 1px solid #d1d5db;
            border-radius: 6px;
            font: inherit;
            resize: vertical;
        }

        #speak {
            width: 100%;
            margin-top: 16px;
            padding: 12px;
            border: 0;
            border-radius: 6px;
            background: #1677e8;
            color: white;
            font: inherit;
            cursor: pointer;
        }

        #speak:hover {
            background: #0864cc;
        }
    </style>



</head>

<body>
    <div id="container1">
        <h1 id="text">Text to Speech</h1>
        <textarea id="texttospeak" placeholder="Enter some text"></textarea>
        <button onclick="speakText()" id="speak">Speak</button>
    </div>

    <script>
        function speakText() {
            const text = document.getElementById("texttospeak").value;
            if (text.trim() !== "") {
                const speech = new SpeechSynthesisUtterance(text);
                speech.rate = 1;
                speech.volume = 1;
                speech.pitch = 1;
                window.speechSynthesis.speak(speech);
            } else {
                alert("Please enter some text");
            }
        }



    </script>
</body>

</html>
