
<!DOCTYPE html>
<html>
<head>
    <title>RentEasy - Vehicle Rental Portal</title>

    <style>
        body {
            margin: 0;
            font-family: Arial;
            background-color: #eeeeee;
            color: black;
        }

        header {
            background-color: navy;
            color: white;
            padding: 20px;
            text-align: center;
        }

        nav {
            background-color: black;
            padding: 15px;
            text-align: center;
        }

        nav a {
            color: white;
            text-decoration: none;
            margin: 20px;
            font-size: 17px;
        }

        nav a:hover {
            color: yellow;
        }

        marquee {
            background-color: orange;
            color: black;
            padding: 12px;
            font-weight: bold;
        }

        .home {
            text-align: center;
            padding: 50px;
            background-color: lightblue;
        }

        .home h1 {
            font-size: 35px;
        }

        button {
            background-color: navy;
            color: white;
            padding: 10px 20px;
            border: none;
            cursor: pointer;
        }

        button:hover {
            background-color: green;
        }

        .vehicles {
            text-align: center;
            padding: 30px;
        }

        .box {
            display: inline-block;
            background-color: white;
            width: 230px;
            margin: 15px;
            padding: 15px;
            border: 1px solid gray;
            border-radius: 10px;
        }

        .box img {
            width: 100%;
            height: 140px;
        }

        .booking {
            background-color: white;
            width: 350px;
            margin: 30px auto;
            padding: 25px;
            border-radius: 10px;
        }

        input, select {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            box-sizing: border-box;
        }

        footer {
            background-color: navy;
            color: white;
            text-align: center;
            padding: 20px;
        }
    </style>
</head>

<body>

<header>
    <h1>RentEasy 🚗</h1>
    <p>Online Rental Vehicle Portal</p>
</header>

<nav>
    <a href="#home">Home</a>
    <a href="#vehicles">Vehicles</a>
    <a href="#booking">Booking</a>
    <a href="#contact">Contact</a>
</nav>

<marquee>
    Welcome to RentEasy! Book Your Favourite Car or Bike
    at Affordable Prices!
</marquee>

<div class="home" id="home">
    <h1>Welcome to RentEasy</h1>
    <p>Find the perfect vehicle for your journey.</p>
    <button onclick="showMessage()">Explore Now</button>
</div>

<div class="vehicles" id="vehicles">

    <h2>Available Vehicles</h2>

    <div class="box">
        <img src="https://images.unsplash.com/photo-1549317661-bd32c8ce0db2?w=500">
        <h3>Maruti Swift</h3>
        <p>Category: Car</p>
        <p>Price: ₹1800/Day</p>
        <button onclick="selectVehicle('Maruti Swift')">
            Book Now
        </button>
    </div>

    <div class="box">
        <img src="https://images.unsplash.com/photo-1519641471654-76ce0107ad1b?w=500">
        <h3>Mahindra Thar</h3>
        <p>Category: SUV</p>
        <p>Price: ₹3500/Day</p>
        <button onclick="selectVehicle('Mahindra Thar')">
            Book Now
        </button>
    </div>

    <div class="box">
        <img src="https://images.unsplash.com/photo-1558981806-ec527fa84c39?w=500">
        <h3>Royal Enfield</h3>
        <p>Category: Bike</p>
        <p>Price: ₹1200/Day</p>
        <button onclick="selectVehicle('Royal Enfield')">
            Book Now
        </button>
    </div>

</div>

<h2 style="text-align:center" id="booking">
    Vehicle Booking Form
</h2>

<div class="booking">

    <form onsubmit="return booking()">

        <label>Customer Name:</label>
        <input type="text" id="name" placeholder="Enter your name" required>

        <label>Email:</label>
        <input type="email" id="email" placeholder="Enter email" required>

        <label>Select Vehicle:</label>
        <select id="vehicle" required>
            <option value="">Choose Vehicle</option>
            <option>Maruti Swift</option>
            <option>Mahindra Thar</option>
            <option>Royal Enfield</option>
        </select>

        <label>Booking Date:</label>
        <input type="date" id="date" required>

        <button type="submit">Submit Booking</button>

    </form>

</div>

<footer id="contact">
    <h3>RentEasy Vehicle Rental Portal</h3>
    <p>Email: renteasy@gmail.com</p>
    <p>Contact: 9876543210</p>
    <p>© 2026 RentEasy. All Rights Reserved.</p>
</footer>

<script>

function showMessage() {
    alert("Welcome to RentEasy! Choose your vehicle.");
}

function selectVehicle(vehicleName) {
    document.getElementById("vehicle").value = vehicleName;

    document.getElementById("booking").scrollIntoView({
        behavior: "smooth"
    });
}

function booking() {

    var name = document.getElementById("name").value;
    var vehicle = document.getElementById("vehicle").value;
    var date = document.getElementById("date").value;

    if (date < new Date().toISOString().split("T")[0]) {
        alert("Please select a valid future date.");
        return false;
    }

    alert(
        "Booking Submitted Successfully!\n" +
        "Customer: " + name + "\n" +
        "Vehicle: " + vehicle + "\n" +
        "Date: " + date
    );

    return false;
}

</script>

</body>
</html>
