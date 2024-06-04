# syssa
HTML (index.html):

html
Copiar código
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Texto com Botões</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <p>Você gostaria de receber nossas atualizações por e-mail?</p>
        <div class="buttons">
            <button id="simButton">Sim</button>
            <button id="naoButton">Não</button>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>
CSS (styles.css):

css
Copiar código
/* Estilos gerais */
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

.container {
    text-align: center;
}

.buttons {
    margin-top: 20px;
}

button {
    padding: 10px 20px;
    margin: 0 10px;
    font-size: 16px;
    cursor: pointer;
}

button:focus {
    outline: none;
}

button#simButton {
    background-color: green;
    color: white;
    border: none;
}

button#naoButton {
    background-color: red;
    color: white;
    border: none;
}
JavaScript (script.js):

javascript
Copiar código
document.getElementById('simButton').addEventListener('click', function() {
    window.location.href = 'https://www.youtube.com/watch?v=-dy1uuJa-vw';
});

document.getElementById('naoButton').addEventListener('mousemove', function(event) {
    var button = document.getElementById('naoButton');
    var buttonRect = button.getBoundingClientRect();
    var mouseX = event.clientX;
    var mouseY = event.clientY;
    
    var distance = Math.sqrt(Math.pow(mouseX - buttonRect.left, 2) + Math.pow(mouseY - buttonRect.top, 2));
    
    if (distance <= 40) {
        var randomX = Math.random() * (window.innerWidth - buttonRect.width);
        var randomY = Math.random() * (window.innerHeight - buttonRect.height);
        
        button.style.position = 'absolute';
        button.style.left = randomX + 'px';
        button.style.top = randomY + 'px';
    }
});
