<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript Demo</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <h1>JavaScript Demo</h1>
    <form id="myForm">
        <label for="name">Name:</label>
        <input type="text" id="name" name="name"><br><br>
        <label for="email">Email:</label>
        <input type="email" id="email" name="email"><br><br>
        <button id="submitBtn">Submit</button>
    </form>
    <div id="result"></div>

    <button id="toggleBtn">Toggle Background Color</button>

    <script src="script.js"></script>
</body>
</html>


styles.css

body {
    font-family: Arial, sans-serif;
}

#myForm {
    width: 50%;
    margin: 40px auto;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

#result {
    margin-top: 20px;
    font-size: 18px;
    font-weight: bold;
}

#toggleBtn {
    margin-top: 20px;
}


script.js

// Get elements
const form = document.getElementById('myForm');
const nameInput = document.getElementById('name');
const emailInput = document.getElementById('email');
const submitBtn = document.getElementById('submitBtn');
const resultDiv = document.getElementById('result');
const toggleBtn = document.getElementById('toggleBtn');

// Add event listeners
form.addEventListener('submit', validateForm);
toggleBtn.addEventListener('click', toggleBackgroundColor);

// Validate form
function validateForm(event) {
    event.preventDefault();
    const nameValue = nameInput.value.trim();
    const emailValue = emailInput.value.trim();

    if (nameValue === '') {
        resultDiv.textContent = 'Please enter your name';
        resultDiv.style.color = 'red';
    } else if (emailValue === '') {
        resultDiv.textContent = 'Please enter your email';
        resultDiv.style.color = 'red';
    } else if (!emailValue.includes('@')) {
        resultDiv.textContent = 'Please enter a valid email';
        resultDiv.style.color = 'red';
    } else {
        resultDiv.textContent = 'Form submitted successfully!';
        resultDiv.style.color = 'green';
    }
}

// Toggle background color
function toggleBackgroundColor() {
    document.body.classList.toggle('dark-mode');
}


