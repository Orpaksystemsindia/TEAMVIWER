<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Welcome To Orpak Software and SOPs</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        body {
            background: linear-gradient(to bottom right, #e0f7fa, #80deea);
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 20px;
            color: #333;
            display: flex;
            flex-direction: column;
            align-items: center;
            position: relative;
            min-height: 100vh;
        }
        h1 {
            color: #007BFF;
            text-align: center;
            margin-bottom: 20px;
            font-size: 2.5em;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.2);
        }
        .maker-name {
            position: absolute;
            top: 20px;
            left: 20px;
            font-size: 0.8em;
            color: #007BFF;
        }
        .login-container {
            text-align: center;
            margin-bottom: 20px;
            transition: all 0.3s ease;
            background-color: #ffffff;
            border-radius: 12px;
            padding: 20px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
            width: 100%;
            max-width: 400px;
        }
        input[type="text"], input[type="password"] {
            width: calc(100% - 22px);
            padding: 10px;
            margin: 5px 0;
            border-radius: 4px;
            border: 1px solid #ccc;
            font-size: 1em;
            transition: border 0.3s;
        }
        input[type="text"]:focus, input[type="password"]:focus {
            border-color: #007BFF;
            outline: none;
        }
        button {
            background-color: #007BFF;
            color: white;
            border: none;
            border-radius: 4px;
            padding: 10px;
            cursor: pointer;
            width: 100%;
            font-size: 1em;
            transition: background-color 0.3s ease, transform 0.3s;
        }
        button:hover {
            background-color: #0056b3;
            transform: scale(1.05);
        }
        .critical-probe-snaps {
            display: none; /* Initially hidden */
            background-color: #ffffff;
            border: 1px solid #ccc;
            border-radius: 12px;
            padding: 10px;
            margin: 20px 0;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
            width: 100%;
            max-width: 400px; /* Small size */
            font-size: 0.9em; /* Smaller font size */
            position: relative; /* Position relative for stacking context */
        }
        .toggle-arrow {
            cursor: pointer;
            color: #007BFF;
            font-size: 1.5em;
            margin-bottom: 10px;
        }
        .notice-board, .updates-board {
            display: none;
            background-color: rgba(255, 215, 0, 0.9);
            border: 2px solid #FFA500;
            border-radius: 12px;
            padding: 20px;
            margin: 20px 0;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
            width: 250px;
            position: absolute;
            text-align: left;
            color: red;
            overflow: hidden;
        }
        .notice-title, .update-title {
            color: #007BFF;
            font-size: 1.5em;
            margin-bottom: 10px;
        }
        .notice-content {
            height: auto;
            overflow: visible;
        }
        .notice {
            padding: 5px 0;
            display: none;
        }
        .notice-board {
            left: 20px;
            top: 100px;
        }
        .updates-board {
            right: 20px;
            top: 100px;
            background-color: rgba(173, 216, 230, 0.9);
        }
        .box {
            background-color: #ffffff;
            border: 1px solid #ccc;
            border-radius: 12px;
            padding: 20px;
            margin: 20px 0;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
            width: 100%;
            max-width: 800px;
        }
        h2 {
            color: #007BFF;
            text-align: center;
            margin-bottom: 15px;
            font-size: 1.8em;
        }
        .software-container, .mandatory-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
            gap: 15px;
            margin: 0 auto;
        }
        .software-item, .mandatory-item {
            border-radius: 10px;
            padding: 15px;
            text-align: center;
            transition: transform 0.3s, box-shadow 0.3s;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
            height: 100px;
        }
        .software-item:nth-child(1) { background-color: #4CAF50; }
        .software-item:nth-child(2) { background-color: #2196F3; }
        .software-item:nth-child(3) { background-color: #FF9800; }
        .software-item:nth-child(4) { background-color: #F44336; }
        .software-item:nth-child(5) { background-color: #8E24AA; }
        .software-item:nth-child(6) { background-color: #009688; }
        .software-item:nth-child(7) { background-color: #3F51B5; }
        .software-item:nth-child(8) { background-color: #FF5722; }

        .mandatory-item:nth-child(1) { background-color: #FF4081; }
        .mandatory-item:nth-child(2) { background-color: #FFC107; }
        .mandatory-item:nth-child(3) { background-color: #FF4081; }
        .mandatory-item:nth-child(4) { background-color: #FFC107; }

        .software-item:hover, .mandatory-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.2);
        }
        a {
            text-decoration: none;
            color: white;
            font-weight: bold;
        }
        a:hover {
            text-decoration: underline;
        }
        .floating-buttons {
            position: absolute;
            top: 20px;
            right: 20px;
        }
        .logout-button {
            background-color: transparent;
            border: none;
            cursor: pointer;
            font-size: 24px;
            color: #dc3545;
        }
        .highlight {
            color: #dc3545;
            transform: scale(1.2);
            transition: transform 0.3s ease, color 0.3s ease;
        }

        /* Popup Styles */
        .popup {
            display: none; /* Hidden by default */
            position: fixed;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5); /* Black background with transparency */
            justify-content: center;
            align-items: center;
        }
        .popup-content {
            background-color: white;
            border-radius: 12px;
            padding: 20px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
            text-align: center;
        }
        .popup input[type="text"], .popup input[type="password"] {
            margin: 10px 0;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
            width: 80%;
        }
        .popup button {
            margin-top: 10px;
        }
        .result-box {
            margin-top: 20px;
            padding: 10px;
            border: 1px solid #007BFF;
            border-radius: 4px;
            background-color: #f0f8ff; /* Light blue background for result box */
            color: #007BFF; /* Blue text color */
        }

        @media (max-width: 600px) {
            h1 {
                font-size: 1.8em;
            }
            .login-container, .notice-board, .updates-board, .box, .critical-probe-snaps {
                width: 90%;
                max-width: none;
            }
            .software-item, .mandatory-item {
                height: auto;
                padding: 10px;
            }
        }
    </style>
</head>
<body>
    <div class="maker-name">KoushalStar</div>
    <h1>Welcome To Orpak Software and SOPs</h1>

    <div class="critical-probe-snaps" id="criticalProbeSnaps">
        <div class="toggle-arrow" id="toggleArrow">
            <i class="fas fa-chevron-down"></i> Critical ATG Probe Snaps
        </div>
        <div class="critical-probe-content" id="criticalProbeContent" style="display: none;">
            <ol>
                <li>Electrical audit to be done for AC input inside ATG Console</li>
                <li>For barrier cards DC input to console and DC output to probes to be checked.</li>
                <li>For barrier communication port volt to be checked at in and out for Probe both.</li>
                <li>Communication Volt from ATG console and Master WGT separately to be checked.</li>
                <li>Probe connection inside Console as well as Tank chamber to be checked as per standard installation & direct probe checking method to be applied.</li>
                <li>Connection for earthing and shield cables to be properly tightened and thimble/LUX may be used to connect properly with Console body.</li>
                <li>Probe installation inside tank chamber.</li>
                <li>Distance between probe and STP or Dicant Pipe (305 mm or 610mm)</li>
                <li>Product, Density & Water Floats with magnet ring to be checked properly</li>
                <li>Probe Serial Number and manufacture year to be checked for warranty claim replacement</li>
                <li>TLS 4B - Check Probe Sr. No. it’s correct or 000000. (In Setup then Devices)</li>
                <li>In Diagnostics/Probe/Overview menu check Probe data for send and received.</li>
                <li>Inventory report for last 15 days to be downloaded</li>
                <li>Alarm Report for last 15 days to be downloaded for any Probe behavior</li>
                <li>Event log report for last 15 days to correlate with Alarm report and FCC Uptime</li>
                <li>Tank Truck Receipts report if any dummy receipt captured or post decantation what was the max height captured for product</li>
            </ol>
        </div>
    </div>

    <div class="login-container" id="loginContainer">
        <h2>Login</h2>
        <input type="text" id="username" placeholder="Username" required>
        <input type="password" id="password" placeholder="Password" required>
        <button id="loginButton">Login</button>
        <div id="loginMessage" style="color: red;"></div>
    </div>

    <div class="notice-board" id="noticeBoard">
        <div class="notice-title">Notice Board</div>
        <div class="notice-content">
            <div class="notice">1. HPCL ITPS Verification With L1 & HPCL ITPS Transaction History.</div>
            <div class="notice">2. HPCL, IOCL, BPCL And NAYARA New Software Need to Update On All Sites.</div>
            <div class="notice">3. HPCL MS To Petrol e20 Conversion need to Update in FCC.</div>
            <div class="notice">4. Take All Sites Access Details with ID And Password.</div>
            <div class="notice">5. Need Upgradation of all OIL Comp.</div>
        </div>
    </div>

    <div class="updates-board" id="updatesBoard">
        <div class="update-title">Upcoming Updates</div>
        <div class="update" id="update1">1. Critical Material Rank</div>
        <div class="update" id="update2">2. UPS Repair SOP's</div>
        <div class="update" id="update3">3. Software Status</div>
        <div class="update" id="update4">4. Engineer Assessments Test Ranking Status</div>
    </div>

    <div class="box" id="mainContent" style="display: none;">
        <h2>Available Software</h2>
        <div class="software-container">
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1OwDG1YIGIvk-pfmb5kl-7idfv1X3mXvt?usp=sharing" target="_blank">HPCL Software</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1CvT6pZt1PVo6U6yVOUEY5Yv-jOGY2nHX?usp=sharing" target="_blank">IOCL Software</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/12oC5wVAhaAyjAI6CFtulWTa0Qkd5nczo?usp=sharing" target="_blank">BPCL Software</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1o63SEJXOrQ8daxBY4EsKDks1hpd2BeFM?usp=sharing" target="_blank">NAYARA Software</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1P_YxkZNUyZJGODZW7fzApLt5WGnwx4fd?usp=sharing" target="_blank">HPCL Related SOP's</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1M2cLs3brGxSojrgMUSTfBBQe-NOfaanw?usp=sharing" target="_blank">IOCL Related SOP's</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/17FpBNsMpH9fkd7ClquCwoNda4anmoVvp?usp=sharing" target="_blank">BPCL Related SOP's</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1KxyMnv-yZe76tsQoEdrbRIEnmmJjPvCi?usp=sharing" target="_blank">NAYARA Related SOP's</a></div>
        </div>

        <h2>Mandatory Activities</h2>
        <div class="mandatory-container">
            <div class="mandatory-item" id="hpclVendor"> 
                <a href="https://drive.google.com/file/d/1ac418hLzLG4-FYYqEtTccZMU1E1X-dpW/view?usp=sharing" target="_blank">Critical Part Validation</a>
            </div>
            <div class="mandatory-item" id="bpclBLNo">
                <a href="#" id="teamViewerId">TeamViewer Id</a>
            </div>
            <div class="mandatory-item" id="hpclItpsVendor"> <a href="#">HPCL itps vender</a></div>
            <div class="mandatory-item" id="bpclBL"> <a href="#">BPCL BL No.</a></div>
        </div>
    </div>

    <div class="box" id="sopContent" style="display: none;">
        <h2>SOP Documents</h2>
        <div class="software-container">
            <div class="software-item"><a href="https://drive.google.com/drive/folders/159TMvskuKCBtS8GO1aXBGuOwrshjUsTV?usp=sharing" target="_blank">ATG/TLS SOP's</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1f5LqNqxcK_7NEiLXltGfJgeyDetjgh3d?usp=sharing" target="_blank">FCC SOP's</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1LgFJ-SO3uis1HuR4ah-vp-GbUnDU4822?usp=sharing" target="_blank">Router SOP's</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1cBQoa0E0H2v3vfYdjCws4PjIp-swGDMZ?usp=sharing" target="_blank">UPS & SPD</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1dajJOPIuZ6Qw9aKhlxL9uCN46VbhmR54?usp=sharing" target="_blank">Du Sop's</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1NqINZsXMvxN3bR0QFkRXrrqaQGggxWKH?usp=sharing" target="_blank">Price Pole</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1XsLTkpFTm19NSTTh-e2lkDbQuo7g1LWE?usp=sharing" target="_blank">OS & Siteomat Installation & Configuration</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1C6sb2hNDdt0RLSkmN7yw36iwYcIx86ZY?usp=sharing" target="_blank">Wireless Gateway Terminal</a></div>
            <div class="software-item"><a href="https://example.com/sop9.pdf" target="_blank">SOP Document 9</a></div>
            <div class="software-item"><a href="https://example.com/sop10.pdf" target="_blank">SOP Document 10</a></div>
        </div>
    </div>

    <div class="floating-buttons">
        <button id="loginIcon" title="Login"><i class="fas fa-sign-in-alt"></i></button>
        <button class="logout-button" id="logoutIcon" title="Logout"><i class="fas fa-sign-out-alt"></i></button>
    </div>

    <!-- New Popup for TeamViewer Input -->
    <div class="popup" id="teamViewerPopup">
        <div class="popup-content">
            <h2>Enter TeamViewer Details</h2>
            <input type="text" id="roCodeInput" placeholder="Ro Code" required>
            <input type="text" id="roNameInput" placeholder="Ro Name" required>
            <input type="text" id="teamViewerIdInput" placeholder="TeamViewer Id" required>
            <input type="password" id="teamViewerPassInput" placeholder="TeamViewer Password" required>
            <input type="password" id="adminPassInput" placeholder="Admin Password" required>
            <button id="submitTeamViewerDetails">Submit</button>
            <button id="closeTeamViewerPopup">Close</button>
            <div class="result-box" id="teamViewerResultMessage" style="display: none;"></div>
        </div>
    </div>

    <!-- Popup for Ro Code Entry -->
    <div class="popup" id="roCodePopup">
        <div class="popup-content">
            <h2>Enter Ro Code</h2>
            <input type="text" id="roCode" placeholder="Ro Code" required>
            <button id="submitRoCode">Submit</button>
            <button id="closePopup">Close</button>
            <div class="result-box" id="resultMessage" style="display: none;"></div>
        </div>
    </div>

    <script>
        const loginButton = document.getElementById('loginButton');
        const loginIcon = document.getElementById('loginIcon');
        const logoutIcon = document.getElementById('logoutIcon');
        const mainContent = document.getElementById('mainContent');
        const sopContent = document.getElementById('sopContent');
        const loginContainer = document.getElementById('loginContainer');
        const loginMessage = document.getElementById('loginMessage');
        const noticeBoard = document.getElementById('noticeBoard');
        const updatesBoard = document.getElementById('updatesBoard');
        const notices = document.querySelectorAll('.notice');
        const criticalProbeSnaps = document.getElementById('criticalProbeSnaps');
        const criticalProbeContent = document.getElementById('criticalProbeContent');
        const toggleArrow = document.getElementById('toggleArrow');

        // Popup functionality for TeamViewer Id
        const teamViewerPopup = document.getElementById('teamViewerPopup');
        const teamViewerIdLink = document.getElementById('teamViewerId');
        const closeTeamViewerPopup = document.getElementById('closeTeamViewerPopup');
        const submitTeamViewerDetails = document.getElementById('submitTeamViewerDetails');
        const teamViewerResultMessage = document.getElementById('teamViewerResultMessage');

        // Show the TeamViewer popup when the link is clicked
        teamViewerIdLink.onclick = function() {
            teamViewerPopup.style.display = 'flex';
        };

        // Close the TeamViewer popup
        closeTeamViewerPopup.onclick = function() {
            teamViewerPopup.style.display = 'none';
            // Clear input fields
            document.getElementById('roCodeInput').value = '';
            document.getElementById('roNameInput').value = '';
            document.getElementById('teamViewerIdInput').value = '';
            document.getElementById('teamViewerPassInput').value = '';
            document.getElementById('adminPassInput').value = '';
            teamViewerResultMessage.style.display = 'none'; // Hide result message box
        };

        // Handle submission of TeamViewer details
        submitTeamViewerDetails.onclick = function() {
            const roCode = document.getElementById('roCodeInput').value;
            const roName = document.getElementById('roNameInput').value;
            const teamViewerId = document.getElementById('teamViewerIdInput').value;
            const teamViewerPass = document.getElementById('teamViewerPassInput').value;
            const adminPass = document.getElementById('adminPassInput').value;

            if (roCode && roName && teamViewerId && teamViewerPass && adminPass) {
                fetch('https://script.google.com/macros/s/AKfycbxE8qSguwe_0RHkAM0BokcWSKG2Ic-xVBmwVAoB5M2Z0EI7vV9AzbvkAk8fuWA-gcs/exec', {
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/x-www-form-urlencoded'
                    },
                    body: new URLSearchParams({
                        roCode: roCode,
                        roName: roName,
                        teamViewerId: teamViewerId,
                        teamViewerPass: teamViewerPass,
                        adminPass: adminPass
                    })
                })
                .then(response => response.json())
                .then(data => {
                    teamViewerResultMessage.style.display = 'block';
                    teamViewerResultMessage.textContent = data.result; // Assuming the Apps Script returns a JSON object with a 'result' key
                    teamViewerResultMessage.style.color = 'green';
                })
                .catch(error => {
                    console.error('Error:', error);
                    teamViewerResultMessage.style.display = 'block';
                    teamViewerResultMessage.textContent = 'An error occurred. Please try again.';
                    teamViewerResultMessage.style.color = 'red';
                });
            } else {
                teamViewerResultMessage.style.display = 'block';
                teamViewerResultMessage.textContent = 'Please fill in all fields.';
                teamViewerResultMessage.style.color = 'red';
            }
        };

        // Existing Popup functionality for Ro Code Entry
        const roCodePopup = document.getElementById('roCodePopup');
        const submitRoCode = document.getElementById('submitRoCode');
        const closePopup = document.getElementById('closePopup');
        const resultMessage = document.getElementById('resultMessage');

        const data = [
            { "RoCode": "12345", "Result": "Passed" },
            { "RoCode": "67890", "Result": "Failed" },
            { "RoCode": "54321", "Result": "Pending" }
        ];

        document.getElementById('hpclItpsVendor').onclick = function() {
            roCodePopup.style.display = 'flex';
        };

        closePopup.onclick = function() {
            roCodePopup.style.display = 'none';
            document.getElementById('roCode').value = ''; // Clear input
            resultMessage.style.display = 'none'; // Hide result message box
        };

        submitRoCode.onclick = function() {
            const roCode = document.getElementById('roCode').value;
            const result = data.find(item => item.RoCode === roCode);
            if (result) {
                resultMessage.style.display = 'block'; // Show result box
                resultMessage.textContent = `Result: ${result.Result}`;
                resultMessage.style.border = '1px solid #007BFF'; // Optional: Add border
            } else {
                resultMessage.style.display = 'block'; // Show result box
                resultMessage.textContent = 'Ro Code not found.';
                resultMessage.style.border = '1px solid red'; // Optional: Add border
            }
        };

        toggleArrow.onclick = function() {
            const isVisible = criticalProbeContent.style.display === 'block';
            criticalProbeContent.style.display = isVisible ? 'none' : 'block';
            toggleArrow.innerHTML = isVisible ? '<i class="fas fa-chevron-down"></i> Critical ATG Probe Snaps' : '<i class="fas fa-chevron-up"></i> Critical ATG Probe Snaps';
        };

        loginButton.addEventListener('click', function () {
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;

            // Check credentials
            if (username === 'Orpak' && password === 'U$4F7dc8') {
                loginMessage.textContent = '';
                loginContainer.style.display = 'none';
                mainContent.style.display = 'block';
                sopContent.style.display = 'block';
                noticeBoard.style.display = 'block';
                updatesBoard.style.display = 'block';
                criticalProbeSnaps.style.display = 'none'; // Hide the critical probe snaps box
                loginIcon.style.display = 'none';
                logoutIcon.style.display = 'block';
                logoutIcon.classList.add('highlight');

                // Show all notices immediately
                notices.forEach(notice => {
                    notice.style.display = 'block';
                });
            } else {
                loginMessage.textContent = 'Invalid username or password.';
            }
        });

        logoutIcon.addEventListener('click', function () {
            loginContainer.style.display = 'block';
            mainContent.style.display = 'none';
            sopContent.style.display = 'none';
            noticeBoard.style.display = 'none';
            updatesBoard.style.display = 'none';
            criticalProbeSnaps.style.display = 'block'; // Show the critical probe snaps box again
            document.getElementById('username').value = '';
            document.getElementById('password').value = '';
            loginIcon.style.display = 'block';
            logoutIcon.style.display = 'none';
            logoutIcon.classList.remove('highlight');

            // Reset notices display
            notices.forEach(notice => {
                notice.style.display = 'none';
            });
        });
    </script>
</body>
</html>
