<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Projet Secret - Révision 1.2</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            background-color: #ffe6e6;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            overflow: hidden; /* Empêche de scroller pour rattraper le bouton */
        }
        h1 { color: #d63384; text-align: center; padding: 0 20px; }
        .container { position: relative; width: 100%; height: 300px; display: flex; justify-content: center; align-items: center; }
        button {
            padding: 15px 30px;
            font-size: 18px;
            font-weight: bold;
            cursor: pointer;
            border: none;
            border-radius: 50px;
            transition: 0.1s;
            position: absolute;
        }
        #yesBtn { background-color: #ff4d6d; color: white; transform: translateX(-70px); }
        #noBtn { background-color: #888; color: white; transform: translateX(70px); }
    </style>
</head>
<body>

    <h1>Veux-tu être ma Valentine ? ❤️</h1>
    
    <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOHpueGZ3bmZ3bmZ3JmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZAmS8dy8dy8dy/l41lTf6fS8sH2Z8pW/giphy.gif" width="180" style="border-radius: 15px; margin-bottom: 20px;">

    <div class="container">
        <button id="yesBtn" onclick="celebrate()">Oui</button>
        <button id="noBtn" onmouseover="moveButton()" ontouchstart="moveButton()">Non</button>
    </div>

    <script>
        function moveButton() {
            const noBtn = document.getElementById('noBtn');
            // Calcule une zone sécurisée pour que le bouton reste visible mais inaccessible
            const x = Math.random() * (window.innerWidth - noBtn.offsetWidth);
            const y = Math.random() * (window.innerHeight - noBtn.offsetHeight);
            
            noBtn.style.left = x + 'px';
            noBtn.style.top = y + 'px';
            noBtn.style.transform = 'none'; // Enlève le centrage initial
        }

        function celebrate() {
            alert("Je savais que tu dirais oui ! 😍");
            // Optionnel : change le texte de la page après le clic
            document.querySelector('h1').innerHTML = "Rendez-vous bientôt ! 🌹";
        }
    </script>
</body>
</html>

