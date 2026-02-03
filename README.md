<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Bussy Bee Couriers</title>
  <style>
:root {
  --primary: #0f172a;
  --secondary: #2563eb;
  --accent: #f59e0b;
  --bg: #f9fafb;
  --card: #ffffff;
}
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Roboto', Arial, sans-serif;
  background: var(--bg);
  color: #111827;
  line-height: 1.6;
}
header {
  background: linear-gradient(135deg, #0f172a, #1f2937);
  color: #fff;
  padding: 80px 20px;
  text-align: center;
}
header h1 {
  font-size: 2.6rem;
  margin-bottom: 10px;
}
nav {
  position: sticky;
  top: 0;
  z-index: 100;
  display: flex;
  justify-content: center;
  gap: 15px;
  background: #020617;
  padding: 14px;
}
nav a {
  color: #fff;
  text-decoration: none;
  font-weight: 500;
  padding: 10px 16px;
  border-radius: 10px;
  transition: 0.3s;
}
nav a:hover {
  background: var(--secondary);
}
.hero {
  max-width: 1100px;
  margin: -40px auto 40px;
  background: var(--card);
  border-radius: 26px;
  padding: 90px 30px;
  text-align: center;
  box-shadow: 0 30px 60px rgba(0,0,0,0.08);
}
.container {
  max-width: 1100px;
  margin: auto;
  padding: 80px 20px;
}
h2 {
  text-align: center;
  font-size: 2rem;
  margin-bottom: 30px;
  color: var(--primary);
}
.services {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 25px;
}
.card {
  background: var(--card);
  padding: 30px;
  border-radius: 22px;
  box-shadow: 0 20px 45px rgba(0,0,0,0.08);
  transition: 0.35s;
}
.card:hover {
  transform: translateY(-6px);
}
.card h3 {
  margin-top: 0;
  color: var(--secondary);
}
input, select {
  width: 100%;
  padding: 14px;
  border-radius: 12px;
  border: 1px solid #e5e7eb;
  margin-bottom: 16px;
  font-size: 1rem;
}
button {
  background: var(--secondary);
  color: #fff;
  border: none;
  padding: 14px 32px;
  border-radius: 999px;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: 0.3s;
}
button:hover {
  background: #1d4ed8;
}
.cta {
  background: linear-gradient(135deg, #2563eb, #1e40af);
  color: #fff;
  text-align: center;
  padding: 80px 20px;
}
iframe {
  width: 100%;
  height: 360px;
  border-radius: 26px;
  border: 0;
}
footer {
  background: #020617;
  color: #fff;
  text-align: center;
  padding: 25px;
  font-size: 14px;
}
@media (max-width: 600px) {
  header h1 { font-size: 1.9rem; }
  .hero { padding: 60px 20px; }
}
</style>
</head>
<body>

<header>
  <img src="logo.png" alt="Bussy Bee Couriers Logo" style="max-width:120px; display:block; margin:0 auto 10px;" />
  <h1>Busy Bee Couriers</h1>
  <p>Fast, Reliable & Door‑to‑Door Courier Services</p>
</header>

<nav>
  <a href="#services">Services</a>
  <a href="#order">Place Order</a>
  <a href="#about">About</a>
  <a href="#contact">Contact</a>
</nav>

<section class="hero">
  <h1>Your Everyday Delivery Partner</h1>
  <p>From errands to surprises — we deliver it all.</p>
</section>

<section id="services" class="container">
  <h2>Our Services</h2>
  <div class="services">
    <div class="card"><h3>Personal Errands</h3><p>Let us handle your day-to-day tasks.</p></div>
    <div class="card"><h3>Medical Errands</h3><p>Prescription and pharmacy deliveries.</p></div>
    <div class="card"><h3>Liquor Delivery</h3><p>Safe and discreet delivery.</p></div>
    <div class="card"><h3>Pick-ups & Dispatch</h3><p>Fast and secure parcel handling.</p></div>
    <div class="card"><h3>Food Delivery</h3><p>Your meals delivered hot.</p></div>
    <div class="card"><h3>Surprise Gift Delivery</h3><p>Make moments special.</p></div>
  </div>
</section>

<section id="order" class="container">
  <h2>Place an Order</h2>
  <form onsubmit="sendWhatsApp(); return false;" class="card">
    <label>Service Type</label><br />
    <select id="service" required>
      <option>Personal Errand</option>
      <option>Medical Errand</option>
      <option>Liquor Delivery</option>
      <option>Pick-up & Dispatch</option>
      <option>Food Delivery</option>
      <option>Surprise Gift</option>
    </select><br /><br />

    <label>Pickup Location</label><br />
    <input id="pickup" required /><br /><br />

    <label>Drop-off Location</label><br />
    <input id="dropoff" required /><br /><br />

    <label>Suburb</label><br />
    <select id="suburb" onchange="updateFee()">
      <option value="5">Harare CBD – $5</option>
      <option value="7">Mbare – $7</option>
      <option value="7">Highfield – $7</option>
      <option value="10">Borrowdale – $10</option>
      <option value="10">Mount Pleasant – $10</option>
    </select><br /><br />

    <p><strong>Delivery Fee: $<span id="fee">5</span></strong></p>
    <button type="submit">Send Order via WhatsApp</button>
    <br /><br />
    <button type="button" onclick="sendSMS()">Send Order via SMS</button>
  </form>
</section>

<section id="admin" class="container">
  <h2>Admin – Update Prices</h2>
  <div class="card">
    <input type="password" id="adminPass" placeholder="Admin password" />
    <button onclick="unlockAdmin()">Unlock</button>
    <div id="adminPanel" style="display:none; margin-top:15px;">
      <label>Set New Price ($)</label><br />
      <input id="newPrice" type="number" />
      <button onclick="applyPrice()">Apply to Selected Suburb</button>
      <p style="font-size:12px;">(Prices update instantly on this device)</p>
    </div>
  </div>
</section>

<section id="hours" class="container">
  <h2>Business Hours</h2>
  <div class="card">
    <p><strong>Monday – Friday:</strong> 8:00am – 5:00pm</p>
    <p><strong>Saturday:</strong> 8:00am – 2:00pm</p>
    <p><strong>Sunday:</strong> Closed</p>
  </div>
</section>

<section id="about" class="container">
  <h2>About Us</h2>
  <p>
    Bussy Bee Couriers is a trusted Harare‑based courier service committed to speed, safety and reliability. From urgent errands to surprise deliveries, we make sure your items arrive on time across Harare.
  </p>
</section>

<section id="service-area" class="container">
  <h2>Service Area</h2>
  <p>We currently serve customers within <strong>Harare</strong> and surrounding suburbs.</p>
  <iframe
    src="https://www.google.com/maps?q=Harare,Zimbabwe&output=embed"
    width="100%"
    height="350"
    style="border:0; border-radius:10px;"
    allowfullscreen=""
    loading="lazy">
  </iframe>
</section>

<section id="payment" class="container">
  <h2>Payment Options</h2>
  <p>Payments are securely processed via <strong>EcoCash</strong>. Payment details are shared privately after order confirmation.</p>
  <div class="services">
    <div class="card">
      <h3>EcoCash Mobile Payment</h3>
      <p>Fast, safe and convenient mobile money payment.</p>
    </div>
  </div>
</section>

<section class="cta" id="contact">
  <h2>Need a Delivery?</h2>
  <p>Contact us today and let’s get moving.</p>
  <button onclick="alert('Call or WhatsApp: +263 780 658 344 / +263 778 199 590 XXX')">Get in Touch</button>
</section>

<footer>
  <p>&copy; 2026 Busy Bee Couriers. All Rights Reserved.</p>
</footer>

<a href="https://wa.me/263780658344" style="position:fixed;bottom:20px;right:20px;background:#25d366;color:#fff;padding:15px 20px;border-radius:50px;text-decoration:none;font-weight:bold;">WhatsApp Order</a>

<script>
function updateFee(){
  fee.innerText = suburb.value;
}

function sendWhatsApp(){
  const msg = `Order Details:%0AService: ${service.value}%0APickup: ${pickup.value}%0ADrop-off: ${dropoff.value}%0ASuburb: ${suburb.options[suburb.selectedIndex].text}%0AFee: $${fee.innerText}`;
  window.open(`https://wa.me/263780658344?text=${msg}`,'_blank');
}

function sendSMS(){
  const msg = `Order Details: Service ${service.value}, Pickup ${pickup.value}, Drop-off ${dropoff.value}, Fee $${fee.innerText}`;
  window.location.href = `sms:+263780658344?body=${encodeURIComponent(msg)}`;
}

function unlockAdmin(){
  if(adminPass.value === 'bee123'){
    adminPanel.style.display = 'block';
  } else {
    alert('Incorrect password');
  }
}

function applyPrice(){
  suburb.options[suburb.selectedIndex].value = newPrice.value;
  updateFee();
}
</script>

</body>
</html>
