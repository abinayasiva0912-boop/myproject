# myproject
<!DOCTYPE html>
<html>
<head>
    <title>FoodExpress - Online Food Order</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background: linear-gradient(135deg,#ff9a9e,#fad0c4);
        }

        header {
            background: #222;
            color: white;
            text-align: center;
            padding: 20px;
            font-size: 28px;
        }

        .container {
            width: 90%;
            margin: auto;
            margin-top: 20px;
        }

        .menu {
            display: grid;
            grid-template-columns: repeat(auto-fit,minmax(220px,1fr));
            gap: 20px;
        }

        .card {
            background: white;
            padding: 15px;
            border-radius: 12px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }

        .card img {
            width: 100%;
            height: 150px;
            object-fit: cover;
            border-radius: 10px;
        }

        button {
            background: #ff4b2b;
            border: none;
            color: white;
            padding: 10px;
            margin-top: 10px;
            border-radius: 8px;
            cursor: pointer;
        }

        button:hover {
            background: #ff416c;
        }

        .cart {
            background: white;
            margin-top: 30px;
            padding: 20px;
            border-radius: 12px;
        }

        input {
            width: 100%;
            padding: 10px;
            margin: 8px 0;
            border-radius: 6px;
            border: 1px solid #ccc;
        }

        .total {
            font-weight: bold;
            font-size: 18px;
        }
    </style>
</head>
<body>

<header>🍔 FoodExpress - Order Now</header>

<div class="container">

    <div class="menu">

        <div class="card">
            <img src="https://images.unsplash.com/photo-1600891964599-f61ba0e24092" alt="">
            <h3>Pizza</h3>
            <p>$10</p>
            <button onclick="addToCart('Pizza',10)">Add to Cart</button>
        </div>

        <div class="card">
            <img src="https://images.unsplash.com/photo-1550547660-d9450f859349" alt="">
            <h3>Burger</h3>
            <p>$8</p>
            <button onclick="addToCart('Burger',8)">Add to Cart</button>
        </div>

        <div class="card">
            <img src="https://images.unsplash.com/photo-1586190848861-99aa4a171e90" alt="">
            <h3>Pasta</h3>
            <p>$12</p>
            <button onclick="addToCart('Pasta',12)">Add to Cart</button>
        </div>

    </div>

    <div class="cart">
        <h2>Your Cart</h2>
        <ul id="cartList"></ul>
        <p class="total">Total: $<span id="total">0</span></p>

        <h3>Customer Details</h3>
        <input type="text" id="name" placeholder="Enter Name">
        <input type="text" id="address" placeholder="Enter Address">
        <button onclick="placeOrder()">Place Order</button>
    </div>

</div>

<script>
let total = 0;

function addToCart(item, price) {
    let li = document.createElement("li");
    li.textContent = item + " - $" + price;
    document.getElementById("cartList").appendChild(li);

    total += price;
    document.getElementById("total").innerText = total;
}

function placeOrder() {
    let name = document.getElementById("name").value;
    let address = document.getElementById("address").value;

    if(name === "" || address === "") {
        alert("Please fill all details");
        return;
    }

    if(total === 0) {
        alert("Cart is empty");
        return;
    }

    alert("Thank you " + name + "! Your order total is $" + total);
}
</script>

</body>
</html>
