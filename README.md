# Butter-Days

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fruit Crombo | BUtter Days</title>

    <style>
        /* GENERAL */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
            background-color: #F8F3EC;
            color: #493323;
        }

        /* NAVBAR */
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 8%;
            background-color: #E9D9C7;
        }

        .logo {
            font-size: 25px;
            font-weight: bold;
            color: #593B29;
        }

        nav a {
            text-decoration: none;
            color: #593B29;
            margin-left: 25px;
            font-weight: 500;
        }

        .cart {
            background-color: #593B29;
            color: white;
            padding: 9px 15px;
            border-radius: 20px;
        }

        /* BREADCRUMB */
        .breadcrumb {
            padding: 25px 8%;
            font-size: 14px;
            color: #987D66;
        }

        .breadcrumb a {
            text-decoration: none;
            color: #987D66;
        }

        /* PRODUCT DETAIL */
        .product-detail {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 55px;
            padding: 10px 8% 50px;
        }

        /* PRODUCT IMAGE */
        .product-image img {
            width: 100%;
            height: 430px;
            object-fit: cover;
            border-radius: 15px;
        }

        .small-images {
            display: flex;
            gap: 12px;
            margin-top: 15px;
        }

        .small-images img {
            width: 100px;
            height: 85px;
            object-fit: cover;
            border-radius: 10px;
        }

        /* PRODUCT INFORMATION */
        .product-info {
            padding-top: 15px;
        }

        .category {
            display: inline-block;
            background-color: #E9D9C7;
            color: #76533B;
            padding: 7px 16px;
            border-radius: 20px;
            font-size: 13px;
            margin-bottom: 18px;
        }

        .product-info h1 {
            font-size: 42px;
            margin-bottom: 15px;
            color: #593B29;
        }

        .price {
            font-size: 30px;
            font-weight: bold;
            color: #805437;
            margin-bottom: 18px;
        }

        .rating {
            color: #B98237;
            margin-bottom: 25px;
        }

        .rating span {
            color: #806D5B;
            margin-left: 5px;
        }

        /* ACTION BUTTONS */
        .actions {
            display: flex;
            gap: 12px;
            margin-bottom: 22px;
            flex-wrap: wrap;
        }

        .actions button {
            background-color: transparent;
            border: 1px solid #805437;
            color: #593B29;
            padding: 12px 20px;
            border-radius: 25px;
            cursor: pointer;
            font-size: 14px;
        }

        .actions button:hover {
            background-color: #E9D9C7;
        }

        .add-cart {
            width: 100%;
            padding: 15px;
            background-color: #68452F;
            color: white;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            cursor: pointer;
            transition: 0.3s;
        }

        .add-cart:hover {
            background-color: #493323;
        }

        /* PRODUCT TABS */
        .product-tabs {
            margin-top: 35px;
        }

        .tab-buttons {
            display: flex;
            gap: 30px;
            border-bottom: 1px solid #D9C8B6;
        }

        .tab-buttons button {
            background: none;
            border: none;
            padding: 13px 5px;
            cursor: pointer;
            font-size: 15px;
            color: #8A7663;
        }

        .tab-buttons button.active {
            color: #593B29;
            border-bottom: 3px solid #805437;
            font-weight: bold;
        }

        .tab-content {
            padding: 25px 5px;
            line-height: 1.8;
            color: #715C4A;
            font-size: 14px;
        }

        .tab-content h3 {
            color: #593B29;
            margin-bottom: 12px;
        }

        .tab-content ul {
            padding-left: 20px;
            margin-top: 10px;
        }

        /* REVIEWS */
        .review {
            border-bottom: 1px solid #E3D6C8;
            padding: 15px 0;
        }

        .review strong {
            color: #593B29;
        }

        .review p {
            margin-top: 7px;
        }

        /* SUGGESTION */
        .suggestions {
            padding: 45px 8% 70px;
        }

        .suggestion-heading {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 25px;
        }

        .suggestion-heading h2 {
            font-size: 28px;
            color: #593B29;
        }

        .carousel-buttons {
            display: flex;
            gap: 10px;
        }

        .carousel-buttons button {
            width: 40px;
            height: 40px;
            border: 1px solid #B99C80;
            border-radius: 50%;
            background: transparent;
            color: #593B29;
            font-size: 20px;
            cursor: pointer;
        }

        .carousel-buttons button:hover {
            background-color: #E9D9C7;
        }

        .product-list {
            display: flex;
            gap: 20px;
            overflow-x: auto;
            scroll-behavior: smooth;
            scrollbar-width: none;
            padding-bottom: 10px;
        }

        .product-list::-webkit-scrollbar {
            display: none;
        }

        .suggestion-card {
            flex: 0 0 240px;
            background-color: white;
            border-radius: 12px;
            overflow: hidden;
            border: 1px solid #E8DCCF;
        }

        .suggestion-card img {
            width: 100%;
            height: 180px;
            object-fit: cover;
        }

        .suggestion-info {
            padding: 15px;
        }

        .suggestion-info h3 {
            font-size: 17px;
            margin-bottom: 8px;
        }

        .suggestion-info p {
            color: #805437;
            font-weight: bold;
        }

        /* FOOTER */
        footer {
            background-color: #593B29;
            color: #F8F3EC;
            text-align: center;
            padding: 25px;
        }

        /* RESPONSIVE */
        @media (max-width: 800px) {
            .product-detail {
                grid-template-columns: 1fr;
                gap: 25px;
            }

            .product-image img {
                height: 350px;
            }

            .product-info h1 {
                font-size: 32px;
            }

            nav {
                padding: 18px 5%;
            }

            nav a {
                margin-left: 8px;
                font-size: 12px;
            }

            .logo {
                font-size: 19px;
            }
        }

        @media (max-width: 480px) {
            .breadcrumb,
            .product-detail,
            .suggestions {
                padding-left: 5%;
                padding-right: 5%;
            }

            .product-image img {
                height: 280px;
            }

            .product-info h1 {
                font-size: 29px;
            }

            .suggestion-card {
                flex-basis: 200px;
            }
        }

    </style>
