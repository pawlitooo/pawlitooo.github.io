<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MiconCartoon Minecraft Server</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f2f2f2;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            text-align: center;
        }

        .container {
            width: 80%;
            max-width: 800px;
            background-color: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }

        h1 {
            color: #333;
        }

        .subscription-card {
            display: flex;
            justify-content: space-around;
            margin-top: 30px;
            flex-wrap: wrap;
        }

        .card {
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            width: 250px;
            margin: 10px;
            padding: 20px;
            text-align: center;
        }

        .card h2 {
            font-size: 24px;
            margin-bottom: 10px;
        }

        .vip {
            color: yellow;
            font-weight: bold;
        }

        .svip {
            color: gold;
            font-weight: bold;
        }

        .elite {
            background: linear-gradient(to right, red, black);
            color: white;
            font-weight: bold;
        }

        .price {
            font-size: 16px;
            margin-top: 10px;
            font-weight: normal;
        }

        .btn {
            background-color: green;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin-top: 15px;
            font-size: 16px;
            text-decoration: none;
        }

        .btn:hover {
            background-color: #45a049;
        }

        .btn:active {
            background-color: #367c39;
        }

        .card-footer {
            font-size: 14px;
            color: #777;
        }

    </style>
</head>
<body>
    <div class="container">
        <h1>Witaj na serwerze MiconCartoon!</h1>
        <p>Wybierz swoją subskrypcję VIP i wspieraj nasz serwer!</p>

        <div class="subscription-card">
            <!-- VIP Card -->
            <div class="card">
                <h2 class="vip">VIP</h2>
                <p class="price">5 PLN</p>
                <p><a href="https://www.paypal.com/donate?amount=5" target="_blank" class="btn">Kup Teraz</a></p>
                <p class="card-footer">Wspieraj nasz serwer!</p>
            </div>

            <!-- SVIP Card -->
            <div class="card">
                <h2 class="svip">SVIP</h2>
                <p class="price">10 PLN</p>
                <p><a href="https://www.paypal.com/donate?amount=10" target="_blank" class="btn">Kup Teraz</a></p>
                <p class="card-footer">Zyskaj wyjątkowe przywileje!</p>
            </div>

            <!-- Elite Card -->
            <div class="card">
                <h2 class="elite">ELITE</h2>
                <p class="price">20 PLN</p>
                <p><a href="https://www.paypal.com/donate?amount=20" target="_blank" class="btn">Kup Teraz</a></p>
                <p class="card-footer">Najwyższy poziom VIP!</p>
            </div>
        </div>
    </div>
</body>
</html>
