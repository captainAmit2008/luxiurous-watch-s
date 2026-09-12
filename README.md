<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>TimeZone Watches</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
            background: #f4f4f4;
            color: #222;
        }

        /* NAVBAR */
        nav {
            background: #111;
            color: white;
            padding: 18px 7%;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        nav h1 {
            font-size: 27px;
        }

        nav a {
            color: white;
            text-decoration: none;
            margin-left: 20px;
        }

        /* HERO */
        .hero {
            background: linear-gradient(135deg, #111, #444);
            color: white;
            text-align: center;
            padding: 90px 20px;
        }

        .hero h2 {
            font-size: 48px;
            margin-bottom: 15px;
        }

        .hero p {
            font-size: 19px;
            margin-bottom: 25px;
        }

        .btn {
            background: #d4af37;
            color: #111;
            border: none;
            padding: 13px 25px;
            border-radius: 6px;
            cursor: pointer;
            font-weight: bold;
        }

        .btn:hover {
            background: #fff;
        }

        /* PRODUCTS */
        .products {
            padding: 50px 7%;
            text-align: center;
        }

        .products h2 {
            font-size: 35px;
            margin-bottom: 30px;
        }

        .product-container {
            display: flex;
            justify-content: center;
            gap: 25px;
            flex-wrap: wrap;
        }

        .card {
            background: white;
            width: 280px;
            padding: 20px;
            border-radius: 12px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.15);
        }

        .card img {
            width: 100%;
            height: 220px;
            object-fit: contain;
        }

        .card h3 {
            margin: 12px 0;
        }

        .card p {
            color: #666;
            margin-bottom: 10px;
        }

        .price {
            font-size: 22px;
            font-weight: bold;
            margin-bottom: 15px;
        }

        /* CHECKOUT */
        .checkout {
            display: none;
            max-width: 600px;
            background: white;
            margin: 40px auto;
            padding: 30px;
            border-radius: 12px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.15);
        }

        .checkout h2 {
            margin-bottom: 20px;
            text-align: center;
        }

        .checkout label {
            display: block;
            margin-top: 15px;
            margin-bottom: 6px;
            font-weight: bold;
        }

        .checkout input,
        .checkout textarea,
        .checkout select {
            width: 100%;
            padding: 12px;
            border: 1px solid #ccc;
            border-radius: 6px;
            font-size: 15px;
        }

        .checkout textarea {
            height: 90px;
            resize: none;
        }

        .order-summary {
            background: #f2f2f2;
            padding: 15px;
            margin: 20px 0;
            border-radius: 7px;
        }

        /* SUCCESS */
        .success {
            display: none;
            text-align: center;
            background: white;
            max-width: 600px;
            margin: 40px auto;
            padding: 50px 20px;
            border-radius: 12px;
        }

        .success h2 {
            color: green;
            margin-bottom: 15px;
        }

        /* FOOTER */
        footer {
            background: #111;
            color: white;
            text-align: center;
            padding: 20px;
            margin-top: 40px;
        }

        @media(max-width: 600px) {
            nav {
                flex-direction: column;
                gap: 12px;
            }

            .hero h2 {
                font-size: 34px;
            }
        }
    </style>
</head>

