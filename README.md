<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Yves</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

<header>
    <h1>WELCOME TO Yves Website</h1>
    <button id="themeBtn">Switch Theme</button>
</header>

<main>
    <section class="box">
        <h2>Click the Image </h2>
        <img id="mainImage" src="c:\Users\GADGET STORE\Desktop\ALL\WEB\assignment 1\image\img1.png" alt="Image" class="interactive-img">
    </section>
    <section class="box">
        <h2>Sign In Form</h2>
        <form id="loginForm">
            <label>Email:</label>
            <input type="text" id="email">
            <label>Password:</label>
            <input type="password" id="password">
            <button type="button" id="submitBtn">Submit</button>
            <p id="formMessage"></p>
        </form>
    </section>
    <script>
    document.getElementById("themeBtn").onclick = function () {
        document.body.classList.toggle("dark");
    };
    document.getElementById("mainImage").onclick = function () {
        this.src = this.src.includes("img1.png") ? "images/img2.png" : "images/img1.png";
    }
    document.getElementById("textBtn").onclick = function () {
        document.getElementById("changeText").innerText = "The text has been changed successfully!";
    };
    document.getElementById("submitBtn").onclick = function () {
        const email = document.getElementById("email").value.trim();
        const password = document.getElementById("password").value.trim();
        const message = document.getElementById("formMessage");
        if (email === "" || password === "") {
            message.style.color = "red";
            message.innerText = "⚠ All fields are required.";
        } else if (!email.includes("@")) {
            message.style.color = "red";
            message.innerText = "⚠ Enter a valid email.";
        } else if (password.length < 6) {
            message.style.color = "red";
            message.innerText = "⚠ Password must be at least 6 characters.";
        } else {
            message.style.color = "green";
            message.innerText = "✅ Login successful!";
        }
    };
</script>
</main>
</body>
<style>
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background: white;
    color: black;
}

header {
    background: #4A90E2;
    padding: 20px;
    text-align: center;
    color: white;
}

.box {
    width: 80%;
    margin: 20px auto;
    padding: 20px;
    background: #fdfafa;
    border-radius: 10px;
}

.interactive-img {
    width: 250px;
    cursor: pointer;
    border-radius: 10px;
}

button {
    padding: 10px 20px;
    margin-top: 10px;
    cursor: pointer;
}

button:hover {
    background: #4A90E2;
    color: white;
}

.dark {
    background: #b1abab;
    color: rgb(31, 28, 28);
}

.dark header {
    background: rgb(143, 138, 138);
}
</style>
    <section class="box">
        <h2>Sign In Form</h2>
        <form id="loginForm">
            <label>Email:</label>
            <input type="text" id="email" placeholder="Enter your email">
            <label>Password:</label>
            <input type="password" id="password" placeholder="Enter your password">
            <button type="button" id="submitBtn">Submit</button>
            <p id="formMessage"></p>
        </form>
    </section>
    <section class="box">
        <h2>Change Text Button</h2>
        <p id="changeText">This text will change when you click the button.</p>
        <button id="textBtn">Change Text</button>
    </section>

</main>
</body>
</html>
