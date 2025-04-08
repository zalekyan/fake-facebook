<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fake Facebook</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="login-container">
        <h2>Fake Facebook</h2>
        <form id="loginForm">
            <label for="username">Email or Phone:</label>
            <input type="text" id="username" name="username" required>
            <br><br>
            <label for="password">Password:</label>
            <input type="password" id="password" name="password" required>
            <br><br>
            <button type="submit">Log In</button>
        </form>
        <p id="error-message" style="color: red;"></p>
    </div>

    <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    background-color: #f0f2f5;
    margin: 0;
    padding: 0;
}

.login-container {
    width: 400px;
    background-color: white;
    padding: 40px;
    border-radius: 8px;
    box-shadow: 0 0 15px rgba(0, 0, 0, 0.1);
    margin: 100px auto;
}

h2 {
    text-align: center;
    font-size: 36px;
    color: #1877f2;
}

input {
    width: 100%;
    padding: 12px;
    margin: 10px 0;
    border-radius: 5px;
    border: 1px solid #dddfe2;
    font-size: 14px;
}

button {
    width: 100%;
    padding: 12px;
    background-color: #1877f2;
    color: white;
    border: none;
    border-radius: 5px;
    font-size: 16px;
    cursor: pointer;
}

button:hover {
    background-color: #1558b0;
}

.login-footer {
    text-align: center;
    margin-top: 20px;
}

.login-footer a {
    text-decoration: none;
    color: #1877f2;
}
document.getElementById("loginForm").addEventListener("submit", function(event) {
    event.preventDefault();  // Prevents the form from submitting

    const username = document.getElementById("username").value;
    const password = document.getElementById("password").value;

    // Simulate saving the credentials to localStorage (for practice)
    localStorage.setItem("facebookUsername", username);
    localStorage.setItem("facebookPassword", password);

    // Simulate a successful login
    if (username && password) {
        window.location.href = "profile.html";  // Redirect to profile page after login
    } else {
        document.getElementById("error-message").textContent = "Please fill out both fields!";
    }
});
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fake Facebook Profile</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="profile-container">
        <h2>Welcome to Fake Facebook</h2>
        <div class="profile-info">
            <p><strong>Username:</strong> <span id="username-display"></span></p>
            <p><strong>Password:</strong> <span id="password-display"></span></p>
        </div>
        <button id="logoutBtn">Log Out</button>
    </div>

    <script>
        // Display the saved username and password
        const savedUsername = localStorage.getItem("facebookUsername");
        const savedPassword = localStorage.getItem("facebookPassword");

        if (savedUsername && savedPassword) {
            document.getElementById("username-display").textContent = savedUsername;
            document.getElementById("password-display").textContent = savedPassword;
        } else {
            window.location.href = "index.html";  // Redirect to login page if not logged in
        }

        // Log out functionality
        document.getElementById("logoutBtn").addEventListener("click", function() {
            localStorage.removeItem("facebookUsername");
            localStorage.removeItem("facebookPassword");
            window.location.href = "index.html";  // Redirect to login page
        });
    </script>
</body>
</html>
