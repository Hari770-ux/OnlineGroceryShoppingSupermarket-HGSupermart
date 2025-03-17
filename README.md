<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SuperMart Online Order</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/bootstrap/5.3.0/css/bootstrap.min.css">
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f2f2f2;
        }
        .navbar {
            margin-bottom: 20px;
        }
        .card {
            margin-bottom: 20px;
            transition: transform 0.2s;
        }
        .card:hover {
            transform: scale(1.05);
        }
        #supermarket, #order-history, #order-confirmation {
            display: none; /* Hide sections initially */
        }
        #login-section {
            max-width: 400px;
            margin: 50px auto;
            padding: 20px;
            background-color: white;
            border-radius: 5px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }
        .login-title {
            font-size: 24px;
            font-weight: bold;
            margin-bottom: 20px;
        }
        .login-button {
            background-color: #f90;
            color: white;
        }
        .login-button:hover {
            background-color: #e68a00;
        }
        .notification {
            display: none; /* Hide notifications initially */
            position: fixed;
            top: 20px;
            right: 20px;
            z-index: 1050;
            width: 300px;
        }
        .product-card {
            border: 1px solid #ddd;
            border-radius: 5px;
            padding: 15px;
            background-color: white;
            text-align: center;
        }
        .product-image {
            height: 200px;
            object-fit: contain;
        }
    </style>
