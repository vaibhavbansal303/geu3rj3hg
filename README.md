<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fun Facts Generator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f9f9f9;
            margin: 0;
            padding: 0;
            background-image: url('https://images.pexels.com/photos/6983524/pexels-photo-6983524.jpeg?auto=compress&cs=tinysrgb&w=600&lazy=load');
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
        }

        .container {
            padding: 20px;
            max-width: 600px;
            margin: auto;
            background-color: rgba(255, 255, 255, 0.8);
            border-radius: 10px;
        }

        button {
            background-color: #007BFF;
            color: #fff;
            border: none;
            padding: 10px 20px;
            margin: 10px;
            cursor: pointer;
            border-radius: 5px;
            font-size: 16px;
        }

        button:hover {
            background-color: #0056b3;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Personal Fun Facts Generator</h1>
        <p id="display-fact">Click the button to generate a fun fact!</p>
        <button id="generate-btn">Generate Fun Fact</button>
        <input type="text" id="new-fact" placeholder="Add your fun fact">
        <button id="add-btn">Add Fact</button>
        <button id="fact-checker-btn">Fact Checker</button>
    </div>
    <script>
        const facts = ["The Eiffel Tower can be 15 cm taller during summer.", "Octopuses have three hearts!"];

        document.getElementById('generate-btn').addEventListener('click', () => {
            if (facts.length === 0) {
                alert("No facts available. Add some!");
                return;
            }
            const randomIndex = Math.floor(Math.random() * facts.length);
            document.getElementById('display-fact').textContent = facts[randomIndex];
        });

        document.getElementById('add-btn').addEventListener('click', () => {
            const newFact = document.getElementById('new-fact').value.trim();
            if (newFact && !facts.includes(newFact)) {
                facts.push(newFact);
                alert("Fact added!");
                document.getElementById('new-fact').value = "";
            } else {
                alert("Invalid or duplicate fact!");
            }
        });

        document.getElementById('fact-checker-btn').addEventListener('click', () => {
            const currentFact = document.getElementById('display-fact').textContent;
            if (currentFact && currentFact !== "Click the button to generate a fun fact!") {
                alert(`Checking the fact: "${currentFact}"`);
                // Implement your fact-checking logic here
            } else {
                alert("No fact to check. Generate a fact first!");
            }
        });
    </script>
</body>
</html>
