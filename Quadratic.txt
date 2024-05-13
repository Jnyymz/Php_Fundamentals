<!-- index.php -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Quadratic Discriminant Calculator</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #8B322C; 
        }
        .container {
            max-width: 400px;
            margin: 50px auto;
            padding: 20px;
            border-radius: 5px;
            background-color: #DD5746;
            
        }

        input[type="text"], button {
            display: block;
            margin-bottom: 10px;
            color: black;
        }

        button {
            padding: 10px 20px;
            background-color: #007bff;
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        button:hover {
            background-color: #0056b3;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Quadratic Discriminant Calculator</h1>
        <?php
        // Check if form is submitted
        if ($_SERVER["REQUEST_METHOD"] == "POST") {
            // Retrieve coefficients from the form
            $a = $_POST['a'];
            $b = $_POST['b'];
            $c = $_POST['c'];

            // Calculate discriminant
            $discriminant = $b * $b - 4 * $a * $c;

            echo "<h2>Result</h2>";
            echo "<p>The discriminant is: $discriminant</p>";
        } else {
            // Display form
            echo '<form action="" method="post">';
            echo '<label for="a">Coefficient a:</label>';
            echo '<input type="text" id="a" name="a" required>';
            echo '<label for="b">Coefficient b:</label>';
            echo '<input type="text" id="b" name="b" required>';
            echo '<label for="c">Coefficient c:</label>';
            echo '<input type="text" id="c" name="c" required>';
            echo '<button type="submit">Calculate Discriminant</button>';
            echo '</form>';
        }
        ?>
    </div>
</body>
</html>
