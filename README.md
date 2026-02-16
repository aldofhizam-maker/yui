<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <title>Login</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: #f1f3f4;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        .login-card {
            background: #fff;
            height: 300px;
            width: 960px;
            padding: 90px;
            border-radius: 10px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.15);
            text-align: center;
        }

        .logo {
            font-size: 32px;
            font-weight: bold;
            color: #1a73e8;
            margin-bottom: 10px;
        }

        h2 {
            font-weight: normal;
            margin-bottom: 20px;
        }

        input {
            width: 100%;
            padding: 12px;
            margin: 10px 0;
            border: 1px solid #dadce0;
            border-radius: 4px;
            font-size: 14px;
        }

        input:focus {
            outline: none;
            border-color: #1a73e8;
        }

        button {
            width: 100%;
            padding: 12px;
            background: #1a73e8;
            color: white;
            border: none;
            border-radius: 4px;
            font-size: 15px;
            cursor: pointer;
            margin-top: 15px;
        }

        button:hover {
            background: #1557b0;
        }

        .error {
            color: red;
            margin-top: 10px;
            font-size: 13px;
        }
    </style>
</head>
<body>

<div class="login-card">
    <div class="logo">Login</div>
    <h2>Masuk ke Webside</h2>

    <input type="text" id="username" placeholder="Username">
    <input type="password" id="password" placeholder="Password">

    <button onclick="login()">Masuk</button>
    <div class="error" id="error"></div>
</div>

<script>
    function login() {
        const username = document.getElementById("username").value;
        const password = document.getElementById("password").value;
        const error = document.getElementById("error");

        // akun contoh
        const validUser = "Islam";
        const validPass = "blue723149";

        if (username === "" || password === "") {
            error.textContent = "Username dan password wajib diisi!";
        } else if (username === validUser && password === validPass) {
            // simpan status login
            localStorage.setItem("login", "true");
            localStorage.setItem("user", username);

            // pindah halaman
            window.location.href = "g.html";
        } else {
            error.textContent = "Username atau password salah!";
        }
    }
</script>

</body>
</html>

