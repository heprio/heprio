<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Relaxation</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            background-color: #f0f0f0;
            font-family: Arial, sans-serif;
        }
        #messageContainer {
            position: absolute;
            top: 10px;
            left: 10px;
            width: 300px;
            max-height: 150px;
            overflow-y: auto;
            border: 1px solid #ccc;
            background-color: white;
            padding: 10px;
        }
        .message {
            margin: 5px 0;
            padding: 5px;
            background-color: #e0e0e0;
            border-radius: 4px;
        }
        input[type="text"] {
            margin-top: 10px;
            padding: 10px;
            font-size: 16px;
            width: 300px;
        }
        button {
            margin-top: 10px;
            padding: 10px 20px;
            font-size: 16px;
        }
    </style>
</head>
<body>
    <h1>Exprimez-vous !</h1>
    
    <input type="text" id="nameInput" placeholder="Entrez votre prénom..." />
    <input type="text" id="relaxInput" placeholder="Écris une phrase..." />
    <button id="addMessageButton">Ajouter</button>
    
    <div id="messageContainer"></div> <!-- Conteneur pour les messages -->

    <script>
        const nameInput = document.getElementById('nameInput');
        const relaxInput = document.getElementById('relaxInput');
        const addMessageButton = document.getElementById('addMessageButton');
        const messageContainer = document.getElementById('messageContainer');

        addMessageButton.addEventListener('click', addMessage);

        function addMessage() {
            const nameText = nameInput.value; // Récupérer le texte du champ de prénom
            const messageText = relaxInput.value; // Récupérer le texte du champ de saisie
            if (messageText) {
                const messageDiv = document.createElement('div'); // Créer un nouvel élément div
                messageDiv.className = 'message'; // Ajouter la classe CSS pour le style
                messageDiv.textContent = `${nameText ? nameText + ': ' : ''}${messageText}`; // Ajouter le prénom et le message
                messageContainer.appendChild(messageDiv); // Ajouter le message au conteneur
                relaxInput.value = ''; // Réinitialiser le champ de saisie
            }
        }
    </script>
</body>
</html>