<body>

    <!-- NAVBAR -->

    <nav>
        <h1>? TimeZone</h1>

        <div>
            <a href="#home">Home</a>
            <a href="#products">Watches</a>
        </div>
    </nav>


    <!-- HERO -->

    <section class="hero" id="home">

        <h2>Time That Defines You</h2>

        <p>
            Premium watches for every occasion.
        </p>

        <button class="btn"
                onclick="document.getElementById('products').scrollIntoView()">
            Shop Now
        </button>

    </section>


    <!-- PRODUCTS -->

    <section class="products" id="products">

        <h2>Our Watches</h2>

        <div class="product-container">


            <!-- WATCH 1 -->

            <div class="card">

                <img src="watch1.jpg" alt="Classic Black Watch">

                <h3>Classic Black</h3>

                <p>Elegant stainless-steel watch.</p>

                <div class="price">?2,999</div>

                <button class="btn"
                    onclick="buyNow('Classic Black', 2999)">
                    Buy Now
                </button>

            </div>


            <!-- WATCH 2 -->

            <div class="card">

                <img src="watch2.jpg" alt="Luxury Gold Watch">

                <h3>Luxury Gold</h3>

                <p>Premium design for special occasions.</p>

                <div class="price">?4,999</div>

                <button class="btn"
                    onclick="buyNow('Luxury Gold', 4999)">
                    Buy Now
                </button>

            </div>


            <!-- WATCH 3 -->

            <div class="card">

                <img src="watch3.jpg" alt="Sport Watch">

                <h3>Sport Pro</h3>

                <p>Modern watch for an active lifestyle.</p>

                <div class="price">?3,499</div>

                <button class="btn"
                    onclick="buyNow('Sport Pro', 3499)">
                    Buy Now
                </button>

            </div>

        </div>

    </section>


    <!-- CHECKOUT -->

    <section class="checkout" id="checkout">

        <h2>Checkout</h2>

        <div class="order-summary">

            <strong>Selected Watch:</strong>

            <p id="selectedWatch"></p>

            <strong>Price:</strong>

            <p id="selectedPrice"></p>

        </div>


        <form onsubmit="placeOrder(event)">

            <label>Full Name</label>

            <input
                type="text"
                id="name"
                placeholder="Enter your full name"
                required
            >


            <label>Mobile Number</label>

            <input
                type="tel"
                id="phone"
                placeholder="Enter your mobile number"
                required
            >


            <label>Email</label>

            <input
                type="email"
                id="email"
                placeholder="Enter your email"
                required
            >


            <label>Delivery Address</label>

            <textarea
                id="address"
                placeholder="House No., Street, City, State, PIN Code"
                required
            ></textarea>


            <label>Payment Method</label>

            <select id="payment" required>

                <option value="">
                    Select Payment Method
                </option>

                <option value="Cash on Delivery">
                    Cash on Delivery
                </option>

                <option value="UPI">
                    UPI
                </option>

                <option value="Debit/Credit Card">
                    Debit / Credit Card
                </option>

            </select>


            <br><br>

            <button class="btn" type="submit">
                Place Order
            </button>

        </form>

    </section>


    <!-- ORDER SUCCESS -->

    <section class="success" id="success">

        <h2>? Order Placed!</h2>

        <p id="confirmation"></p>

        <br>

        <button class="btn" onclick="location.reload()">
            Continue Shopping
        </button>

    </section>


    <!-- FOOTER -->

    <footer>

        <p>
            © 2026 TimeZone Watches |
            All Rights Reserved
        </p>

    </footer>


    <!-- JAVASCRIPT -->

    <script>

        let watchName = "";
        let watchPrice = 0;


        function buyNow(name, price) {

            watchName = name;
            watchPrice = price;

            document.getElementById("selectedWatch").innerText =
                watchName;

            document.getElementById("selectedPrice").innerText =
                "?" + watchPrice;

            document.getElementById("checkout").style.display =
                "block";

            document.getElementById("checkout").scrollIntoView({
                behavior: "smooth"
            });
        }


        function placeOrder(event) {

            event.preventDefault();

            let name =
                document.getElementById("name").value;

            let payment =
                document.getElementById("payment").value;

            document.getElementById("checkout").style.display =
                "none";

            document.getElementById("success").style.display =
                "block";

            document.getElementById("confirmation").innerHTML =

                "Thank you <b>" + name + "</b>!<br><br>" +

                "Your order for <b>" +
                watchName +
                "</b> has been received.<br><br>" +

                "Amount: <b>?" +
                watchPrice +
                "</b><br>" +

                "Payment Method: <b>" +
                payment +
                "</b><br><br>" +

                "We will contact you regarding delivery.";

            document.getElementById("success").scrollIntoView({
                behavior: "smooth"
            });
        }

    </script>

</body>
</html># luxiurous-watch-s
