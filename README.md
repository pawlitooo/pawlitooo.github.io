<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sklep z Rangami - Minecraft</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #2b2b2b;
            color: white;
            text-align: center;
            padding: 20px;
        }
        .container {
            max-width: 600px;
            margin: auto;
            background: #3b3b3b;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0px 0px 10px rgba(255, 255, 255, 0.1);
        }
        h1 {
            color: #ffd700;
        }
        .rank {
            padding: 15px;
            margin: 10px 0;
            background: #444;
            border-radius: 5px;
        }
        .rank h2 {
            margin: 0;
            color: #00ff00;
        }
        .price {
            font-size: 20px;
            font-weight: bold;
            color: #ffcc00;
        }
        .buy-button {
            background: #008000;
            color: white;
            padding: 10px 15px;
            text-decoration: none;
            border-radius: 5px;
            display: inline-block;
            margin-top: 10px;
        }
        .buy-button:hover {
            background: #00b300;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Sklep z Rangami - Minecraft</h1>
        <div class="rank">
            <h2>VIP</h2>
            <p class="price">5 PLN</p>
            <a href="#" class="buy-button">Kup Teraz</a>
        </div>
        <div class="rank">
            <h2>SVIP</h2>
            <p class="price">10 PLN</p>
            <a href="#" class="buy-button">Kup Teraz</a>
        </div>
        <div class="rank">
            <h2>ELITA</h2>
            <p class="price">15 PLN</p>
            <a href="#" class="buy-button">Kup Teraz</a>
        </div>
    </div>
</body>
</html>
<button id="buyNow">Kup teraz</button>
<script src="https://js.stripe.com/v3/"></script>
<script src="script.js"></script>
JavaScript (script.js)
javascript
Kopiuj
Edytuj
const stripe = Stripe("TWÓJ_KLUCZ_STRIPE");

document.getElementById("buyNow").addEventListener("click", async () => {
    const response = await fetch("/create-checkout-session", { method: "POST" });
    const session = await response.json();
    window.location.href = session.url;
});
Backend (Node.js – serwer obsługujący płatności)
javascript
Kopiuj
Edytuj
const express = require("express");
const stripe = require("stripe")("TWÓJ_TAJNY_KLUCZ_STRIPE");

const app = express();
app.use(express.json());

app.post("/create-checkout-session", async (req, res) => {
    const session = await stripe.checkout.sessions.create({
        payment_method_types: ["card"],
        line_items: [
            {
                price_data: {
                    currency: "pln",
                    product_data: { name: "Produkt XYZ" },
                    unit_amount: 5000, // 50.00 PLN
                },
                quantity: 1,
            },
        ],
        mode: "payment",
        success_url: "https://twoja-strona.pl/success",
        cancel_url: "https://twoja-strona.pl/cancel",
    });

    res.json({ url: session.url });
});

app.listen(3000, () => console.log("Serwer działa na porcie 3000"));
