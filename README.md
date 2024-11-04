<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Airdrop Listing Form</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      margin: 0;
      background: #f4f4f9;
    }
    .form-container {
      background: #fff;
      border-radius: 8px;
      box-shadow: 0px 0px 15px rgba(0,0,0,0.1);
      max-width: 600px;
      width: 100%;
      padding: 20px;
    }
    h2 {
      text-align: center;
      color: #333;
      margin-bottom: 1rem;
    }
    .form-group {
      margin-bottom: 1rem;
    }
    .form-group label {
      display: block;
      font-weight: bold;
      color: #333;
      margin-bottom: 0.5rem;
    }
    .form-group input,
    .form-group textarea {
      width: 100%;
      padding: 0.5rem;
      border: 1px solid #ccc;
      border-radius: 4px;
      font-size: 1rem;
    }
    .form-group input[type="text"] {
      background-color: #f9f9f9;
    }
    .form-group input[type="submit"] {
      background-color: #6B46C1;
      color: #fff;
      font-size: 1rem;
      font-weight: bold;
      cursor: pointer;
      border: none;
      padding: 0.75rem;
      width: 100%;
      border-radius: 4px;
      transition: background-color 0.3s ease;
    }
    .form-group input[type="submit"]:hover {
      background-color: #805AD5;
    }
  </style>
</head>
<body>

  <div class="form-container">
    <h2>Airdrop Listing Form</h2>
    <form id="airdropForm">
      
      <div class="form-group">
        <label for="elementId">Element ID</label>
        <input type="text" id="elementId" placeholder="airdrop-token" required>
      </div>

      <div class="form-group">
        <label for="logo">Logo URL</label>
        <input type="text" id="logo" placeholder="https://cryptologos.cc/logos/airdrop-air-logo.svg?v=025" required>
      </div>

      <div class="form-group">
        <label for="title">Title</label>
        <input type="text" id="title" placeholder="AirToken Airdrop" required>
      </div>

      <div class="form-group">
        <label for="subtitle">Subtitle</label>
        <input type="text" id="subtitle" placeholder="Participate in our community airdrop" required>
      </div>

      <div class="form-group">
        <label for="airdropDate">Airdrop Date</label>
        <input type="text" id="airdropDate" placeholder="October 20, 2024" required>
      </div>

      <div class="form-group">
        <label for="airdropAmount">Airdrop Amount</label>
        <input type="text" id="airdropAmount" placeholder="100 AirTokens" required>
      </div>

      <div class="form-group">
        <label for="detailBoxes">Detail Boxes </label>
        <textarea id="detailBoxes" rows="4" placeholder='[{"title": "Overview", "content": "Community Rewards Program", "gradient": "linear-gradient(...)"}]'></textarea>
      </div>

      <div class="form-group">
        <label for="airdropInfo">Airdrop Info </label>
        <textarea id="airdropInfo" rows="4" placeholder='[{"label": "Total Tokens", "value": "1,000,000 AIR"}]'></textarea>
      </div>

      <div class="form-group">
        <label for="buttons">Buttons </label>
        <textarea id="buttons" rows="4" placeholder='[{"text": "Register", "class": "btn-primary"}]'></textarea>
      </div>

      <div class="form-group">
        <label for="socialLinks">Social Links </label>
        <textarea id="socialLinks" rows="4" placeholder='[{"icon": "fab fa-telegram", "url": "#"}]'></textarea>
      </div>

      <div class="form-group">
        <label for="airdropDescription">Airdrop Description </label>
        <textarea id="airdropDescription" rows="6" placeholder="<h2>About AirToken Airdrop</h2>..."></textarea>
      </div>

      <div class="form-group">
        <input type="submit" value="Submit Airdrop Data">
      </div>
    </form>
  </div>

  <script>
document.getElementById('airdropForm').addEventListener('submit', function(event) {
  event.preventDefault();

  const formData = {
    elementId: document.getElementById('elementId').value,
    logo: document.getElementById('logo').value,
    title: document.getElementById('title').value,
    subtitle: document.getElementById('subtitle').value,
    airdropDate: document.getElementById('airdropDate').value,
    airdropAmount: document.getElementById('airdropAmount').value,
    detailBoxes: JSON.parse(document.getElementById('detailBoxes').value || '[]'),
    airdropInfo: JSON.parse(document.getElementById('airdropInfo').value || '[]'),
    buttons: JSON.parse(document.getElementById('buttons').value || '[]'),
    socialLinks: JSON.parse(document.getElementById('socialLinks').value || '[]'),
    airdropDescription: document.getElementById('airdropDescription').value,
  };

  fetch('https://script.google.com/macros/s/AKfycbwOZi2ZinJnBlbG-UjBjgT_zcqdrKv_sF828JpBnNRHEOLVeuZowWJWqvzC_zvJitza/exec', {
    method: 'POST',
    mode: 'no-cors',
    headers: {
      'Content-Type': 'application/json',
    },
    body: JSON.stringify(formData),
  })
  .then(response => {
    alert("Airdrop data submitted successfully!");
  })
  .catch(error => {
    console.error("Error:", error);
    alert("There was an error submitting the data.");
  });
});
  </script>

</body>
</html>
