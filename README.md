<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flashflood Restaurant</title>
    <link rel="icon" type="image/png" href="favicon.png">
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f8f8f8;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 20px;
        }
        .menu-container {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            justify-content: center;
        }
        .menu-item {
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            padding: 15px;
            text-align: center;
            width: 200px;
        }
        .menu-item img {
            width: 100%;
            border-radius: 10px;
        }
        .menu-item h3 {
            margin: 10px 0;
        }
        .menu-item button {
            background-color: black;
            color: white;
            border: none;
            padding: 10px;
            border-radius: 5px;
            cursor: pointer;
            transition: 0.3s;
        }
        .menu-item button:hover {
            background-color: #ff6600;
        }
        .logo {
            display: flex;
            justify-content: center;
            margin: 10px;
            width: 30px;
            height: 30px;
            border-radius: 10px;
        }
    </style>
</head>
<body>
    <img src="favicon.png" alt="icon" class="logo">
    <div class="menu-container">
        <div class="menu-item">
            <img src="dish1.jpg" alt="Dish 1">
            <h3>Delicious Meal</h3>
            <h2>230 ৳</h2>
            <button onclick="order('Delicious Meal', 230)">Order Now</button>
        </div>
        <div class="menu-item">
            <img src="dish2.jpg" alt="Dish 2">
            <h3>Spicy Special</h3>
            <h2>250 ৳</h2>
            <button onclick="order('Spicy Special', 250)">Order Now</button>
        </div>
        <div class="menu-item">
            <img src="dish3.jpg" alt="Dish 3">
            <h3>Chef’s Special</h3>
            <h2>270 ৳</h2>
            <button onclick="order('Chef’s Special', 270)">Order Now</button>
        </div>
    </div>
    <script>
        function order(item, price) {
            alert(`Order placed successfully!\nItem: ${item}\nPrice: ${price} ৳`);
            generateBill(item, price);
        }
        
        function generateBill(item, price) {
            let billWindow = window.open('', '', 'width=400,height=400');
            billWindow.document.write(`<h2>Flashflood Restaurant</h2>`);
            billWindow.document.write(`<p>Item: ${item}</p>`);
            billWindow.document.write(`<p>Price: ${price} ৳</p>`);
            billWindow.document.write(`<p>Tax: 5% (${(price * 0.05).toFixed(2)} ৳)</p>`);
            billWindow.document.write(`<p>Total: ${(price * 1.05).toFixed(2)} ৳</p>`);
            billWindow.document.write('<button onclick="window.print()">Print Bill</button>');
        }
    </script>
</body>
</html>
