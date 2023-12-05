# online-shopping-website
html website
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Online Shopping</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }

        header {
            background-color: #333;
            color: #fff;
            padding: 10px;
            text-align: center;
        }

        main {
            padding: 20px;
        }

        .product {
            border: 1px solid #ddd;
            border-radius: 5px;
            padding: 10px;
            margin: 10px;
            background-color: #fff;
            box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
            display: inline-block;
            width: 200px;
            text-align: center;
        }

        button {
            background-color: #333;
            color: #fff;
            padding: 5px 10px;
            border: none;
            border-radius: 3px;
            cursor: pointer;
        }
    </style>
</head>
<body>

<header>
    <h1>Online Shopping</h1>
</header>

<main>
    <div class="product" id="product1">
        <h2>Product 1</h2>
        <p>Price: $20</p>
        <button onclick="addToCart('Product 1', 20)">Add to Cart</button>
    </div>

    <div class="product" id="product2">
        <h2>Product 2</h2>
        <p>Price: $30</p>
        <button onclick="addToCart('Product 2', 30)">Add to Cart</button>
    </div>

    <div id="cart">
        <h2>Shopping Cart</h2>
        <ul id="cart-items"></ul>
        <p>Total: $<span id="total">0</span></p>
    </div>
</main>

<script>
    let cartItems = [];
    let total = 0;

    function addToCart(productName, price) {
        cartItems.push({ name: productName, price: price });
        total += price;

        // Update the cart display
        updateCartDisplay();
    }

    function updateCartDisplay() {
        const cartItemsElement = document.getElementById("cart-items");
        const totalElement = document.getElementById("total");

        // Clear previous items
        cartItemsElement.innerHTML = "";

        // Add current items
        cartItems.forEach(item => {
            const li = document.createElement("li");
            li.textContent = `${item.name} - $${item.price}`;
            cartItemsElement.appendChild(li);
        });

        // Update total
        totalElement.textContent = total;
    }
</script>

</body>
</html>

