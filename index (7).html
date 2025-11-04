<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Clan Management Portal (Online)</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&family=Roboto:wght@400;500&display=swap" rel="stylesheet">
    
    <script src="https://www.gstatic.com/firebasejs/8.10.0/firebase-app.js"></script>
    <script src="https://www.gstatic.com/firebasejs/8.10.0/firebase-firestore.js"></script>
    <script src="https://www.gstatic.com/firebasejs/8.10.0/firebase-storage.js"></script>
    
    <style>
        /* --- 1. Global Styles & Theme --- */
        :root {
            --color-primary: #007bff;
            --color-primary-dark: #0056b3;
            --color-white: #ffffff;
            --color-light-gray: #f4f7f6;
            --color-medium-gray: #ddd;
            --color-dark-gray: #555;
            --color-text: #333;
            --color-leader: #ffd700; /* Gold */
            --color-coleader: #c0c0c0; /* Silver */
            --color-me-message-bg: #dcf8c6; /* WhatsApp "me" green */
            --shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
            --radius: 8px;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Poppins', 'Roboto', sans-serif;
            background-color: var(--color-light-gray);
            color: var(--color-text);
            line-height: 1.6;
        }

        #app {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            flex-direction: column;
            min-height: 100vh;
        }

        .container {
            width: 100%;
            padding: 20px;
        }

        .page {
            display: none; /* Hidden by default */
            flex-direction: column;
            animation: fadeIn 0.3s ease-in-out;
        }

        .page.active {
            display: flex;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* --- 2. Header & Navigation --- */
        #header-bar {
            background-color: var(--color-white);
            box-shadow: var(--shadow);
            padding: 15px 20px;
            position: sticky;
            top: 0;
            z-index: 100;
        }

        #header-logged-out {
            text-align: center;
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--color-primary-dark);
            text-transform: uppercase;
        }

        #header-logged-in {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .profile-info {
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .profile-avatar {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--color-primary), var(--color-primary-dark));
            color: var(--color-white);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
            font-weight: 600;
            text-transform: uppercase;
            border: 2px solid var(--color-white);
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }

        .profile-name-role span {
            display: block;
        }

        .profile-name {
            font-weight: 600;
            font-size: 1.1rem;
        }

        .profile-role {
            font-size: 0.9rem;
            color: var(--color-dark-gray);
            text-transform: capitalize;
        }

        .header-nav .btn {
            margin-left: 10px;
        }

        /* --- 3. Buttons & Forms --- */
        .btn {
            padding: 10px 18px;
            border-radius: var(--radius);
            border: none;
            cursor: pointer;
            font-family: 'Poppins', sans-serif;
            font-weight: 600;
            font-size: 0.95rem;
            transition: all 0.2s ease;
            text-decoration: none;
            display: inline-block;
            text-align: center;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--color-primary), var(--color-primary-dark));
            color: var(--color-white);
        }

        .btn-primary:hover {
            opacity: 0.9;
            box-shadow: 0 4px 8px rgba(0, 123, 255, 0.2);
        }

        .btn-secondary {
            background-color: #6c757d;
            color: var(--color-white);
        }

        .btn-danger {
            background-color: #dc3545;
            color: var(--color-white);
        }

        .btn-success {
            background-color: #28a745;
            color: var(--color-white);
        }

        .btn-warning {
            background-color: #ffc107;
            color: var(--color-text);
        }

        .btn-icon {
            padding: 8px 10px;
            font-size: 1.1rem;
        }
        
        .btn-sm {
            padding: 3px 6px;
            font-size: 0.75rem;
        }

        .form-group {
            margin-bottom: 15px;
        }

        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: 600;
        }

        .form-control {
            width: 100%;
            padding: 12px;
            border: 1px solid var(--color-medium-gray);
            border-radius: var(--radius);
            font-family: 'Roboto', sans-serif;
            font-size: 1rem;
        }
        
        select.form-control[multiple] {
            height: auto;
            padding: 10px;
        }

        textarea.form-control {
            min-height: 120px;
            resize: vertical;
        }

        .card {
            background-color: var(--color-white);
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            padding: 25px;
            margin-bottom: 20px;
        }

        .card-title {
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 20px;
            color: var(--color-primary-dark);
            border-bottom: 2px solid var(--color-light-gray);
            padding-bottom: 10px;
        }

        .alert {
            padding: 15px;
            margin-bottom: 20px;
            border-radius: var(--radius);
            font-weight: 500;
        }
        .alert-danger { background-color: #f8d7da; color: #721c24; border: 1px solid #f5c6cb; }
        .alert-success { background-color: #d4edda; color: #155724; border: 1px solid #c3e6cb; }
        .alert-info { background-color: #d1ecf1; color: #0c5460; border: 1px solid #bee5eb; }

        /* --- 4. Page-Specific Styles --- */

        /* Login & Register */
        #login-page, #register-page {
            justify-content: center;
            padding-top: 40px;
        }
        .form-container {
            max-width: 500px;
            width: 100%;
            margin: 0 auto;
        }
        .form-container .card-title {
            text-align: center;
        }
        .form-footer {
            text-align: center;
            margin-top: 20px;
        }
        .form-footer a {
            color: var(--color-primary);
            font-weight: 600;
            cursor: pointer;
        }

        /* Home Page */
        .home-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }

        .home-button {
            background: linear-gradient(135deg, var(--color-primary), var(--color-primary-dark));
            color: var(--color-white);
            padding: 20px;
            border-radius: var(--radius);
            text-align: center;
            font-size: 1.2rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.2s ease;
            box-shadow: 0 4px 8px rgba(0, 123, 255, 0.1);
        }
        .home-button:hover {
            transform: translateY(-5px);
            box-shadow: 0 6px 12px rgba(0, 123, 255, 0.2);
        }
        .home-button.leader-btn {
            background: linear-gradient(135deg, #ffc107, #e0a800);
            color: #333;
        }
        .cabinet-list {
            margin-top: 30px;
        }
        .cabinet-list h3 {
            margin-bottom: 10px;
        }
        .cabinet-list span {
            display: inline-block;
            background-color: #e9ecef;
            padding: 5px 10px;
            border-radius: 5px;
            margin-right: 5px;
            font-weight: 500;
        }

        /* Assembly (Chat) */
        .assembly-layout {
            display: flex;
            gap: 20px;
            height: calc(100vh - 160px);
        }
        .player-list-sidebar {
            flex: 0 0 250px;
            background-color: var(--color-white);
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            overflow-y: auto;
            padding: 15px;
        }
        .player-list-item {
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 8px;
            border-bottom: 1px solid var(--color-light-gray);
        }
        .player-list-item:last-child {
            border-bottom: none;
        }
        .player-list-item .avatar {
            width: 30px;
            height: 30px;
            font-size: 0.9rem;
        }
        .player-list-item .name { font-weight: 600; }
        .player-list-item .role { font-size: 0.8rem; color: var(--color-dark-gray); }
        .chat-main {
            flex: 1;
            display: flex;
            flex-direction: column;
            background-color: var(--color-white);
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            overflow: hidden;
        }
        
        /* ★★★ NEW: Pinned Message ★★★ */
        .pinned-message {
            padding: 10px 15px;
            background-color: #fff8e1;
            border-bottom: 1px solid #ffeeba;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 0.9rem;
        }
        .pinned-message-content {
            font-weight: 500;
            overflow: hidden;
            text-overflow: ellipsis;
            white-space: nowrap;
        }
        
        .chat-box {
            flex: 1;
            padding: 20px;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
        }
        
        /* ★★★ NEW: Chat Message Actions (Pin/Delete) ★★★ */
        .message-actions {
            display: none; /* Hide by default */
            margin-left: 10px;
            margin-right: 10px;
            align-self: center;
        }
        .chat-message:hover .message-actions {
            display: block; /* Show on hover */
        }
        .message-actions .btn-icon {
            padding: 2px 5px;
            font-size: 0.8rem;
            background: none;
            border: none;
            color: var(--color-dark-gray);
            cursor: pointer;
        }
        .message-actions .btn-icon:hover {
            color: var(--color-primary);
        }

        .chat-message {
            max-width: 80%;
            margin-bottom: 15px;
            display: flex;
            gap: 10px;
        }
        .chat-message .avatar {
            width: 35px;
            height: 35px;
            font-size: 1rem;
            flex-shrink: 0;
        }
        .message-content {
            border-radius: var(--radius);
            padding: 10px 15px;
        }
        
        /* ★★★ NEW: "Me" (Right) vs "Other" (Left) styles ★★★ */
        .chat-message.other {
            flex-direction: row; /* Default */
            align-self: flex-start;
        }
        .chat-message.me {
            flex-direction: row-reverse; /* My messages on the right */
            align-self: flex-end;
        }
        .chat-message.me .message-content {
            background-color: var(--color-me-message-bg);
        }
        .chat-message.other .message-content {
            background-color: var(--color-light-gray);
        }
        
        .message-sender {
            font-weight: 600;
            font-size: 0.9rem;
            margin-bottom: 5px;
        }
        .message-text {
            word-wrap: break-word;
        }
        .message-timestamp {
            font-size: 0.75rem;
            color: var(--color-dark-gray);
            margin-top: 5px;
        }
        
        /* ★★★ NEW: Media (Image/Video) in chat ★★★ */
        .message-media {
            margin-top: 10px;
        }
        .message-media img,
        .message-media video {
            max-width: 100%;
            border-radius: var(--radius);
            max-height: 300px;
            cursor: pointer;
        }
        .message-media-download {
            display: inline-block;
            padding: 8px 12px;
            background-color: var(--color-primary);
            color: var(--color-white);
            border-radius: var(--radius);
            text-decoration: none;
            font-weight: 600;
        }
        
        /* Special Assembly Styles (Overrides) */
        .message-leader .message-content {
            background-color: #fff8e1; /* Light gold */
            border: 1px solid var(--color-leader);
        }
        .message-leader .message-sender {
            color: #b8860b; /* Dark Gold */
            font-weight: 700;
        }
        .message-coleader .message-content {
            background-color: #f8f9fa; /* Light silver */
            border: 1px solid var(--color-coleader);
        }
        .message-coleader .message-sender {
            color: #5a6268; /* Dark Silver */
            font-weight: 700;
        }
        
        /* Override for "me" special roles */
        .chat-message.me.message-leader .message-content,
        .chat-message.me.message-coleader .message-content {
             background-color: var(--color-me-message-bg); /* Keep "me" green */
        }


        /* --- ★★★ MODIFIED CHAT CONTROLS ★★★ --- */
        .chat-controls-container {
            padding: 10px 20px 0 20px;
            background-color: #fdfdfd;
            border-top: 1px solid var(--color-light-gray);
            display: flex;
            gap: 15px;
            align-items: center;
            flex-wrap: wrap; /* For responsiveness */
        }
        .chat-controls-container label {
            font-weight: 600;
            font-size: 0.9rem;
            margin-right: 5px;
        }
        .chat-controls-container select {
            padding: 5px;
            border-radius: var(--radius);
            border: 1px solid var(--color-medium-gray);
            font-family: 'Roboto', sans-serif;
        }
        .chat-controls-container input[type="color"] {
            width: 40px;
            height: 30px;
            padding: 0 2px;
            border: 1px solid var(--color-medium-gray);
            border-radius: 4px;
            cursor: pointer;
        }

        /* ★★★ NEW: File Input Wrapper ★★★ */
        .file-input-wrapper {
            position: relative;
            overflow: hidden;
            display: inline-block;
        }
        .file-input-wrapper .btn {
            padding: 10px 12px;
            font-size: 1.1rem;
        }
        .file-input-wrapper input[type=file] {
            font-size: 100px;
            position: absolute;
            left: 0;
            top: 0;
            opacity: 0;
            cursor: pointer;
        }

        .chat-input-form {
            display: flex;
            padding: 10px 20px 20px 20px;
            background-color: #fdfdfd;
            align-items: center; /* Align file button */
        }
        
        .chat-input-form input[type="text"] {
            flex: 1;
            margin: 0;
            border-right: 0;
            border-top-right-radius: 0;
            border-bottom-right-radius: 0;
        }
        .chat-input-form .btn { /* Submit button */
            border-top-left-radius: 0;
            border-bottom-left-radius: 0;
        }

        /* Rules, Notices, Drafts */
        .item-list .item-card {
            background-color: var(--color-white);
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            padding: 20px;
            margin-bottom: 15px;
            position: relative;
        }
        .item-card h3 {
            color: var(--color-primary-dark);
            margin-bottom: 10px;
        }
        .item-card p {
            margin-bottom: 10px;
        }
        .item-meta {
            font-size: 0.85rem;
            color: var(--color-dark-gray);
        }
        .item-card .btn {
            margin-top: 10px;
        }
        .leader-action-btn {
            position: absolute;
            top: 15px;
            right: 15px;
        }

        /* Draft Detail Page */
        .draft-status-bar {
            padding: 15px;
            border-radius: var(--radius);
            font-weight: 600;
            text-align: center;
            margin-bottom: 20px;
            font-size: 1.1rem;
        }
        .status-advice { background-color: #fff3cd; color: #856404; }
        .status-voting { background-color: #d1ecf1; color: #0c5460; }
        .status-passed { background-color: #d4edda; color: #155724; }
        .status-failed { background-color: #f8d7da; color: #721c24; }
        .status-canceled { background-color: #e2e3e5; color: #383d41; }
        .status-active { background-color: #cce5ff; color: #004085; }

        .vote-options {
            display: flex;
            gap: 15px;
            margin: 20px 0;
        }
        .vote-options .btn {
            flex: 1;
            font-size: 1.1rem;
            padding: 15px;
        }
        
        .vote-results {
            margin-top: 20px;
        }
        .vote-summary {
            background-color: var(--color-light-gray);
            padding: 15px;
            border-radius: var(--radius);
            font-weight: 500;
        }

        .advice-section .advice-item {
            border-bottom: 1px solid var(--color-light-gray);
            padding: 10px 0;
        }
        .advice-section .advice-item:last-child {
            border-bottom: none;
        }
        .advice-sender {
            font-weight: 600;
            font-size: 0.9rem;
        }

        /* Leader Dashboard & Player Lists */
        .dashboard-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
        }
        .dashboard-button {
            display: block;
            background-color: var(--color-white);
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            padding: 25px;
            text-align: center;
            font-size: 1.2rem;
            font-weight: 600;
            color: var(--color-primary-dark);
            text-decoration: none;
            transition: all 0.2s ease;
        }
        .dashboard-button:hover {
            transform: translateY(-5px);
            box-shadow: 0 6px 16px rgba(0, 0, 0, 0.08);
        }
        
        .player-table-container {
            overflow-x: auto;
        }
        .player-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }
        .player-table th, .player-table td {
            padding: 12px 15px;
            border-bottom: 1px solid var(--color-medium-gray);
            text-align: left;
        }
        .player-table th {
            background-color: var(--color-light-gray);
            font-weight: 700;
        }
        .player-table td .btn {
            padding: 5px 8px;
            font-size: 0.85rem;
            margin-right: 5px;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .assembly-layout {
                flex-direction: column;
                height: auto;
            }
            .player-list-sidebar {
                flex: 0 0 auto;
                max-height: 200px;
            }
            .chat-main {
                height: 60vh;
            }
            .header-nav {
                display: flex;
                flex-direction: column;
                gap: 5px;
                align-items: flex-end;
            }
            .profile-name-role {
                display: none;
            }
        }

    </style>
</head>
<body>

    <div id="app">
        <header id="header-bar">
            <div id="header-logged-out">
                PLEASE LOGIN
            </div>
            <div id="header-logged-in" style="display: none;">
                <div class="profile-info">
                    <div id="user-avatar" class="profile-avatar"></div>
                    <div class="profile-name-role">
                        <span id="user-name" class="profile-name"></span>
                        <span id="user-role" class="profile-role"></span>
                    </div>
                </div>
                <nav class="header-nav">
                    <button class="btn btn-primary" data-action="show-home">🏠 Home</button>
                    <button id="logout-button" class="btn btn-secondary" data-action="logout">Logout</button>
                </nav>
            </div>
        </header>

        <main class="container">
            <div id="login-page" class="page active">
                <div class="form-container">
                    <div class="card">
                        <h2 class="card-title">Clan Portal Login</h2>
                        <div id="login-error" class="alert alert-danger" style="display: none;"></div>
                        <form id="login-form">
                            <div class="form-group">
                                <label for="login-id">Player ID</label>
                                <input type="text" id="login-id" class="form-control" required>
                            </div>
                            <div class="form-group">
                                <label for="login-password">Password</label>
                                <input type="password" id="login-password" class="form-control" required>
                            </div>
                            <button type="submit" class="btn btn-primary" style="width: 100%;">Login</button>
                        </form>
                        <div class="form-footer">
                            Don't have an account? <a data-action="show-register">Register here</a>
                        </div>
                    </div>
                </div>
            </div>

            <div id="register-page" class="page">
                <div class="form-container">
                    <div class="card">
                        <h2 class="card-title">New Player Registration</h2>
                        <form id="register-form">
                            <div class="form-group">
                                <label for="reg-player-id">Player ID (User ID)</label>
                                <input type="text" id="reg-player-id" class="form-control" required>
                            </div>
                            <div class="form-group">
                                <label for="reg-player-name">Player Name</label>
                                <input type="text" id="reg-player-name" class="form-control" required>
                            </div>
                            <div class="form-group">
                                <label for="reg-clan-name">Clan Name</label>
                                <input type="text" id="reg-clan-name" class="form-control" required>
                            </div>
                            <div class="form-group">
                                <label for="reg-clan-id">Clan ID</label>
                                <input type="text" id="reg-clan-id" class="form-control" required>
                            </div>
                            <div class="form-group">
                                <label for="reg-dob">Date of Birth</label>
                                <input type="date" id="reg-dob" class="form-control" required>
                            </div>
                            <div class="form-group">
                                <label for="reg-country">Country</label>
                                <select id="reg-country" class="form-control" required>
                                    <option value="">-- Select Country --</option>
                                    <option value="India">India</option>
                                    <option value="China">China</option>
                                    <option value="Vietnam">Vietnam</option>
                                    <option value="Indonesia">Indonesia</option>
                                    <option value="Japan">Japan</option>
                                    <option value="South Korea">South Korea</option>
                                    <option value="Philippines">Philippines</option>
                                    <option value="Thailand">Thailand</option>
                                    <option value="Malaysia">Malaysia</option>
                                    <option value="Singapore">Singapore</option>
                                    <option value="Other">Other (Asia)</option>
                                </select>
                            </div>
                            <div class="form-group" id="india-states-group" style="display: none;">
                                <label for="reg-india-state">State / Union Territory</label>
                                <select id="reg-india-state" class="form-control">
                                    <option value="">-- Select State/UT --</option>
                                    <option value="Andhra Pradesh">Andhra Pradesh</option>
                                    <option value="Arunachal Pradesh">Arunachal Pradesh</option>
                                    <option value="Assam">Assam</option>
                                    <option value="Bihar">Bihar</option>
                                    <option value="Chhattisgarh">Chhattisgarh</option>
                                    <option value="Goa">Goa</option>
                                    <option value="Gujarat">Gujarat</option>
                                    <option value="Haryana">Haryana</option>
                                    <option value="Himachal Pradesh">Himachal Pradesh</option>
                                    <option value="Jharkhand">Jharkhand</option>
                                    <option value="Karnataka">Karnataka</option>
                                    <option value="Kerala">Kerala</option>
                                    <option value="Madhya Pradesh">Madhya Pradesh</option>
                                    <option value="Maharashtra">Maharashtra</option>
                                    <option value="Manipur">Manipur</option>
                                    <option value="Meghalaya">Meghalaya</option>
                                    <option value="Mizoram">Mizoram</option>
                                    <option value="Nagaland">Nagaland</option>
                                    <option value="Odisha">Odisha</option>
                                    <option value="Punjab">Punjab</option>
                                    <option value="Rajasthan">Rajasthan</option>
                                    <option value="Sikkim">Sikkim</option>
                                    <option value="Tamil Nadu">Tamil Nadu</option>
                                    <option value="Telangana">Telangana</option>
                                    <option value="Tripura">Tripura</option>
                                    <option value="Uttar Pradesh">Uttar Pradesh</option>
                                    <option value="Uttarakhand">Uttarakhand</option>
                                    <option value="West Bengal">West Bengal</option>
                                    <option value="Andaman and Nicobar">Andaman and Nicobar Islands</option>
                                    <option value="Chandigarh">Chandigarh</option>
                                    <option value="Dadra and Nagar Haveli">Dadra and Nagar Haveli and Daman and Diu</option>
                                    <option value="Delhi">Delhi</option>
                                    <option value="Jammu and Kashmir">Jammu and Kashmir</option>
                                    <option value="Ladakh">Ladakh</option>
                                    <option value="Lakshadweeep">Lakshadweeep</option>
                                    <option value="Puducherry">Puducherry</option>
                                </select>
                            </div>
                            <div class="form-group" id="other-region-group" style="display: none;">
                                <label for="reg-other-region">Region / State</label>
                                <input type="text" id="reg-other-region" class="form-control">
                            </div>
                            
                            <div class="form-group">
                                <label for="reg-lang-primary">Primary Language (Compulsory)</label>
                                <select id="reg-lang-primary" class="form-control" required disabled>
                                    <option value="English" selected>English</option>
                                </select>
                            </div>
                            <div class="form-group">
                                <label for="reg-lang-secondary">Secondary Languages (Select at least 1)</label>
                                <select id="reg-lang-secondary" class="form-control" multiple size="8">
                                    <option value="Mandarin Chinese">Mandarin Chinese</option>
                                    <option value="Hindi">Hindi</option>
                                    <option value="Bengali">Bengali</option>
                                    <option value="Japanese">Japanese</option>
                                    <option value="Vietnamese">Vietnamese</option>
                                    <option value="Korean">Korean</option>
                                    <option value="Tamil">Tamil</option>
                                    <option value="Urdu">Urdu</option>
                                    <option value="Javanese">Javanese</option>
                                    <option value="Telugu">Telugu</option>
                                    <option value="Turkish">Turkish</option>
                                    <option value="Marathi">Marathi</option>
                                    <option value="Thai">Thai</option>
                                    <option value="Malay/Indonesian">Malay/Indonesian</option>
                                    <option value="Filipino (Tagalog)">Filipino (Tagalog)</option>
                                </select>
                                <small>Hold Ctrl (or Cmd on Mac) to select multiple.</small>
                            </div>
                            <div class="form-group">
                                <label for="reg-role">Select Your Role</label>
                                <select id="reg-role" class="form-control" required>
                                    <option value="Member" selected>Member</option>
                                    <option value="Elder">Elder</option>
                                    <option value="Co-Leader">Co-Leader</option>
                                </select>
                                <small>Leader role cannot be registered.</small>
                            </div>
                            
                            <button type="submit" class="btn btn-primary" style="width: 100%;">Register</button>
                        </form>
                        <div class="form-footer">
                            Already have an account? <a data-action="show-login">Login here</a>
                        </div>
                    </div>
                </div>
            </div>

            <div id="home-page" class="page">
                <div class="home-grid" id="home-buttons-grid">
                    </div>
                <div class="card cabinet-list">
                    <h3>👑 Cabinet Players</h3>
                    <div id="cabinet-player-list">
                        </div>
                </div>
            </div>
            
            <div id="general-assembly-page" class="page">
                <div class="assembly-layout">
                    <div class="player-list-sidebar">
                        <h3>All Players</h3>
                        <div id="ga-player-list"></div>
                    </div>
                    <div class="chat-main">
                        <div class="card-title" style="padding: 15px 20px; margin: 0; border-radius: 0;">🗣 General Assembly</div>
                        
                        <div id="ga-pinned-message" class="pinned-message" style="display: none;"></div>

                        <div class="chat-box" id="ga-chat-box">
                            </div>
                        
                        <div id="ga-controls-container" class="chat-controls-container">
                            </div>

                        <form id="ga-chat-form" class="chat-input-form">
                            <div class="file-input-wrapper">
                                <button type="button" class="btn btn-secondary">📎</button>
                                <input type="file" id="ga-file-input" accept="image/*,video/*">
                            </div>
                            <input type="text" id="ga-chat-input" class="form-control" placeholder="Type your message..." autocomplete="off">
                            <button type="submit" class="btn btn-primary">Send</button>
                        </form>
                    </div>
                </div>
            </div>

            <div id="special-assembly-page" class="page">
                 <div class="assembly-layout">
                    <div class="player-list-sidebar">
                        <h3>Leadership</h3>
                        <div id="sa-player-list"></div>
                    </div>
                    <div class="chat-main">
                        <div class="card-title" style="padding: 15px 20px; margin: 0; border-radius: 0;">👑 Special Assembly</div>
                        
                        <div id="sa-pinned-message" class="pinned-message" style="display: none;"></div>
                        
                        <div class="chat-box" id="sa-chat-box">
                            </div>
                        
                        <div id="sa-controls-container" class="chat-controls-container">
                            </div>

                        <form id="sa-chat-form" class="chat-input-form">
                            <div class="file-input-wrapper">
                                <button type="button" class="btn btn-secondary">📎</button>
                                <input type="file" id="sa-file-input" accept="image/*,video/*">
                            </div>
                            <input type="text" id="sa-chat-input" class="form-control" placeholder="Type your message..." autocomplete="off">
                            <button type="submit" class="btn btn-primary">Post</button>
                        </form>
                        <div id="sa-post-error" class="alert alert-danger" style="display: none; margin: 20px;">Only Leader and Co-Leaders can post here.</div>
                    </div>
                </div>
            </div>

            <div id="notice-board-page" class="page">
                <div class="card">
                    <h2 class="card-title">📢 Notice Board</h2>
                    <div id="notice-board-post-form" style="display: none;">
                        <h3>Post a New Notice</h3>
                        <form id="new-notice-form">
                            <div class="form-group">
                                <label for="notice-title">Title</label>
                                <input type="text" id="notice-title" class="form-control" required>
                            </div>
                            <div class="form-group">
                                <label for="notice-content">Content</label>
                                <textarea id="notice-content" class="form-control" required></textarea>
                            </div>
                            <button type="submit" class="btn btn-primary">Post Notice</button>
                        </form>
                    </div>
                    <div class="item-list" id="notice-list" style="margin-top: 20px;">
                        </div>
                </div>
            </div>

            <div id="drafts-voting-page" class="page">
                <div class="card">
                    <h2 class="card-title">⚖️ Drafts & Voting</h2>
                    <div class="item-list" id="drafts-list">
                        </div>
                </div>
            </div>

            <div id="draft-detail-page" class="page">
                <div class="card">
                    <button class="btn btn-secondary" data-action="show-drafts-voting" style="margin-bottom: 20px;">&larr; Back to Drafts</button>
                    <h2 class="card-title" id="draft-detail-title"></h2>
                    <div class="draft-status-bar" id="draft-detail-status"></div>
                    <div id="draft-detail-timer" class="alert alert-info"></div>
                    <p id="draft-detail-description"></p>

                    <div id="draft-results-section" style="display: none;">
                        <h3>Vote Results</h3>
                        <div class="vote-results">
                            <pre id="draft-vote-summary" class="vote-summary"></pre>
                        </div>
                        <div id="draft-leader-activation-section" style="display: none; margin-top: 20px;">
                            <button id="draft-activate-btn" class="btn btn-success" style="width: 100%; padding: 15px; font-size: 1.2rem;">Notify & Activate Law</button>
                        </div>
                    </div>

                    <div id="draft-voting-section" style="display: none;">
                        <h3>Cast Your Vote</h3>
                        <div id="draft-vote-error" class="alert alert-danger" style="display: none;"></div>
                        <div class="vote-options">
                            <button class="btn btn-success" data-action="draft-vote" data-vote="yes">✅ Yes</button>
                            <button class="btn btn-danger" data-action="draft-vote" data-vote="no">❌ No</button>
                            <button class="btn btn-secondary" data-action="draft-vote" data-vote="absent">⚪ Absent</button>
                        </div>
                    </div>
                    
                    <div id="draft-advice-section" style="display: none;">
                        <hr style="margin: 20px 0;">
                        <div class="advice-section">
                            <h3>Public Advice</h3>
                            <div id="draft-advice-list"></div>
                        </div>
                        <form id="draft-advice-form" style="margin-top: 20px;">
                            <div class="form-group">
                                <label for="draft-advice-input">Submit Your Advice</label>
                                <textarea id="draft-advice-input" class="form-control" required></textarea>
                            </div>
                            <button type="submit" class="btn btn-primary">Submit Advice</button>
                        </form>
                    </div>
                </div>
            </div>

            <div id="leader-chat-page" class="page">
                <div class="card form-container">
                    <h2 class="card-title">💬 Leader Chat (Private Message)</h2>
                    <div class="alert alert-info">Your message will be sent privately to the Leader.</div>
                    <form id="leader-chat-form">
                        <div class="form-group">
                            <label for="leader-chat-subject">Subject</label>
                            <input type="text" id="leader-chat-subject" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="leader-chat-message">Message</label>
                            <textarea id="leader-chat-message" class="form-control" required></textarea>
                        </div>
                        <button type="submit" class="btn btn-primary">Send Private Message</button>
                    </form>
                </div>
            </div>

            <div id="rules-page" class="page">
                <div class="card">
                    <h2 class="card-title">📜 Rules of Clan</h2>
                    <div class="item-list" id="rules-list">
                        </div>
                </div>
            </div>

            <div id="advisory-page" class="page">
                <div class="card form-container">
                    <h2 class="card-title">🧠 Advisory Committee</h2>
                    <div class="alert alert-info">Submit your advice directly to the Leader's private dashboard.</div>
                    <form id="advisory-form">
                        <div class="form-group">
                            <label for="advisory-subject">Subject / Category</label>
                            <input type="text" id="advisory-subject" class="form-control" placeholder="e.g. War Strategy, New Rule Idea, Member Conduct" required>
                        </div>
                        <div class="form-group">
                            <label for="advisory-message">Your Advice</label>
                            <textarea id="advisory-message" class="form-control" required></textarea>
                        </div>
                        <button type="submit" class="btn btn-primary">Submit Advice</button>
                    </form>
                </div>
            </div>

            <div id="leader-dashboard-page" class="page">
                <h2 class="card-title">🛡️ Leader Dashboard</h2>
                <div class="dashboard-grid">
                    <a href="#" class="dashboard-button" data-action="show-players-actions">👥 Players & Actions</a>
                    <a href="#" class="dashboard-button" data-action="show-quarry">📥 Quarry (Inbox)</a>
                    <a href="#" class="dashboard-button" data-action="show-advisory-inbox">🧠 Advisory Inbox</a>
                    <a href="#" class="dashboard-button" data-action="show-create-draft">✍️ Create Draft Rule</a>
                    <a href="#" class="dashboard-button" data-action="show-cabinet-management">🎖️ Cabinet Management</a>
                    <a href="#" class="dashboard-button" data-action="export-player-data">📊 Export Player Data (JSON)</a>
                </div>
                
                <div id="new-registrations-card" class="card" style="margin-top: 30px;">
                    <h3 class="card-title">🔔 New Registrations</h3>
                    <div id="new-registrations-list"></div>
                </div>
            </div>
            <div id="players-actions-page" class="page">
                <div class="card">
                    <button class="btn btn-secondary" data-action="show-leader-dashboard" style="margin-bottom: 20px;">&larr; Back to Dashboard</button>
                    <h2 class="card-title">👥 Players & Actions</h2>
                    <div class="player-table-container">
                        <table class="player-table">
                            <thead>
                                <tr>
                                    <th>Name (ID)</th>
                                    <th>Password</th>
                                    <th>Role</th>
                                    <th>Status</th>
                                    <th>Joined</th>
                                    <th>Actions</th>
                                </tr>
                            </thead>
                            <tbody id="players-actions-table-body">
                                </tbody>
                        </table>
                    </div>
                </div>
            </div>

            <div id="player-details-page" class="page">
                 <div class="card">
                    <button class="btn btn-secondary" data-action="show-players-actions" style="margin-bottom: 20px;">&larr; Back to Players</button>
                    <h2 class="card-title">📊 Player Details: <span id="player-detail-name"></span></h2>
                    
                    <div id="player-detail-info"></div>

                    <h3>Activity Log</h3>
                    <div id="player-detail-activity" style="background: #f9f9f9; border: 1px solid #eee; padding: 15px; border-radius: var(--radius); max-height: 500px; overflow-y: auto;">
                        </div>
                </div>
            </div>

            <div id="quarry-page" class="page">
                <div class="card">
                    <button class="btn btn-secondary" data-action="show-leader-dashboard" style="margin-bottom: 20px;">&larr; Back to Dashboard</button>
                    <h2 class="card-title">📥 Quarry (Leader's Inbox)</h2>
                    <div class="item-list" id="quarry-list">
                        </div>
                </div>
            </div>

            <div id="advisory-inbox-page" class="page">
                <div class="card">
                    <button class="btn btn-secondary" data-action="show-leader-dashboard" style="margin-bottom: 20px;">&larr; Back to Dashboard</button>
                    <h2 class="card-title">🧠 Advisory Committee Inbox</h2>
                    <div class="item-list" id="advisory-inbox-list">
                        </div>
                </div>
            </div>
            
            <div id="create-draft-page" class="page">
                <div class="card form-container">
                    <button class="btn btn-secondary" data-action="show-leader-dashboard" style="margin-bottom: 20px;">&larr; Back to Dashboard</button>
                    <h2 class="card-title">✍️ Create New Draft Rule</h2>
                    <form id="create-draft-form">
                        <div class="form-group">
                            <label for="draft-title">Draft Title</label>
                            <input type="text" id="draft-title" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="draft-description">Full Description</label>
                            <textarea id="draft-description" class="form-control" required></textarea>
                        </div>
                        <button type="submit" class="btn btn-primary" style="width: 100%;">Publish Draft (Starts 5h Advice Phase)</button>
                    </form>
                </div>
            </div>

            <div id="cabinet-management-page" class="page">
                <div class="card">
                    <button class="btn btn-secondary" data-action="show-leader-dashboard" style="margin-bottom: 20px;">&larr; Back to Dashboard</button>
                    <h2 class="card-title">🎖️ Cabinet Management (Max 5)</h2>
                    <div class="alert alert-info">Cabinet Players can post on the Notice Board. Select Co-Leaders or Elders to be in the cabinet.</div>
                    <form id="cabinet-management-form">
                        <div class="form-group" id="cabinet-player-options">
                            </div>
                        <button type="submit" class="btn btn-primary">Save Cabinet</button>
                    </form>
                </div>
            </div>

        </main>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', () => {

            // --- 1. FIREBASE SETUP ---
            // 🔴 यह आपका FIREBASE CONFIG कोड है
            const firebaseConfig = {
              apiKey: "AIzaSyDkKkOLlq-Ipr8mgzd5hfE6X-qkQgAdYCE",
              authDomain: "clanportal.firebaseapp.com",
              projectId: "clanportal",
              storageBucket: "clanportal.firebasestorage.app",
              messagingSenderId: "881645657294",
              appId: "1:881645657294:web:e0f46054f8a113ce37c49f",
              measurementId: "G-Z84SMVXCTX"
            };

            // Initialize Firebase
            firebase.initializeApp(firebaseConfig);
            
            const db = firebase.firestore(); 
            // ★★★ NEW: Firebase Storage reference ★★★
            const storage = firebase.storage();

            // --- 2. State and Database References ---

            let appState = {
                currentUser: null,
                currentPage: 'login-page',
                currentDraftId: null,
                viewingPlayerId: null,
                allUsersCache: [], // सभी यूज़र्स को कैश करने के लिए
                listeners: {}, // Real-time listeners को मैनेज करने के लिए
                // ★★★ NEW: Store files being uploaded ★★★
                fileToUpload: {
                    ga: null,
                    sa: null
                }
            };

            // Database collections के रेफरेन्स
            const usersCollection = db.collection('users');
            const metaCollection = db.collection('meta'); // Cabinet, New Reg etc.
            const messagesCollection = db.collection('messages');
            const draftsCollection = db.collection('drafts');
            const rulesCollection = db.collection('rules');
            const noticesCollection = db.collection('notices');
            const adviceCollection = db.collection('advice');
            const dmsCollection = db.collection('dms');


            // --- 3. Initialization ---

            async function initApp() {
                try {
                    const metaDoc = await metaCollection.doc('main').get();
                    if (!metaDoc.exists) {
                        await metaCollection.doc('main').set({
                            cabinet: [],
                            newRegistrations: [],
                            pinnedMessageGA: null, // ★★★ NEW
                            pinnedMessageSA: null  // ★★★ NEW
                        }, { merge: true });
                        console.log("Initialized 'meta/main' document.");
                    }
                } catch (error) {
                    console.error("Error initializing meta doc:", error);
                }


                // Set up the final Leader account if it doesn't exist
                try {
                    const leaderDoc = await usersCollection.doc('Aryanrajput').get();
                    
                    if (!leaderDoc.exists) {
                        await usersCollection.doc('Aryanrajput').set({
                            id: 'Aryanrajput',
                            name: '⚔️Aryan⚔️',
                            clanName: '👑 king 👑',
                            clanId: '#2G0YJ080V',
                            dob: '2000-01-01',
                            country: 'India',
                            state: 'Delhi',
                            languages: 'English',
                            password: '91621272', 
                            role: 'Leader',
                            status: 'active',
                            createdAt: firebase.firestore.FieldValue.serverTimestamp()
                        });
                        console.log("Final Leader account created. ID: Aryanrajput, Pass: 91621272");
                    }
                } catch (error) {
                    console.error("Error checking/creating leader:", error);
                }

                
                // Check session storage for logged in user
                const sessionUser = sessionStorage.getItem('clanPortalUser');
                if (sessionUser) {
                    appState.currentUser = JSON.parse(sessionUser);
                    await cacheAllUsers(); // सभी यूज़र्स की जानकारी लोड करें
                    updateHeader();
                    showPage('home-page');
                } else {
                    updateHeader();
                    showPage('login-page');
                }

                // Attach all event listeners
                attachEventListeners();
            }

            // --- Helper: Cache All Users ---
            async function cacheAllUsers() {
                try {
                    const snapshot = await usersCollection.get();
                    appState.allUsersCache = snapshot.docs.map(doc => doc.data());
                    console.log('All users cached:', appState.allUsersCache.length);
                } catch (error) {
                    console.error("Error caching users:", error);
                }
            }


            // --- 4. Page Navigation & Real-time Listeners ---

            function detachAllListeners() {
                console.log("Detaching all listeners...");
                for (let key in appState.listeners) {
                    if (appState.listeners[key]) {
                        appState.listeners[key](); // Unsubscribe
                        appState.listeners[key] = null;
                    }
                }
            }

            function showPage(pageId, context = null) {
                detachAllListeners();
                
                // ★★★ NEW: Clear file uploads on page change ★★★
                appState.fileToUpload = { ga: null, sa: null };
                document.getElementById('ga-file-input').value = null;
                document.getElementById('sa-file-input').value = null;


                document.querySelectorAll('.page').forEach(page => {
                    page.classList.remove('active');
                });

                const targetPage = document.getElementById(pageId);
                if (targetPage) {
                    targetPage.classList.add('active');
                    appState.currentPage = pageId;

                    switch (pageId) {
                        case 'home-page':
                            renderHomePageButtons();
                            renderCabinetList();
                            break;
                        case 'general-assembly-page':
                            renderGeneralAssembly();
                            renderChatControls('ga'); 
                            break;
                        case 'special-assembly-page':
                            renderSpecialAssembly();
                            renderChatControls('sa');
                            break;
                        case 'notice-board-page':
                            renderNoticeBoard();
                            break;
                        case 'drafts-voting-page':
                            renderDraftsVotingPage();
                            break;
                        case 'draft-detail-page':
                            appState.currentDraftId = context.draftId;
                            renderDraftDetailPage(context.draftId);
                            break;
                        case 'rules-page':
                            renderRules();
                            break;
                        case 'leader-dashboard-page':
                            renderLeaderDashboard();
                            break;
                        case 'players-actions-page':
                            renderPlayersActions();
                            break;
                        case 'player-details-page':
                            appState.viewingPlayerId = context.userId;
                            renderPlayerDetails(context.userId);
                            break;
                        case 'quarry-page':
                            renderQuarry();
                            break;
                        case 'advisory-inbox-page':
                            renderAdvisoryInbox();
                            break;
                        case 'cabinet-management-page':
                            renderCabinetManagement();
                            break;
                    }
                    
                    window.scrollTo(0, 0);

                } else {
                    console.error(`Page not found: ${pageId}`);
                    if (appState.currentUser) {
                        showPage('home-page');
                    } else {
                        showPage('login-page');
                    }
                }
            }

            // --- 5. Event Listeners ---

            function attachEventListeners() {
                document.body.addEventListener('click', (e) => {
                    // Use `closest` for data-action to catch clicks on icons inside buttons
                    let target = e.target.closest('[data-action]');
                    if (!target) return;

                    const action = target.dataset.action;
                    if (action) {
                        // e.preventDefault(); // Only prevent if it's not a link action like export
                        
                        if (action.startsWith('show-')) {
                            e.preventDefault();
                            const pageId = action.replace('show-', '') + '-page';
                            showPage(pageId);
                        }
                        
                        switch (action) {
                            case 'logout':
                                e.preventDefault();
                                handleLogout();
                                break;
                            case 'show-draft-detail':
                                e.preventDefault();
                                showPage('draft-detail-page', { draftId: target.dataset.id });
                                break;
                            case 'draft-vote':
                                e.preventDefault();
                                handleDraftVote(appState.currentDraftId, target.dataset.vote);
                                break;
                            case 'activate-draft':
                                e.preventDefault();
                                handleActivateLaw(target.dataset.id); // Pass ID from button
                                break;
                            case 'leader-delete-rule':
                                e.preventDefault();
                                handleRemoveRule(target.dataset.id);
                                break;
                            case 'show-player-details':
                                e.preventDefault();
                                showPage('player-details-page', { userId: target.dataset.id });
                                break;
                            case 'player-action':
                                e.preventDefault();
                                handlePlayerAction(target.dataset.id, target.dataset.task);
                                break;
                            case 'acknowledge-registration':
                                e.preventDefault();
                                acknowledgeRegistration(target.dataset.id);
                                break;
                            case 'mark-advice':
                                e.preventDefault();
                                markAdvice(target.dataset.id, target.dataset.status);
                                break;
                            case 'reply-dm':
                                e.preventDefault();
                                handleQuarryReply(target.dataset.id);
                                break;
                            // ★★★ NEW: Chat Message Actions ★★★
                            case 'pin-message':
                                e.preventDefault();
                                handlePinMessage(target.dataset.id, target.dataset.room);
                                break;
                            case 'unpin-message':
                                e.preventDefault();
                                handlePinMessage(null, target.dataset.room); // Set to null to unpin
                                break;
                            case 'delete-message':
                                e.preventDefault();
                                handleDeleteMessage(target.dataset.id, target.dataset.room);
                                break;
                            // ★★★ NEW: Leader Data Export ★★★
                            case 'export-player-data':
                                e.preventDefault();
                                handleExportData();
                                break;
                        }
                    }
                });

                document.getElementById('login-form').addEventListener('submit', handleLogin);
                document.getElementById('register-form').addEventListener('submit', handleRegister);
                document.getElementById('ga-chat-form').addEventListener('submit', (e) => handleChatMessagePost(e, 'ga'));
                document.getElementById('sa-chat-form').addEventListener('submit', (e) => handleChatMessagePost(e, 'sa'));
                document.getElementById('new-notice-form').addEventListener('submit', handleNoticePost);
                document.getElementById('draft-advice-form').addEventListener('submit', handleDraftAdvice);
                document.getElementById('leader-chat-form').addEventListener('submit', handleLeaderChatSubmit);
                document.getElementById('advisory-form').addEventListener('submit', handleAdvisorySubmit);
                document.getElementById('create-draft-form').addEventListener('submit', handleCreateDraft);
                document.getElementById('cabinet-management-form').addEventListener('submit', handleCabinetSave);

                document.getElementById('reg-country').addEventListener('change', (e) => {
                    const country = e.target.value;
                    document.getElementById('india-states-group').style.display = (country === 'India') ? 'block' : 'none';
                    document.getElementById('other-region-group').style.display = (country !== 'India' && country !== '') ? 'block' : 'none';
                });
                
                // ★★★ NEW: File Input Listeners ★★★
                document.getElementById('ga-file-input').addEventListener('change', (e) => {
                    const file = e.target.files[0];
                    if (file) {
                        appState.fileToUpload.ga = file;
                        document.getElementById('ga-chat-input').placeholder = `File attached: ${file.name} (Press Send)`;
                    }
                });
                document.getElementById('sa-file-input').addEventListener('change', (e) => {
                    const file = e.target.files[0];
                    if (file) {
                        appState.fileToUpload.sa = file;
                        document.getElementById('sa-chat-input').placeholder = `File attached: ${file.name} (Press Send)`;
                    }
                });
            }

            // --- 6. UI Rendering Functions (BASIC) ---

            function updateHeader() {
                const loggedOutHeader = document.getElementById('header-logged-out');
                const loggedInHeader = document.getElementById('header-logged-in');
                
                if (appState.currentUser) {
                    loggedOutHeader.style.display = 'none';
                    loggedInHeader.style.display = 'flex';
                    
                    const user = appState.currentUser;
                    const avatar = user.name.charAt(0).toUpperCase();
                    document.getElementById('user-avatar').textContent = avatar;
                    document.getElementById('user-name').textContent = user.name;
                    document.getElementById('user-role').textContent = user.role;
                } else {
                    loggedOutHeader.style.display = 'block';
                    loggedInHeader.style.display = 'none';
                }
            }
            function renderHomePageButtons() {
                const grid = document.getElementById('home-buttons-grid');
                if (!grid) return;
                const user = appState.currentUser;
                let buttons = `
                    <div class="home-button" data-action="show-general-assembly">🗣 General Assembly</div>
                    <div class="home-button" data-action="show-special-assembly">👑 Special Assembly</div>
                    <div class="home-button" data-action="show-notice-board">📢 Notice Board</div>
                    <div class="home-button" data-action="show-drafts-voting">⚖️ Drafts & Voting</div>
                    <div class="home-button" data-action="show-rules">📜 Rules of Clan</div>
                    <div class="home-button" data-action="show-leader-chat">💬 Leader Chat (DM)</div>
                    <div class="home-button" data-action="show-advisory">🧠 Give Advice</div>
                `;

                if (user.role === 'Leader') {
                    buttons += `
                        <div class="home-button leader-btn" data-action="show-leader-dashboard">🛡️ Leader Dashboard</div>
                    `;
                }

                grid.innerHTML = buttons;
            }

            async function renderCabinetList() {
                const listEl = document.getElementById('cabinet-player-list');
                if (!listEl) return;
                try {
                    const metaDoc = await metaCollection.doc('main').get();
                    const cabinetIds = metaDoc.data()?.cabinet || [];
                    
                    if (cabinetIds.length === 0) {
                        listEl.innerHTML = '<span>No cabinet players assigned.</span>';
                        return;
                    }

                    const cabinetUsers = appState.allUsersCache.filter(u => cabinetIds.includes(u.id));
                    listEl.innerHTML = cabinetUsers.map(u => `<span>${u.name} (${u.role})</span>`).join('');

                } catch (error) {
                    console.error("Error rendering cabinet list:", error);
                    listEl.innerHTML = '<span>Error loading cabinet.</span>';
                }
            }
            
            function getAvatar(user) {
                if (!user || !user.name) return `<div class="profile-avatar avatar">?</div>`;
                return `<div class="profile-avatar avatar">${user.name.charAt(0).toUpperCase()}</div>`;
            }

            function renderPlayerList(elementId, users) {
                const listEl = document.getElementById(elementId);
                if (!listEl) return;
                const roleOrder = { 'Leader': 1, 'Co-Leader': 2, 'Elder': 3, 'Member': 4 };
                
                users.sort((a, b) => roleOrder[a.role] - roleOrder[b.role]);
                
                listEl.innerHTML = users.map(user => `
                    <div class="player-list-item">
                        ${getAvatar(user)}
                        <div>
                            <div class="name">${user.name}</div>
                            <div class="role">${user.role}</div>
                        </div>
                    </div>
                `).join('');
            }
            
            // --- 7. REAL-TIME CHAT FUNCTIONS ---

            function renderGeneralAssembly() {
                const activeUsers = appState.allUsersCache.filter(u => u.status === 'active');
                renderPlayerList('ga-player-list', activeUsers);
                
                // ★★★ NEW: Listen for pinned message ★★★
                appState.listeners.pinnedGA = metaCollection.doc('main')
                    .onSnapshot((doc) => {
                        const pinnedMsgId = doc.data()?.pinnedMessageGA;
                        renderPinnedMessage('ga-pinned-message', pinnedMsgId, 'ga');
                    });
                
                appState.listeners.generalMessages = messagesCollection
                    .doc('general')
                    .collection('chats')
                    .orderBy('timestamp', 'asc')
                    .limitToLast(100)
                    .onSnapshot((snapshot) => {
                        const messages = snapshot.docs.map(doc => ({ id: doc.id, ...doc.data() }));
                        renderMessages('ga-chat-box', messages, appState.allUsersCache, 'ga');
                    }, (error) => {
                        console.error("Error listening to general chat:", error);
                    });
            }
            
            function renderSpecialAssembly() {
                const leadership = appState.allUsersCache.filter(u => (u.role === 'Leader' || u.role === 'Co-Leader') && u.status === 'active');
                renderPlayerList('sa-player-list', leadership);
                
                // ★★★ NEW: Listen for pinned message ★★★
                appState.listeners.pinnedSA = metaCollection.doc('main')
                    .onSnapshot((doc) => {
                        const pinnedMsgId = doc.data()?.pinnedMessageSA;
                        renderPinnedMessage('sa-pinned-message', pinnedMsgId, 'sa');
                    });
                
                appState.listeners.specialMessages = messagesCollection
                    .doc('special')
                    .collection('chats')
                    .orderBy('timestamp', 'asc')
                    .limitToLast(100)
                    .onSnapshot((snapshot) => {
                        const messages = snapshot.docs.map(doc => ({ id: doc.id, ...doc.data() }));
                        renderMessages('sa-chat-box', messages, appState.allUsersCache, 'sa');
                    }, (error) => {
                        console.error("Error listening to special chat:", error);
                    });
            }

            function renderChatControls(pagePrefix) {
                const container = document.getElementById(`${pagePrefix}-controls-container`);
                if (!container) return;

                const user = appState.currentUser;
                let controlsHTML = '';

                const memberColors = `
                    <option value="#333333">Black</option>
                    <option value="#FFFFFF">White</option>
                    <option value="#FFD700">Yellow</option>
                    <option value="#87CEEB">Sky Blue</option>
                `;
                const coLeaderColors = `
                    ${memberColors}
                    <option value="#DC3545">Red</option>
                    <option value="#007BFF">Blue</option>
                `;

                if (user.role === 'Leader') {
                    controlsHTML = `
                        <div>
                            <label for="${pagePrefix}-color-picker">Color:</label>
                            <input type="color" id="${pagePrefix}-color-picker" value="#333333">
                        </div>
                        <div>
                            <label for="${pagePrefix}-font-select">Font:</label>
                            <select id="${pagePrefix}-font-select">
                                <option value="'Poppins', sans-serif">Poppins (Default)</option>
                                <option value="Arial, sans-serif">Arial</option>
                                <option value="'Courier New', monospace">Courier New</option>
                                <option value="'Times New Roman', serif">Times New Roman</option>
                            </select>
                        </div>
                    `;
                } else if (user.role === 'Co-Leader') {
                    controlsHTML = `
                        <div>
                            <label for="${pagePrefix}-color-select">Color:</label>
                            <select id="${pagePrefix}-color-select">
                                ${coLeaderColors}
                            </select>
                        </div>
                    `;
                } else if (user.role === 'Member' || user.role === 'Elder') {
                    controlsHTML = `
                        <div>
                            <label for="${pagePrefix}-color-select">Color:</label>
                            <select id="${pagePrefix}-color-select">
                                ${memberColors}
                            </select>
                        </div>
                    `;
                }

                container.innerHTML = controlsHTML;
            }

            // ★★★ NEW: Render Pinned Message Bar ★★★
            async function renderPinnedMessage(elementId, messageId, room) {
                const pinEl = document.getElementById(elementId);
                if (!pinEl) return;
                
                if (!messageId) {
                    pinEl.style.display = 'none';
                    return;
                }
                
                try {
                    const roomName = (room === 'ga' ? 'general' : 'special');
                    const msgDoc = await messagesCollection.doc(roomName).collection('chats').doc(messageId).get();
                    if (!msgDoc.exists) {
                        pinEl.style.display = 'none';
                        return;
                    }
                    
                    const msg = msgDoc.data();
                    const user = appState.allUsersCache.find(u => u.id === msg.userId);
                    let content = msg.text;
                    if (msg.type === 'image') content = '📷 Image';
                    if (msg.type === 'video') content = '🎥 Video';
                    
                    pinEl.innerHTML = `
                        <div class="pinned-message-content">
                            <b>📌 PINNED:</b> ${user ? user.name : '...'} - ${content.substring(0, 50)}...
                        </div>
                        ${appState.currentUser.role === 'Leader' ? 
                            `<button class="btn btn-icon btn-sm" data-action="unpin-message" data-room="${room}">✖</button>` : ''}
                    `;
                    pinEl.style.display = 'flex';
                    
                } catch (error) {
                    console.error("Error rendering pinned message:", error);
                    pinEl.style.display = 'none';
                }
            }

            // ★★★ HEAVILY MODIFIED: renderMessages Function ★★★
            function renderMessages(boxId, messages, users, room) {
                const box = document.getElementById(boxId);
                if (!box) return;

                box.innerHTML = messages.map(msg => {
                    const user = users.find(u => u.id === msg.userId);
                    if (!user) return ''; 
                    
                    let roleClass = '';
                    if (user.role === 'Leader') roleClass = 'message-leader';
                    if (user.role === 'Co-Leader') roleClass = 'message-coleader';

                    const color = msg.color || '#333333';
                    const font = msg.font || "'Poppins', sans-serif";
                    
                    let textShadow = 'none';
                    const lightColors = ['#ffffff', '#ffd700', '#87ceeb'];
                    if (lightColors.includes(color.toLowerCase())) {
                        textShadow = '0 0 3px rgba(0,0,0,0.7)';
                    }
                    
                    const isLeader = user.role === 'Leader';
                    const fontWeight = isLeader ? '700' : 'normal';
                    
                    const style = `color: ${color}; font-family: ${font}; font-weight: ${fontWeight}; text-shadow: ${textShadow};`;

                    const timestamp = msg.timestamp?.toDate ? msg.timestamp.toDate() : new Date();

                    // Check if message is from "me" or "other"
                    const meOrOther = (msg.userId === appState.currentUser.id) ? 'me' : 'other';

                    // Media Content
                    let mediaHTML = '';
                    if (msg.type === 'image') {
                        mediaHTML = `<div class="message-media"><img src="${msg.url}" alt="Image" onclick="window.open('${msg.url}')"></div>`;
                    } else if (msg.type === 'video') {
                        mediaHTML = `<div class="message-media"><video controls src="${msg.url}"></video></div>`;
                    } else if (msg.type === 'file') {
                        mediaHTML = `<div class="message-media"><a href="${msg.url}" target="_blank" class="message-media-download">Download File</a></div>`;
                    }
                    
                    // Leader actions
                    let leaderActions = '';
                    if (appState.currentUser.role === 'Leader') {
                        leaderActions = `
                            <button class_:"btn-icon" data-action="pin-message" data-id="${msg.id}" data-room="${room}" title="Pin">📌</button>
                            <button class_:"btn-icon" data-action="delete-message" data-id="${msg.id}" data-room="${room}" title="Delete">🗑️</button>
                        `;
                    }

                    return `
                        <div class="chat-message ${roleClass} ${meOrOther}">
                            ${getAvatar(user)}
                            <div class="message-content">
                                <div class="message-sender">${user.name} ${user.role === 'Leader' ? '👑' : (user.role === 'Co-Leader' ? '⭐' : '')}</div>
                                ${msg.text ? `<div class="message-text" style="${style}">${msg.text}</div>` : ''}
                                ${mediaHTML}
                                <div class="message-timestamp">${timestamp.toLocaleString()}</div>
                            </div>
                            <div class="message-actions">
                                ${leaderActions}
                            </div>
                        </div>
                    `;
                }).join('');
                box.scrollTop = box.scrollHeight;
            }
            
            function renderNoticeBoard() {
                const listEl = document.getElementById('notice-list');
                const formEl = document.getElementById('notice-board-post-form');
                if (!listEl || !formEl) return;

                // Show post form only for cabinet members
                metaCollection.doc('main').get().then(doc => {
                    const cabinetIds = doc.data()?.cabinet || [];
                    if (cabinetIds.includes(appState.currentUser.id)) {
                        formEl.style.display = 'block';
                    } else {
                        formEl.style.display = 'none';
                    }
                }).catch(error => console.error("Error getting cabinet status:", error));

                // Notices के लिए Real-time listener
                appState.listeners.notices = noticesCollection
                    .orderBy('timestamp', 'desc')
                    .onSnapshot(snapshot => {
                        const notices = snapshot.docs.map(doc => ({ id: doc.id, ...doc.data() }));
                        
                        if (notices.length === 0) {
                            listEl.innerHTML = '<p>No notices have been posted.</p>';
                            return;
                        }
                        
                        listEl.innerHTML = notices.map(notice => {
                            const author = appState.allUsersCache.find(u => u.id === notice.userId);
                            const timestamp = notice.timestamp?.toDate ? notice.timestamp.toDate() : new Date();
                            return `
                                <div class="item-card">
                                    <h3>${notice.title}</h3>
                                    <p>${notice.content.replace(/\n/g, '<br>')}</p>
                                    <div class="item-meta">
                                        Posted by ${author ? author.name : 'Unknown'} on ${timestamp.toLocaleDateString()}
                                    </div>
                                </div>
                            `;
                        }).join('');
                    }, error => console.error("Error listening to notices:", error));
            }
            
            function renderRules() {
                const listEl = document.getElementById('rules-list');
                if (!listEl) return;
                
                appState.listeners.rules = rulesCollection
                    .orderBy('activatedAt', 'asc') // नए रूल्स नीचे आएँगे
                    .onSnapshot(snapshot => {
                        const rules = snapshot.docs.map(doc => ({ id: doc.id, ...doc.data() }));

                        if (rules.length === 0) {
                            listEl.innerHTML = '<p>No clan rules have been activated yet.</p>';
                            return;
                        }
                        
                        listEl.innerHTML = rules.map((rule, index) => `
                            <div class="item-card">
                                <h3>Rule ${index + 1}: ${rule.title}</h3>
                                <p>${rule.description.replace(/\n/g, '<br>')}</p>
                                ${appState.currentUser.role === 'Leader' ? 
                                    `<button class="btn btn-danger btn-sm leader-action-btn" data-action="leader-delete-rule" data-id="${rule.id}">Delete</button>` : ''
                                }
                            </div>
                        `).join('');
                    }, error => console.error("Error listening to rules:", error));
            }

            function renderLeaderDashboard() {
                const listEl = document.getElementById('new-registrations-list');
                if (!listEl) return;
                
                // 'meta' collection में 'main' document से 'newRegistrations' सुनें
                appState.listeners.newRegistrations = metaCollection.doc('main')
                    .onSnapshot(doc => {
                        if (!doc.exists) {
                            console.error("Meta document does not exist.");
                            return;
                        }
                        const newRegistrations = doc.data()?.newRegistrations || [];
                        
                        if (newRegistrations.length === 0) {
                            listEl.innerHTML = '<p>No new registrations.</p>';
                            return;
                        }
                        
                        listEl.innerHTML = newRegistrations.map(reg => {
                            return `
                                <div class="item-card">
                                    <p><b>Name:</b> ${reg.name} (<b>Role:</b> ${reg.role})</p>
                                    <p><b>ID:</b> ${reg.id}</p>
                                    <p><b>Password:</b> ${reg.password}</p>
                                    <p><b>Country:</b> ${reg.country} (${reg.state || 'N/A'})</p>
                                    <p><b>Languages:</b> ${reg.languages}</p>
                                    <button class="btn btn-success btn-sm" data-action="acknowledge-registration" data-id="${reg.id}">Acknowledge</button>
                                </div>
                            `;
                        }).join('');
                    }, error => console.error("Error listening to new registrations:", error));
            }

            async function renderPlayersActions() {
                const bodyEl = document.getElementById('players-actions-table-body');
                if (!bodyEl) return;
                
                try {
                    const snapshot = await usersCollection.orderBy('name', 'asc').get();
                    const users = snapshot.docs.map(doc => doc.data());
                    appState.allUsersCache = users; // Cache को अपडेट करें

                    bodyEl.innerHTML = users.map(user => {
                        const joinedDate = user.createdAt?.toDate ? user.createdAt.toDate() : new Date();
                        return `
                            <tr>
                                <td>
                                    <b>${user.name}</b><br>
                                    <small>${user.id}</small>
                                </td>
                                <td>${user.password}</td>
                                <td>
                                    <select class="form-control" data-action="player-action-select" data-task="role" data-id="${user.id}" ${user.role === 'Leader' ? 'disabled' : ''}>
                                        <option value="Member" ${user.role === 'Member' ? 'selected' : ''}>Member</option>
                                        <option value="Elder" ${user.role === 'Elder' ? 'selected' : ''}>Elder</option>
                                        <option value="Co-Leader" ${user.role === 'Co-Leader' ? 'selected' : ''}>Co-Leader</option>
                                        <option value="Leader" ${user.role === 'Leader' ? 'selected' : ''}>Leader</option>
                                    </select>
                                </td>
                                <td>
                                    <span style="font-weight: 600; text-transform: capitalize; color: ${user.status === 'active' ? 'green' : 'red'};">${user.status}</span>
                                </td>
                                <td>${joinedDate.toLocaleDateString()}</td>
                                <td>
                                    <button class="btn btn-primary btn-sm" data-action="show-player-details" data-id="${user.id}">Details</button>
                                    ${user.role !== 'Leader' ? `
                                        <button class="btn btn-secondary btn-sm" data-action="player-action" data-task="suspend" data-id="${user.id}">Suspend</button>
                                        <button class="btn btn-warning btn-sm" data-action="player-action" data-task="ban" data-id="${user.id}">Ban</button>
                                        <button class="btn btn-danger btn-sm" data-action="player-action" data-task="delete" data-id="${user.id}">Delete</button>
                                    ` : ''}
                                    ${user.status !== 'active' ? `
                                        <button class="btn btn-success btn-sm" data-action="player-action" data-task="reactivate" data-id="${user.id}">Reactivate</button>
                                    ` : ''}
                                </td>
                            </tr>
                        `
                    }).join('');
                    
                    bodyEl.querySelectorAll('select[data-action="player-action-select"]').forEach(select => {
                        select.addEventListener('change', (e) => {
                            handlePlayerAction(e.target.dataset.id, 'role', e.target.value);
                        });
                    });

                } catch (error) {
                    console.error("Error rendering player actions:", error);
                    bodyEl.innerHTML = `<tr><td colspan="6">Error loading players.</td></tr>`;
                }
            }
            
            async function renderPlayerDetails(userId) {
                const user = appState.allUsersCache.find(u => u.id === userId);
                if (!user) {
                    showPage('players-actions-page');
                    return;
                }

                document.getElementById('player-detail-name').textContent = user.name;
                const joinedDate = user.createdAt?.toDate ? user.createdAt.toDate() : new Date();
                
                document.getElementById('player-detail-info').innerHTML = `
                    <p><strong>Player ID:</strong> ${user.id}</p>
                    <p><strong>Role:</strong> ${user.role}</p>
                    <p><strong>Status:</strong> ${user.status}</p>
                    <p><strong>Clan:</strong> ${user.clanName} (${user.clanId})</p>
                    <p><strong>From:</strong> ${user.state ? user.state + ', ' : ''}${user.country}</p>
                    <p><strong>Languages:</strong> ${user.languages}</p>
                    <p><strong>Joined:</strong> ${joinedDate.toLocaleString()}</p>
                `;
                
                const activityEl = document.getElementById('player-detail-activity');
                activityEl.innerHTML = '<p>Loading activity...</p>';
                let activity = [];

                try {
                    const gaMsgs = await messagesCollection.doc('general').collection('chats').where('userId', '==', userId).limit(20).get();
                    gaMsgs.docs.forEach(m => {
                        const data = m.data();
                        let content = data.text;
                        if(data.type) content = `[${data.type}]`;
                        activity.push({ time: data.timestamp.toDate(), text: `[General] ${content}` });
                    });
                    
                    const saMsgs = await messagesCollection.doc('special').collection('chats').where('userId', '==', userId).limit(20).get();
                    saMsgs.docs.forEach(m => {
                        const data = m.data();
                        let content = data.text;
                        if(data.type) content = `[${data.type}]`;
                        activity.push({ time: data.timestamp.toDate(), text: `[Special] ${content}` });
                    });

                    const dms = await dmsCollection.where('userId', '==', userId).limit(20).get();
                    dms.docs.forEach(m => {
                        const data = m.data();
                        activity.push({ time: data.timestamp.toDate(), text: `[DM to Leader] ${data.subject}: ${data.message}` });
                    });
                    
                    const advice = await adviceCollection.where('userId', '==', userId).limit(20).get();
                    advice.docs.forEach(m => {
                        const data = m.data();
                        activity.push({ time: data.timestamp.toDate(), text: `[Advice] ${data.subject}: ${data.message}` });
                    });
                    
                    activity.sort((a, b) => b.time - a.time);
                    
                    if (activity.length === 0) {
                        activityEl.innerHTML = '<p>No activity recorded.</p>';
                    } else {
                        activityEl.innerHTML = activity.map(a => `
                            <div class="advice-item">
                                <small>${a.time.toLocaleString()}</small>
                                <p>${a.text}</p>
                            </div>
                        `).join('');
                    }
                } catch (error) {
                    console.error("Error loading player activity:", error);
                    activityEl.innerHTML = '<p>Error loading activity.</p>';
                }
            }

            function renderQuarry() {
                const listEl = document.getElementById('quarry-list');
                if (!listEl) return;
                
                appState.listeners.dms = dmsCollection
                    .orderBy('timestamp', 'desc')
                    .onSnapshot(snapshot => {
                        const allDMs = snapshot.docs.map(doc => ({ id: doc.id, ...doc.data() }));
                        const threads = {};

                        allDMs.forEach(dm => {
                            const threadId = dm.threadId || dm.id;
                            if (!threads[threadId]) {
                                threads[threadId] = [];
                            }
                            threads[threadId].push(dm);
                        });

                        const sortedThreadIds = Object.keys(threads).sort((a, b) => {
                            const lastMsgA = threads[a].reduce((latest, msg) => msg.timestamp.toDate() > latest ? msg.timestamp.toDate() : latest, new Date(0));
                            const lastMsgB = threads[b].reduce((latest, msg) => msg.timestamp.toDate() > latest ? msg.timestamp.toDate() : latest, new Date(0));
                            return lastMsgB - lastMsgA;
                        });

                        if (sortedThreadIds.length === 0) {
                            listEl.innerHTML = '<p>Your inbox is empty.</p>';
                            return;
                        }

                        listEl.innerHTML = sortedThreadIds.map(threadId => {
                            const threadMessages = threads[threadId].sort((a, b) => a.timestamp.toDate() - b.timestamp.toDate());
                            const firstDM = threadMessages[0];
                            const sender = appState.allUsersCache.find(u => u.id === firstDM.userId);

                            return `
                                <div class="item-card">
                                    <h3>${firstDM.subject}</h3>
                                    <div class="item-meta">
                                        From: ${sender ? sender.name : 'Unknown'}
                                    </div>
                                    
                                    <div class="advice-section" style="padding-left: 15px; border-left: 3px solid #eee;">
                                        ${threadMessages.map(dm => {
                                            const isReply = dm.userId === appState.currentUser.id;
                                            const timestamp = dm.timestamp.toDate();
                                            return `
                                                <div class="advice-item">
                                                    <p>${dm.message}</p>
                                                    <small><b>${isReply ? 'Your Reply' : (sender ? sender.name : 'Their') + ' Message'}:</b> ${timestamp.toLocaleString()}</small>
                                                </div>
                                            `
                                        }).join('')}
                                    </div>
                                    
                                    <form class="reply-dm-form" style="margin-top: 15px;">
                                        <textarea id="reply-dm-${firstDM.id}" class="form-control" placeholder="Type your reply..."></textarea>
                                        <button type="button" class="btn btn-primary btn-sm" style="margin-top: 5px;" data-action="reply-dm" data-id="${firstDM.id}">Send Reply</button>
                                    </form>
                                </div>
                            `;
                        }).join('');
                    }, error => console.error("Error listening to DMs:", error));
            }
            
            function renderAdvisoryInbox() {
                const listEl = document.getElementById('advisory-inbox-list');
                if (!listEl) return;
                
                appState.listeners.advice = adviceCollection
                    .orderBy('timestamp', 'desc')
                    .onSnapshot(snapshot => {
                        const adviceItems = snapshot.docs.map(doc => ({ id: doc.id, ...doc.data() }));

                        if (adviceItems.length === 0) {
                            listEl.innerHTML = '<p>No advice submitted.</p>';
                            return;
                        }
                        
                        listEl.innerHTML = adviceItems.map(item => {
                            const sender = appState.allUsersCache.find(u => u.id === item.userId);
                            const timestamp = item.timestamp.toDate();
                            return `
                                <div class="item-card">
                                    <h3>${item.subject} (Status: ${item.status})</h3>
                                    <div class="item-meta">
                                        From: ${sender ? sender.name : 'Unknown'} on ${timestamp.toLocaleString()}
                                    </div>
                                    <p>${item.message}</p>
                                    <div style="margin-top: 10px;">
                                        <button class="btn btn-success btn-sm" data-action="mark-advice" data-id="${item.id}" data-status="Applied">Mark as Applied</button>
                                        <button class="btn btn-warning btn-sm" data-action="mark-advice" data-id="${item.id}" data-status="Considered">Mark as Considered</button>
                                    </div>
                                </div>
                            `;
                        }).join('');
                    }, error => console.error("Error listening to advice inbox:", error));
            }

            async function renderCabinetManagement() {
                const optionsEl = document.getElementById('cabinet-player-options');
                if (!optionsEl) return;
                
                const eligible = appState.allUsersCache.filter(u => (u.role === 'Co-Leader' || u.role === 'Elder') && u.status === 'active');
                
                if (eligible.length === 0) {
                    optionsEl.innerHTML = '<p>No Co-Leaders or Elders available to add to the cabinet.</p>';
                    return;
                }
                
                try {
                    const metaDoc = await metaCollection.doc('main').get();
                    const cabinetIds = metaDoc.data()?.cabinet || [];

                    optionsEl.innerHTML = eligible.map(user => `
                        <div class="form-check">
                            <input class="form-check-input" type="checkbox" value="${user.id}" id="cab-${user.id}"
                                ${cabinetIds.includes(user.id) ? 'checked' : ''}>
                            <label class="form-check-label" for="cab-${user.id}">
                                ${user.name} (${user.role})
                            </label>
                        </div>
                    `).join('');
                } catch (error) {
                    console.error("Error rendering cabinet management:", error);
                    optionsEl.innerHTML = '<p>Error loading cabinet options.</p>';
                }
            }
            
            async function updateAllDraftsStatus() {
                const now = new Date();
                
                const draftsToUpdateQuery = draftsCollection
                    .where('status', 'in', ['advice', 'voting']);
                
                try {
                    const snapshot = await draftsToUpdateQuery.get();
                    if (snapshot.empty) {
                        return; // कोई काम नहीं है
                    }

                    const batch = db.batch();
                    
                    snapshot.docs.forEach(doc => {
                        const draft = { id: doc.id, ...doc.data() };
                        const draftRef = draftsCollection.doc(draft.id);

                        const adviceEnds = draft.adviceEndsAt.toDate();
                        const votingEnds = draft.votingEndsAt.toDate();

                        if (draft.status === 'advice' && now > adviceEnds) {
                            batch.update(draftRef, { status: 'voting' });
                        }
                        
                        else if (draft.status === 'voting' && now > votingEnds) {
                            const { newStatus, newSummary } = tallyVotes(draft); 
                            batch.update(draftRef, { 
                                status: newStatus, 
                                resultSummary: newSummary 
                            });
                        }
                    });

                    await batch.commit();

                } catch (error) {
                    console.error("Error updating draft statuses:", error);
                }
            }
            
            function tallyVotes(draft) {
                if (!draft || !['voting', 'advice'].includes(draft.status)) {
                    return { newStatus: draft.status, newSummary: draft.resultSummary }; 
                }

                let yesVotes = 0;
                let noVotes = 0;
                let absentVotes = 0;
                
                const activeUsers = appState.allUsersCache.filter(u => u.status === 'active');
                if (activeUsers.length === 0) {
                    return { newStatus: 'canceled', newSummary: 'Draft Canceled: No active users found.' };
                }

                const totalPossibleWeightedVotes = activeUsers.reduce((acc, user) => acc + (user.role === 'Leader' ? 3 : 1), 0);
                
                (draft.votes || []).forEach(v => {
                    if (v.vote === 'yes') yesVotes += v.weight;
                    if (v.vote === 'no') noVotes += v.weight;
                    if (v.vote === 'absent') absentVotes += v.weight;
                });

                const votedUserIds = (draft.votes || []).map(v => v.userId);
                activeUsers.forEach(user => {
                    if (!votedUserIds.includes(user.id)) {
                        absentVotes += (user.role === 'Leader' ? 3 : 1);
                    }
                });

                let newStatus = draft.status;
                let newSummary = draft.resultSummary;

                if (totalPossibleWeightedVotes === 0) {
                     newStatus = 'canceled';
                     newSummary = 'Draft Canceled: No voters eligible.';
                }
                else if (absentVotes / totalPossibleWeightedVotes >= (1/3)) {
                    newStatus = 'canceled';
                    newSummary = `Draft Canceled: ${((absentVotes / totalPossibleWeightedVotes) * 100).toFixed(1)}% of players were absent.`;
                }
                else if (yesVotes > (yesVotes + noVotes) / 2) {
                    newStatus = 'passed_pending_activation';
                    newSummary = `Draft Passed!\nYes: ${yesVotes}\nNo: ${noVotes}\nAbsent: ${absentVotes}`;
                }
                else {
                    newStatus = 'failed';
                    newSummary = `Draft Failed.\nYes: ${yesVotes}\nNo: ${noVotes}\nAbsent: ${absentVotes}`;
                }
                
                return { newStatus, newSummary };
            }

            function renderDraftsVotingPage() {
                updateAllDraftsStatus().then(() => {
                    const listEl = document.getElementById('drafts-list');
                    if (!listEl) return;
                    
                    appState.listeners.drafts = draftsCollection
                        .orderBy('createdAt', 'desc')
                        .onSnapshot(snapshot => {
                            const drafts = snapshot.docs.map(doc => ({ id: doc.id, ...doc.data() }));

                            if (drafts.length === 0) {
                                listEl.innerHTML = '<p>No drafts are currently active.</p>';
                                return;
                            }
                            
                            listEl.innerHTML = drafts.map(draft => {
                                let statusText = '';
                                const adviceEnds = draft.adviceEndsAt?.toDate();
                                const votingEnds = draft.votingEndsAt?.toDate();

                                switch (draft.status) {
                                    case 'advice': statusText = `Status: Advice Phase (ends ${adviceEnds?.toLocaleTimeString()})`; break;
                                    case 'voting': statusText = `Status: Voting Phase (ends ${votingEnds?.toLocaleTimeString()})`; break;
                                    case 'passed_pending_activation': statusText = 'Status: Passed, Awaiting Leader Activation'; break;
                                    case 'active': statusText = 'Status: Activated as Law'; break;
                                    case 'failed': statusText = 'Status: Failed'; break;
                                    case 'canceled': statusText = 'Status: Canceled (High Abstention)'; break;
                                    default: statusText = `Status: ${draft.status}`;
                                }

                                return `
                                    <div class="item-card">
                                        <h3>${draft.title}</h3>
                                        <div class="item-meta">${statusText}</div>
                                        <p>${(draft.description || "").substring(0, 150)}...</p>
                                        <button class="btn btn-primary" data-action="show-draft-detail" data-id="${draft.id}">View Details & Vote</button>
                                    </div>
                                `;
                            }).join('');
                        }, error => console.error("Error listening to drafts:", error));
                });
            }
            
            function renderDraftDetailPage(draftId) {
                updateAllDraftsStatus().then(() => {
                    appState.listeners.draftDetail = draftsCollection.doc(draftId)
                        .onSnapshot(doc => {
                            if (!doc.exists) {
                                showPage('drafts-voting-page');
                                return;
                            }
                            
                            const draft = { id: doc.id, ...doc.data() };
                            
                            document.getElementById('draft-detail-title').textContent = draft.title;
                            document.getElementById('draft-detail-description').textContent = draft.description;

                            const statusEl = document.getElementById('draft-detail-status');
                            const timerEl = document.getElementById('draft-detail-timer');
                            const adviceSection = document.getElementById('draft-advice-section');
                            const votingSection = document.getElementById('draft-voting-section');
                            const resultsSection = document.getElementById('draft-results-section');
                            const activationSection = document.getElementById('draft-leader-activation-section');
                            
                            [adviceSection, votingSection, resultsSection, activationSection, timerEl].forEach(el => {
                                if (el) el.style.display = 'none';
                            });
                            
                            statusEl.className = 'draft-status-bar'; 
                            const adviceEnds = draft.adviceEndsAt.toDate();
                            const votingEnds = draft.votingEndsAt.toDate();

                            if (draft.status === 'advice') {
                                statusEl.textContent = 'Advice Phase';
                                statusEl.classList.add('status-advice');
                                timerEl.textContent = `Advice phase ends at: ${adviceEnds.toLocaleString()}`;
                                timerEl.style.display = 'block';
                                adviceSection.style.display = 'block';
                                
                                const adviceListEl = document.getElementById('draft-advice-list');
                                if (draft.advice.length === 0) {
                                    adviceListEl.innerHTML = '<p>No advice submitted yet.</p>';
                                } else {
                                    adviceListEl.innerHTML = (draft.advice || []).map(a => {
                                        const user = appState.allUsersCache.find(u => u.id === a.userId);
                                        const timestamp = a.timestamp.toDate();
                                        return `
                                            <div class="advice-item">
                                                <p>${a.text}</p>
                                                <small class="advice-sender">by ${user ? user.name : 'Unknown'} on ${timestamp.toLocaleString()}</small>
                                            </div>
                                        `;
                                    }).join('');
                                }
                            } 
                            else if (draft.status === 'voting') {
                                statusEl.textContent = 'Voting Phase';
                                statusEl.classList.add('status-voting');
                                timerEl.textContent = `Voting ends at: ${votingEnds.toLocaleString()}`;
                                timerEl.style.display = 'block';

                                const userVote = (draft.votes || []).find(v => v.userId === appState.currentUser.id);
                                if (userVote) {
                                    votingSection.style.display = 'block';
                                    votingSection.innerHTML = `<div class="alert alert-success">You have voted: <strong>${userVote.vote.toUpperCase()}</strong></div>`;
                                } else {
                                    votingSection.style.display = 'block';
                                    const voteErrorEl = document.getElementById('draft-vote-error');
                                    if (!voteErrorEl) {
                                        votingSection.innerHTML = `
                                            <h3>Cast Your Vote</h3>
                                            <div id="draft-vote-error" class="alert alert-danger" style="display: none;"></div>
                                            <div class="vote-options">
                                                <button class="btn btn-success" data-action="draft-vote" data-vote="yes">✅ Yes</button>
                                                <button class="btn btn-danger" data-action="draft-vote" data-vote="no">❌ No</button>
                                                <button class="btn btn-secondary" data-action="draft-vote" data-vote="absent">⚪ Absent</button>
                                            </div>
                                        `;
                                    }
                                }
                            }
                            else { 
                                resultsSection.style.display = 'block';
                                document.getElementById('draft-vote-summary').textContent = draft.resultSummary || 'Results are being tallied.';
                                
                                if (draft.status === 'passed_pending_activation') {
                                    statusEl.textContent = 'Passed - Awaiting Activation';
                                    statusEl.classList.add('status-passed');
                                    if (appState.currentUser.role === 'Leader') {
                                        activationSection.style.display = 'block';
                                        document.getElementById('draft-activate-btn').dataset.id = draft.id;
                                    }
                                } else if (draft.status === 'failed') {
                                    statusEl.textContent = 'Failed';
                                    statusEl.classList.add('status-failed');
                                } else if (draft.status === 'canceled') {
                                    statusEl.textContent = 'Canceled (High Abstention)';
                                    statusEl.classList.add('status-canceled');
                                } else if (draft.status === 'active') {
                                    statusEl.textContent = 'Activated as Law';
                                    statusEl.classList.add('status-active');
                                }
                            }

                        }, error => console.error("Error listening to draft detail:", error));
                });
            }
            
            async function handleLogin(e) {
                e.preventDefault();
                const id = document.getElementById('login-id').value;
                const password = document.getElementById('login-password').value;
                const errorEl = document.getElementById('login-error');
                
                try {
                    const userDoc = await usersCollection.doc(id).get();

                    if (userDoc.exists) {
                        const user = userDoc.data();
                        if (user.password === password) {
                            if (user.status !== 'active') {
                                errorEl.textContent = `Your account is currently ${user.status}. Please contact the Leader.`;
                                errorEl.style.display = 'block';
                                return;
                            }
                            
                            appState.currentUser = user;
                            sessionStorage.setItem('clanPortalUser', JSON.stringify(user)); 
                            await cacheAllUsers(); // लॉगिन के बाद सभी यूज़र्स को कैश करें
                            updateHeader();
                            showPage('home-page');
                            errorEl.style.display = 'none';
                            document.getElementById('login-form').reset();
                        } else {
                            errorEl.textContent = 'Invalid Player ID or Password.';
                            errorEl.style.display = 'block';
                        }
                    } else {
                        errorEl.textContent = 'Invalid Player ID or Password.';
                        errorEl.style.display = 'block';
                    }
                } catch (error) {
                    console.error("Error logging in:", error);
                    errorEl.textContent = 'An error occurred. Please try again.';
                    errorEl.style.display = 'block';
                }
            }
            
            function handleLogout() {
                appState.currentUser = null;
                sessionStorage.removeItem('clanPortalUser');
                detachAllListeners(); // लॉगआउट पर सभी listeners बंद करें
                appState.allUsersCache = []; // Cache खाली करें
                updateHeader();
                showPage('login-page');
            }

            async function handleRegister(e) {
                e.preventDefault();
                console.log('Registration attempt started...');
                
                const playerId = document.getElementById('reg-player-id').value;
                
                try {
                    const userDoc = await usersCollection.doc(playerId).get();
                    if (userDoc.exists) {
                        alert('Error: This Player ID is already taken. Please choose another one.');
                        return;
                    }
                    
                    const country = document.getElementById('reg-country').value;
                    let state = '';
                    if (country === 'India') {
                        state = document.getElementById('reg-india-state').value;
                    } else {
                        state = document.getElementById('reg-other-region').value;
                    }
                    
                    const primaryLang = document.getElementById('reg-lang-primary').value; 
                    const secondaryLangsEl = document.getElementById('reg-lang-secondary');
                    const secondaryLangs = [...secondaryLangsEl.selectedOptions].map(option => option.value);
                    
                    if (secondaryLangs.length === 0) {
                         alert('Error: Please select at least one secondary language.');
                         return;
                    }
                    const allLanguages = [primaryLang, ...secondaryLangs].join(', ');

                    const newPassword = Math.floor(10000 + Math.random() * 90000).toString();
                    
                    const newUser = {
                        id: playerId,
                        name: document.getElementById('reg-player-name').value,
                        clanName: document.getElementById('reg-clan-name').value,
                        clanId: document.getElementById('reg-clan-id').value,
                        dob: document.getElementById('reg-dob').value,
                        country: country,
                        state: state,
                        languages: allLanguages,
                        password: newPassword,
                        role: document.getElementById('reg-role').value, 
                        status: 'active',
                        createdAt: firebase.firestore.FieldValue.serverTimestamp() // सर्वर टाइम
                    };

                    await usersCollection.doc(newUser.id).set(newUser);
                    
                    const newRegData = {
                        id: newUser.id,
                        name: newUser.name,
                        password: newUser.password,
                        country: newUser.country,
                        state: newUser.state,
                        role: newUser.role,
                        languages: newUser.languages
                    };

                    await metaCollection.doc('main').update({
                        newRegistrations: firebase.firestore.FieldValue.arrayUnion(newRegData)
                    });
                    
                    console.log('Registration successful for user:', newUser.id);

                    alert(
                        'Registration Successful!\n\n' +
                        'Your account has been created and is now active.\n' +
                        'Your login details are:\n\n' +
                        `Player ID: ${newUser.id}\n` +
                        `Password: ${newUser.password}\n\n` +
                        'Please save this password. It is also visible to the Clan Leader.'
                    );
                    
                    document.getElementById('register-form').reset();
                    showPage('login-page');

                } catch (error) {
                    console.error('Registration failed:', error);
                    alert('An unexpected error occurred during registration. Please try again.');
                }
            }
            
            async function acknowledgeRegistration(userId) {
                try {
                    const metaDoc = await metaCollection.doc('main').get();
                    if (!metaDoc.exists) return;
                    const newRegistrations = metaDoc.data()?.newRegistrations || [];
                    
                    const updatedRegistrations = newRegistrations.filter(reg => reg.id !== userId);

                    await metaCollection.doc('main').update({
                        newRegistrations: updatedRegistrations
                    });

                } catch (error) {
                    console.error("Error acknowledging registration:", error);
                }
            }
            
            // ★★★ MODIFIED: handleChatMessagePost for file upload ★★★
            async function handleChatMessagePost(e, pagePrefix) {
                e.preventDefault();
                const input = document.getElementById(`${pagePrefix}-chat-input`);
                const text = input.value.trim();
                const file = appState.fileToUpload[pagePrefix];
                
                if (!text && !file) return; // Don't send empty messages

                const user = appState.currentUser;
                
                if (pagePrefix === 'sa' && !['Leader', 'Co-Leader'].includes(user.role)) {
                    document.getElementById('sa-post-error').style.display = 'block';
                    return;
                }
                document.getElementById('sa-post-error').style.display = 'none';

                let color = '#333333'; 
                let font = "'Poppins', sans-serif"; 

                if (user.role === 'Leader') {
                    color = document.getElementById(`${pagePrefix}-color-picker`).value;
                    font = document.getElementById(`${pagePrefix}-font-select`).value;
                } else if (user.role === 'Co-Leader' || user.role === 'Member' || user.role === 'Elder') {
                    const colorSelect = document.getElementById(`${pagePrefix}-color-select`);
                    if (colorSelect) {
                        color = colorSelect.value;
                    }
                }

                const message = {
                    userId: appState.currentUser.id,
                    text: text,
                    color: color,
                    font: font,
                    timestamp: firebase.firestore.FieldValue.serverTimestamp(),
                    type: 'text',
                    url: null,
                };
                
                // Clear inputs
                input.value = '';
                appState.fileToUpload[pagePrefix] = null;
                document.getElementById(`${pagePrefix}-file-input`).value = null;
                input.placeholder = 'Type your message...';


                try {
                    // Handle file upload first
                    if (file) {
                        const fileType = file.type.split('/')[0]; // 'image', 'video'
                        const filePath = `chat/${pagePrefix}/${Date.now()}_${file.name}`;
                        const fileRef = storage.ref(filePath);
                        
                        // Show uploading status
                        input.placeholder = 'Uploading file...';
                        
                        const uploadTask = fileRef.put(file);
                        
                        uploadTask.on('state_changed', 
                            (snapshot) => {
                                // Progress
                                const progress = (snapshot.bytesTransferred / snapshot.totalBytes) * 100;
                                input.placeholder = `Uploading... ${Math.round(progress)}%`;
                            }, 
                            (error) => {
                                // Error
                                console.error("Upload failed:", error);
                                alert("File upload failed.");
                                input.placeholder = 'Type your message...';
                            }, 
                            async () => {
                                // Success
                                const downloadURL = await uploadTask.snapshot.ref.getDownloadURL();
                                message.url = downloadURL;
                                if (fileType === 'image') message.type = 'image';
                                else if (fileType === 'video') message.type = 'video';
                                else message.type = 'file';
                                
                                // Now add the message to Firestore
                                await addMessageToDb(pagePrefix, message);
                                input.placeholder = 'Type your message...';
                            }
                        );
                    } else {
                        // Just send text message
                        await addMessageToDb(pagePrefix, message);
                    }
                } catch (error) {
                    console.error("Error sending message:", error);
                }
            }

            async function addMessageToDb(pagePrefix, message) {
                try {
                    const chatDocRef = messagesCollection.doc(pagePrefix === 'ga' ? 'general' : 'special');
                    await chatDocRef.collection('chats').add(message);
                } catch (error) {
                    console.error("Error adding message to DB:", error);
                }
            }

            async function handleNoticePost(e) {
                e.preventDefault();
                const title = document.getElementById('notice-title').value;
                const content = document.getElementById('notice-content').value;

                try {
                    await noticesCollection.add({
                        userId: appState.currentUser.id,
                        title: title,
                        content: content,
                        timestamp: firebase.firestore.FieldValue.serverTimestamp()
                    });
                    
                    document.getElementById('new-notice-form').reset();
                } catch (error) {
                    console.error("Error posting notice:", error);
                }
            }
            
            async function handleLeaderChatSubmit(e) {
                e.preventDefault();
                const subject = document.getElementById('leader-chat-subject').value;
                const message = document.getElementById('leader-chat-message').value;

                try {
                    const newDMRef = dmsCollection.doc();
                    await newDMRef.set({
                        id: newDMRef.id, 
                        threadId: newDMRef.id, 
                        userId: appState.currentUser.id,
                        subject: subject,
                        message: message,
                        timestamp: firebase.firestore.FieldValue.serverTimestamp(),
                        isReply: false
                    });
                    
                    alert('Your private message has been sent to the Leader.');
                    document.getElementById('leader-chat-form').reset();
                    showPage('home-page');
                } catch (error) {
                    console.error("Error sending DM:", error);
                }
            }
            
            async function handleQuarryReply(dmId) {
                const message = document.getElementById(`reply-dm-${dmId}`).value;
                if (!message) return;
                
                try {
                    const originalDM = await dmsCollection.doc(dmId).get();
                    if (!originalDM.exists) {
                        alert("Error: Could not find original message.");
                        return;
                    }
                    const threadId = originalDM.data().threadId;

                    await dmsCollection.add({
                        threadId: threadId, 
                        userId: appState.currentUser.id, 
                        subject: `Re: ${originalDM.data().subject}`,
                        message: message,
                        timestamp: firebase.firestore.FieldValue.serverTimestamp(),
                        isReply: true
                    });
                    
                } catch (error) {
                    console.error("Error replying to DM:", error);
                }
            }

            async function handleAdvisorySubmit(e) {
                e.preventDefault();
                const subject = document.getElementById('advisory-subject').value;
                const message = document.getElementById('advisory-message').value;

                try {
                    await adviceCollection.add({
                        userId: appState.currentUser.id,
                        subject: subject,
                        message: message,
                        timestamp: firebase.firestore.FieldValue.serverTimestamp(),
                        status: 'Submitted'
                    });
                    
                    alert('Your advice has been sent to the Leader.');
                    document.getElementById('advisory-form').reset();
                    showPage('home-page');
                } catch (error) {
                    console.error("Error submitting advice:", error);
                }
            }
            
            async function markAdvice(adviceId, status) {
                try {
                    await adviceCollection.doc(adviceId).update({
                        status: status
                    });
                } catch (error) {
                    console.error("Error marking advice:", error);
                }
            }

            async function handleCreateDraft(e) {
                e.preventDefault();
                const title = document.getElementById('draft-title').value;
                const description = document.getElementById('draft-description').value;
                
                const now = new Date(); 
                const fiveHours = 5 * 60 * 60 * 1000;
                const eightHours = 8 * 60 * 60 * 1000;
                
                const adviceEnds = new Date(now.getTime() + fiveHours);
                const votingEnds = new Date(now.getTime() + fiveHours + eightHours);
                
                try {
                    await draftsCollection.add({
                        title: title,
                        description: description,
                        status: 'advice',
                        createdAt: firebase.firestore.FieldValue.serverTimestamp(),
                        adviceEndsAt: adviceEnds, 
                        votingEndsAt: votingEnds,
                        advice: [],
                        votes: [],
                        resultSummary: ''
                    });
                    
                    alert('Draft published! The 5-hour advice phase has begun.');
                    document.getElementById('create-draft-form').reset();
                    showPage('drafts-voting-page');
                } catch (error) {
                    console.error("Error creating draft:", error);
                    alert('Error creating draft.');
                }
            }
            
            async function handleDraftAdvice(e) {
                e.preventDefault();
                const text = document.getElementById('draft-advice-input').value;
                if (!text) return;
                
                const newAdvice = {
                    userId: appState.currentUser.id,
                    text: text,
                    timestamp: new Date() 
                };
                
                try {
                    await draftsCollection.doc(appState.currentDraftId).update({
                        advice: firebase.firestore.FieldValue.arrayUnion(newAdvice)
                    });
                    
                    document.getElementById('draft-advice-form').reset();
                } catch (error) {
                    console.error("Error submitting draft advice:", error);
                }
            }

            async function handleDraftVote(draftId, vote) {
                const draftRef = draftsCollection.doc(draftId);

                try {
                    const doc = await draftRef.get();
                    if (!doc.exists) return;
                    const draft = doc.data();

                    if ((draft.votes || []).some(v => v.userId === appState.currentUser.id)) {
                        document.getElementById('draft-vote-error').textContent = 'You have already voted on this draft.';
                        document.getElementById('draft-vote-error').style.display = 'block';
                        return;
                    }
                    
                    const newVote = {
                        userId: appState.currentUser.id,
                        vote: vote,
                        weight: appState.currentUser.role === 'Leader' ? 3 : 1,
                        timestamp: new Date()
                    };

                    await draftRef.update({
                        votes: firebase.firestore.FieldValue.arrayUnion(newVote)
                    });
                    
                } catch (error) {
                    console.error("Error casting vote:", error);
                }
            }
            
            async function handleActivateLaw(draftId) {
                const draftRef = draftsCollection.doc(draftId);
                
                try {
                    const draftDoc = await draftRef.get();
                    if (!draftDoc.exists) return;
                    const draft = draftDoc.data();
                    
                    if (draft.status !== 'passed_pending_activation') return;

                    await draftRef.update({ status: 'active' });

                    await rulesCollection.add({
                        title: draft.title,
                        description: draft.description,
                        activatedAt: firebase.firestore.FieldValue.serverTimestamp()
                    });
                    
                    await noticesCollection.add({
                        userId: appState.currentUser.id, 
                        title: `New Rule Activated: ${draft.title}`,
                        content: `The draft "${draft.title}" has been passed and is now an official clan rule.\n\n${draft.description}`,
                        timestamp: firebase.firestore.FieldValue.serverTimestamp()
                    });
                    
                    alert('Law has been activated and added to the Rules of Clan. A notice has been posted.');
                } catch (error) {
                    console.error("Error activating law:", error);
                }
            }
            
            async function handleRemoveRule(ruleId) {
                if (!confirm('Are you sure you want to permanently delete this rule? This action does not require a vote and is final.')) {
                    return;
                }
                
                try {
                    await rulesCollection.doc(ruleId).delete();
                } catch (error) {
                    console.error("Error removing rule:", error);
                }
            }
            
            // ★★★ MODIFIED: Player Actions (Suspend added) ★★★
            async function handlePlayerAction(userId, task, value = null) {
                const userRef = usersCollection.doc(userId);
                
                try {
                    const userDoc = await userRef.get();
                    if (!userDoc.exists) return;
                    const user = userDoc.data();
                    if (user.role === 'Leader') return;

                    switch (task) {
                        case 'role':
                            await userRef.update({ role: value });
                            alert(`User ${user.name} role changed to ${value}.`);
                            break;
                        case 'suspend':
                            if (confirm(`Are you sure you want to suspend ${user.name}? This is temporary.`)) {
                                await userRef.update({ status: 'suspended' });
                            }
                            break;
                        case 'ban':
                            if (confirm(`Are you sure you want to ban ${user.name}? This is permanent.`)) {
                                await userRef.update({ status: 'banned' });
                            }
                            break;
                        case 'delete':
                            if (confirm(`Are you sure you want to PERMANENTLY DELETE ${user.name}? This action cannot be undone.`)) {
                                await userRef.delete();
                                await metaCollection.doc('main').update({
                                    cabinet: firebase.firestore.FieldValue.arrayRemove(userId)
                                });
                            }
                            break;
                        case 'reactivate':
                            await userRef.update({ status: 'active' });
                            break;
                    }
                    
                    renderPlayersActions(); // पेज को फिर से रेंडर करें

                } catch (error) {
                    console.error("Error performing player action:", error);
                }
            }
            
            async function handleCabinetSave(e) {
                e.preventDefault();
                const selected = [];
                document.querySelectorAll('#cabinet-player-options input[type="checkbox"]:checked').forEach(input => {
                    selected.push(input.value);
                });
                
                if (selected.length > 5) {
                    alert('Error: You can select a maximum of 5 cabinet players.');
                    return;
                }
                
                try {
                    await metaCollection.doc('main').set({ 
                        cabinet: selected
                    }, { merge: true }); 
                    
                    alert('Cabinet players updated.');
                    showPage('leader-dashboard-page');
                } catch (error) {
                    console.error("Error saving cabinet:", error);
                }
            }
            
            // ★★★ NEW: Chat Action Handlers (Pin, Delete) ★★★
            async function handlePinMessage(messageId, room) {
                if (appState.currentUser.role !== 'Leader') return;
                
                const fieldToUpdate = (room === 'ga') ? 'pinnedMessageGA' : 'pinnedMessageSA';
                
                try {
                    await metaCollection.doc('main').update({
                        [fieldToUpdate]: messageId 
                    });
                } catch (error) {
                    console.error("Error pinning message:", error);
                }
            }
            
            async function handleDeleteMessage(messageId, room) {
                if (appState.currentUser.role !== 'Leader') return;
                
                if (!confirm('Are you sure you want to delete this message forever?')) return;
                
                const roomName = (room === 'ga' ? 'general' : 'special');
                const msgRef = messagesCollection.doc(roomName).collection('chats').doc(messageId);

                try {
                    // Check if message has a file
                    const msgDoc = await msgRef.get();
                    if(msgDoc.exists && msgDoc.data().url) {
                        // Delete file from Storage
                        const fileRef = storage.refFromURL(msgDoc.data().url);
                        await fileRef.delete();
                    }
                    
                    // Delete message from Firestore
                    await msgRef.delete();
                    
                } catch (error) {
                    console.error("Error deleting message (and file):", error);
                }
            }
            
            // ★★★ NEW: Export Player Data Function ★★★
            async function handleExportData() {
                if (appState.currentUser.role !== 'Leader') return;

                try {
                    // We already have all users in the cache
                    const allData = {
                        exportedAt: new Date().toISOString(),
                        users: appState.allUsersCache
                    };
                    
                    const dataStr = JSON.stringify(allData, null, 2);
                    const blob = new Blob([dataStr], { type: 'application/json' });
                    const url = URL.createObjectURL(blob);
                    
                    const a = document.createElement('a');
                    a.href = url;
                    a.download = `clan_portal_export_${Date.now()}.json`;
                    document.body.appendChild(a);
                    a.click();
                    document.body.removeChild(a);
                    URL.revokeObjectURL(url);
                    
                } catch (error) {
                    console.error("Error exporting data:", error);
                    alert("Error exporting data.");
                }
            }


            // --- 13. Start the App ---
            initApp();
        });
    </script>

</body>
</html>
