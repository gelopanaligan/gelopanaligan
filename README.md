<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Basketball Court Reservation</title>
<style>
    body {
        font-family: Arial, sans-serif;
    }
    .container {
        max-width: 600px;
        margin: 0 auto;
        padding: 20px;
    }
    label {
        font-weight: bold;
    }
    input[type="datetime-local"] {
        width: 100%;
        margin-bottom: 10px;
    }
    button {
        padding: 10px 20px;
        background-color: #007bff;
        color: #fff;
        border: none;
        cursor: pointer;
    }
    #availability {
        margin-top: 20px;
    }
</style>
</head>
<body>
<div class="container">
    <h2>Basketball Court Reservation</h2>
    <form id="reservationForm">
        <div>
            <label for="date">Select Date and Time:</label>
            <input type="datetime-local" id="date" name="date" required>
        </div>
        <button type="submit">Check Availability</button>
    </form>
    <div id="availability"></div>
</div>

<script>
    const reservationForm = document.getElementById('reservationForm');
    const availabilityDiv = document.getElementById('availability');

    reservationForm.addEventListener('submit', function(event) {
        event.preventDefault();
        const dateTime = document.getElementById('date').value;
        // Here you can make an AJAX request to your backend to check availability
        // For now, let's simulate availability randomly
        const isAvailable = Math.random() < 0.5; // Example random check

        if (isAvailable) {
            availabilityDiv.innerHTML = '<p>Selected date and time is available. You can proceed with reservation.</p>';
        } else {
            availabilityDiv.innerHTML = '<p>Selected date and time is not available. Please choose another time.</p>';
        }
    });
</script>
</body>
</html>

