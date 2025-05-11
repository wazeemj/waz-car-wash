<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>WAZ Car Wash Centre</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f4f4f4;
      padding: 20px;
      text-align: center;
    }
    .container {
      background: #fff;
      padding: 20px;
      max-width: 500px;
      margin: auto;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      border-radius: 10px;
    }
    h1 {
      color: #007BFF;
    }
    input, select {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      border-radius: 5px;
      border: 1px solid #ccc;
    }
    .checkboxes {
      text-align: left;
      margin-bottom: 15px;
    }
    button {
      background-color: #28a745;
      color: white;
      padding: 10px 20px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    button:hover {
      background-color: #218838;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>WAZ Car Wash Centre</h1>
    <form id="washForm">
      <input type="text" id="name" placeholder="Enter your name" required />

      <label for="time">Choose Time of Wash:</label>
      <select id="time" required>
        <option value="7:00 AM">7:00 AM</option>
        <option value="8:30 AM">8:30 AM</option>
        <option value="9:30 AM">9:30 AM</option>
        <option value="11:00 AM">11:00 AM</option>
        <option value="12:30 PM">12:30 PM</option>
        <option value="2:00 PM">2:00 PM</option>
        <option value="3:30 PM">3:30 PM</option>
        <option value="5:00 PM">5:00 PM</option>
        <option value="6:30 PM">6:30 PM</option>
      </select>

      <p><strong>Duration: 1.5 hrs</strong></p>

      <div class="checkboxes">
        <label><input type="checkbox" value="Vacuum" /> Vacuum</label><br />
        <label><input type="checkbox" value="Full Clean" /> Full Clean</label><br />
        <label><input type="checkbox" value="Normal Cleaning" /> Normal Cleaning</label>
      </div>

      <button type="submit">Submit</button>
    </form>
  </div>

  <script>
    document.getElementById("washForm").addEventListener("submit", function(e) {
      e.preventDefault();

      const name = document.getElementById("name").value;
      const time = document.getElementById("time").value;
      const duration = "1.5 hrs";

      const checkboxes = document.querySelectorAll("input[type=checkbox]:checked");
      const services = Array.from(checkboxes).map(cb => cb.value).join(", ") || "Not selected";

      const message = `New Car Wash Booking:%0AName: ${name}%0ATime: ${time}%0ADuration: ${duration}%0AService: ${services}`;

      const phoneNumber = "91xxxxxxxxxx"; // 🔁 Replace with your WhatsApp number
      window.open(`https://wa.me/${phoneNumber}?text=${message}`, "_blank");
    });
  </script>
</body>
</html>
