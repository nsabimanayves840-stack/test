
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Yves</title>
    <style>
        body { font-family: Arial; margin: 0; padding: 0; background: white; color: rgb(146, 141, 141); }
        header { background: #6d6d6e; padding: 20px; text-align: center; color: white; }
        .box { width: 80%; margin: 20px auto; padding: 20px; background: #1a1919; border-radius: 10px; text-align: center; }
        .interactive-img { width: 250px; cursor: pointer; border-radius: 10px; transition: transform 0.3s; }
        .interactive-img:hover { transform: scale(1.05); }
        button { padding: 10px 20px; margin-top: 10px; cursor: pointer; border: none; border-radius: 5px; transition: background 0.3s, color 0.3s; }
        button:hover { background: #4A90E2; color: white; }
        input[type="text"], input[type="password"] { padding: 10px; width: 80%; margin: 5px 0 15px 0; border-radius: 5px; border: 1px solid #000000; }
        .dark { background: #6d6a6a; color: white; }
        .dark header { background: #bdafaf; }
    </style>
</head>
<body>

<header>
    <h1>WELCOME TO Yves Website</h1>
    <button id="themeBtn">Switch Theme</button>
</header>

<main>

   
    <section class="box">
        <h2>Click the Image to Change It</h2>
        <img id="mainImage" src="c:\Users\GADGET STORE\Desktop\image\img1.png" alt="Interactive Image" class="interactive-img">
        <p>Click the image above to switch it.</p>
    </section>

    
    <section class="box">
        <h2>Sign In Form</h2>
        <form id="loginForm">
            <label>Email:</label>
            <input type="text" id="email" placeholder="Enter your email">
            <p><label>Password:</label>
            <input type="password" id="password" placeholder="Enter your password"></p>
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

<script>
  
    document.getElementById("themeBtn").onclick = function () {
        document.body.classList.toggle("dark");
    };

    document.getElementById("mainImage").onclick = function () {
        this.src = this.src.includes("img1.png") ? "images/img2.png" : "images/img1.png";
    };

   
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

</body>
</html>
