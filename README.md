<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Age Calculator</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(120deg, #8e44ad, #3498db);
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            color: white;
        }
        .calculator {
            background: #fff;
            color: #333;
            padding: 20px 30px;
            border-radius: 15px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
            text-align: center;
            max-width: 400px;
            width: 100%;
        }
        h1 {
            font-size: 1.8em;
            margin-bottom: 20px;
        }
        input {
            padding: 10px;
            font-size: 1em;
            border: 1px solid #ccc;
            border-radius: 5px;
            width: calc(100% - 22px);
            margin-bottom: 20px;
            text-align: center;
        }
        button {
            padding: 10px 20px;
            font-size: 1em;
            border: none;
            border-radius: 5px;
            background-color: #3498db;
            color: white;
            cursor: pointer;
            margin-top: 10px;
            transition: background-color 0.3s;
        }
        button:hover {
            background-color: #2980b9;
        }
        .result {
            margin-top: 20px;
            font-size: 1.2em;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <h1>Age Calculator</h1>
        <input type="date" id="birthdate" />
        <button onclick="calculateAge()">Calculate Age</button>
        <div class="result" id="result"></div>
    </div>

    <script>
        function calculateAge() {
            const birthdate = document.getElementById("birthdate").value;
            if (!birthdate) {
                document.getElementById("result").innerText = "Please select your birthdate.";
                return;
            }
            const birthDate = new Date(birthdate);
            const today = new Date();
            let age = today.getFullYear() - birthDate.getFullYear();
            const monthDifference = today.getMonth() - birthDate.getMonth();

            if (
                monthDifference < 0 || 
                (monthDifference === 0 && today.getDate() < birthDate.getDate())
            ) {
                age--;
            }
            
            document.getElementById("result").innerText = `Your age is: ${age} years old.`;
        }
    </script>
</body>
</html>
