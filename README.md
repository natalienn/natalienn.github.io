# Welcome to My Business Website

## About Us

Welcome to our business! We offer a variety of classes for individuals looking to learn and grow.

## Class Options

- [Class 1](#class-1)
- [Class 2](#class-2)
- [Class 3](#class-3)

## Class 1

To sign up for Class 1, please fill out the form below:

<form id="class1SignupForm" class="classSignupForm" style="display: none;">
  <h2>Class 1 Signup Form</h2>
  <label for="class1FullName">Full Name:</label>
  <input type="text" id="class1FullName" name="class1FullName" required><br><br>
  
  <label for="class1Email">Email:</label>
  <input type="email" id="class1Email" name="class1Email" required><br><br>
  
  <input type="submit" value="Sign Up">
</form>

## Class 2

To sign up for Class 2, please fill out the form below:

<form id="class2SignupForm" class="classSignupForm" style="display: none;">
  <h2>Class 2 Signup Form</h2>
  <label for="class2FullName">Full Name:</label>
  <input type="text" id="class2FullName" name="class2FullName" required><br><br>
  
  <label for="class2Email">Email:</label>
  <input type="email" id="class2Email" name="class2Email" required><br><br>
  
  <input type="submit" value="Sign Up">
</form>

## Class 3

To sign up for Class 3, please fill out the form below:

<form id="class3SignupForm" class="classSignupForm" style="display: none;">
  <h2>Class 3 Signup Form</h2>
  <label for="class3FullName">Full Name:</label>
  <input type="text" id="class3FullName" name="class3FullName" required><br><br>
  
  <label for="class3Email">Email:</label>
  <input type="email" id="class3Email" name="class3Email" required><br><br>
  
  <input type="submit" value="Sign Up">
</form>

<script>
document.querySelectorAll("a[href^='#']").forEach(function(anchor) {
  anchor.addEventListener("click", function(event) {
    event.preventDefault(); // Prevent the default anchor behavior
    
    // Hide all class signup forms
    document.querySelectorAll(".classSignupForm").forEach(function(form) {
      form.style.display = "none";
    });
    
    // Show the selected class signup form
    var classId = this.getAttribute("href").substring(1);
    var signupForm = document.getElementById(classId + "SignupForm");
    if (signupForm) {
      signupForm.style.display = "block";
    }
  });
});

document.querySelectorAll(".classSignupForm").forEach(function(form) {
  form.addEventListener("submit", function(event) {
    event.preventDefault(); // Prevent the form from submitting
    
    // Get form data
    var formData = new FormData(form);
    var fullName = formData.get("fullName");
    var email = formData.get("email");
    var className = form.id.replace("SignupForm", ""); // Get class name from form ID
    
    // You can now do something with the form data, such as sending it to a server
    console.log("Class:", className);
    console.log("Full Name:", fullName);
    console.log("Email:", email);
    
    // For demonstration purposes, let's just display an alert message
    alert("Thank you for signing up for " + className + "!");
  });
});
</script>
