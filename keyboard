<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gardiner Hieroglyph Keyboard</title>
    <style>
        /* Loading the uploaded EOT font */
        @font-face {
            font-family: 'GardinerFont';
            src: url('eot(1).ttf') format('truetype');
        }

        body {
            font-family: sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            background-color: #f4f4f9;
            margin: 0;
        }

        .container {
            background: white;
            padding: 2rem;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            text-align: center;
            width: 90%;
            max-width: 600px;
        }

        #display-field {
            font-family: 'GardinerFont', serif;
            font-size: 2rem;
            width: 100%;
            padding: 10px;
            margin-bottom: 20px;
            border: 2px solid #ddd;
            border-radius: 4px;
            box-sizing: border-box;
        }

        .keyboard {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }

        .key {
            font-family: 'GardinerFont';
            font-size: 1.8rem;
            padding: 15px;
            cursor: pointer;
            background-color: #eee;
            border: 1px solid #ccc;
            border-radius: 4px;
            transition: background 0.2s;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .key:hover {
            background-color: #ddd;
        }

        .key:active {
            background-color: #bbb;
        }

        .label {
            font-family: sans-serif;
            font-size: 0.6rem;
            color: #666;
            margin-top: 5px;
        }
    </style>
</head>
<body>

<div class="container">
    <h2>Hieroglyphic Input</h2>
    <input type="text" id="display-field" placeholder="Symbols appear here..." autofocus>
    
    <div class="keyboard" id="keyboard">
        </div>
</div>

<script>
    // Mapping Gardiner Numbers to Unicode hex points
    const glyphs = [
        { id: "A28", char: "\u{1301B}" }, // 𓀛
        { id: "V13", char: "\u{1339D}" }, // 𓎝
        { id: "D36", char: "\u{130AD}" }, // 𓂭
        { id: "N32", char: "\u{1320F}" }, // 𓈏
        { id: "S29", char: "\u{132F7}" }, // 𓋷
        { id: "N17", char: "\u{131FE}" }, // 𓈞
        { id: "M22", char: "\u{131B9}" }, // 𓆹
        { id: "V24", char: "\u{133A9}" }, // 𓎩
        { id: "V20", char: "\u{133A4}" }, // 𓎤
        { id: "S21", char: "\u{132EF}" }, // 𓋯
        { id: "Z4",  char: "\u{133E4}" }, // 𓏤
        { id: "D21", char: "\u{1308B}" }  // 𓂋
    ];

    const inputField = document.getElementById('display-field');
    const keyboard = document.getElementById('keyboard');

    glyphs.forEach(glyph => {
        const button = document.createElement('button');
        button.className = 'key';
        button.innerHTML = `${glyph.char}<span class="label">${glyph.id}</span>`;
        
        button.addEventListener('click', () => {
            const start = inputField.selectionStart;
            const end = inputField.selectionEnd;
            const text = inputField.value;
            
            // Insert character at cursor position
            inputField.value = text.slice(0, start) + glyph.char + text.slice(end);
            
            // Reposition cursor
            inputField.selectionStart = inputField.selectionEnd = start + glyph.char.length;
            inputField.focus();
        });

        keyboard.appendChild(button);
    });
</script>

</body>
</html>