</head>
<body>
    <!-- Navbar -->
    <nav class="navbar navbar-expand-lg navbar-dark bg-primary" id="navbar">
        <div class="container">
            <a class="navbar-brand" href="#">HG SuperMart</a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNav">
                <ul class="navbar-nav ms-auto">
                    <li class="nav-item">
                        <a class="nav-link" href="#products">Products</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#cart">Cart</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#checkout">Checkout</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#order-history" id="order-history-link" style="display: none;">Order History</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#" id="logout" style="display: none;">Logout</a>
                    </li>
                </ul>
            </div>
        </div>
    </nav>

    <!-- Notification Messages -->
    <div class="container">
        <div id="notification" class="alert alert-success notification" role="alert"></div>
    </div>

    <!-- Login Section -->
    <div class="container" id="login-section">
        <h1 class="login-title">Sign-In</h1>
        <form id="login-form">
            <div class="mb-3">
                <label for="username" class="form-label">Email, Phone Number, or Username</label>
                <input type="text" class="form-control" id="username" required>
            </div>
            <div class="mb-3">
                <label for="password" class="form-label">Password</label>
                <input type="password" class="form-control" id="password" required>
            </div>
            <button type="submit" class="btn login-button">Continue</button>
        </form>
        <div class="mt-3">
            <a href="#" class="text-primary">Forgot your password?</a>
        </div>
    </div>

    <!-- Supermarket Section -->
    <div class="container mt-5" id="supermarket">
        <h1>           WELCOME TO HG SUPERMARKET</h1>
        <p>Here Only Available Fresh Fruits & Vegitables...</p>
        <a href="#products" class="btn btn-primary">SHOP NOW</a>

        <!-- Products Section -->
        <div class="mt-5" id="products">
            <h2>FRESH VEGITABLES & FRUITS</h2>
            <div class="row">
                <!-- Carrot -->
                <div class="col-md-4">
                    <div class="product-card">
                        <img src="https://th.bing.com/th/id/OIP.MAIgGI6xRjMVX4mHIl_GtgHaFY?w=271&h=197&c=7&r=0&o=5&pid=1.7" class="product-image" alt="Carrot">
                        <h5 class="card-title">Carrot</h5>
                        <p class="card-text">Price: ₹50/kg</p>
                        <button class="btn btn-primary add-to-cart" data-name="Carrot" data-price="50">Add to Cart</button>
                    </div>
                </div>
                <!-- Beans -->
                <div class="col-md-4">
                    <div class="product-card">
                        <img src="https://th.bing.com/th/id/OIP.z5nW3zNAHwgqN6Zb9EXPLAHaFj?w=271&h=197&c=7&r=0&o=5&pid=1.7" class="product-image" alt="Beans">
                        <h5 class="card-title">Beans</h5>
                        <p class="card-text">Price: ₹70/kg</p>
                        <button class="btn btn-primary add-to-cart" data-name="Beans" data-price="70">Add to Cart</button>
                    </div>
                </div>
                <!-- Banana -->
                <div class="col-md-4">
                    <div class="product-card">
                        <img src="https://th.bing.com/th/id/OIP.WMlIV8rCPqup00I_UvZFUgHaE3?w=271&h=197&c=7&r=0&o=5&pid=1.7" class="product-image" alt="Banana">
                        <h5 class="card-title">Banana</h5>
                        <p class="card-text">Price: ₹40/dozen</p>
                        <button class="btn btn-primary add-to-cart" data-name="Banana" data-price="40">Add to Cart</button>
                    </div>
                </div>
                <!-- Tomato -->
                <div class="col-md-4">
                    <div class="product-card">
                        <img src="https://images.pexels.com/photos/1327838/pexels-photo-1327838.jpeg?cs=srgb&dl=tomato-lot-1327838.jpg&fm=jpg" class="product-image" alt="Tomato">
                        <h5 class="card-title">Tomato</h5>
                        <p class="card-text">Price: ₹30/kg</p>
                        <button class="btn btn-primary add-to-cart" data-name="Tomato" data-price="30">Add to Cart</button>
                    </div>
                </div>
                <!-- Onion -->
                <div class="col-md-4">
                    <div class="product-card">
                        <img src="https://th.bing.com/th/id/OIP.PBIEHhmO8R0K7SJAkpmFawHaE9?w=271&h=197&c=7&r=0&o=5&pid=1.7" class="product-image" alt="Onion">
                        <h5 class="card-title">Onion</h5>
                        <p class="card-text">Price: ₹25/kg</p>
                        <button class="btn btn-primary add-to-cart" data-name="Onion" data-price="25">Add to Cart</button>
                    </div>
                </div>
                <!-- Cauliflower -->
                <div class="col-md-4">
                    <div class="product-card">
                        <img src="https://th.bing.com/th/id/OIP.KXHZmVVoLhGdpn1X9BOrUQHaE-?w=271&h=197&c=7&r=0&o=5&pid=1.7" class="product-image" alt="Cauliflower">
                        <h5 class="card-title">Cauliflower</h5>
                        <p class="card-text">Price: ₹35/kg</p>
                        <button class="btn btn-primary add-to-cart" data-name="Cauliflower" data-price="35">Add to Cart</button>
                    </div>
                </div>
                <!-- Spinach -->
                <div class="col-md-4">
                    <div class="product-card">
                        <img src="https://www.theharvestkitchen.com/wp-content/uploads/2023/05/what-is-spinach.jpg" class="product-image" alt="Spinach">
                        <h5 class="card-title">Spinach</h5>
                        <p class="card-text">Price: ₹20/kg</p>
                        <button class="btn btn-primary add-to-cart" data-name="Spinach" data-price="20">Add to Cart</button>
                    </div>
                </div>
                <!-- Cabbage -->
                <div class="col-md-4">
                    <div class="product-card">
                        <img src="https://purepng.com/public/uploads/large/purepng.com-cabbagevegetables-cabbage-941524725589l8d6d.png" class="product-image" alt="Cabbage">
                        <h5 class="card-title">Cabbage</h5>
                        <p class="card-text">Price: ₹30/kg</p>
                        <button class="btn btn-primary add-to-cart" data-name="Cabbage" data-price="30">Add to Cart</button>
                    </div>
                </div>
                <!-- Potato -->
                <div class="col-md-4">
                    <div class="product-card">
                        <img src="https://freepngimg.com/thumb/potato/4-potato-png-images-thumb.png" class="product-image" alt="Potato">
                        <h5 class="card-title">Potato</h5>
                        <p class="card-text">Price: ₹25/kg</p>
                        <button class="btn btn-primary add-to-cart" data-name="Potato" data-price="25">Add to Cart</button>
                    </div>
                </div>
            </div>
        </div>

        <!-- Cart Section -->
        <div class="container mt-5" id="cart">
            <h2>Shopping Cart</h2>
            <table class="table table-bordered">
                <thead>
                    <tr>
                        <th>Product</th>
                        <th>Price</th>
                        <th>Quantity</th>
                        <th>Total</th>
                        <th>Action</th>
                    </tr>
                </thead>
                <tbody id="cart-items">
                    <tr>
                        <td colspan="5" class="text-center">Your cart is empty</td>
                    </tr>
                </tbody>
            </table>
            <h4 class="text-end">Grand Total: ₹<span id="grand-total">0</span></h4>
        </div>

        <!-- Checkout Section -->
        <div class="container mt-5" id="checkout">
            <h2>Checkout</h2>
            <form id="checkout-form">
                <div class="mb-3">
                    <label for="name" class="form-label">Name</label>
                    <input type="text" class="form-control" id="name" required>
                </div>
                <div class="mb-3">
                    <label for="address" class="form-label">Address</label>
                    <textarea class="form-control" id="address" rows="3" required></textarea>
                </div>
                <div class="mb-3">
                    <label for="payment" class="form-label">Payment Method</label>
                    <select class="form-control" id="payment" required>
                        <option value="cod">Cash on Delivery</option>
                        <option value="card">Credit/Debit Card</option>
                    </select>
                </div>
                <button type="submit" class="btn btn-success">Place Order</button>
            </form>
        </div>
    </div>

    <!-- Order History Section -->
    <div class="container mt-5" id="order-history">
        <h2>Order History</h2>
        <table class="table table-bordered">
            <thead>
                <tr>
                    <th>Order ID</th>
                    <th>Product</th>
                    <th>Quantity</th>
                    <th>Total Price</th>
                    <th>Date</th>
                </tr>
            </thead>
            <tbody id="order-history-items">
                <tr>
                    <td colspan="5" class="text-center">No orders placed yet.</td>
                </tr>
            </tbody>
        </table>
        <button class="btn btn-primary" onclick="goToHomePage()">Back to Home</button>
    </div>

    <!-- Order Confirmation Section -->
    <div class="container mt-5" id="order-confirmation">
        <h2>Thank You for Your Purchase!</h2>
        <p>Your order has been placed successfully.</p>
        <p><strong>Shipping Address:</strong></p>
        <p id="confirmation-address"></p>
        <button class="btn btn-primary" onclick="goToHomePage()">Back to Home</button>
    </div>

    <script>
        const cart = [];
        const orders = []; // Array to store order history
        let orderIdCounter = 1; // Simple counter for order IDs

        // Handle login form submission
        document.getElementById('login-form').addEventListener('submit', (event) => {
            event.preventDefault();
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;

            // Allow any username and password to log in
            if (username && password) {
                alert(`Logged in as ${username}`);
                document.getElementById('login-section').style.display = 'none'; // Hide login section
                document.getElementById('supermarket').style.display = 'block'; // Show supermarket section
                document.getElementById('logout').style.display = 'block'; // Show logout link
                document.getElementById('order-history-link').style.display = 'block'; // Show order history link
            } else {
                alert('Please enter valid credentials.');
            }
        });

        document.querySelectorAll('.add-to-cart').forEach(button => {
            button.addEventListener('click', () => {
                const name = button.getAttribute('data-name');
                const price = parseFloat(button.getAttribute('data-price'));

                const existingItem = cart.find(item => item.name === name);
                if (existingItem) {
                    existingItem.quantity++;
                } else {
                    cart.push({ name, price, quantity: 1 });
                }
                updateCart();
            });
        });

        function updateCart() {
            const cartItems = document.getElementById('cart-items');
            const grandTotal = document.getElementById('grand-total');
            let total = 0;

            cartItems.innerHTML = '';
            cart.forEach((item, index) => {
                const itemTotal = item.price * item.quantity;
                total += itemTotal;

                cartItems.innerHTML += `
                    <tr>
                        <td>${item.name}</td>
                        <td>₹${item.price.toFixed(2)}</td>
                        <td>${item.quantity}</td>
                        <td>₹${itemTotal.toFixed(2)}</td>
                        <td>
                            <button class="btn btn-danger btn-sm" onclick="removeFromCart(${index})">Remove</button>
                        </td>
                    </tr>
                `;
            });

            if (cart.length === 0) {
                cartItems.innerHTML = '<tr><td colspan="5" class="text-center">Your cart is empty</td></tr>';
            }

            grandTotal.textContent = total.toFixed(2);
        }

        function removeFromCart(index) {
            cart.splice(index, 1);
            updateCart();
        }

        document.getElementById('checkout-form').addEventListener('submit', (event) => {
            event.preventDefault();
            const name = document.getElementById('name').value;
            const address = document.getElementById('address').value;

            // Save the order
            orders.push({
                orderId: orderIdCounter++,
                products: [...cart],
                totalPrice: cart.reduce((sum, item) => sum + (item.price * item.quantity), 0),
                date: new Date().toLocaleString(),
                address: address
            });

            // Show order confirmation
            document.getElementById('supermarket').style.display = 'none'; // Hide supermarket section
            document.getElementById('order-confirmation').style.display = 'block'; // Show order confirmation section
            document.getElementById('confirmation-address').textContent = address;

            // Clear the cart
            cart.length = 0;
            updateCart();
        });

        // Logout functionality
        document.getElementById('logout').addEventListener('click', () => {
            document.getElementById('supermarket').style.display = 'none'; // Hide supermarket section
            document.getElementById('login-section').style.display = 'block'; // Show login section
            document.getElementById('logout').style.display = 'none'; // Hide logout link
            document.getElementById('order-history-link').style.display = 'none'; // Hide order history link
        });

        // Function to go back to the home page
        function goToHomePage() {
            document.getElementById('order-confirmation').style.display = 'none'; // Hide order confirmation section
            document.getElementById('order-history').style.display = 'none'; // Hide order history section
            document.getElementById('supermarket').style.display = 'block'; // Show supermarket section
        }

        // Function to view order history
        document.getElementById('order-history-link').addEventListener('click', () => {
            document.getElementById('supermarket').style.display = 'none'; // Hide supermarket section
            document.getElementById('order-history').style.display = 'block'; // Show order history section

            const orderHistoryItems = document.getElementById('order-history-items');
            orderHistoryItems.innerHTML = ''; // Clear previous orders

            if (orders.length === 0) {
                orderHistoryItems.innerHTML = '<tr><td colspan="5" class="text-center">No orders placed yet.</td></tr>';
            } else {
                orders.forEach(order => {
                    order.products.forEach(product => {
                        orderHistoryItems.innerHTML += `
                            <tr>
                                <td>${order.orderId}</td>
                                <td>${product.name}</td>
                                <td>${product.quantity}</td>
                                <td>₹${(product.price * product.quantity).toFixed(2)}</td>
                                <td>${order.date}</td>
                            </tr>
                        `;
                    });
                });
            }
        });
    </script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/bootstrap/5.3.0/js/bootstrap.bundle.min.js"></script>
</body>
</html>
