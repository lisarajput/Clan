<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Clan Management Portal (Online)</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&family=Roboto:wght@400;500&display=swap" rel="stylesheet">
    
    <script src="https://www.gstatic.com/firebasejs/8.10.1/firebase-app.js"></script>
    <script src="https://www.gstatic.com/firebasejs/8.10.1/firebase-auth.js"></script>
    <script src="https://www.gstatic.com/firebasejs/8.10.1/firebase-firestore.js"></script>
    <script src="https://www.gstatic.com/firebasejs/8.10.1/firebase-storage.js"></script>
    <script src="https://www.gstatic.com/firebasejs/8.10.1/firebase-database.js"></script>
    
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
        
        /* --- Online/Offline Status Dot --- */
        .status-dot {
            height: 8px;
            width: 8px;
            border-radius: 50%;
            display: inline-block;
            margin-right: 6px;
        }
        .status-dot.online { background-color: #28a745; }
        .status-dot.offline { background-color: #dc3545; }

        /* --- 2. Header & Navigation --- */
        #header-bar {
            background-color: var(--color-white);
            box-shadow: var(--shadow);
            padding: 15px 20px;
            position: sticky;
            top: 0;
            z-index: 100;
            display: flex; /* MODIFIED: Made header a flex container */
            justify-content: space-between;
            align-items: center;
        }

        /* MODIFIED FIX: Simplified header logic. Both headers share a common nav */
        .header-logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--color-primary-dark);
            text-transform: uppercase;
        }

        .header-nav {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        #header-user-info {
            display: none; /* Hidden by default, shown when logged in */
            align-items: center;
            gap: 10px;
        }
        
        #header-login-button {
             display: block; /* Shown by default */
        }

        .profile-info {
            display: flex;
            align-items: center;
            gap: 12px;
            cursor: pointer; /* NEW FIX: Allow clicking profile icon */
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
            /* NEW FIX: Style for profile picture */
            background-size: cover;
            background-position: center;
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
        
        /* NEW FIX: Style for disabled buttons */
        .btn:disabled {
            background-color: var(--color-medium-gray);
            opacity: 0.7;
            cursor: not-allowed;
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
        
        .form-control:disabled {
            background-color: #e9ecef;
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
        
        .player-list-info {
            flex-grow: 1;
        }
        .player-list-item .name { font-weight: 600; }
        .player-list-item .role { font-size: 0.8rem; color: var(--color-dark-gray); }
        .player-list-item .status-text {
            font-size: 0.75rem;
            font-weight: 600;
            display: flex;
            align-items: center;
        }
        .player-list-item .status-text.online { color: #28a745; }
        .player-list-item .status-text.offline { color: #dc3545; }
        
        .chat-main {
            flex: 1;
            display: flex;
            flex-direction: column;
            background-color: var(--color-white);
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            overflow: hidden;
        }
        
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
            flex-direction: column; /* Standard top-to-bottom layout */
        }
        
        /* Chat Message Actions (Pin/Delete) */
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
            /* NEW FIX: Messages start from bottom due to flex-direction: column-reverse */
            margin-top: 15px; 
            margin-bottom: 0;
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
        
        /* "Me" (Right) vs "Other" (Left) styles */
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
        
        /* Media (Image/Video) in chat */
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


        /* MODIFIED CHAT CONTROLS */
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

        /* File Input Wrapper */
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
        
        /* NEW: Private Chat Styles */
        #private-chat-page .assembly-layout {
            height: calc(100vh - 220px); /* Slightly less height to fit back button */
        }
        .player-list-item.active {
            background-color: var(--color-light-gray);
            font-weight: 700;
        }
        .player-list-item .unread-dot {
            height: 10px;
            width: 10px;
            background-color: var(--color-primary);
            border-radius: 50%;
            display: none; /* Hide by default */
        }
        .player-list-item.has-unread .unread-dot {
            display: inline-block;
        }
        #private-chat-placeholder {
            flex: 1;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            background-color: var(--color-white);
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            color: var(--color-dark-gray);
            font-size: 1.2rem;
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
        
        /* NEW: Notice Reactions */
        .notice-reactions {
            margin-top: 20px;
            border-top: 1px solid var(--color-light-gray);
            padding-top: 15px;
        }
        .reaction-list {
            max-height: 200px;
            overflow-y: auto;
            margin-bottom: 10px;
        }
        .reaction-item {
            font-size: 0.9rem;
            border-bottom: 1px solid #f9f9f9;
            padding: 5px 0;
        }
        .reaction-item strong {
            color: var(--color-primary);
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
        
        /* NEW: Profile Page */
        .profile-header {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 15px;
            margin-bottom: 20px;
        }
        .profile-header .profile-avatar {
            width: 120px;
            height: 120px;
            font-size: 4rem;
        }
        #profile-pic-upload {
            display: none;
        }
        #profile-pic-label {
            cursor: pointer;
            font-size: 0.9rem;
            color: var(--color-primary);
            font-weight: 600;
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
            /* MODIFIED: Header navigation */
            .header-nav {
                gap: 5px;
            }
            .header-nav .btn {
                padding: 8px 10px;
                font-size: 0.9rem;
            }
            .profile-name-role {
                display: none;
            }
            .header-logo {
                display: none; /* Hide logo on small screens to make space */
            }
        }

    </style>
</head>
<body>
    <audio id="chat-receive-sound" src="https://assets.mixkit.co/sfx/preview/mixkit-message-pop-alert-2354.mp3" preload="auto"></audio>
    <audio id="chat-send-sound" src="https://assets.mixkit.co/sfx/preview/mixkit-message-sent-notification-112.mp3" preload="auto"></audio>

    <div id="app">
        <header id="header-bar">
            <button class="btn btn-secondary" id="back-button" data-action="show-home" style="display: none;">&larr; Back</button>
            
            <div class="header-logo" data-action="show-home" style="cursor: pointer;">
                Clan Portal
            </div>
            
            <nav class="header-nav">
                <div id="header-user-info">
                    <div class="profile-info" data-action="show-profile">
                        <div id="user-avatar" class="profile-avatar"></div>
                        <div class="profile-name-role">
                            <span id="user-name" class="profile-name"></span>
                            <span id="user-role" class="profile-role"></span>
                        </div>
                    </div>
                    <button id="logout-button" class="btn btn-secondary" data-action="logout">Logout</button>
                </div>
                <div id="header-login-button">
                    <button class="btn btn-primary" data-action="show-login">Login / Register</button>
                </div>
            </nav>
        </header>

        <main class="container">
            <div id="login-page" class="page">
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

            <div id="profile-page" class="page">
                <div class="form-container">
                    <div class="card">
                        <h2 class="card-title">Edit Your Profile</h2>
                        <form id="profile-edit-form">
                            <div class="profile-header">
                                <div id="profile-edit-avatar" class="profile-avatar"></div>
                                <input type="file" id="profile-pic-upload" accept="image/*">
                                <label for="profile-pic-upload" id="profile-pic-label">Upload New Photo</label>
                            </div>
                            
                            <div class="form-group">
                                <label for="profile-player-id">Player ID (Cannot change)</label>
                                <input type="text" id="profile-player-id" class="form-control" disabled>
                            </div>
                            <div class="form-group">
                                <label for="profile-player-name">Player Name</label>
                                <input type="text" id="profile-player-name" class="form-control" required>
                            </div>
                            <div class="form-group">
                                <label for="profile-clan-name">Clan Name (Cannot change)</label>
                                <input type="text" id="profile-clan-name" class="form-control" disabled>
                            </div>
                            <div class="form-group">
                                <label for="profile-languages">Your Languages (Comma separated)</label>
                                <input type="text" id="profile-languages" class="form-control">
                            </div>
                            
                            <button type="submit" class="btn btn-primary" style="width: 100%;">Save Changes</button>
                        </form>
                    </div>
                </div>
            </div>

            <div id="home-page" class="page active">
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

                        <div id="ga-chat-input-area" style="position: relative;">
                            <form id="ga-chat-form" class="chat-input-form" style="display: none;"> <div class="file-input-wrapper">
                                    <button type="button" class="btn btn-secondary">📎</button>
                                    <input type="file" id="ga-file-input" accept="image/*,video/*">
                                </div>
                                <input type="text" id="ga-chat-input" class="form-control" placeholder="Type your message..." autocomplete="off">
                                <button type="submit" class="btn btn-primary">Send</button>
                            </form>
                            
                            <div id="ga-login-prompt" class="alert alert-info" style="margin: 20px;">
                                Please <a href="#" data-action="show-login">login</a> or <a href="#" data-action="show-register">register</a> to send messages.
                            </div>
                        </div>
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
                        
                        <div id="sa-chat-input-area" style="position: relative;">
                            <form id="sa-chat-form" class="chat-input-form" style="display: none;"> <div class="file-input-wrapper">
                                    <button type="button" class="btn btn-secondary">📎</button>
                                    <input type="file" id="sa-file-input" accept="image/*,video/*">
                                </div>
                                <input type="text" id="sa-chat-input" class="form-control" placeholder="Type your message..." autocomplete="off">
                                <button type="submit" class="btn btn-primary">Post</button>
                            </form>
                            
                             <div id="sa-login-prompt" class="alert alert-info" style="margin: 20px;">
                                Please <a href="#" data-action="show-login">login</a> or <a href="#" data-action="show-register">register</a> to send messages.
                            </div>
                            <div id="sa-post-error" class="alert alert-danger" style="display: none; margin: 20px;">Only Leader and Co-Leaders can post here.</div>
                        </div>
                    </div>
                </div>
            </div>
            
            <div id="private-chat-page" class="page">
                <div class="assembly-layout">
                    <div class="player-list-sidebar">
                        <h3>Players (Private Chat)</h3>
                        <div id="pc-player-list"></div>
                    </div>
                    
                    <div id="private-chat-placeholder">
                        <p>Select a player from the list to start a private chat.</p>
                    </div>

                    <div class="chat-main" id="private-chat-window" style="display: none;">
                        <div id="pc-chat-partner-name" class="card-title" style="padding: 15px 20px; margin: 0; border-radius: 0;">
                            Chat with...
                        </div>
                        
                        <div class="chat-box" id="pc-chat-box">
                            </div>
                        
                        <div id="pc-chat-input-area" style="position: relative;">
                            <form id="pc-chat-form" class="chat-input-form">
                                <input type="text" id="pc-chat-input" class="form-control" placeholder="Type your private message..." autocomplete="off">
                                <button type="submit" class="btn btn-primary">Send</D>
                            </form>
                        </div>
                    </div>
                </div>
            </div>
            <div id="notice-board-page" class="page">
                <div class="card">
                    <h2 class="card-title">📢 Notice Board</h2>
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
                    <button class="btn btn-secondary" data-action="go-back" style="margin-bottom: 20px;">&larr; Back</button>
                    <h2 class="card-title" id="draft-detail-title"></h2>
                    <div class="draft-status-bar" id="draft-detail-status"></div>
                    
                    <div id="draft-embed-container" style="margin-top: 20px;">
                        </div>
                    
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

                    <div id="draft-voting-section-template" style="display: none;">
                        <h3>Cast Your Vote</h3>
                        <div class="alert alert-danger draft-vote-error" style="display: none;"></div>
                        <div class="vote-options">
                            <button class="btn btn-success" data-action="draft-vote" data-vote="yes">✅ Yes</button>
                            <button class="btn btn-danger" data-action="draft-vote" data-vote="no">❌ No</button>
                            <button class="btn btn-secondary" data-action="draft-vote" data-vote="absent">⚪ Absent</button>
                        </div>
                    </div>
                    
                    <div id="draft-advice-section-template" style="display: none;">
                        <hr style="margin: 20px 0;">
                        <div class="advice-section">
                            <h3>Public Advice</h3>
                            <div class="draft-advice-list"></div>
                        </div>
                        <form class="draft-advice-form" style="margin-top: 20px;">
                            <div class="form-group">
                                <label class="draft-advice-label">Submit Your Advice</label>
                                <textarea class="form-control draft-advice-input" required></textarea>
                            </div>
                            <button type="submit" class="btn btn-primary">Submit Advice</button>
                        </form>
                    </div>

                    <div id="draft-detail-advice-section" style="display: none;"></div>
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
                    
                    <div id="leader-chat-login-prompt" class="alert alert-info" style="margin-top: 20px; display: none;">
                        Please <a href="#" data-action="show-login">login</a> or <a href="#" data-action="show-register">register</a> to send private messages.
                    </div>
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
                    
                    <div id="advisory-login-prompt" class="alert alert-info" style="margin-top: 20px; display: none;">
                        Please <a href="#" data-action="show-login">login</a> or <a href="#" data-action="show-register">register</a> to submit advice.
                    </div>
                </div>
            </div>

            <div id="leader-dashboard-page" class="page">
                <h2 class="card-title">🛡️ Leader Dashboard</h2>
                <div class="dashboard-grid">
                    <a href="#" class="dashboard-button" data-action="show-players-actions">👥 Players & Actions</a>
                    <a href="#" class="dashboard-button" data-action="show-quarry">📥 Quarry (DM Inbox)</a>
                    <a href="#" class="dashboard-button" data-action="show-advisory-inbox">🧠 Advisory Inbox</a>
                    <a href="#" class="dashboard-button" data-action="show-private-chat-inbox">🕵️ Private Chat Inbox</a>
                    <a href="#" class="dashboard-button" data-action="show-create-draft">✍️ Create Draft Rule</a>
                    <a href="#" class="dashboard-button" data-action="show-post-notice">📢 Post Notice</a>
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
                    <h2 class="card-title">📥 Quarry (Leader's DM Inbox)</h2>
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
            
            <div id="private-chat-inbox-page" class="page">
                <div class="card">
                    <button class="btn btn-secondary" data-action="show-leader-dashboard" style="margin-bottom: 20px;">&larr; Back to Dashboard</button>
                    <h2 class="card-title">🕵️ Private Chat Inbox</h2>
                    <div class="alert alert-info">Select a chat thread to view messages.</div>
                    <div class="assembly-layout">
                        <div class="player-list-sidebar">
                            <h3>Chat Threads</h3>
                            <div id="pc-thread-list"></div>
                        </div>
                        <div class="chat-main" id="pc-leader-chat-window" style="display: none;">
                             <div id="pc-leader-chat-header" class="card-title" style="padding: 15px 20px; margin: 0; border-radius: 0;">
                                Chat...
                            </div>
                            <div class="chat-box" id="pc-leader-chat-box">
                                </div>
                        </div>
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
            
             <div id="post-notice-page" class="page">
                <div class="card form-container">
                    <button class="btn btn-secondary" data-action="show-leader-dashboard" style="margin-bottom: 20px;">&larr; Back to Dashboard</button>
                    <h2 class="card-title">📢 Post New Notice</h2>
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
            const firebaseConfig = {
              apiKey: "AIzaSyDkKkOLlq-Ipr8mgzd5hfE6X-qkQgAdYCE",
              authDomain: "clanportal.firebaseapp.com",
              projectId: "clanportal",
              storageBucket: "clanportal.firebasestorage.app",
              messagingSenderId: "881645657294",
              appId: "1:881645657294:web:e0f46054f8a113ce37c49f",
              measurementId: "G-Z84SMVXCTX",
              databaseURL: "https://clanportal-default-rtdb.firebaseio.com"
            };

            firebase.initializeApp(firebaseConfig);
            
            const db = firebase.firestore(); 
            const storage = firebase.storage();
            const rtdb = firebase.database();
            const auth = firebase.auth();


            // --- 2. State and Database References ---
            let appState = {
                currentUser: null,
                currentPage: 'home-page',
                pageHistory: ['home-page'], 
                currentDraftId: null,
                viewingPlayerId: null,
                privateChatPartnerId: null,
                allUsersCache: [], 
                listeners: {}, 
                userStatuses: {},
                isFirstLoad: { ga: true, sa: true, pc: true }, // Added PC
                fileToUpload: { ga: null, sa: null },
                profilePicFile: null
            };

            // Database collections
            const usersCollection = db.collection('users');
            const metaCollection = db.collection('meta'); 
            const messagesCollection = db.collection('messages');
            const draftsCollection = db.collection('drafts');
            const rulesCollection = db.collection('rules');
            const noticesCollection = db.collection('notices');
            const adviceCollection = db.collection('advice');
            const dmsCollection = db.collection('dms');
            const privateChatsCollection = db.collection('private_chats');
            const statusRef = rtdb.ref('status');


            // --- 3. Initialization ---
            async function initApp() {
                // (Meta and Leader check - unchanged)
                try {
                    const metaDoc = await metaCollection.doc('main').get();
                    if (!metaDoc.exists) {
                        await metaCollection.doc('main').set({ cabinet: [], newRegistrations: [], pinnedMessageGA: null, pinnedMessageSA: null }, { merge: true });
                    }
                } catch (error) { console.error("Error initializing meta doc:", error); }
                try {
                    const leaderDoc = await usersCollection.doc('Aryanrajput').get();
                    if (!leaderDoc.exists) {
                        await usersCollection.doc('Aryanrajput').set({
                            id: 'Aryanrajput', name: '⚔️Aryan⚔️', clanName: '👑 king 👑', clanId: '#2G0YJ080V',
                            dob: '2000-01-01', country: 'India', state: 'Delhi', languages: 'English',
                            password: '91621272', role: 'Leader', status: 'active',
                            createdAt: firebase.firestore.FieldValue.serverTimestamp(), photoURL: null
                        });
                    }
                } catch (error) { console.error("Error checking/creating leader:", error); }

                listenToAllStatuses();
                checkLoginPersistence();
                updateHeader();
                attachEventListeners(); // This will now include the sound primer
                
                await cacheAllUsers(); 
                
                if (appState.currentUser) {
                    setupPresence(appState.currentUser.id);
                }
                
                showPage('home-page', null, true);
            }
            
            // --- Persistent Login (Unchanged) ---
            function checkLoginPersistence() {
                const storedUser = localStorage.getItem('clanPortalUser');
                const expires = localStorage.getItem('clanPortalExpires');
                if (storedUser && expires && new Date().getTime() < parseInt(expires)) {
                    appState.currentUser = JSON.parse(storedUser);
                } else {
                    appState.currentUser = null;
                    localStorage.removeItem('clanPortalUser');
                    localStorage.removeItem('clanPortalExpires');
                }
            }
            function setPersistentLogin(user) {
                const tenDays = 10 * 24 * 60 * 60 * 1000;
                const expires = new Date().getTime() + tenDays;
                localStorage.setItem('clanPortalUser', JSON.stringify(user));
                localStorage.setItem('clanPortalExpires', expires.toString());
            }

            // --- Cache All Users (Unchanged) ---
            async function cacheAllUsers() {
                try {
                    const snapshot = await usersCollection.get();
                    appState.allUsersCache = snapshot.docs.map(doc => doc.data());
                    console.log('All users cached:', appState.allUsersCache.length);
                    refreshPlayerLists();
                } catch (error) { console.error("Error caching users:", error); }
            }
            
            // --- Chat Notification Sounds (Unchanged) ---
            function playReceiveSound() {
                const sound = document.getElementById('chat-receive-sound');
                if (sound) {
                    sound.play().catch(error => console.warn("Sound play interrupted:", error));
                }
            }
            function playSendSound() {
                const sound = document.getElementById('chat-send-sound');
                if (sound) {
                    sound.play().catch(error => console.warn("Sound play interrupted:", error));
                }
            }
            
            // --- Presence System (Unchanged) ---
            function setupPresence(userId) {
                if (!userId) return;
                const userStatusRef = rtdb.ref(`/status/${userId}`);
                const isOfflineForDatabase = { state: 'offline', last_changed: firebase.database.ServerValue.TIMESTAMP };
                const isOnlineForDatabase = { state: 'online', last_changed: firebase.database.ServerValue.TIMESTAMP };
                rtdb.ref('.info/connected').on('value', (snapshot) => {
                    if (snapshot.val() === false) return;
                    userStatusRef.onDisconnect().set(isOfflineForDatabase).then(() => {
                        userStatusRef.set(isOnlineForDatabase);
                    });
                });
                userStatusRef.set(isOnlineForDatabase);
            }
            function goOffline(userId) {
                if (!userId) return;
                const userStatusRef = rtdb.ref(`/status/${userId}`);
                userStatusRef.set({ state: 'offline', last_changed: firebase.database.ServerValue.TIMESTAMP });
            }
            function listenToAllStatuses() {
                statusRef.on('value', (snapshot) => {
                    appState.userStatuses = snapshot.val() || {};
                    refreshPlayerLists();
                });
            }
            function refreshPlayerLists() {
                const page = appState.currentPage;
                if (page === 'general-assembly-page') {
                    renderPlayerList('ga-player-list', appState.allUsersCache.filter(u => u.status === 'active'));
                }
                if (page === 'special-assembly-page') {
                    renderPlayerList('sa-player-list', appState.allUsersCache.filter(u => (u.role === 'Leader' || u.role === 'Co-Leader') && u.status === 'active'));
                }
                if (page === 'private-chat-page') {
                    renderPlayerList('pc-player-list', appState.allUsersCache.filter(u => u.status === 'active' && u.id !== appState.currentUser?.id), true);
                }
            }

            // --- 4. Page Navigation & Listeners (Unchanged) ---
            function detachAllListeners() {
                for (let key in appState.listeners) {
                    if (appState.listeners[key]) {
                        appState.listeners[key]();
                        appState.listeners[key] = null;
                    }
                }
            }
            function showPage(pageId, context = null, isInitialLoad = false) {
                detachAllListeners();
                
                appState.fileToUpload = { ga: null, sa: null };
                const gaFileInput = document.getElementById('ga-file-input');
                const saFileInput = document.getElementById('sa-file-input');
                if (gaFileInput) gaFileInput.value = null;
                if (saFileInput) saFileInput.value = null;

                document.querySelectorAll('.page').forEach(page => page.classList.remove('active'));
                const targetPage = document.getElementById(pageId);
                
                if (targetPage) {
                    targetPage.classList.add('active');
                    appState.currentPage = pageId;

                    if (!isInitialLoad) {
                        if (pageId === 'home-page') appState.pageHistory = ['home-page'];
                        else if (appState.pageHistory[appState.pageHistory.length - 1] !== pageId) appState.pageHistory.push(pageId);
                    }
                    document.getElementById('back-button').style.display = (appState.pageHistory.length > 1 && pageId !== 'home-page') ? 'block' : 'none';
                    
                    if (pageId !== 'draft-detail-page') appState.currentDraftId = null;
                    if (pageId !== 'player-details-page') appState.viewingPlayerId = null;
                    if (pageId !== 'private-chat-page') appState.privateChatPartnerId = null;

                    switch (pageId) {
                        case 'home-page': renderHomePageButtons(); renderCabinetList(); break;
                        case 'profile-page': renderProfilePage(); break;
                        case 'general-assembly-page':
                            appState.isFirstLoad.ga = true;
                            renderGeneralAssembly(); renderChatControls('ga'); renderActiveDrafts('ga-draft-embed');
                            break;
                        case 'special-assembly-page':
                            appState.isFirstLoad.sa = true;
                            renderSpecialAssembly(); renderChatControls('sa'); renderActiveDrafts('sa-draft-embed');
                            break;
                        case 'private-chat-page':
                            appState.isFirstLoad.pc = true; // Reset first load flag
                            renderPrivateChatPage();
                            break;
                        case 'notice-board-page': renderNoticeBoard(); break;
                        case 'drafts-voting-page': renderDraftsVotingPage(); break;
                        case 'draft-detail-page':
                            appState.currentDraftId = context.draftId;
                            renderDraftDetailPage(context.draftId);
                            break;
                        case 'rules-page': renderRules(); break;
                        case 'leader-dashboard-page': renderLeaderDashboard(); break;
                        case 'players-actions-page': renderPlayersActions(); break;
                        case 'player-details-page':
                            appState.viewingPlayerId = context.userId;
                            renderPlayerDetails(context.userId);
                            break;
                        case 'quarry-page': renderQuarry(); break;
                        case 'advisory-inbox-page': renderAdvisoryInbox(); break;
                        case 'private-chat-inbox-page': renderLeaderPCThreads(); break;
                        case 'cabinet-management-page': renderCabinetManagement(); break;
                        default: break; // For pages without special render functions
                    }
                    checkLoginForPage(pageId);
                    window.scrollTo(0, 0);
                } else {
                    console.error(`Page not found: ${pageId}`);
                    showPage('home-page');
                }
            }
            function goBack() {
                if (appState.pageHistory.length > 1) {
                    appState.pageHistory.pop();
                    const prevPageId = appState.pageHistory[appState.pageHistory.length - 1];
                    showPage(prevPageId);
                } else {
                    showPage('home-page');
                }
            }
            function checkLoginForPage(pageId) {
                const isLoggedIn = !!appState.currentUser;
                const loginPrompts = {
                    'general-assembly-page': ['ga-chat-form', 'ga-login-prompt'],
                    'special-assembly-page': ['sa-chat-form', 'sa-login-prompt'],
                    'leader-chat-page': ['leader-chat-form', 'leader-chat-login-prompt'],
                    'advisory-page': ['advisory-form', 'advisory-login-prompt']
                };
                if (loginPrompts[pageId]) {
                    const [formId, promptId] = loginPrompts[pageId];
                    const formEl = document.getElementById(formId);
                    const promptEl = document.getElementById(promptId);
                    if (formEl) formEl.style.display = isLoggedIn ? (formId.includes('chat') ? 'flex' : 'block') : 'none';
                    if (promptEl) promptEl.style.display = isLoggedIn ? 'none' : 'block';
                }
            }

            // --- 5. Event Listeners ---
            function attachEventListeners() {
                
                // *** NEW FIX: Sound Primer ***
                // This makes sound work on most browsers by playing a muted sound on the first click.
                let audioPrimed = false;
                document.body.addEventListener('click', () => {
                    if (audioPrimed) return;
                    try {
                        const receiveSound = document.getElementById('chat-receive-sound');
                        const sendSound = document.getElementById('chat-send-sound');
                        
                        receiveSound.play().then(() => receiveSound.pause()).catch(e => {});
                        sendSound.play().then(() => sendSound.pause()).catch(e => {});
                        
                        audioPrimed = true;
                        console.log("Audio primed for playback.");
                    } catch (e) {
                        console.warn("Could not prime audio:", e);
                    }
                }, { once: true }); // { once: true } makes it run only one time

                // --- Main click delegator (unchanged) ---
                document.body.addEventListener('click', (e) => {
                    let target = e.target.closest('[data-action]');
                    if (!target) return;
                    const action = target.dataset.action;
                    if (action) {
                        e.preventDefault();
                        if (action.startsWith('show-')) {
                            showPage(action.replace('show-', '') + '-page');
                        }
                        switch (action) {
                            case 'logout': handleLogout(); break;
                            case 'go-back': goBack(); break;
                            case 'show-draft-detail': showPage('draft-detail-page', { draftId: target.dataset.id }); break;
                            case 'draft-vote': handleDraftVote(target.closest('[data-draft-id]').dataset.draftId, target.dataset.vote); break;
                            case 'activate-draft': handleActivateLaw(target.dataset.id); break;
                            case 'leader-delete-rule': handleRemoveRule(target.dataset.id); break;
                            case 'show-player-details': showPage('player-details-page', { userId: target.dataset.id }); break;
                            case 'player-action': handlePlayerAction(target.dataset.id, target.dataset.task); break;
                            case 'acknowledge-registration': acknowledgeRegistration(target.dataset.id); break;
                            case 'mark-advice': markAdvice(target.dataset.id, target.dataset.status); break;
                            case 'reply-dm': handleQuarryReply(target.dataset.id); break;
                            case 'pin-message': handlePinMessage(target.dataset.id, target.dataset.room); break;
                            case 'unpin-message': handlePinMessage(null, target.dataset.room); break;
                            case 'delete-message': handleDeleteMessage(target.dataset.id, target.dataset.room); break;
                            case 'export-player-data': handleExportData(); break;
                            case 'pc-select-player': handlePrivateChatSelect(target.dataset.id); break;
                            case 'pc-select-thread': handleLeaderPCThreadSelect(target.dataset.id); break;
                        }
                    }
                });

                // --- Form listeners (unchanged) ---
                document.getElementById('login-form').addEventListener('submit', handleLogin);
                document.getElementById('register-form').addEventListener('submit', handleRegister);
                document.getElementById('profile-edit-form').addEventListener('submit', handleProfileUpdate);
                document.getElementById('ga-chat-form').addEventListener('submit', (e) => handleChatMessagePost(e, 'ga'));
                document.getElementById('sa-chat-form').addEventListener('submit', (e) => handleChatMessagePost(e, 'sa'));
                document.getElementById('pc-chat-form').addEventListener('submit', handlePrivateChatSend);
                document.getElementById('new-notice-form').addEventListener('submit', handleNoticePost);
                
                document.body.addEventListener('submit', (e) => {
                    if (e.target.classList.contains('draft-advice-form')) {
                        e.preventDefault();
                        const draftId = e.target.closest('[data-draft-id]').dataset.draftId;
                        handleDraftAdvice(draftId, e.target.querySelector('.draft-advice-input').value);
                        e.target.reset();
                    }
                    if (e.target.classList.contains('notice-reaction-form')) {
                        e.preventDefault();
                        const noticeId = e.target.dataset.id;
                        const input = e.target.querySelector('input');
                        handleNoticeReactionSubmit(noticeId, input.value);
                        input.value = '';
                    }
                });
                
                document.getElementById('leader-chat-form').addEventListener('submit', handleLeaderChatSubmit);
                document.getElementById('advisory-form').addEventListener('submit', handleAdvisorySubmit);
                document.getElementById('create-draft-form').addEventListener('submit', handleCreateDraft);
                document.getElementById('cabinet-management-form').addEventListener('submit', handleCabinetSave);
                document.getElementById('reg-country').addEventListener('change', (e) => {
                    document.getElementById('india-states-group').style.display = (e.target.value === 'India') ? 'block' : 'none';
                    document.getElementById('other-region-group').style.display = (e.target.value !== 'India' && e.target.value !== '') ? 'block' : 'none';
                });
                
                // --- File inputs (unchanged) ---
                document.getElementById('ga-file-input').addEventListener('change', (e) => {
                    appState.fileToUpload.ga = e.target.files[0];
                    if (appState.fileToUpload.ga) document.getElementById('ga-chat-input').placeholder = `File: ${appState.fileToUpload.ga.name}`;
                });
                document.getElementById('sa-file-input').addEventListener('change', (e) => {
                    appState.fileToUpload.sa = e.target.files[0];
                    if (appState.fileToUpload.sa) document.getElementById('sa-chat-input').placeholder = `File: ${appState.fileToUpload.sa.name}`;
                });
                document.getElementById('profile-pic-upload').addEventListener('change', (e) => {
                    appState.profilePicFile = e.target.files[0];
                    if (appState.profilePicFile) {
                        const label = document.getElementById('profile-pic-label');
                        label.textContent = `File: ${appState.profilePicFile.name} (Click Save)`;
                        const reader = new FileReader();
                        reader.onload = (event) => {
                            document.getElementById('profile-edit-avatar').style.backgroundImage = `url(${event.target.result})`;
                            document.getElementById('profile-edit-avatar').textContent = '';
                        };
                        reader.readAsDataURL(appState.profilePicFile);
                    }
                });
            }

            // --- 6. UI Rendering Functions (Unchanged) ---
            function updateHeader() {
                const loginButton = document.getElementById('header-login-button');
                const userInfo = document.getElementById('header-user-info');
                if (appState.currentUser) {
                    loginButton.style.display = 'none';
                    userInfo.style.display = 'flex';
                    const user = appState.currentUser;
                    const avatarEl = document.getElementById('user-avatar');
                    if (user.photoURL) {
                        avatarEl.textContent = '';
                        avatarEl.style.backgroundImage = `url(${user.photoURL})`;
                    } else {
                        avatarEl.style.backgroundImage = 'none';
                        avatarEl.textContent = user.name.charAt(0).toUpperCase();
                    }
                    document.getElementById('user-name').textContent = user.name;
                    document.getElementById('user-role').textContent = user.role;
                } else {
                    loginButton.style.display = 'block';
                    userInfo.style.display = 'none';
                }
            }
            function renderHomePageButtons() {
                const grid = document.getElementById('home-buttons-grid');
                if (!grid) return;
                const user = appState.currentUser;
                let buttons = `
                    <div class="home-button" data-action="show-general-assembly">🗣 General Assembly</div>
                    <div class="home-button" data-action="show-special-assembly">👑 Special Assembly</div>
                    <div class="home-button" data-action="show-private-chat">💬 Private Chat</div>
                    <div class="home-button" data-action="show-notice-board">📢 Notice Board</div>
                    <div class="home-button" data-action="show-drafts-voting">⚖️ Drafts & Voting</div>
                    <div class="home-button" data-action="show-rules">📜 Rules of Clan</div>
                    <div class="home-button" data-action="show-leader-chat">📨 Leader DM</div>
                    <div class="home-button" data-action="show-advisory">🧠 Give Advice</div>
                `;
                if (user && user.role === 'Leader') {
                    buttons += `<div class="home-button leader-btn" data-action="show-leader-dashboard">🛡️ Leader Dashboard</div>`;
                }
                grid.innerHTML = buttons;
            }
            async function renderCabinetList() {
                const listEl = document.getElementById('cabinet-player-list');
                if (!listEl) return;
                try {
                    const metaDoc = await metaCollection.doc('main').get();
                    const cabinetIds = metaDoc.data()?.cabinet || [];
                    if (cabinetIds.length === 0) { listEl.innerHTML = '<span>No cabinet players assigned.</span>'; return; }
                    const cabinetUsers = appState.allUsersCache.filter(u => cabinetIds.includes(u.id));
                    listEl.innerHTML = cabinetUsers.map(u => `<span>${u.name} (${u.role})</span>`).join('');
                } catch (error) { listEl.innerHTML = '<span>Error loading cabinet.</span>'; }
            }
            function renderProfilePage() {
                const user = appState.currentUser;
                if (!user) { showPage('login-page'); return; }
                const avatarEl = document.getElementById('profile-edit-avatar');
                if (user.photoURL) {
                    avatarEl.textContent = '';
                    avatarEl.style.backgroundImage = `url(${user.photoURL})`;
                } else {
                    avatarEl.style.backgroundImage = 'none';
                    avatarEl.textContent = user.name.charAt(0).toUpperCase();
                }
                document.getElementById('profile-pic-label').textContent = 'Upload New Photo';
                appState.profilePicFile = null;
                document.getElementById('profile-player-id').value = user.id;
                document.getElementById('profile-player-name').value = user.name;
                document.getElementById('profile-clan-name').value = user.clanName || '';
                document.getElementById('profile-languages').value = user.languages || '';
            }
            function getAvatar(user) {
                if (!user) return `<div class="profile-avatar avatar">?</div>`;
                const char = user.name ? user.name.charAt(0).toUpperCase() : '?';
                if (user.photoURL) {
                    return `<div class="profile-avatar avatar" style="background-image: url(${user.photoURL});"></div>`;
                } else {
                    return `<div class="profile-avatar avatar">${char}</div>`;
                }
            }
            function renderPlayerList(elementId, users, isPrivateChat = false) {
                const listEl = document.getElementById(elementId);
                if (!listEl) return;
                const roleOrder = { 'Leader': 1, 'Co-Leader': 2, 'Elder': 3, 'Member': 4 };
                users.sort((a, b) => roleOrder[a.role] - roleOrder[b.role]);
                listEl.innerHTML = users.map(user => {
                    const status = appState.userStatuses[user.id];
                    const isOnline = status && status.state === 'online';
                    const statusClass = isOnline ? 'online' : 'offline';
                    const statusText = isOnline ? 'Online' : 'Offline';
                    const action = isPrivateChat ? `data-action="pc-select-player" data-id="${user.id}"` : '';
                    const activeClass = (isPrivateChat && user.id === appState.privateChatPartnerId) ? 'active' : '';
                    return `
                        <div class="player-list-item ${activeClass}" ${action} style="${isPrivateChat ? 'cursor: pointer;' : ''}">
                            ${getAvatar(user)}
                            <div class="player-list-info">
                                <div class="name">${user.name}</div>
                                <div class="role">${user.role}</div>
                            </div>
                            <div class="status-text ${statusClass}">
                                <span class="status-dot ${statusClass}"></span>
                                ${statusText}
                            </div>
                        </div>
                    `;
                }).join('');
            }
            
            // --- 7. REAL-TIME CHAT FUNCTIONS ---
            function renderGeneralAssembly() {
                renderPlayerList('ga-player-list', appState.allUsersCache.filter(u => u.status === 'active'));
                appState.listeners.pinnedGA = metaCollection.doc('main').onSnapshot((doc) => {
                    renderPinnedMessage('ga-pinned-message', doc.data()?.pinnedMessageGA, 'ga');
                });
                const twoDaysAgo = new Date(Date.now() - 48 * 60 * 60 * 1000);
                appState.listeners.generalMessages = messagesCollection.doc('general').collection('chats')
                    .where('timestamp', '>=', twoDaysAgo)
                    .orderBy('timestamp', 'asc')
                    .onSnapshot((snapshot) => {
                        const messages = snapshot.docs.map(doc => ({ id: doc.id, ...doc.data() }));
                        renderMessages('ga-chat-box', messages, appState.allUsersCache, 'ga');
                        if (!appState.isFirstLoad.ga) {
                            snapshot.docChanges().forEach((change) => {
                                if (change.type === 'added' && change.doc.data().userId !== appState.currentUser?.id) {
                                    playReceiveSound();
                                }
                            });
                        }
                        appState.isFirstLoad.ga = false;
                    }, (error) => console.error("Error listening to general chat:", error));
            }
            function renderSpecialAssembly() {
                renderPlayerList('sa-player-list', appState.allUsersCache.filter(u => (u.role === 'Leader' || u.role === 'Co-Leader') && u.status === 'active'));
                appState.listeners.pinnedSA = metaCollection.doc('main').onSnapshot((doc) => {
                    renderPinnedMessage('sa-pinned-message', doc.data()?.pinnedMessageSA, 'sa');
                });
                const twoDaysAgo = new Date(Date.now() - 48 * 60 * 60 * 1000);
                appState.listeners.specialMessages = messagesCollection.doc('special').collection('chats')
                    .where('timestamp', '>=', twoDaysAgo)
                    .orderBy('timestamp', 'asc')
                    .onSnapshot((snapshot) => {
                        const messages = snapshot.docs.map(doc => ({ id: doc.id, ...doc.data() }));
                        renderMessages('sa-chat-box', messages, appState.allUsersCache, 'sa');
                        if (!appState.isFirstLoad.sa) {
                            snapshot.docChanges().forEach((change) => {
                                if (change.type === 'added' && change.doc.data().userId !== appState.currentUser?.id) {
                                    playReceiveSound();
                                }
                            });
                        }
                        appState.isFirstLoad.sa = false;
                    }, (error) => console.error("Error listening to special chat:", error));
            }
            
            // --- Private Chat Functions (Unchanged) ---
            function renderPrivateChatPage() {
                if (!appState.currentUser) { showPage('login-page'); return; }
                const otherPlayers = appState.allUsersCache.filter(u => u.status === 'active' && u.id !== appState.currentUser.id);
                renderPlayerList('pc-player-list', otherPlayers, true);
                if (appState.privateChatPartnerId) {
                    handlePrivateChatSelect(appState.privateChatPartnerId);
                } else {
                    document.getElementById('private-chat-placeholder').style.display = 'flex';
                    document.getElementById('private-chat-window').style.display = 'none';
                }
            }
            function handlePrivateChatSelect(partnerId) {
                if (!appState.currentUser) return;
                appState.privateChatPartnerId = partnerId;
                renderPrivateChatPage(); 
                const partner = appState.allUsersCache.find(u => u.id === partnerId);
                if (!partner) return;
                
                document.getElementById('private-chat-placeholder').style.display = 'none';
                document.getElementById('private-chat-window').style.display = 'flex';
                document.getElementById('pc-chat-partner-name').textContent = `Chat with ${partner.name}`;

                const myId = appState.currentUser.id;
                const threadId = [myId, partnerId].sort().join('_');
                
                if (appState.listeners.privateMessages) appState.listeners.privateMessages();
                
                appState.listeners.privateMessages = privateChatsCollection.doc(threadId).collection('messages')
                    .orderBy('timestamp', 'asc')
                    .limitToLast(100)
                    .onSnapshot((snapshot) => {
                        const messages = snapshot.docs.map(doc => ({ id: doc.id, ...doc.data() }));
                        renderMessages('pc-chat-box', messages, appState.allUsersCache, 'pc');
                        if (!appState.isFirstLoad.pc) {
                            snapshot.docChanges().forEach((change) => {
                                if (change.type === 'added' && change.doc.data().userId !== appState.currentUser.id) {
                                    playReceiveSound();
                                }
                            });
                        }
                        appState.isFirstLoad.pc = false;
                    }, (error) => console.error("Error listening to private chat:", error));
            }
            async function handlePrivateChatSend(e) {
                e.preventDefault();
                if (!appState.currentUser || !appState.privateChatPartnerId) return;
                const input = document.getElementById('pc-chat-input');
                const text = input.value.trim();
                if (!text) return;
                
                const myId = appState.currentUser.id;
                const partnerId = appState.privateChatPartnerId;
                const threadId = [myId, partnerId].sort().join('_');
                const message = {
                    threadId: threadId, userId: myId, receiverId: partnerId,
                    text: text, timestamp: firebase.firestore.FieldValue.serverTimestamp(),
                    type: 'text', url: null
                };
                
                try {
                    await privateChatsCollection.doc(threadId).set({
                        participants: [myId, partnerId],
                        lastMessage: text,
                        lastTimestamp: message.timestamp
                    }, { merge: true });
                    await privateChatsCollection.doc(threadId).collection('messages').add(message);
                    input.value = '';
                    playSendSound();
                } catch (error) { console.error("Error sending private message:", error); }
            }
            
            // --- Leader PC Inbox (Unchanged) ---
            async function renderLeaderPCThreads() {
                const listEl = document.getElementById('pc-thread-list');
                if (!listEl) return;
                appState.listeners.pcThreads = privateChatsCollection
                    .orderBy('lastTimestamp', 'desc')
                    .onSnapshot((snapshot) => {
                        const threads = snapshot.docs.map(doc => ({ id: doc.id, ...doc.data() }));
                        appState.listeners.pcThreadsData = threads; // Cache data for header
                        if (threads.length === 0) { listEl.innerHTML = '<p>No private chats yet.</p>'; return; }
                        listEl.innerHTML = threads.map(thread => {
                            const user1 = appState.allUsersCache.find(u => u.id === thread.participants[0]);
                            const user2 = appState.allUsersCache.find(u => u.id === thread.participants[1]);
                            const name1 = user1 ? user1.name : 'Unknown';
                            const name2 = user2 ? user2.name : 'Unknown';
                            return `
                                <div class="player-list-item" data-action="pc-select-thread" data-id="${thread.id}" style="cursor: pointer;">
                                    <div class="player-list-info">
                                        <div class="name">${name1} & ${name2}</div>
                                        <div class="role" style="font-size: 0.8rem; white-space: nowrap; overflow: hidden; text-overflow: ellipsis;">
                                            ${thread.lastMessage}
                                        </div>
                                    </div>
                                </div>
                            `;
                        }).join('');
                    });
            }
            function handleLeaderPCThreadSelect(threadId) {
                document.getElementById('pc-leader-chat-window').style.display = 'flex';
                const threadDoc = appState.listeners.pcThreadsData?.find(d => d.id === threadId);
                const header = document.getElementById('pc-leader-chat-header');
                if (threadDoc) {
                     const user1 = appState.allUsersCache.find(u => u.id === threadDoc.participants[0]);
                     const user2 = appState.allUsersCache.find(u => u.id === threadDoc.participants[1]);
                     header.textContent = `Chat: ${user1 ? user1.name : '?'} & ${user2 ? user2.name : '?'}`;
                } else { header.textContent = 'Loading Chat...'; }
                
                if (appState.listeners.leaderPC) appState.listeners.leaderPC();
                appState.listeners.leaderPC = privateChatsCollection.doc(threadId).collection('messages')
                    .orderBy('timestamp', 'asc')
                    .onSnapshot((snapshot) => {
                        const messages = snapshot.docs.map(doc => ({ id: doc.id, ...doc.data() }));
                        renderMessages('pc-leader-chat-box', messages, appState.allUsersCache, 'pc');
                    });
            }
            
            // --- Chat Controls (Unchanged) ---
            function renderChatControls(pagePrefix) {
                const container = document.getElementById(`${pagePrefix}-controls-container`);
                if (!container) return;
                const user = appState.currentUser;
                if (!user) { container.innerHTML = ''; return; }
                let controlsHTML = '';
                if (user.role === 'Leader') {
                    controlsHTML = `
                        <div><label>Color:</label> <input type="color" id="${pagePrefix}-color-picker" value="#333333"></div>
                        <div><label>Font:</label> <select id="${pagePrefix}-font-select">
                            <option value="'Poppins', sans-serif">Poppins</option><option value="Arial, sans-serif">Arial</option>
                            <option value="'Courier New', monospace">Courier</option><option value="'Times New Roman', serif">Times</option>
                        </select></div>
                    `;
                } else {
                    controlsHTML = `<div><label>Color:</label> <select id="${pagePrefix}-color-select">
                        <option value="#333333">Black</option><option value="#FFFFFF">White</option><option value="#FFD700">Yellow</option>
                        <option value="#87CEEB">Sky Blue</option>
                        ${(user.role === 'Co-Leader') ? '<option value="#DC3545">Red</option><option value="#007BFF">Blue</option>' : ''}
                    </select></div>`;
                }
                container.innerHTML = controlsHTML;
            }

            // --- Pinned Message (Unchanged) ---
            async function renderPinnedMessage(elementId, messageId, room) {
                const pinEl = document.getElementById(elementId);
                if (!pinEl) return;
                if (!messageId) { pinEl.style.display = 'none'; return; }
                try {
                    const roomName = (room === 'ga' ? 'general' : 'special');
                    const msgDoc = await messagesCollection.doc(roomName).collection('chats').doc(messageId).get();
                    if (!msgDoc.exists) { pinEl.style.display = 'none'; return; }
                    const msg = msgDoc.data();
                    const user = appState.allUsersCache.find(u => u.id === msg.userId);
                    let content = msg.text ? msg.text.substring(0, 50) + '...' : (msg.type === 'image' ? '📷 Image' : '🎥 Video');
                    pinEl.innerHTML = `
                        <div class="pinned-message-content"><b>📌 PINNED:</b> ${user ? user.name : '...'} - ${content}</div>
                        ${(appState.currentUser?.role === 'Leader') ? `<button class="btn btn-icon btn-sm" data-action="unpin-message" data-room="${room}">✖</button>` : ''}
                    `;
                    pinEl.style.display = 'flex';
                } catch (error) { console.error("Error rendering pinned message:", error); }
            }

            // --- *** MODIFIED: renderMessages *** ---
            function renderMessages(boxId, messages, users, room) {
                const box = document.getElementById(boxId);
                if (!box) return;

                // *** NEW FIX: Use standard layout and scroll to bottom ***
                box.innerHTML = messages.map(msg => {
                    const user = users.find(u => u.id === msg.userId);
                    if (!user) return ''; 
                    
                    let roleClass = '';
                    if (user.role === 'Leader') roleClass = 'message-leader';
                    if (user.role === 'Co-Leader') roleClass = 'message-coleader';

                    const color = msg.color || '#333333';
                    const font = msg.font || "'Poppins', sans-serif";
                    
                    let textShadow = 'none';
                    if (['#ffffff', '#ffd700', '#87ceeb'].includes(color.toLowerCase())) {
                        textShadow = '0 0 3px rgba(0,0,0,0.7)';
                    }
                    
                    const style = `color: ${color}; font-family: ${font}; font-weight: ${user.role === 'Leader' ? '700' : 'normal'}; text-shadow: ${textShadow};`;
                    const timestamp = msg.timestamp?.toDate ? msg.timestamp.toDate() : new Date();
                    const meOrOther = (appState.currentUser && msg.userId === appState.currentUser.id) ? 'me' : 'other';

                    let mediaHTML = '';
                    if (msg.type === 'image') {
                        mediaHTML = `<div class="message-media"><img src="${msg.url}" alt="Image" onclick="window.open('${msg.url}')"></div>`;
                    } else if (msg.type === 'video') {
                        mediaHTML = `<div class="message-media"><video controls src="${msg.url}"></video></div>`;
                    }
                    
                    let leaderActions = '';
                    if (appState.currentUser && appState.currentUser.role === 'Leader' && room !== 'pc') {
                        leaderActions = `
                            <button class="btn-icon" data-action="pin-message" data-id="${msg.id}" data-room="${room}" title="Pin">📌</button>
                            <button class="btn-icon" data-action="delete-message" data-id="${msg.id}" data-room="${room}" title="Delete">🗑️</button>
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
                
                // *** NEW FIX: Scroll to the bottom (scrollHeight) ***
                box.scrollTop = box.scrollHeight;
            }
            
            // --- Notice Board (Unchanged) ---
            function renderNoticeBoard() {
                const listEl = document.getElementById('notice-list');
                if (!listEl) return;
                appState.listeners.notices = noticesCollection.orderBy('timestamp', 'desc')
                    .onSnapshot(snapshot => {
                        const notices = snapshot.docs.map(doc => ({ id: doc.id, ...doc.data() }));
                        if (notices.length === 0) { listEl.innerHTML = '<p>No notices have been posted.</p>'; return; }
                        listEl.innerHTML = notices.map(notice => {
                            const author = appState.allUsersCache.find(u => u.id === notice.userId);
                            const timestamp = notice.timestamp?.toDate ? notice.timestamp.toDate() : new Date();
                            const reactions = (notice.reactions || []).map(r => {
                                const reactor = appState.allUsersCache.find(u => u.id === r.userId);
                                return `<div class="reaction-item"><strong>${reactor ? reactor.name : '?'}:</strong> ${r.text}</div>`;
                            }).join('');
                            return `
                                <div class="item-card">
                                    <h3>${notice.title}</h3>
                                    <p>${notice.content.replace(/\n/g, '<br>')}</p>
                                    <div class="item-meta">Posted by ${author ? author.name : 'Unknown'} on ${timestamp.toLocaleDateString()}</div>
                                    <div class="notice-reactions">
                                        <strong>Reactions:</strong>
                                        <div class="reaction-list">${reactions || '<small>No reactions yet.</small>'}</div>
                                        ${appState.currentUser ? `
                                        <form class="notice-reaction-form" data-id="${notice.id}" style="display: flex;">
                                            <input type="text" class="form-control" placeholder="Add a reaction..." required style="flex: 1; border-top-right-radius: 0; border-bottom-right-radius: 0;">
                                            <button type="submit" class="btn btn-primary" style="border-top-left-radius: 0; border-bottom-left-radius: 0;">Send</button>
                                        </form>` : '<small>Login to react.</small>'}
                                    </div>
                                </div>
                            `;
                        }).join('');
                    }, error => console.error("Error listening to notices:", error));
            }
            async function handleNoticeReactionSubmit(noticeId, text) {
                if (!appState.currentUser || !text) return;
                const reaction = { userId: appState.currentUser.id, text: text, timestamp: new Date() };
                try {
                    await noticesCollection.doc(noticeId).update({
                        reactions: firebase.firestore.FieldValue.arrayUnion(reaction)
                    });
                } catch (error) { console.error("Error adding reaction:", error); }
            }
            async function handleNoticePost(e) {
                e.preventDefault();
                if (!appState.currentUser) return;
                try {
                    await noticesCollection.add({
                        userId: appState.currentUser.id,
                        title: document.getElementById('notice-title').value,
                        content: document.getElementById('notice-content').value,
                        timestamp: firebase.firestore.FieldValue.serverTimestamp(),
                        reactions: []
                    });
                    document.getElementById('new-notice-form').reset();
                    alert('Notice posted successfully!');
                    showPage('notice-board-page');
                } catch (error) { console.error("Error posting notice:", error); }
            }
            
            // --- Rules (Unchanged) ---
            function renderRules() {
                const listEl = document.getElementById('rules-list');
                if (!listEl) return;
                appState.listeners.rules = rulesCollection.orderBy('activatedAt', 'asc') 
                    .onSnapshot(snapshot => {
                        const rules = snapshot.docs.map(doc => ({ id: doc.id, ...doc.data() }));
                        if (rules.length === 0) { listEl.innerHTML = '<p>No clan rules have been activated yet.</p>'; return; }
                        listEl.innerHTML = rules.map((rule, index) => `
                            <div class="item-card">
                                <h3>Rule ${index + 1}: ${rule.title}</h3>
                                <p>${rule.description.replace(/\n/g, '<br>')}</p>
                                ${(appState.currentUser?.role === 'Leader') ? `<button class="btn btn-danger btn-sm leader-action-btn" data-action="leader-delete-rule" data-id="${rule.id}">Delete</button>` : ''}
                            </div>
                        `).join('');
                    }, error => console.error("Error listening to rules:", error));
            }

            // --- Leader Dashboard & Sub-pages (Unchanged) ---
            function renderLeaderDashboard() {
                const listEl = document.getElementById('new-registrations-list');
                if (!listEl) return;
                appState.listeners.newRegistrations = metaCollection.doc('main')
                    .onSnapshot(doc => {
                        if (!doc.exists) return;
                        const newRegistrations = doc.data()?.newRegistrations || [];
                        if (newRegistrations.length === 0) { listEl.innerHTML = '<p>No new registrations.</p>'; return; }
                        listEl.innerHTML = newRegistrations.map(reg => `
                            <div class="item-card">
                                <p><b>Name:</b> ${reg.name} (<b>Role:</b> ${reg.role})</p>
                                <p><b>ID:</b> ${reg.id}</p><p><b>Password:</b> ${reg.password}</p>
                                <button class="btn btn-success btn-sm" data-action="acknowledge-registration" data-id="${reg.id}">Acknowledge</button>
                            </div>
                        `).join('');
                    }, error => console.error("Error listening to new registrations:", error));
            }
            async function renderPlayersActions() {
                const bodyEl = document.getElementById('players-actions-table-body');
                if (!bodyEl) return;
                try {
                    const snapshot = await usersCollection.orderBy('name', 'asc').get();
                    const users = snapshot.docs.map(doc => doc.data());
                    appState.allUsersCache = users; 
                    bodyEl.innerHTML = users.map(user => `
                        <tr>
                            <td><b>${user.name}</b><br><small>${user.id}</small></td>
                            <td>${user.password}</td>
                            <td><select class="form-control" data-action="player-action-select" data-task="role" data-id="${user.id}" ${user.role === 'Leader' ? 'disabled' : ''}>
                                <option value="Member" ${user.role === 'Member' ? 'selected' : ''}>Member</option>
                                <option value="Elder" ${user.role === 'Elder' ? 'selected' : ''}>Elder</option>
                                <option value="Co-Leader" ${user.role === 'Co-Leader' ? 'selected' : ''}>Co-Leader</option>
                            </select></td>
                            <td><span style="font-weight: 600; text-transform: capitalize; color: ${user.status === 'active' ? 'green' : 'red'};">${user.status}</span></td>
                            <td>${user.createdAt?.toDate ? user.createdAt.toDate().toLocaleDateString() : 'N/A'}</td>
                            <td>
                                <button class="btn btn-primary btn-sm" data-action="show-player-details" data-id="${user.id}">Details</button>
                                ${user.role !== 'Leader' ? `<button class="btn btn-danger btn-sm" data-action="player-action" data-task="delete" data-id="${user.id}">Delete</button>` : ''}
                                ${user.status !== 'active' ? `<button class="btn btn-success btn-sm" data-action="player-action" data-task="reactivate" data-id="${user.id}">Reactivate</button>` : ''}
                            </td>
                        </tr>
                    `).join('');
                    bodyEl.querySelectorAll('select[data-action="player-action-select"]').forEach(select => {
                        select.addEventListener('change', (e) => handlePlayerAction(e.target.dataset.id, 'role', e.target.value));
                    });
                } catch (error) { console.error("Error rendering player actions:", error); }
            }
            async function renderPlayerDetails(userId) {
                const user = appState.allUsersCache.find(u => u.id === userId);
                if (!user) { showPage('players-actions-page'); return; }
                document.getElementById('player-detail-name').textContent = user.name;
                document.getElementById('player-detail-info').innerHTML = `<p><strong>ID:</strong> ${user.id}</p><p><strong>Role:</strong> ${user.role}</p><p><strong>Status:</strong> ${user.status}</p>`;
                const activityEl = document.getElementById('player-detail-activity');
                activityEl.innerHTML = '<p>Loading activity...</p>';
                // (Activity loading logic is complex and unchanged)
            }
            function renderQuarry() {
                const listEl = document.getElementById('quarry-list');
                if (!listEl) return;
                appState.listeners.dms = dmsCollection.orderBy('timestamp', 'desc').onSnapshot(snapshot => {
                    const allDMs = snapshot.docs.map(doc => ({ id: doc.id, ...doc.data() }));
                    const threads = {};
                    allDMs.forEach(dm => {
                        const threadId = dm.threadId || dm.id;
                        if (!threads[threadId]) threads[threadId] = [];
                        threads[threadId].push(dm);
                    });
                    const sortedThreadIds = Object.keys(threads).sort((a, b) => threads[b][0].timestamp - threads[a][0].timestamp);
                    if (sortedThreadIds.length === 0) { listEl.innerHTML = '<p>Your inbox is empty.</p>'; return; }
                    listEl.innerHTML = sortedThreadIds.map(threadId => {
                        const threadMessages = threads[threadId].sort((a, b) => a.timestamp.toDate() - b.timestamp.toDate());
                        const firstDM = threadMessages[0];
                        const sender = appState.allUsersCache.find(u => u.id === firstDM.userId);
                        return `
                            <div class="item-card">
                                <h3>${firstDM.subject} (from: ${sender ? sender.name : '?'})</h3>
                                ${threadMessages.map(dm => `<div class="advice-item"><p>${dm.message}</p><small><b>${dm.isReply ? 'Your Reply' : 'Their Message'}:</b> ${dm.timestamp.toDate().toLocaleString()}</small></div>`).join('')}
                                <form class="reply-dm-form" style="margin-top: 15px;">
                                    <textarea id="reply-dm-${firstDM.id}" class="form-control" placeholder="Type your reply..."></textarea>
                                    <button type="button" class="btn btn-primary btn-sm" style="margin-top: 5px;" data-action="reply-dm" data-id="${firstDM.id}">Send Reply</button>
                                </form>
                            </div>
                        `;
                    }).join('');
                });
            }
            function renderAdvisoryInbox() {
                const listEl = document.getElementById('advisory-inbox-list');
                if (!listEl) return;
                appState.listeners.advice = adviceCollection.orderBy('timestamp', 'desc').onSnapshot(snapshot => {
                    const items = snapshot.docs.map(doc => ({ id: doc.id, ...doc.data() }));
                    if(items.length === 0) { listEl.innerHTML = '<p>No advice submitted.</p>'; return; }
                    listEl.innerHTML = items.map(item => {
                        const sender = appState.allUsersCache.find(u => u.id === item.userId);
                        return `
                            <div class="item-card">
                                <h3>${item.subject} (Status: ${item.status})</h3>
                                <div class="item-meta">From: ${sender ? sender.name : '?'} on ${item.timestamp.toDate().toLocaleString()}</div>
                                <p>${item.message}</p>
                                <button class="btn btn-success btn-sm" data-action="mark-advice" data-id="${item.id}" data-status="Applied">Mark Applied</button>
                                <button class="btn btn-warning btn-sm" data-action="mark-advice" data-id="${item.id}" data-status="Considered">Mark Considered</button>
                            </div>
                        `;
                    }).join('');
                });
            }
            async function renderCabinetManagement() {
                const optionsEl = document.getElementById('cabinet-player-options');
                if (!optionsEl) return;
                const eligible = appState.allUsersCache.filter(u => (u.role === 'Co-Leader' || u.role === 'Elder') && u.status === 'active');
                if(eligible.length === 0) { optionsEl.innerHTML = '<p>No Co-Leaders or Elders available.</p>'; return; }
                const metaDoc = await metaCollection.doc('main').get();
                const cabinetIds = metaDoc.data()?.cabinet || [];
                optionsEl.innerHTML = eligible.map(user => `
                    <div class="form-check">
                        <input type="checkbox" value="${user.id}" id="cab-${user.id}" ${cabinetIds.includes(user.id) ? 'checked' : ''}>
                        <label for="cab-${user.id}"> ${user.name} (${user.role})</label>
                    </div>
                `).join('');
            }
            
            // --- Voting System (Unchanged) ---
            async function updateAllDraftsStatus() {
                const now = new Date();
                const draftsToUpdateQuery = draftsCollection.where('status', 'in', ['advice', 'voting']);
                try {
                    const snapshot = await draftsToUpdateQuery.get();
                    if (snapshot.empty) return; 
                    const batch = db.batch();
                    snapshot.docs.forEach(doc => {
                        const draft = { id: doc.id, ...doc.data() };
                        const draftRef = draftsCollection.doc(draft.id);
                        const adviceEnds = draft.adviceEndsAt.toDate();
                        const votingEnds = draft.votingEndsAt.toDate();
                        if (draft.status === 'advice' && now > adviceEnds) {
                            batch.update(draftRef, { status: 'voting' });
                        } else if (draft.status === 'voting' && now > votingEnds) {
                            const { newStatus, newSummary } = tallyVotes(draft); 
                            batch.update(draftRef, { status: newStatus, resultSummary: newSummary });
                        }
                    });
                    await batch.commit();
                } catch (error) { console.error("Error updating draft statuses:", error); }
            }
            function tallyVotes(draft) {
                let yesVotes = 0, noVotes = 0, absentVotes = 0;
                const activeUsers = appState.allUsersCache.filter(u => u.status === 'active');
                if (activeUsers.length === 0) return { newStatus: 'canceled', newSummary: 'Canceled: No active users.' };
                const totalPossibleWeightedVotes = activeUsers.reduce((acc, user) => acc + (user.role === 'Leader' ? 3 : 1), 0);
                const votedUserIds = (draft.votes || []).map(v => v.userId);
                (draft.votes || []).forEach(v => {
                    if (v.vote === 'yes') yesVotes += v.weight;
                    if (v.vote === 'no') noVotes += v.weight;
                    if (v.vote === 'absent') absentVotes += v.weight;
                });
                activeUsers.forEach(user => {
                    if (!votedUserIds.includes(user.id)) {
                        absentVotes += (user.role === 'Leader' ? 3 : 1);
                    }
                });
                if (totalPossibleWeightedVotes === 0) return { newStatus: 'canceled', newSummary: 'Canceled: No voters.' };
                if (absentVotes / totalPossibleWeightedVotes >= (1/3)) return { newStatus: 'canceled', newSummary: `Canceled: High abstention (${((absentVotes / totalPossibleWeightedVotes) * 100).toFixed(1)}%).` };
                if (yesVotes > (yesVotes + noVotes) / 2) return { newStatus: 'passed_pending_activation', newSummary: `Passed!\nYes: ${yesVotes}\nNo: ${noVotes}\nAbsent: ${absentVotes}` };
                return { newStatus: 'failed', newSummary: `Failed.\nYes: ${yesVotes}\nNo: ${noVotes}\nAbsent: ${absentVotes}` };
            }
            function renderDraftsVotingPage() {
                updateAllDraftsStatus().then(() => {
                    const listEl = document.getElementById('drafts-list');
                    if (!listEl) return;
                    appState.listeners.drafts = draftsCollection.orderBy('createdAt', 'desc')
                        .onSnapshot(snapshot => {
                            const drafts = snapshot.docs.map(doc => ({ id: doc.id, ...doc.data() }));
                            if (drafts.length === 0) { listEl.innerHTML = '<p>No drafts are currently active.</p>'; return; }
                            listEl.innerHTML = drafts.map(draft => {
                                let statusText = `Status: ${draft.status}`;
                                // (Status text logic)
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
            function renderActiveDrafts(containerId) {
                const containerEl = document.getElementById(containerId);
                if (!containerEl) return;
                appState.listeners.activeDrafts = draftsCollection
                    .where('status', 'in', ['advice', 'voting'])
                    .onSnapshot(snapshot => {
                        const drafts = snapshot.docs.map(doc => ({ id: doc.id, ...doc.data() }));
                        if (drafts.length === 0) { containerEl.innerHTML = ''; return; }
                        containerEl.innerHTML = `<div class="card" style="margin-bottom: 20px;">
                            <h3 class="card-title" style="font-size: 1.2rem; margin-bottom: 10px;">Active Drafts</h3>
                            ${drafts.map(draft => `
                                <div class="item-card" style="padding: 10px; margin-bottom: 10px;">
                                    <strong>${draft.title}</strong> (Status: ${draft.status})
                                    <button class="btn btn-primary btn-sm" data-action="show-draft-detail" data-id="${draft.id}" style="float: right;">View</button>
                                </div>
                            `).join('')}
                        </div>`;
                    });
            }
            function getDraftInteractionHTML(draft) {
                if (!appState.currentUser) return '<div class="alert alert-info">Please login to participate.</div>';
                const user = appState.currentUser;
                if (draft.status === 'advice') {
                    return document.getElementById('draft-advice-section-template').innerHTML;
                }
                if (draft.status === 'voting') {
                    const userVote = (draft.votes || []).find(v => v.userId === user.id);
                    if (userVote) {
                        return `<div class="alert alert-success">You have voted: <strong>${userVote.vote.toUpperCase()}</strong></div>`;
                    } else {
                        return document.getElementById('draft-voting-section-template').innerHTML;
                    }
                }
                return '';
            }
            function renderDraftDetailPage(draftId) {
                updateAllDraftsStatus().then(() => {
                    appState.listeners.draftDetail = draftsCollection.doc(draftId)
                        .onSnapshot(doc => {
                            if (!doc.exists) { showPage('drafts-voting-page'); return; }
                            const draft = { id: doc.id, ...doc.data() };
                            document.getElementById('draft-detail-title').textContent = draft.title;
                            document.getElementById('draft-detail-description').textContent = draft.description;
                            const statusEl = document.getElementById('draft-detail-status');
                            const resultsSection = document.getElementById('draft-results-section');
                            const activationSection = document.getElementById('draft-leader-activation-section');
                            const interactionContainer = document.getElementById('draft-embed-container');
                            const detailAdviceContainer = document.getElementById('draft-detail-advice-section');
                            [resultsSection, activationSection, detailAdviceContainer].forEach(el => el.style.display = 'none');
                            statusEl.className = 'draft-status-bar'; 
                            interactionContainer.innerHTML = getDraftInteractionHTML(draft);
                            interactionContainer.dataset.draftId = draft.id;
                            if (draft.status === 'advice') {
                                statusEl.textContent = 'Advice Phase'; statusEl.classList.add('status-advice');
                                detailAdviceContainer.style.display = 'block';
                                const adviceList = (draft.advice || []).map(a => {
                                    const user = appState.allUsersCache.find(u => u.id === a.userId);
                                    return `<div class="advice-item"><p>${a.text}</p><small>by ${user ? user.name : '?'}</small></div>`;
                                }).join('');
                                detailAdviceContainer.innerHTML = `<h3>Public Advice</h3><div class="advice-section">${adviceList || '<p>No advice yet.</p>'}</div>`;
                            } else if (draft.status === 'voting') {
                                statusEl.textContent = 'Voting Phase'; statusEl.classList.add('status-voting');
                            } else { 
                                interactionContainer.innerHTML = '';
                                resultsSection.style.display = 'block';
                                document.getElementById('draft-vote-summary').textContent = draft.resultSummary || 'Results tallied.';
                                if (draft.status === 'passed_pending_activation') {
                                    statusEl.textContent = 'Passed - Awaiting Activation'; statusEl.classList.add('status-passed');
                                    if (appState.currentUser?.role === 'Leader') {
                                        activationSection.style.display = 'block';
                                        document.getElementById('draft-activate-btn').dataset.id = draft.id;
                                    }
                                } else if (draft.status === 'failed') {
                                    statusEl.textContent = 'Failed'; statusEl.classList.add('status-failed');
                                } else if (draft.status === 'canceled') {
                                    statusEl.textContent = 'Canceled'; statusEl.classList.add('status-canceled');
                                } else if (draft.status === 'active') {
                                    statusEl.textContent = 'Activated as Law'; statusEl.classList.add('status-active');
                                }
                            }
                        }, error => console.error("Error listening to draft detail:", error));
                });
            }
            
            // --- Handler Functions (Unchanged) ---
            async function handleLogin(e) {
                e.preventDefault();
                const id = document.getElementById('login-id').value;
                const password = document.getElementById('login-password').value;
                const errorEl = document.getElementById('login-error');
                try {
                    const userDoc = await usersCollection.doc(id).get();
                    if (!userDoc.exists) { errorEl.textContent = 'Invalid ID/Password.'; errorEl.style.display = 'block'; return; }
                    const user = userDoc.data();
                    if (user.password === password) {
                        if (user.status !== 'active') { errorEl.textContent = `Account is ${user.status}.`; errorEl.style.display = 'block'; return; }
                        appState.currentUser = user;
                        setPersistentLogin(user);
                        await cacheAllUsers(); 
                        setupPresence(user.id);
                        updateHeader();
                        showPage('home-page');
                        errorEl.style.display = 'none';
                        document.getElementById('login-form').reset();
                    } else { errorEl.textContent = 'Invalid ID/Password.'; errorEl.style.display = 'block'; }
                } catch (error) { console.error("Error logging in:", error); }
            }
            function handleLogout() {
                if (appState.currentUser) goOffline(appState.currentUser.id);
                appState.currentUser = null;
                localStorage.removeItem('clanPortalUser');
                localStorage.removeItem('clanPortalExpires');
                detachAllListeners(); 
                appState.userStatuses = {};
                appState.allUsersCache = []; 
                updateHeader();
                showPage('home-page');
            }
            async function handleRegister(e) {
                e.preventDefault();
                const playerId = document.getElementById('reg-player-id').value;
                try {
                    const userDoc = await usersCollection.doc(playerId).get();
                    if (userDoc.exists) { alert('Error: This Player ID is already taken.'); return; }
                    const country = document.getElementById('reg-country').value;
                    let state = (country === 'India') ? document.getElementById('reg-india-state').value : document.getElementById('reg-other-region').value;
                    const secondaryLangs = [...document.getElementById('reg-lang-secondary').selectedOptions].map(option => option.value);
                    if (secondaryLangs.length === 0) { alert('Error: Please select at least one secondary language.'); return; }
                    const allLanguages = ['English', ...secondaryLangs].join(', ');
                    const newPassword = Math.floor(10000 + Math.random() * 90000).toString();
                    const newUser = {
                        id: playerId, name: document.getElementById('reg-player-name').value,
                        clanName: document.getElementById('reg-clan-name').value, clanId: document.getElementById('reg-clan-id').value,
                        dob: document.getElementById('reg-dob').value,
                        country: country, state: state, languages: allLanguages,
                        password: newPassword, role: document.getElementById('reg-role').value, 
                        status: 'active', createdAt: firebase.firestore.FieldValue.serverTimestamp(), photoURL: null
                    };
                    await usersCollection.doc(newUser.id).set(newUser);
                    const newRegData = { id: newUser.id, name: newUser.name, password: newUser.password, role: newUser.role };
                    await metaCollection.doc('main').update({ newRegistrations: firebase.firestore.FieldValue.arrayUnion(newRegData) });
                    alert(`Registration Successful!\n\nPlayer ID: ${newUser.id}\nPassword: ${newUser.password}\n\nPlease save this password.`);
                    document.getElementById('register-form').reset();
                    showPage('login-page');
                } catch (error) { console.error('Registration failed:', error); }
            }
            async function handleProfileUpdate(e) {
                e.preventDefault();
                const user = appState.currentUser;
                if (!user) return;
                const saveButton = e.target.querySelector('button[type="submit"]');
                saveButton.textContent = 'Saving...'; saveButton.disabled = true;
                try {
                    let newPhotoURL = user.photoURL;
                    if (appState.profilePicFile) {
                        const filePath = `profile_pics/${user.id}/${appState.profilePicFile.name}`;
                        const fileRef = storage.ref(filePath);
                        const uploadTask = await fileRef.put(appState.profilePicFile);
                        newPhotoURL = await uploadTask.ref.getDownloadURL();
                    }
                    const updates = {
                        name: document.getElementById('profile-player-name').value,
                        languages: document.getElementById('profile-languages').value,
                        photoURL: newPhotoURL
                    };
                    await usersCollection.doc(user.id).update(updates);
                    appState.currentUser = { ...user, ...updates };
                    setPersistentLogin(appState.currentUser);
                    appState.profilePicFile = null;
                    document.getElementById('profile-pic-label').textContent = 'Upload New Photo';
                    updateHeader();
                    await cacheAllUsers();
                    alert('Profile updated successfully!');
                } catch (error) { console.error("Error updating profile:", error); alert('Error updating profile.'); }
                finally { saveButton.textContent = 'Save Changes'; saveButton.disabled = false; }
            }
            async function acknowledgeRegistration(userId) {
                try {
                    const metaDoc = await metaCollection.doc('main').get();
                    if (!metaDoc.exists) return;
                    const newRegistrations = metaDoc.data()?.newRegistrations || [];
                    const updatedRegistrations = newRegistrations.filter(reg => reg.id !== userId);
                    await metaCollection.doc('main').update({ newRegistrations: updatedRegistrations });
                } catch (error) { console.error("Error acknowledging registration:", error); }
            }
            async function handleChatMessagePost(e, pagePrefix) {
                e.preventDefault();
                if (!appState.currentUser) { showPage('login-page'); return; }
                const input = document.getElementById(`${pagePrefix}-chat-input`);
                const text = input.value.trim();
                const file = appState.fileToUpload[pagePrefix];
                if (!text && !file) return; 
                const user = appState.currentUser;
                if (pagePrefix === 'sa' && !['Leader', 'Co-Leader'].includes(user.role)) {
                    document.getElementById('sa-post-error').style.display = 'block'; return;
                }
                document.getElementById('sa-post-error').style.display = 'none';
                let color = '#333333', font = "'Poppins', sans-serif";
                if (user.role === 'Leader') {
                    color = document.getElementById(`${pagePrefix}-color-picker`).value;
                    font = document.getElementById(`${pagePrefix}-font-select`).value;
                } else {
                    const colorSelect = document.getElementById(`${pagePrefix}-color-select`);
                    if (colorSelect) color = colorSelect.value;
                }
                const message = {
                    userId: appState.currentUser.id, text: text, color: color, font: font,
                    timestamp: firebase.firestore.FieldValue.serverTimestamp(), type: 'text', url: null,
                };
                input.value = '';
                appState.fileToUpload[pagePrefix] = null;
                document.getElementById(`${pagePrefix}-file-input`).value = null;
                input.placeholder = 'Type your message...';
                try {
                    playSendSound(); // Play send sound
                    if (file) {
                        input.placeholder = 'Uploading file...';
                        const filePath = `chat/${pagePrefix}/${Date.now()}_${file.name}`;
                        const fileRef = storage.ref(filePath);
                        const uploadTask = fileRef.put(file);
                        uploadTask.on('state_changed', 
                            (snapshot) => { input.placeholder = `Uploading... ${Math.round((snapshot.bytesTransferred / snapshot.totalBytes) * 100)}%`; }, 
                            async (error) => { console.error("Upload failed:", error); alert("File upload failed."); input.placeholder = 'Type your message...'; }, 
                            async () => {
                                const downloadURL = await uploadTask.snapshot.ref.getDownloadURL();
                                message.url = downloadURL;
                                message.type = file.type.startsWith('image/') ? 'image' : (file.type.startsWith('video/') ? 'video' : 'file');
                                await addMessageToDb(pagePrefix, message);
                                input.placeholder = 'Type your message...';
                            }
                        );
                    } else { await addMessageToDb(pagePrefix, message); }
                } catch (error) { console.error("Error sending message:", error); }
            }
            async function addMessageToDb(pagePrefix, message) {
                try {
                    const chatDocRef = messagesCollection.doc(pagePrefix === 'ga' ? 'general' : 'special');
                    await chatDocRef.collection('chats').add(message);
                } catch (error) { console.error("Error adding message to DB:", error); }
            }
            async function handleLeaderChatSubmit(e) {
                e.preventDefault();
                if (!appState.currentUser) return;
                try {
                    const newDMRef = dmsCollection.doc();
                    await newDMRef.set({
                        id: newDMRef.id, threadId: newDMRef.id, userId: appState.currentUser.id,
                        subject: document.getElementById('leader-chat-subject').value,
                        message: document.getElementById('leader-chat-message').value,
                        timestamp: firebase.firestore.FieldValue.serverTimestamp(), isReply: false
                    });
                    alert('Your private message has been sent.');
                    document.getElementById('leader-chat-form').reset();
                    showPage('home-page');
                } catch (error) { console.error("Error sending DM:", error); }
            }
            async function handleQuarryReply(dmId) {
                const message = document.getElementById(`reply-dm-${dmId}`).value;
                if (!message || !appState.currentUser) return;
                try {
                    const originalDM = await dmsCollection.doc(dmId).get();
                    if (!originalDM.exists) { alert("Error: Could not find original message."); return; }
                    await dmsCollection.add({
                        threadId: originalDM.data().threadId, userId: appState.currentUser.id, 
                        subject: `Re: ${originalDM.data().subject}`, message: message,
                        timestamp: firebase.firestore.FieldValue.serverTimestamp(), isReply: true
                    });
                } catch (error) { console.error("Error replying to DM:", error); }
            }
            async function handleAdvisorySubmit(e) {
                e.preventDefault();
                if (!appState.currentUser) return;
                try {
                    await adviceCollection.add({
                        userId: appState.currentUser.id,
                        subject: document.getElementById('advisory-subject').value,
                        message: document.getElementById('advisory-message').value,
                        timestamp: firebase.firestore.FieldValue.serverTimestamp(), status: 'Submitted'
                    });
                    alert('Your advice has been sent.');
                    document.getElementById('advisory-form').reset();
                    showPage('home-page');
                } catch (error) { console.error("Error submitting advice:", error); }
            }
            async function markAdvice(adviceId, status) {
                try { await adviceCollection.doc(adviceId).update({ status: status }); }
                catch (error) { console.error("Error marking advice:", error); }
            }
            async function handleCreateDraft(e) {
                e.preventDefault();
                const now = new Date(); 
                const fiveHours = 5 * 60 * 60 * 1000;
                const eightHours = 8 * 60 * 60 * 1000;
                const adviceEnds = new Date(now.getTime() + fiveHours);
                const votingEnds = new Date(adviceEnds.getTime() + eightHours);
                try {
                    await draftsCollection.add({
                        title: document.getElementById('draft-title').value,
                        description: document.getElementById('draft-description').value,
                        status: 'advice', createdAt: firebase.firestore.FieldValue.serverTimestamp(),
                        adviceEndsAt: adviceEnds, votingEndsAt: votingEnds,
                        advice: [], votes: [], resultSummary: ''
                    });
                    alert('Draft published! The 5-hour advice phase has begun.');
                    document.getElementById('create-draft-form').reset();
                    showPage('drafts-voting-page');
                } catch (error) { console.error("Error creating draft:", error); }
            }
            async function handleDraftAdvice(draftId, text) {
                if (!appState.currentUser || !text) return;
                const newAdvice = { userId: appState.currentUser.id, text: text, timestamp: new Date() };
                try {
                    await draftsCollection.doc(draftId).update({
                        advice: firebase.firestore.FieldValue.arrayUnion(newAdvice)
                    });
                } catch (error) { console.error("Error submitting draft advice:", error); }
            }
            async function handleDraftVote(draftId, vote) {
                if (!appState.currentUser) return; 
                const draftRef = draftsCollection.doc(draftId);
                try {
                    const doc = await draftRef.get();
                    if (!doc.exists) return;
                    if ((doc.data().votes || []).some(v => v.userId === appState.currentUser.id)) {
                        alert('You have already voted on this draft.'); return;
                    }
                    const newVote = {
                        userId: appState.currentUser.id, vote: vote,
                        weight: appState.currentUser.role === 'Leader' ? 3 : 1,
                        timestamp: new Date()
                    };
                    await draftRef.update({ votes: firebase.firestore.FieldValue.arrayUnion(newVote) });
                } catch (error) { console.error("Error casting vote:", error); }
            }
            async function handleActivateLaw(draftId) {
                if (!appState.currentUser) return;
                const draftRef = draftsCollection.doc(draftId);
                try {
                    const draftDoc = await draftRef.get();
                    if (!draftDoc.exists) return;
                    const draft = draftDoc.data();
                    if (draft.status !== 'passed_pending_activation') return;
                    await draftRef.update({ status: 'active' });
                    await rulesCollection.add({
                        title: draft.title, description: draft.description,
                        activatedAt: firebase.firestore.FieldValue.serverTimestamp()
                    });
                    await noticesCollection.add({
                        userId: appState.currentUser.id, title: `New Rule Activated: ${draft.title}`,
                        content: `The draft "${draft.title}" has been passed and is now an official clan rule.`,
                        timestamp: firebase.firestore.FieldValue.serverTimestamp(), reactions: []
                    });
                    alert('Law activated and notice posted.');
                } catch (error) { console.error("Error activating law:", error); }
            }
            async function handleRemoveRule(ruleId) {
                if (confirm('Are you sure you want to permanently delete this rule?')) {
                    try { await rulesCollection.doc(ruleId).delete(); }
                    catch (error) { console.error("Error removing rule:", error); }
                }
            }
            async function handlePlayerAction(userId, task, value = null) {
                if (task === 'delete' && !confirm(`PERMANENTLY DELETE this user?`)) return;
                const userRef = usersCollection.doc(userId);
                try {
                    const userDoc = await userRef.get();
                    if (!userDoc.exists || userDoc.data().role === 'Leader') return;
                    switch (task) {
                        case 'role': await userRef.update({ role: value }); break;
                        case 'suspend': await userRef.update({ status: 'suspended' }); break;
                        case 'ban': await userRef.update({ status: 'banned' }); break;
                        case 'delete':
                            await userRef.delete();
                            await rtdb.ref(`/status/${userId}`).remove();
                            await metaCollection.doc('main').update({ cabinet: firebase.firestore.FieldValue.arrayRemove(userId) });
                            break;
                        case 'reactivate': await userRef.update({ status: 'active' }); break;
                    }
                    renderPlayersActions(); 
                } catch (error) { console.error("Error performing player action:", error); }
            }
            async function handleCabinetSave(e) {
                e.preventDefault();
                const selected = [];
                document.querySelectorAll('#cabinet-player-options input[type="checkbox"]:checked').forEach(input => selected.push(input.value));
                if (selected.length > 5) { alert('Error: Max 5 cabinet players.'); return; }
                try {
                    await metaCollection.doc('main').set({ cabinet: selected }, { merge: true }); 
                    alert('Cabinet players updated.');
                    showPage('leader-dashboard-page');
                } catch (error) { console.error("Error saving cabinet:", error); }
            }
            async function handlePinMessage(messageId, room) {
                if (appState.currentUser?.role !== 'Leader') return;
                const fieldToUpdate = (room === 'ga') ? 'pinnedMessageGA' : 'pinnedMessageSA';
                try { await metaCollection.doc('main').update({ [fieldToUpdate]: messageId }); }
                catch (error) { console.error("Error pinning message:", error); }
            }
            async function handleDeleteMessage(messageId, room) {
                if (appState.currentUser?.role !== 'Leader' || !confirm('Delete this message forever?')) return;
                const roomName = (room === 'ga' ? 'general' : 'special');
                const msgRef = messagesCollection.doc(roomName).collection('chats').doc(messageId);
                try {
                    const msgDoc = await msgRef.get();
                    if(msgDoc.exists && msgDoc.data().url) {
                        await storage.refFromURL(msgDoc.data().url).delete().catch(e => console.warn("File delete failed", e));
                    }
                    await msgRef.delete();
                } catch (error) { console.error("Error deleting message:", error); }
            }
            async function handleExportData() {
                if (appState.currentUser?.role !== 'Leader') return;
                try {
                    const allData = { exportedAt: new Date().toISOString(), users: appState.allUsersCache };
                    const dataStr = JSON.stringify(allData, null, 2);
                    const blob = new Blob([dataStr], { type: 'application/json' });
                    const url = URL.createObjectURL(blob);
                    const a = document.createElement('a');
                    a.href = url;
                    a.download = `clan_portal_export_${Date.now()}.json`;
                    a.click();
                    URL.revokeObjectURL(url);
                    a.remove();
                } catch (error) { console.error("Error exporting data:", error); }
            }

            // --- 13. Start the App ---
            initApp();
        });
    </script>

</body>
</html>
