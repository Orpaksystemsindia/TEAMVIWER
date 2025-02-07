<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Submit TeamViewer Details</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            padding: 20px;
            background-color: #f4f4f4;
        }
        h1 {
            color: #333;
        }
        input[type="text"], input[type="password"] {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        button {
            padding: 10px;
            background-color: #007BFF;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            width: 100%;
        }
        button:hover {
            background-color: #0056b3;
        }
        #resultMessage {
            margin-top: 20px;
            color: green;
        }
    </style>
</head>
<body>
    <h1>Submit TeamViewer Details</h1>
    <input type="text" id="roCodeInput" placeholder="Ro Code" required>
    <input type="text" id="roNameInput" placeholder="Ro Name" required>
    <input type="text" id="teamViewerIdInput" placeholder="TeamViewer Id" required>
    <input type="password" id="teamViewerPassInput" placeholder="TeamViewer Password" required>
    <input type="password" id="adminPassInput" placeholder="Admin Password" required>
    <button id="submitTeamViewerDetails">Submit</button>
    <div id="resultMessage"></div>

    <script>
        document.getElementById('submitTeamViewerDetails').onclick = function() {
            const roCode = document.getElementById('roCodeInput').value;
            const roName = document.getElementById('roNameInput').value;
            const teamViewerId = document.getElementById('teamViewerIdInput').value;
            const teamViewerPass = document.getElementById('teamViewerPassInput').value;
            const adminPass = document.getElementById('adminPassInput').value;

            // Make a POST request to the Google Apps Script URL
            fetch('https://script.google.com/macros/s/AKfycbyE_Pl2wKsNX5uyAGDmhG40aTfGuRH-9BwLJa6IgGjV6ZPuphaI7F-nkTrc0N8IOTxP0w/exec', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify({
                    roCode: roCode,
                    roName: roName,
                    teamViewerId: teamViewerId,
                    teamViewerPass: teamViewerPass,
                    adminPass: adminPass
                })
            })
            .then(response => response.json())
            .then(data => {
                document.getElementById('resultMessage').textContent = data.result;
            })
            .catch(error => {
                console.error('Error:', error);
                document.getElementById('resultMessage').textContent = 'An error occurred. Please try again.';
            });
        };
    </script>
</body>
</html>
