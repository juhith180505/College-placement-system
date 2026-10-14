# College-placement-system
college placement

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>College Placement Portal</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }

        body {
            min-height: 100vh;
            background: linear-gradient(135deg, #0f172a, #1d4ed8);
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 25px;
        }

        .container {
            width: 100%;
            max-width: 1000px;
            min-height: 550px;
            display: grid;
            grid-template-columns: 1fr 1fr;
            background: white;
            border-radius: 18px;
            overflow: hidden;
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.3);
        }

        .left-panel {
            background: linear-gradient(145deg, #172554, #2563eb);
            color: white;
            padding: 45px 35px;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        .left-panel h1 {
            font-size: 32px;
            margin-bottom: 18px;
        }

        .left-panel p {
            color: #dbeafe;
            line-height: 1.7;
            margin-bottom: 28px;
        }

        .branches {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 12px;
        }

        .branch {
            padding: 14px 10px;
            border: 1px solid rgba(255, 255, 255, 0.3);
            border-radius: 9px;
            background: rgba(255, 255, 255, 0.1);
            text-align: center;
            cursor: pointer;
            transition: 0.3s;
        }

        .branch:hover,
        .branch.active {
            background: white;
            color: #1d4ed8;
            transform: translateY(-2px);
        }

        .branch strong {
            display: block;
            font-size: 16px;
            margin-bottom: 5px;
        }

        .branch span {
            font-size: 12px;
        }

        .right-panel {
            padding: 45px 40px;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        .right-panel h2 {
            color: #172554;
            font-size: 28px;
            margin-bottom: 10px;
        }

        .subtitle {
            color: #64748b;
            margin-bottom: 28px;
            font-size: 14px;
        }

        label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
            color: #334155;
            font-size: 14px;
        }

        input, select {
            width: 100%;
            padding: 13px;
            border: 1px solid #cbd5e1;
            border-radius: 8px;
            margin-bottom: 20px;
            outline: none;
            font-size: 14px;
            background: white;
        }

        input:focus, select:focus {
            border-color: #2563eb;
            box-shadow: 0 0 0 3px #dbeafe;
        }

        .login-btn {
            width: 100%;
            padding: 14px;
            background: #2563eb;
            color: white;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            transition: 0.3s;
        }

        .login-btn:hover {
            background: #1d4ed8;
        }

        .register {
            text-align: center;
            margin-top: 22px;
            color: #64748b;
            font-size: 14px;
        }

        .register a {
            color: #2563eb;
            text-decoration: none;
            font-weight: bold;
        }

        .footer {
            text-align: center;
            margin-top: 25px;
            font-size: 12px;
            color: #94a3b8;
        }

        #message {
            font-size: 13px;
            margin-top: 15px;
            text-align: center;
        }

        @media (max-width: 700px) {
            .container {
                grid-template-columns: 1fr;
            }

            .left-panel, .right-panel {
                padding: 30px 25px;
            }

            .left-panel h1 {
                font-size: 26px;
            }
        }
    </style>
</head>

<body>

<div class="container">

    <!-- Left Side: Branch Selection -->
    <div class="left-panel">
        <h1>College Placement Portal</h1>

        <p>
            Welcome to the campus recruitment portal.
            Select your engineering branch and log in
            to explore placement opportunities.
        </p>

        <div class="branches">
            <div class="branch active" data-branch="CSE">
                <strong>CSE</strong>
                <span>Computer Science</span>
            </div>

            <div class="branch" data-branch="ECE">
                <strong>ECE</strong>
                <span>Electronics</span>
            </div>

            <div class="branch" data-branch="EEE">
                <strong>EEE</strong>
                <span>Electrical</span>
            </div>

            <div class="branch" data-branch="MECH">
                <strong>MECH</strong>
                <span>Mechanical</span>
            </div>

            <div class="branch" data-branch="CIVIL">
                <strong>CIVIL</strong>
                <span>Civil Engineering</span>
            </div>

            <div class="branch" data-branch="IT">
                <strong>IT</strong>
                <span>Information Technology</span>
            </div>

            <div class="branch" data-branch="AIML">
                <strong>AI & ML</strong>
                <span>Artificial Intelligence</span>
            </div>

            <div class="branch" data-branch="DS">
                <strong>DS</strong>
                <span>Data Science</span>
            </div>
        </div>
    </div>

    <!-- Right Side: Login Form -->
    <div class="right-panel">
        <h2>Student Login</h2>
        <p class="subtitle">
            Sign in to access your placement dashboard.
        </p>

        <form id="loginForm">
            <label for="studentId">Student ID</label>
            <input
                type="text"
                id="studentId"
                placeholder="Enter your student ID"
                required
            >

            <label for="email">Email Address</label>
            <input
                type="email"
                id="email"
                placeholder="Enter your college email"
                required
            >

            <label for="branch">Engineering Branch</label>
            <select id="branch" required>
                <option value="CSE">Computer Science (CSE)</option>
                <option value="ECE">Electronics (ECE)</option>
                <option value="EEE">Electrical (EEE)</option>
                <option value="MECH">Mechanical (MECH)</option>
                <option value="CIVIL">Civil (CIVIL)</option>
                <option value="IT">Information Technology (IT)</option>
                <option value="AIML">Artificial Intelligence & ML</option>
                <option value="DS">Data Science</option>
            </select>

            <label for="password">Password</label>
            <input
                type="password"
                id="password"
                placeholder="Enter your password"
                required
            >

            <button type="submit" class="login-btn">
                Login to Portal
            </button>

            <p id="message" role="status"></p>
        </form>

        <div class="register">
            New student? <a href="#" id="registerLink">Register here</a>
        </div>

        <div class="footer">
            © 2026 College Placement Cell
        </div>
    </div>

</div>

<script>
    const branchCards = document.querySelectorAll(".branch");
    const branchSelect = document.getElementById("branch");

    // Select branch by clicking its card
    branchCards.forEach(card => {
        card.addEventListener("click", function () {
            branchCards.forEach(item =>
                item.classList.remove("active")
            );

            this.classList.add("active");
            branchSelect.value = this.dataset.branch;
        });
    });

    // Also update the selected card when dropdown changes
    branchSelect.addEventListener("change", function () {
        branchCards.forEach(card => {
            card.classList.toggle(
                "active",
                card.dataset.branch === this.value
            );
        });
    });

    // Demo login form
    document.getElementById("loginForm").addEventListener(
        "submit", function (event) {
            event.preventDefault();

            const studentId =
                document.getElementById("studentId").value.trim();

            const email =
                document.getElementById("email").value.trim();

            const password =
                document.getElementById("password").value;

            const branch = branchSelect.value;
            const message = document.getElementById("message");

            if (!studentId || !email || !password) {
                message.style.color = "red";
                message.textContent = "Please fill in all fields.";
                return;
            }

            message.style.color = "#15803d";
            message.textContent =
                "Demo login submitted for " + branch +
                ". Connect a backend to authenticate your account.";
        }
    );

    document.getElementById("registerLink").addEventListener(
        "click", function (event) {
            event.preventDefault();
            alert("Connect this link to your student registration page.");
        }
    );
</script>

</body>
</html>
