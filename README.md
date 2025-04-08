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