</head>

<body>

    <!-- NAVBAR -->
    <nav>
        <div class="logo">BUtter Days.</div>

        <div>
            <a href="index.html">Home</a>
            <a href="products.html">Products</a>
            <a href="about.html">About</a>
        </div>

        <div class="cart">
            🛍 Cart (<span id="cart-count">0</span>)
        </div>
    </nav>


    <!-- BREADCRUMB -->
    <div class="breadcrumb">
        <a href="index.html">Home</a> /
        <a href="products.html">Products</a> /
        Pastries / Fruit Crombo
    </div>


    <!-- PRODUCT DETAIL -->
    <section class="product-detail">

        <!-- PRODUCT IMAGE -->
        <div class="product-image">

            <img
                src="https://images.unsplash.com/photo-1555507036-ab1f4038808a?w=800"
                alt="Fruit Crombo">

            <div class="small-images">
                <img src="https://images.unsplash.com/photo-1555507036-ab1f4038808a?w=300" alt="Fruit Crombo view 1">

                <img src="https://images.unsplash.com/photo-1509365465985-25d11c17e812?w=300" alt="Fruit Crombo view 2">

                <img src="https://images.unsplash.com/photo-1623334044303-241021148842?w=300" alt="Fruit Crombo view 3">
            </div>

        </div>


        <!-- PRODUCT INFORMATION -->
        <div class="product-info">

            <span class="category">Pastries</span>

            <h1>Fruit Crombo</h1>

            <div class="price">Rp25.000,00</div>

            <div class="rating">
                ★★★★★ <span>4.9 (Customer Reviews)</span>
            </div>


            <!-- FAVORITE AND SHARE -->
            <div class="actions">

                <button onclick="toggleFavorite()" id="favorite-btn">
                    ♡ Add to Favorite
                </button>

                <button onclick="shareProduct()">
                    ↗ Share
                </button>

            </div>


            <!-- ADD TO CART -->
            <button class="add-cart" onclick="addToCart()">
                🛍 Add to Cart
            </button>


            <!-- PRODUCT TABS -->
            <div class="product-tabs">

                <div class="tab-buttons">

                    <button
                        class="active"
                        onclick="showTab('description', this)">
                        Description
                    </button>

                    <button
                        onclick="showTab('reviews', this)">
                        Reviews
                    </button>

                </div>


                <!-- DESCRIPTION -->
                <div class="tab-content" id="description">

                    <h3>Product Description</h3>

                    <p>
                        Fruit Crombo is a cromboloni pastry combined
                        with various fresh fruits, especially berries.
                        It has a crunchy texture on the outside and
                        a soft, melt-in-your-mouth filling on the inside.
                    </p>

                    <p>
                        The rich taste of premium butter combined with
                        the sweet and tangy flavor of fresh fruits
                        creates a perfect sensation in every bite.
                    </p>

                    <br>

                    <h3>Serving Instructions</h3>

                    <ul>
                        <li>Ready to eat and enjoy immediately.</li>

                        <li>
                            Store in the refrigerator for longer freshness,
                            up to 3 days.
                        </li>

                        <li>
                            Reheat using a microwave or air fryer
                            before serving.
                        </li>
                    </ul>

                </div>


                <!-- REVIEWS -->
                <div class="tab-content" id="reviews" hidden>

                    <h3>Customer Reviews</h3>

                    <div class="review">
                        <strong>Alya R.</strong>
                        <div class="rating">★★★★★</div>
                        <p>
                            The pastry is so crunchy and the berry
                            combination tastes amazing!
                        </p>
                    </div>

                    <div class="review">
                        <strong>Nadia S.</strong>
                        <div class="rating">★★★★★</div>
                        <p>
                            Love the buttery flavor and creamy filling.
                            Definitely worth trying!
                        </p>
                    </div>

                    <div class="review">
                        <strong>Michelle A.</strong>
                        <div class="rating">★★★★☆</div>
                        <p>
                            Delicious pastry with a perfect balance
                            of sweet and sour flavors.
                        </p>
                    </div>

                </div>

            </div>

        </div>

    </section>



    <!-- PRODUCT SUGGESTIONS -->
    <section class="suggestions">

        <div class="suggestion-heading">

            <h2>You May Also Like</h2>

            <div class="carousel-buttons">

                <button onclick="scrollProducts(-1)">‹</button>

                <button onclick="scrollProducts(1)">›</button>

            </div>

        </div>


        <div class="product-list" id="product-list">


            <!-- BASIC CROMBO -->
            <div class="suggestion-card">

                <img
                    src="https://images.unsplash.com/photo-1555507036-ab1f4038808a?w=500"
                    alt="Basic Crombo">

                <div class="suggestion-info">

                    <h3>Basic Crombo</h3>

                    <p>Rp18.000,00</p>

                </div>

            </div>


            <!-- BUTTER CROISSANT -->
            <div class="suggestion-card">

                <img
                    src="https://images.unsplash.com/photo-1555507036-ab1f4038808a?w=500"
                    alt="Butter Croissant">

                <div class="suggestion-info">

                    <h3>Butter Croissant</h3>

                    <p>Rp18.000,00</p>

                </div>

            </div>


            <!-- CHOCO CROISSANT -->
            <div class="suggestion-card">

                <img
                    src="https://images.unsplash.com/photo-1509365465985-25d11c17e812?w=500"
                    alt="Choco Croissant">

                <div class="suggestion-info">

                    <h3>Choco Croissant</h3>

                    <p>Rp23.000,00</p>

                </div>

            </div>


            <!-- CROISSANT CREAM -->
            <div class="suggestion-card">

                <img
                    src="https://images.unsplash.com/photo-1623334044303-241021148842?w=500"
                    alt="Croissant Cream">

                <div class="suggestion-info">

                    <h3>Croissant Cream</h3>

                    <p>Rp27.000,00</p>

                </div>

            </div>

        </div>

    </section>


    <!-- FOOTER -->
    <footer>

        <h3>BUtter Days.</h3>

        <p>Freshly Baked, Made with Love.</p>

        <br>

        <p>© 2026 BUtter Days. All Rights Reserved.</p>

    </footer>



    <!-- JAVASCRIPT -->
    <script>

        // FAVORITE BUTTON
        function toggleFavorite() {

            const button = document.getElementById("favorite-btn");

            if (button.innerHTML.includes("Add to Favorite")) {

                button.innerHTML = "♥ Added to Favorite";

            } else {

                button.innerHTML = "♡ Add to Favorite";

            }
        }

        // SHARE BUTTON
        function shareProduct() {

            if (navigator.share) {

                navigator.share({
                    title: "Fruit Crombo - BUtter Days",
                    text: "Try our delicious Fruit Crombo!",
                    url: window.location.href
                });

            } else {

                navigator.clipboard.writeText(window.location.href);

               alert("Product link copied!");
            }
        }
        // ADD TO CART
        let cartCount = 0;
        function addToCart() {
            cartCount++;
            document.getElementById("cart-count").innerText = cartCount;
            alert("Fruit Crombo has been added to your cart!");
        }
        // PRODUCT TABS
        function showTab(tabName, button) {
            document.getElementById("description").hidden = true;
            document.getElementById("reviews").hidden = true;
            document.getElementById(tabName).hidden = false;

            const buttons = document.querySelectorAll(".tab-buttons button");

            buttons.forEach(btn => {

                btn.classList.remove("active");

            });

            button.classList.add("active");

        }

        // HORIZONTAL PRODUCT CAROUSEL
        function scrollProducts(direction) {

            const container = document.getElementById("product-list");

            container.scrollBy({

                left: direction * 260,

                behavior: "smooth"

            });

        }

    </script>

</body>
</html>

