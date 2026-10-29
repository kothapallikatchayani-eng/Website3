
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TravelGo - Travel Booking</title>

    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap" rel="stylesheet">

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background: #f4f7fb;
            color: #263247;
        }

        header {
            background: #102d4f;
            color: white;
            padding: 18px 7%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 15px;
        }

        .logo {
            font-size: 27px;
            font-weight: 700;
            color: #55d6be;
        }

        nav {
            display: flex;
            gap: 22px;
            flex-wrap: wrap;
        }

        nav a {
            color: white;
            text-decoration: none;
            font-size: 14px;
        }

        nav a:hover {
            color: #55d6be;
        }

        .hero {
            background:
                linear-gradient(90deg, #102d4feF, #102d4f66),
                url('https://images.unsplash.com/photo-1464822759023-fed622ff2c3b?auto=format&fit=crop&w=1600&q=85')
                center/cover;
            color: white;
            padding: 75px 7% 100px;
        }

        .hero h1 {
            font-size: clamp(32px, 5vw, 52px);
            margin-bottom: 12px;
        }

        .hero p {
            margin-bottom: 28px;
            color: #e3edf7;
        }

        .container {
            width: 86%;
            max-width: 1200px;
            margin: auto;
        }

        .booking-form {
            background: white;
            padding: 28px;
            border-radius: 12px;
            box-shadow: 0 8px 30px #122c4b18;
            margin-top: -55px;
            position: relative;
        }

        .form-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 18px;
        }

        label {
            display: block;
            font-size: 13px;
            font-weight: 600;
            margin-bottom: 7px;
        }

        input, select {
            width: 100%;
            padding: 12px;
            border: 1px solid #d5dce6;
            border-radius: 6px;
            background: white;
            font: inherit;
            font-size: 14px;
            color: #263247;
        }

        input:focus, select:focus {
            outline: 2px solid #55d6be;
            border-color: #55d6be;
        }

        .btn {
            display: inline-block;
            background: #087f8c;
            color: white;
            border: none;
            padding: 13px 22px;
            border-radius: 6px;
            cursor: pointer;
            font: inherit;
            font-weight: 600;
            text-decoration: none;
        }

        .btn:hover {
            background: #06636e;
        }

        .search-btn {
            margin-top: 20px;
            width: 100%;
        }

        section.content {
            padding: 60px 0;
        }

        .section-title {
            font-size: 29px;
            margin-bottom: 10px;
            color: #102d4f;
        }

        .section-desc {
            color: #718096;
            margin-bottom: 28px;
        }

        .travel-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 22px;
        }

        .travel-card {
            background: white;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 5px 20px #102d4f0c;
            border: 1px solid #e5eaf1;
        }

        .travel-card img {
            width: 100%;
            height: 180px;
            object-fit: cover;
            display: block;
        }

        .card-body {
            padding: 20px;
        }

        .card-body h3 {
            font-size: 19px;
            margin-bottom: 8px;
        }

        .tag {
            display: inline-block;
            background: #e0f7f2;
            color: #087f8c;
            padding: 5px 10px;
            font-size: 12px;
            border-radius: 20px;
            margin-bottom: 12px;
        }

        .card-body p {
            color: #65748b;
            font-size: 14px;
            margin-bottom: 8px;
        }

        .fare {
            color: #087f8c !important;
            font-size: 23px !important;
            font-weight: 700;
            margin: 15px 0 !important;
        }

        .card-body .btn {
            width: 100%;
            text-align: center;
        }

        .table-wrapper {
            overflow-x: auto;
            background: white;
            border-radius: 10px;
            box-shadow: 0 5px 20px #102d4f0c;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            min-width: 600px;
        }

        th, td {
            padding: 16px;
            text-align: left;
            border-bottom: 1px solid #e5eaf1;
            font-size: 14px;
        }

        th {
            background: #102d4f;
            color: white;
        }

        tr:hover td {
            background: #f0faf9;
        }

        .seat-layout {
            background: white;
            border-radius: 12px;
            padding: 28px;
            max-width: 560px;
            margin: auto;
            box-shadow: 0 5px 20px #102d4f0c;
        }

        .seat-legend {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 18px;
            margin: 20px 0;
            font-size: 13px;
        }

        .legend-item {
            display: flex;
            align-items: center;
            gap: 7px;
        }

        .seat-box {
            width: 19px;
            height: 19px;
            border-radius: 4px;
            display: inline-block;
        }

        .available {
            background: #e1f6f0;
            border: 1px solid #39a68b;
        }

        .selected {
            background: #087f8c;
        }

        .booked {
            background: #d4d9e2;
        }

        .seat-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 13px;
            max-width: 300px;
            margin: 25px auto;
        }

        .seat {
            padding: 12px 4px;
            border-radius: 6px;
            border: 1px solid #39a68b;
            background: #e1f6f0;
            color: #175a4b;
            cursor: pointer;
            font-weight: 600;
        }

        .seat:hover:not(:disabled) {
            outline: 2px solid #087f8c;
        }

        .seat.chosen {
            background: #087f8c;
            color: white;
        }

        .seat:disabled {
            background: #d4d9e2;
            color: #788397;
            border-color: #d4d9e2;
            cursor: not-allowed;
        }

        .aisle {
            visibility: hidden;
        }

        .seat-summary {
            text-align: center;
            margin: 20px 0;
        }

        .passenger-form {
            background: white;
            padding: 28px;
            border-radius: 12px;
            box-shadow: 0 5px 20px #102d4f0c;
        }

        .passenger-form .form-grid {
            margin-bottom: 20px;
        }

        .message {
            margin-top: 15px;
            color: #087f8c;
            font-size: 14px;
        }

        .hidden {
            display: none !important;
        }

        footer {
            background: #102d4f;
            color: #d6e2f0;
            text-align: center;
            padding: 28px 15px;
            font-size: 14px;
        }

        @media (max-width: 900px) {
            .container {
                width: 92%;
            }

            .form-grid {
                grid-template-columns: repeat(2, 1fr);
            }

            .travel-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (max-width: 600px) {
            header {
                flex-direction: column;
                align-items: flex-start;
            }

            nav {
                gap: 12px;
            }

            nav a {
                font-size: 12px;
            }

            .hero {
                padding: 55px 5% 80px;
            }

            .container {
                width: 92%;
            }

            .booking-form {
                padding: 20px;
            }

            .form-grid, .travel-grid {
                grid-template-columns: 1fr;
            }

            section.content {
                padding: 42px 0;
            }

            .section-title {
                font-size: 25px;
            }
        }
    </style>
</head>

<body>

<header>
    <div class="logo">TravelGo</div>

    <nav>
        <a href="#home">Home</a>
        <a href="#services">Services</a>
        <a href="#fares">Fares</a>
        <a href="#seats">Select Seats</a>
        <a href="#passengers">Passenger Details</a>
    </nav>
</header>

<!-- HERO -->
<section class="hero" id="home">
    <div>
        <h1>Your Journey, Your Way</h1>
        <p>Discover destinations, compare fares and plan your next trip.</p>
    </div>
</section>

<main class="container">

    <!-- SEARCH FORM -->
    <section class="booking-form" aria-label="Travel search">
        <h2 class="section-title">Find Your Journey</h2>
        <p class="section-desc">Enter your trip details to explore sample travel options.</p>

        <form id="searchForm">
            <div class="form-grid">
                <div>
                    <label for="source">From</label>
                    <input id="source" name="source" list="cities"
                           placeholder="Enter source city" required>
                </div>

                <div>
                    <label for="destination">To</label>
                    <input id="destination" name="destination" list="cities"
                           placeholder="Enter destination city" required>
                </div>

                <datalist id="cities">
                    <option value="Vijayawada">
                    <option value="Hyderabad">
                    <option value="Chennai">
                    <option value="Bengaluru">
                    <option value="Visakhapatnam">
                    <option value="Tirupati">
                    <option value="Mumbai">
                    <option value="Delhi">
                </datalist>

                <div>
                    <label for="travelDate">Travel Date</label>
                    <input type="date" id="travelDate" name="travelDate" required>
                </div>

                <div>
                    <label for="returnDate">Return Date (optional)</label>
                    <input type="date" id="returnDate" name="returnDate">
                </div>

                <div>
                    <label for="passengerCount">Passengers</label>
                    <select id="passengerCount" name="passengerCount">
                        <option value="1">1 Passenger</option>
                        <option value="2">2 Passengers</option>
                        <option value="3">3 Passengers</option>
                        <option value="4">4 Passengers</option>
                        <option value="5">5 Passengers</option>
                        <option value="6">6 Passengers</option>
                    </select>
                </div>

                <div>
                    <label for="travelClass">Travel Class</label>
                    <select id="travelClass" name="travelClass">
                        <option value="Economy">Economy</option>
                        <option value="Standard">Standard</option>
                        <option value="Premium">Premium</option>
                    </select>
                </div>
            </div>

            <button class="btn search-btn" type="submit">Search Travel Options</button>
            <p id="searchMessage" class="message" role="status" aria-live="polite"></p>
        </form>
    </section>

    <!-- AVAILABLE SERVICES -->
    <section class="content" id="services">
        <h2 class="section-title">Available Travel Services</h2>
        <p class="section-desc">Choose a travel option that suits your needs.</p>

        <div class="travel-grid">
            <article class="travel-card">
                <img src="https://images.unsplash.com/photo-1570125909232-eb263c188f7e?auto=format&fit=crop&w=900&q=80"
                     alt="Passenger bus">
                <div class="card-body">
                    <span class="tag">Bus Travel</span>
                    <h3>Comfort Bus</h3>
                    <p>Air-conditioned seats and luggage space.</p>
                    <p>Estimated duration: 5 hours</p>
                    <p class="fare">₹650 <small>/ person</small></p>
                    <button class="btn choose-service" data-service="Bus">Select Bus</button>
                </div>
            </article>

            <article class="travel-card">
                <img src="https://images.unsplash.com/photo-1474487548417-781cb71495f3?auto=format&fit=crop&w=900&q=80"
                     alt="Passenger train">
                <div class="card-body">
                    <span class="tag">Rail Travel</span>
                    <h3>Express Train</h3>
                    <p>Comfortable rail travel with multiple classes.</p>
                    <p>Estimated duration: 4 hours</p>
                    <p class="fare">₹450 <small>/ person</small></p>
                    <button class="btn choose-service" data-service="Train">Select Train</button>
                </div>
            </article>

            <article class="travel-card">
                <img src="https://images.unsplash.com/photo-1436491865332-7a61a109cc05?auto=format&fit=crop&w=900&q=80"
                     alt="Passenger airplane">
                <div class="card-body">
                    <span class="tag">Air Travel</span>
                    <h3>Domestic Flight</h3>
                    <p>Quick travel for longer-distance journeys.</p>
                    <p>Estimated duration: 1 hour 15 minutes</p>
                    <p class="fare">₹3,500 <small>/ person</small></p>
                    <button class="btn choose-service" data-service="Flight">Select Flight</button>
                </div>
            </article>
        </div>

        <p class="message" id="serviceMessage" role="status" aria-live="polite"></p>
    </section>

    <!-- FARE TABLE -->
    <section class="content" id="fares">
        <h2 class="section-title">Fare Comparison</h2>
        <p class="section-desc">Example fares for comparing travel services.</p>

        <div class="table-wrapper">
            <table>
                <thead>
                    <tr>
                        <th>Travel Service</th>
                        <th>Travel Class</th>
                        <th>Estimated Duration</th>
                        <th>Fare per Person</th>
                        <th>Availability</th>
                    </tr>
                </thead>

                <tbody>
                    <tr>
                        <td>Bus</td>
                        <td>Standard AC</td>
                        <td>5 hours</td>
                        <td>₹650</td>
                        <td>Sample</td>
                    </tr>
                    <tr>
                        <td>Train</td>
                        <td>Chair Car</td>
                        <td>4 hours</td>
                        <td>₹450</td>
                        <td>Sample</td>
                    </tr>
                    <tr>
                        <td>Flight</td>
                        <td>Economy</td>
                        <td>1 hr 15 min</td>
                        <td>₹3,500</td>
                        <td>Sample</td>
                    </tr>
                </tbody>
            </table>
        </div>
    </section>

    <!-- SEAT SELECTION -->
    <section class="content" id="seats">
        <h2 class="section-title">Choose Your Seat</h2>
        <p class="section-desc">Select available seats for your sample bus booking.</p>

        <div class="seat-layout">
            <h3 style="text-align:center;">Bus Seat Layout</h3>

            <div class="seat-legend">
                <div class="legend-item">
                    <span class="seat-box available"></span> Available
                </div>
                <div class="legend-item">
                    <span class="seat-box selected"></span> Selected
                </div>
                <div class="legend-item">
                    <span class="seat-box booked"></span> Unavailable
                </div>
            </div>

            <div class="seat-grid" id="seatGrid">
                <button type="button" class="seat">A1</button>
                <button type="button" class="seat">A2</button>
                <span class="aisle"> </span>
                <button type="button" class="seat" disabled>B1</button>

                <button type="button" class="seat">A3</button>
                <button type="button" class="seat">A4</button>
                <span class="aisle"> </span>
                <button type="button" class="seat">B2</button>

                <button type="button" class="seat">A5</button>
                <button type="button" class="seat" disabled>A6</button>
                <span class="aisle"> </span>
                <button type="button" class="seat">B3</button>

                <button type="button" class="seat">A7</button>
                <button type="button" class="seat">A8</button>
                <span class="aisle"> </span>
                <button type="button" class="seat">B4</button>
            </div>

            <div class="seat-summary">
                <p>Selected Seats: <strong id="selectedSeats">None</strong></p>
                <p>Total Seat Fare: <strong id="seatFare">₹0</strong></p>
                <p style="font-size:12px;color:#718096;">
                    Demo seat price: ₹650 per seat.
                </p>
            </div>

            <button type="button" class="btn" id="confirmSeats" style="width:100%;">
                Confirm Seat Selection
            </button>

            <p class="message" id="seatMessage" role="status" aria-live="polite"></p>
        </div>
    </section>

    <!-- PASSENGER DETAILS -->
    <section class="content" id="passengers">
        <h2 class="section-title">Passenger Details</h2>
        <p class="section-desc">Enter the lead passenger's information.</p>

        <form class="passenger-form" id="passengerForm">
            <div class="form-grid">
                <div>
                    <label for="fullName">Full Name</label>
                    <input type="text" id="fullName" required
                           placeholder="Enter full name">
                </div>

                <div>
                    <label for="email">Email Address</label>
                    <input type="email" id="email" required
                           placeholder="name@example.com">
                </div>

                <div>
                    <label for="phone">Phone Number</label>
                    <input type="tel" id="phone" required
                           pattern="[0-9+() -]{7,20}"
                           placeholder="Enter phone number">
                </div>

                <div>
                    <label for="age">Age</label>
                    <input type="number" id="age" min="1" max="120"
                           required placeholder="Enter age">
                </div>

                <div>
                   
