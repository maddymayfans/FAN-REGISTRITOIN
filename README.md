<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Maddy May Super Fans</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        .container {
            background-color: #ffffff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            width: 400px;
            text-align: center;
        }
        .hidden {
            display: none;
        }
        input[type="text"], input[type="email"], input[type="password"], input[type="date"], input[type="tel"], input[type="file"], textarea {
            width: 90%;
            padding: 10px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        select {
            width: 92%;
            padding: 10px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        button {
            padding: 10px 20px;
            background-color: #007BFF;
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin-top: 10px;
        }
        button:hover {
            background-color: #0056b3;
        }
        .alert {
            color: red;
            margin-top: 10px;
        }
        .profile-info {
            text-align: left;
            margin-bottom: 20px;
        }
        .profile-info img {
            max-width: 100%;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <div id="signup-page" class="container">
        <h2>Sign up to support your favorite creators</h2>
        <input type="text" id="signup-name" placeholder="Name" required>
        <input type="email" id="signup-email" placeholder="Email" required>
        <input type="password" id="signup-password" placeholder="Password" required>
        <button onclick="signup()">Sign Up</button>
        <p>Already have an account? <a href="#" onclick="showPage('login-page')">Log in</a></p>
        <p class="alert hidden" id="signup-alert"></p>
    </div>

    <div id="login-page" class="container hidden">
        <h2>Log in</h2>
        <input type="email" id="login-email" placeholder="Email" required>
        <input type="password" id="login-password" placeholder="Password" required>
        <button onclick="login()">Log In</button>
        <p>Don't have an account? <a href="#" onclick="showPage('signup-page')">Sign up</a></p>
        <p class="alert hidden" id="login-alert"></p>
    </div>

    <div id="thank-you-page" class="container hidden">
        <h2>Thank You</h2>
        <p>I just wanted to take a moment to say thank you to all my amazing fans! Your support means the world to me, and I couldn't do this without you. You all are the best, and I'm so grateful for each and every one of you.</p>
        <p>Lots of love, Maddy May</p>
        <button onclick="showPage('info-page')">Next</button>
    </div>

    <div id="info-page" class="container hidden">
        <h2>Membership Information</h2>
        <input type="text" id="full-name" placeholder="Full Name" required>
        <input type="date" id="dob" placeholder="Date of Birth" required>
        <select id="gender">
            <option value="" disabled selected>Gender</option>
            <option value="Male">Male</option>
            <option value="Female">Female</option>
            <option value="Other">Other</option>
        </select>
        <input type="tel" id="contact-number" placeholder="Contact Number" required>
        <input type="email" id="info-email" placeholder="Email Address" required>
        <input type="text" id="mailing-address" placeholder="Mailing Address" required>
        <input type="file" id="profile-picture" accept="image/*" required>
        <h3>Membership Details</h3>
        <select id="membership-type">
            <option value="Regular">Regular</option>
            <option value="Premium">Premium</option>
        </select>
        <select id="communication-method">
            <option value="" disabled selected>Preferred Method of Communication</option>
            <option value="Email">Email</option>
            <option value="Phone">Phone</option>
            <option value="Mail">Mail</option>
        </select>
        <button onclick="submitInfo()">Submit</button>
        <p class="alert hidden" id="info-alert"></p>
    </div>

    <div id="fan-club-info-page" class="container hidden">
        <h2>Fan Club-Specific Information</h2>
        <textarea id="how-hear" placeholder="How did you hear about the fan club?" rows="3" required></textarea>
        <textarea id="hopes" placeholder="What do you hope to gain from joining the fan club?" rows="3" required></textarea>
        <textarea id="suggestions" placeholder="Any suggestions for activities or events?" rows="3" required></textarea>
        <button onclick="submitFanClubInfo()">Submit</button>
        <p class="alert hidden" id="fan-club-info-alert"></p>
    </div>

    <div id="superfans-page" class="container hidden">
        <h2>❤️‍🔥What my superfans grant ⬇️</h2>
        <p>📍Daily New Content (over 500 sexy & nudes pics including vids you get immediate access to upon subscription)</p>
        <p>📍B/G and Solo content (PPV)</p>
        <p>📌I sell my panties</p>
        <p>📍Twerk videos</p>
        <p>❣️Video call</p>
        <p>❤️Hookup</p>
        <p>🥰 Unlimited talk</p>
        <p>❣️Masturbating video</p>
        <p>❣️Random meeting</p>
        <p>📌One on one messaging 24/7 with you</p>
        <button onclick="showPage('subscription-page')">Next</button>
    </div>

    <div id="subscription-page" class="container hidden">
        <h2>Profile Information</h2>
        <div class="profile-info">
            <p><strong>Full Name:</strong> <span id="profile-full-name"></span></p>
            <p><strong>Date of Birth:</strong> <span id="profile-dob"></span></p>
            <p><strong>Gender:</strong> <span id="profile-gender"></span></p>
            <p><strong>Contact Number:</strong> <span id="profile-contact-number"></span></p>
            <p><strong>Email Address:</strong> <span id="profile-email"></span></p>
            <p><strong>Mailing Address:</strong> <span id="profile-mailing-address"></span></p>
            <p><strong>Membership Type:</strong> <span id="profile-membership-type"></span></p>
            <p><strong>Preferred Method of Communication:</strong> <span id="profile-communication-method"></span></p>
            <img id="profile-picture-img" src="#" alt="Profile Picture">
        </div>
        <p>To proceed with your subscription, please confirm your agreement to the subscription amount.</p>
        <p>
            <label>
                <input type="checkbox" id="subscription-agreement">
                By checking this box, you acknowledge and agree to the annual subscription fee of $100.
            </label>
        </p>
        <button onclick="confirmSubscription()">Next</button>
        <p class="alert hidden" id="subscription-alert"></p>
    </div>

    <div id="payment-page" class="container hidden">
        <h2>Payment Mode</h2>
        <select id="payment-method" onchange="displayPaymentDetails()">
            <option value="" disabled selected>Select Payment Method</option>
            <option value="cashapp">Cash App</option>
            <option value="paypal">PayPal</option>
            <option value="crypto">Crypto</option>
        </select>
        <p id="payment-details" class="hidden"></p>
    </div>

    <script>
        let users = [];

        function showPage(pageId) {
            const pages = document.querySelectorAll('.container');
            pages.forEach(page => page.classList.add('hidden'));
            document.getElementById(pageId).classList.remove('hidden');
        }

        function signup() {
            const name = document.getElementById('signup-name').value;
            const email = document.getElementById('signup-email').value;
            const password = document.getElementById('signup-password').value;

            if (name && email && password) {
                users.push({ name, email, password });
                alert('Signup successful');
                showPage('login-page');
                document.getElementById('signup-alert').classList.add('hidden');
            } else {
                document.getElementById('signup-alert').innerText = 'All fields are required.';
                document.getElementById('signup-alert').classList.remove('hidden');
            }
        }

        function login() {
            const email = document.getElementById('login-email').value;
            const password = document.getElementById('login-password').value;
            const user = users.find(user => user.email === email && user.password === password);

            if (user) {
                alert('Login successful');
                showPage('thank-you-page');
                document.getElementById('login-alert').classList.add('hidden');
            } else {
                document.getElementById('login-alert').innerText = 'Incorrect email or password.';
                document.getElementById('login-alert').classList.remove('hidden');
            }
        }

        function submitInfo() {
            const fullName = document.getElementById('full-name').value;
            const dob = document.getElementById('dob').value;
            const gender = document.getElementById('gender').value;
            const contactNumber = document.getElementById('contact-number').value;
            const email = document.getElementById('info-email').value;
            const mailingAddress = document.getElementById('mailing-address').value;
            const profilePicture = document.getElementById('profile-picture').files[0];
            const membershipType = document.getElementById('membership-type').value;
            const communicationMethod = document.getElementById('communication-method').value;

            if (fullName && dob && gender && contactNumber && email && mailingAddress && profilePicture && membershipType && communicationMethod) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    document.getElementById('profile-full-name').innerText = fullName;
                    document.getElementById('profile-dob').innerText = dob;
                    document.getElementById('profile-gender').innerText = gender;
                    document.getElementById('profile-contact-number').innerText = contactNumber;
                    document.getElementById('profile-email').innerText = email;
                    document.getElementById('profile-mailing-address').innerText = mailingAddress;
                    document.getElementById('profile-membership-type').innerText = membershipType;
                    document.getElementById('profile-communication-method').innerText = communicationMethod;
                    document.getElementById('profile-picture-img').src = e.target.result;
                }
                reader.readAsDataURL(profilePicture);

                showPage('fan-club-info-page');
                document.getElementById('info-alert').classList.add('hidden');
            } else {
                document.getElementById('info-alert').innerText = 'All fields are required.';
                document.getElementById('info-alert').classList.remove('hidden');
            }
        }

        function submitFanClubInfo() {
            const howHear = document.getElementById('how-hear').value;
            const hopes = document.getElementById('hopes').value;
            const suggestions = document.getElementById('suggestions').value;

            if (howHear && hopes && suggestions) {
                alert('Fan club information submitted successfully');
                showPage('superfans-page');
                document.getElementById('fan-club-info-alert').classList.add('hidden');
            } else {
                document.getElementById('fan-club-info-alert').innerText = 'All fields are required.';
                document.getElementById('fan-club-info-alert').classList.remove('hidden');
            }
        }

        function confirmSubscription() {
            const agreement = document.getElementById('subscription-agreement').checked;

            if (agreement) {
                alert('Subscription confirmed. Further instructions will be sent to your email.');
                showPage('payment-page');
                document.getElementById('subscription-alert').classList.add('hidden');
            } else {
                document.getElementById('subscription-alert').innerText = 'You must agree to the subscription fee.';
                document.getElementById('subscription-alert').classList.remove('hidden');
            }
        }

        function displayPaymentDetails() {
            const paymentMethod = document.getElementById('payment-method').value;
            let details = '';

            switch (paymentMethod) {
                case 'cashapp':
                    details = '$SoutherFusion';
                    break;
                case 'paypal':
                    details = 'M.howe30@yahoo.com';
                    break;
                case 'crypto':
                    details = '13CVQWXmyHA1YgcH9JDUq7BWkZGfcdKEoN';
                    break;
            }

            document.getElementById('payment-details').innerText = details;
            document.getElementById('payment-details').classList.remove('hidden');
        }
    </script>
</body>
</html>
