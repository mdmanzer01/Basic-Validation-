# Basic-Validation-
HTML form with basic validation for name, email, phone number, password, age, gender, date, and color picker inputs:

html
Copy code
<!DOCTYPE html>
<html>
<head>
  <title>Form with Basic Validation</title>
  <style>
    .error {
      color: red;
    }
  </style>
  <script>
    function validateForm() {
      var name = document.forms["myForm"]["name"].value;
      var email = document.forms["myForm"]["email"].value;
      var phone = document.forms["myForm"]["phone"].value;
      var password = document.forms["myForm"]["password"].value;
      var age = document.forms["myForm"]["age"].value;
      var gender = document.forms["myForm"]["gender"].value;
      var date = document.forms["myForm"]["date"].value;
      var color = document.forms["myForm"]["color"].value;

      // Name validation (should not be empty)
      if (name === "") {
        document.getElementById("nameError").innerHTML = "Name is required";
        return false;
      }

      // Email validation (should be a valid email address)
      var emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
      if (!email.match(emailPattern)) {
        document.getElementById("emailError").innerHTML = "Invalid email address";
        return false;
      }

      // Phone number validation (should be a valid phone number)
      var phonePattern = /^\d{10}$/; // 10-digit phone number
      if (!phone.match(phonePattern)) {
        document.getElementById("phoneError").innerHTML = "Invalid phone number";
        return false;
      }

      // Password validation (should be at least 8 characters long)
      if (password.length < 8) {
        document.getElementById("passwordError").innerHTML = "Password should be at least 8 characters";
        return false;
      }

      // Age validation (should be a number between 1 and 120)
      if (isNaN(age) || age < 1 || age > 120) {
        document.getElementById("ageError").innerHTML = "Invalid age";
        return false;
      }

      // Gender validation (should be selected)
      if (gender === "") {
        document.getElementById("genderError").innerHTML = "Please select a gender";
        return false;
      }

      // Date validation (should not be empty)
      if (date === "") {
        document.getElementById("dateError").innerHTML = "Date is required";
        return false;
      }

      // Color validation (should not be empty)
      if (color === "") {
        document.getElementById("colorError").innerHTML = "Color is required";
        return false;
      }

      // If all validations pass, the form is valid
      return true;
    }
  </script>
</head>
<body>
  <h2>Form with Basic Validation</h2>
  <form name="myForm" onsubmit="return validateForm()" method="post">
    <label for="name">Name:</label>
    <input type="text" id="name" name="name" required>
    <span id="nameError" class="error"></span>
    <br><br>

    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required>
    <span id="emailError" class="error"></span>
    <br><br>

    <label for="phone">Phone Number:</label>
    <input type="tel" id="phone" name="phone" required>
    <span id="phoneError" class="error"></span

