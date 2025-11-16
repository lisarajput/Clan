<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Clan Command Hub</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&family=Roboto:wght@400;500;700&display=swap" rel="stylesheet">
    
    <script src="https://www.gstatic.com/firebasejs/8.10.1/firebase-app.js"></script>
    <script src="https://www.gstatic.com/firebasejs/8.10.1/firebase-auth.js"></script>
    <script src="https://www.gstatic.com/firebasejs/8.10.1/firebase-firestore.js"></script>
    <script src="https://www.gstatic.com/firebasejs/8.10.1/firebase-storage.js"></script>

    <style>
        /* 1. Global Styles & Variables (Light Theme) */
        :root {
            --color-bg-sidebar: #111b21;
            --color-bg-main: #e5ddd5; 
            --color-bg-card: #ffffff;
            --color-bg-chat-window: #e5ddd5;
            
            --color-text-primary: #0b0b0b;
            --color-text-secondary: #54656f;
            --color-text-light: #ffffff;
            
            --color-accent-blue: #0077b6;
            --color-accent-blue-hover: #005f90;
            
            --color-chat-self: #d9fdd3; /* Self message bubble */
            --color-chat-other: #ffffff; /* Other message bubble */
            
            --color-success: #25D366;
            --color-danger: #f85149;
            --color-warning: #f0c674;
            --color-leader: #fff8e1; /* Light gold for leader messages */
            --color-coleader: #f5f5f5; /* Light silver for co-leader */
            
            --shadow-light: 0 1px 3px rgba(0,0,0,0.05);
            --shadow-medium: 0 4px 12px rgba(0,0,0,0.1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', 'Roboto', sans-serif;
        }

        body {
            background-color: var(--color-bg-main);
            color: var(--color-text-primary);
            overflow-x: hidden;
            background-image: url('data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABgAAAAYCAYAAADgdz34AAAAAXNSR0IArs4c6QAAADFJREFUWEVjZJmY+T8DEjAwMDAwMDKgAwA3K/H/PwYkYJDMuAwkBiMNAAANTQFBKjv+kAAAAABJRU5ErkJggg==');
        }

        h1, h2, h3, h4, h5, h6 { color: var(--color-text-primary); margin-bottom: 1rem; }
        p { color: var(--color-text-secondary); line-height: 1.6; margin-bottom: 1rem; }
        a { color: var(--color-accent-blue); text-decoration: none; }
        pre { background: #f0f2f5; padding: 1rem; border-radius: 8px; overflow-x: auto; }
        
        /* 2. App Layout */
        .app-container { display: flex; min-height: 100vh; }
        .sidebar {
            width: 250px;
            background-color: var(--color-bg-sidebar);
            color: var(--color-text-light);
            padding: 2rem 1rem;
            position: fixed;
            left: 0; top: 0; height: 100%;
            transition: transform 0.3s ease-in-out;
            z-index: 1000;
            display: flex;
            flex-direction: column;
            overflow-y: auto;
        }
        .sidebar-header { text-align: center; margin-bottom: 2rem; padding-bottom: 1rem; border-bottom: 1px solid rgba(255,255,255,0.1); }
        .sidebar-header h2 { font-size: 1.5rem; color: var(--color-text-light); }
        .user-profile-sidebar { text-align: center; }
        .user-profile-sidebar #sidebar-username { font-weight: 600; font-size: 1.1rem; margin-bottom: 0.25rem; color: var(--color-text-light); }
        .user-profile-sidebar #sidebar-userrole { font-weight: 300; font-size: 0.9rem; color: var(--color-accent-blue); }
        .sidebar-auth-links { text-align: center; padding: 1rem 0; }
        .sidebar nav { flex-grow: 1; }
        .sidebar nav ul { list-style: none; }
        .sidebar nav ul li a, .logout-btn, .sidebar-auth-links .btn {
            display: block; padding: 1rem; color: var(--color-text-light); font-weight: 500;
            border-radius: 8px; margin-bottom: 0.5rem; transition: background-color 0.2s ease, color 0.2s ease;
            cursor: pointer; text-align: left;
        }
        .sidebar-auth-links .btn { text-align: center; background-color: var(--color-accent-blue); }
        .sidebar-auth-links .btn-link { background: none; color: var(--color-text-light); font-size: 1rem; }
        .sidebar nav ul li a:hover, .sidebar nav ul li a.active-nav, .logout-btn:hover {
            background-color: rgba(255,255,255,0.1); color: var(--color-text-light);
        }
        .logout-btn { background-color: var(--color-danger); }
        .nav-section-leader { border-top: 1px solid rgba(255,255,255,0.1); margin-top: 1rem; padding-top: 1rem; }
        .content-area { flex-grow: 1; padding: 2rem; margin-left: 250px; transition: margin-left 0.3s ease-in-out; }
        .content-area.full-width { margin-left: 0; }

        /* 3. Page & Helper Classes */
        .page { display: none; }
        .page.active { display: block; }
        .hidden { display: none !important; }

        /* 4. Hamburger Menu (Mobile) */
        .hamburger-menu {
            display: none; position: fixed; top: 15px; left: 15px; z-index: 1001;
            background: var(--color-bg-sidebar); border: none; color: white;
            padding: 0.5rem; font-size: 1.5rem; cursor: pointer; border-radius: 8px;
        }
        .sidebar-close-btn {
            display: none; background: none; border: none; color: white;
            font-size: 1.5rem; position: absolute; top: 10px; right: 10px; cursor: pointer;
        }

        /* 5. Responsive Design */
        @media (max-width: 768px) {
            .sidebar { transform: translateX(-100%); }
            .sidebar.active { transform: translateX(0); }
            .sidebar-close-btn { display: block; }
            .content-area { margin-left: 0; padding: 4rem 1rem 1rem 1rem; }
            .hamburger-menu { display: block; }
            
            /* Chat layout stacking */
            .assembly-layout { flex-direction: column; }
            .player-list-sidebar { width: 100%; max-height: 200px; border-right: none; border-bottom: 1px solid #ddd; }
            .chat-main { flex-grow: 1; }
        }
        
        /* 6. Form & UI Elements */
        .card { background-color: var(--color-bg-card); border-radius: 12px; padding: 1.5rem; margin-bottom: 1.5rem; box-shadow: var(--shadow-medium); }
        .form-group { margin-bottom: 1rem; }
        .form-group label { display: block; margin-bottom: 0.5rem; font-weight: 500; }
        .form-control {
            width: 100%; padding: 0.75rem; background-color: #f0f2f5;
            border: 1px solid #ddd; border-radius: 8px; color: var(--color-text-primary); font-size: 1rem;
        }
        .form-control:focus { outline: none; border-color: var(--color-accent-blue); box-shadow: 0 0 0 3px rgba(0, 119, 182, 0.2); }
        .btn { padding: 0.75rem 1.5rem; font-size: 1rem; font-weight: 600; border: none; border-radius: 8px; cursor: pointer; transition: all 0.2s ease; }
        .btn-primary { background-color: var(--color-accent-blue); color: var(--color-text-light); }
        .btn-primary:hover { background-color: var(--color-accent-blue-hover); }
        .btn-success { background-color: var(--color-success); color: var(--color-text-light); }
        .btn-danger { background-color: var(--color-danger); color: var(--color-text-light); }
        .btn-warning { background-color: var(--color-warning); color: var(--color-text-primary); }
        .btn-link { background: none; color: var(--color-accent-blue); padding: 0; cursor: pointer; font-size: 0.9rem; }
        .error-message { color: var(--color-danger); background-color: rgba(248, 81, 73, 0.1); border: 1px solid var(--color-danger); padding: 1rem; border-radius: 8px; margin-bottom: 1rem; display: none; }
        .loading-spinner {
            border: 4px solid #f3f3f3; border-top: 4px solid var(--color-accent-blue);
            border-radius: 50%; width: 30px; height: 30px; animation: spin 1s linear infinite;
            margin: 1rem auto; display: none;
        }
        @keyframes spin { 0% { transform: rotate(0deg); } 100% { transform: rotate(360deg); } }
        
        /* 7. Auth Page */
        .auth-container { max-width: 450px; margin: 3rem auto 0 auto; padding: 2rem; background-color: var(--color-bg-card); border-radius: 12px; box-shadow: var(--shadow-medium); }
        .auth-container h2 { text-align: center; color: var(--color-text-primary); margin-bottom: 2rem; }
        .auth-container .text-center { text-align: center; margin-top: 1.5rem; color: var(--color-text-secondary); }

        /* 8. NEW: Two-Column Chat Layout */
        .assembly-layout {
            display: flex;
            height: 80vh; /* Full height layout */
            background: var(--color-bg-card);
            border-radius: 12px;
            box-shadow: var(--shadow-medium);
            overflow: hidden;
        }
        .player-list-sidebar {
            width: 250px;
            background: #f0f2f5;
            border-right: 1px solid #ddd;
            overflow-y: auto;
            flex-shrink: 0;
        }
        .player-list-sidebar h3 {
            padding: 1rem;
            margin-bottom: 0;
            border-bottom: 1px solid #ddd;
            font-size: 1.1rem;
            position: sticky; top: 0; background: #f0f2f5;
        }
        .player-list-item {
            display: flex;
            align-items: center;
            padding: 0.75rem 1rem;
            border-bottom: 1px solid #e0e0e0;
        }
        .avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: var(--color-accent-blue);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 600;
            margin-right: 10px;
            flex-shrink: 0;
        }
        .player-list-item .info {
            overflow: hidden;
            white-space: nowrap;
        }
        .player-list-item .info .name {
            font-weight: 600;
            display: block;
            color: var(--color-text-primary);
        }
        .player-list-item .info .role {
            font-size: 0.8rem;
            color: var(--color-text-secondary);
        }
        
        .chat-main {
            flex-grow: 1;
            display: flex;
            flex-direction: column;
            height: 100%;
        }

        /* 9. NEW: Pinned Message */
        .pinned-message {
            padding: 0.5rem 1rem;
            background: var(--color-bg-card);
            border-bottom: 1px solid #eee;
            font-size: 0.9rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-shrink: 0;
        }
        .pinned-message-content {
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }
        .pinned-message-content strong { color: var(--color-accent-blue); }
        .unpin-btn {
            background: none; border: none; color: var(--color-text-secondary);
            cursor: pointer; font-size: 1.2rem;
        }

        /* 10. NEW: Chat Styles (WhatsApp Theme) */
        .chat-window {
            height: 100%; /* Takes remaining space */
            background-color: var(--color-bg-chat-window);
            overflow-y: auto;
            padding: 1rem;
            display: flex;
            flex-direction: column-reverse; /* New messages at bottom */
            flex-grow: 1; /* Key change */
        }
        .chat-messages { display: flex; flex-direction: column; gap: 0.5rem; }
        .chat-message {
            max-width: 70%; padding: 0.5rem 0.75rem; border-radius: 8px;
            word-wrap: break-word; box-shadow: var(--shadow-light);
            position: relative;
        }
        .chat-message .msg-content { font-size: 1rem; margin: 0; padding: 0; color: var(--color-text-primary); }
        .chat-message .msg-timestamp { display: block; font-size: 0.7rem; color: var(--color-text-secondary); margin-top: 0.25rem; text-align: right; }
        
        /* Me vs Other */
        .chat-message.self { background-color: var(--color-chat-self); align-self: flex-end; }
        .chat-message.other { background-color: var(--color-chat-other); align-self: flex-start; }
        
        /* Role Styling */
        .chat-message.other.message-leader { background-color: var(--color-leader); border: 1px solid #ffecb3; }
        .chat-message.other.message-coleader { background-color: var(--color-coleader); border: 1px solid #e0e0e0; }
        
        .message-sender {
            display: block; font-weight: 700; font-size: 0.9rem;
            margin-bottom: 0.25rem; color: var(--color-accent-blue);
        }
        .message-media { max-width: 100%; border-radius: 8px; margin-top: 0.5rem; }
        .message-media img { max-width: 100%; cursor: pointer; }
        .message-media video { max-width: 100%; }
        
        /* Leader Actions */
        .message-actions {
            display: none; /* Hidden by default */
            position: absolute;
            top: -10px;
            right: 0;
            background: white;
            border: 1px solid #ddd;
            border-radius: 8px;
            box-shadow: var(--shadow-medium);
            z-index: 10;
        }
        .chat-message:hover .message-actions { display: flex; }
        .message-actions button {
            background: none; border: none; padding: 0.5rem; cursor: pointer;
            font-size: 0.8rem;
        }
        .message-actions button:hover { background: #f0f0f0; }

        /* Chat Controls & Input */
        .chat-controls-container {
            padding: 0.5rem 1rem;
            background: #f0f2f5;
            border-top: 1px solid #ddd;
            flex-shrink: 0;
        }
        .chat-controls-container select, .chat-controls-container input {
            padding: 0.25rem;
            border-radius: 4px;
            border: 1px solid #ccc;
        }
        .chat-input-form {
            display: flex; gap: 0.5rem; background: #f0f2f5;
            padding: 0.5rem 1rem; border-top: 1px solid #ddd; flex-shrink: 0;
        }
        .chat-input-form input[type="text"] { flex-grow: 1; }
        .attach-btn {
            position: relative; cursor: pointer; padding: 0.75rem 1rem;
            background: var(--color-text-secondary); color: white;
        }
        .attach-btn:hover { background: var(--color-accent-blue); }
        .attach-btn input[type="file"] { position: absolute; top: 0; left: 0; width: 100%; height: 100%; opacity: 0; cursor: pointer; }
        
        /* Login Prompt */
        .login-prompt-overlay {
            text-align: center; padding: 1rem; background: rgba(255,255,255,0.8);
            border: 1px dashed var(--color-text-secondary); border-radius: 8px; margin-top: 1rem;
        }
        .login-prompt-overlay p { margin: 0; color: var(--color-text-primary); font-weight: 500; }
        .login-prompt-overlay .btn-link { font-weight: 600; font-size: 1rem; }

        /* 11. Ranking Grids */
        .ranking-grid-image { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 1.5rem; }
        .ranking-card-image { background-color: var(--color-bg-card); border-radius: 8px; overflow: hidden; box-shadow: var(--shadow-medium); }
        .ranking-card-image img { width: 100%; height: 200px; object-fit: cover; display: block; cursor: pointer; }
        .ranking-card-image h4 { padding: 1rem; text-align: center; margin-bottom: 0; }
        .ranking-list-pdf .ranking-item-pdf {
            display: flex; justify-content: space-between; align-items: center;
            padding: 1rem 1.5rem; background-color: var(--color-bg-card);
            border: 1px solid #eee; border-radius: 8px; margin-bottom: 1rem;
        }
        .ranking-item-pdf .info h4 { margin-bottom: 0.25rem; }
        .ranking-item-pdf .info p { margin-bottom: 0; font-size: 0.9rem; }
        
        /* 12. Voting & Drafts */
        .draft-list { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 1.5rem; }
        .draft-card {
            background-color: var(--color-bg-card); padding: 1.5rem; border-radius: 12px;
            cursor: pointer; transition: transform 0.2s ease, box-shadow 0.2s ease; box-shadow: var(--shadow-light);
        }
        .draft-card:hover { transform: translateY(-5px); box-shadow: var(--shadow-medium); }
        .draft-card h3 { color: var(--color-accent-blue); margin-bottom: 0.5rem; }
        .draft-status {
            font-weight: 600; padding: 0.25rem 0.5rem; border-radius: 6px;
            font-size: 0.9rem; display: inline-block; color: var(--color-text-primary);
        }
        .draft-status.advice { background-color: var(--color-warning); }
        .draft-status.voting { background-color: var(--color-accent-blue); color: white; }
        .draft-status.passed_pending_activation { background-color: var(--color-success); color: white; }
        .draft-status.failed { background-color: var(--color-danger); color: white; }
        .draft-status.canceled { background-color: #aaa; color: white; }
        .draft-status.active { background-color: #ffc978; }
        .countdown-timer { font-size: 1.2rem; font-weight: 600; color: var(--color-accent-blue); margin-bottom: 1rem; }
        .vote-buttons { display: flex; gap: 1rem; margin-bottom: 1rem; }
        .vote-buttons .btn { flex-grow: 1; }

        /* 13. Leader Dashboard */
        .dashboard-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 1.5rem; margin-bottom: 2rem; }
        .dashboard-grid-btn {
            background-color: var(--color-bg-card); color: var(--color-text-primary); padding: 1.5rem;
            border-radius: 12px; text-align: center; font-size: 1.2rem; font-weight: 600;
            cursor: pointer; transition: all 0.2s ease; box-shadow: var(--shadow-light);
        }
        .dashboard-grid-btn:hover { background-color: var(--color-accent-blue); color: white; box-shadow: var(--shadow-medium); }
        .leader-section { display: none; }
        .leader-section.active { display: block; }
        .leader-back-btn { margin-bottom: 1.5rem; }
        .mgmt-table { width: 100%; border-collapse: collapse; margin-top: 1rem; }
        .mgmt-table th, .mgmt-table td { padding: 0.75rem 1rem; border: 1px solid #eee; text-align: left; vertical-align: middle; }
        .mgmt-table th { background-color: #f9f9f9; }
        .mgmt-table td .btn { padding: 0.4rem 0.8rem; font-size: 0.8rem; margin-right: 0.25rem; }
        .mgmt-table td .form-control { font-size: 0.9rem; padding: 0.5rem; }
        .registration-password { font-family: 'Courier New', Courier, monospace; background: #eee; padding: 0.25rem 0.5rem; border-radius: 4px; color: var(--color-text-primary); font-weight: 700; }
        
        /* NEW: Upload Progress */
        .upload-progress-container {
            margin-top: 1rem;
            font-weight: 600;
        }

        /* 14. NEW: Player Dashboard */
        #page-player-dashboard .widget {
            background: var(--color-bg-card);
            border-radius: 8px;
            padding: 1.5rem;
            margin-bottom: 1.5rem;
            box-shadow: var(--shadow-light);
        }
        #page-player-dashboard .widget h3 {
            border-bottom: 1px solid #eee;
            padding-bottom: 0.5rem;
        }
        .chat-log {
            max-height: 200px;
            overflow-y: auto;
            background: #f9f9f9;
            border: 1px solid #eee;
            padding: 1rem;
            border-radius: 8px;
        }
        .chat-log p { margin-bottom: 0.5rem; font-size: 0.9rem; }
        
        /* 15. NEW: Force Mode Modals */
        .modal-overlay {
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            background: rgba(0,0,0,0.6);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 2000;
        }
        .modal-content {
            background: var(--color-bg-card);
            padding: 2rem;
            border-radius: 12px;
            max-width: 500px;
            width: 90%;
        }
        .modal-content h3 { margin-top: 0; }
        #modal-captcha-image {
            background: #f0f2f5;
            padding: 1rem;
            font-size: 2rem;
            font-family: 'Courier New', Courier, monospace;
            letter-spacing: 5px;
            text-align: center;
            border-radius: 8px;
            margin-bottom: 1rem;
            user-select: none;
        }
        #word-count {
            font-size: 0.9rem;
            color: var(--color-text-secondary);
        }

    </style>
</head>
<body>

    <div class="app-container">
        
        <aside class="sidebar" id="app-sidebar">
            <button class="sidebar-close-btn" id="sidebar-close-btn">&times;</button>
            <div class="sidebar-header">
                <h2>Clan Hub</h2>
                
                <div class="user-profile-sidebar hidden" id="user-profile-sidebar">
                    <h3 id="sidebar-username">Player Name</h3>
                    <p id="sidebar-userrole">Role</p>
                </div>
                
                <div class="sidebar-auth-links" id="sidebar-auth-links">
                    <button class="btn btn-primary" id="sidebar-login-btn">Login</button>
                    <button class="btn-link" id="sidebar-register-btn">Register</button>
                </div>
            </div>
            
            <nav>
                <ul>
                    <li><a href="#" class="nav-link" data-page="home">Home</a></li>
                    <li><a href="#" class="nav-link" data-page="player-dashboard">My Dashboard</a></li>
                    <li><a href="#" class="nav-link" data-page="chat-general">General Chat</a></li>
                    <li><a href="#" class="nav-link" data-page="rules">Rules & Laws</a></li>
                    <li><a href="#" class="nav-link" data-page="drafts-list">Voting (Drafts)</a></li>
                    <li><a href="#" class="nav-link" data-page="notice-board">Notice Board</a></li>
                    <li><a href="#" class="nav-link" data-page="rankings-pdf">PDF Rankings</a></li>
                    <li><a href="#" class="nav-link" data-page="rankings-image">Image Rankings</a></li>
                    <li><a href="#" class="nav-link" data-page="leader-dm">Leader Private Message</a></li>
                    <li><a href="#" class="nav-link" data-page="advisory">Give Advice</a></li>
                    
                    <li class="nav-section-leader hidden" id="nav-special-chat-link">
                         <a href="#" class="nav-link" data-page="chat-special">Special Assembly</a>
                    </li>
                    <li class="nav-section-leader hidden" id="nav-leader-link">
                        <a href="#" class="nav-link" data-page="leader-dashboard">Leader Dashboard</a>
                    </li>
                </ul>
            </nav>
            
            <button class="logout-btn hidden" id="logout-btn">Logout</button>
        </aside>
        
        <button class="hamburger-menu" id="hamburger-menu-btn">&#9776;</button>

        <main class="content-area" id="main-content">

            <div class="page" id="page-login">
                <div class="auth-container">
                    <h2>Clan Hub Login</h2>
                    <div class="error-message" id="login-error"></div>
                    <form id="login-form">
                        <div class="form-group">
                            <label for="login-id">Player ID</label>
                            <input type="text" id="login-id" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="login-password">Password</label>
                            <input type="password" id="login-password" class="form-control" required>
                        </div>
                        <div class="loading-spinner" id="login-spinner"></div>
                        <button type="submit" class="btn btn-primary" style="width: 100%;">Login</button>
                    </form>
                    <div class="text-center">
                        Don't have an account? 
                        <button class="btn-link" id="goto-register-btn">Register here</button>
                    </div>
                </div>
            </div>
            
            <div class="page" id="page-register">
                <div class="auth-container">
                    <h2>New Registration</h2>
                    <div class="error-message" id="register-error"></div>
                    <form id="register-form">
                        <div class="form-group">
                            <label for="reg-player-id">Player ID (e.g., #P0LYJCQ)</label>
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
                            <input type="text" id="reg-clan-id" class="form-control">
                        </div>
                        <div class="form-group">
                            <label for="reg-dob">Date of Birth</label>
                            <input type="date" id="reg-dob" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="reg-country">Country</label>
                            <select id="reg-country" class="form-control" required>
                                <option value="">Select Country...</option>
                                <option value="India">India</option>
                                <option value="USA">USA</option>
                                <option value="UK">UK</option>
                                <option value="Other">Other</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="reg-state">State / Region</label>
                            <input type="text" id="reg-state" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="reg-languages">Languages (comma-separated)</label>
                            <input type="text" id="reg-languages" class="form-control" placeholder="e.g., English, Hindi">
                        </div>
                        <div class="form-group">
                            <label for="reg-role">Role</label>
                            <select id="reg-role" class="form-control" required>
                                <option value="Member">Member</option>
                                <option value="Elder">Elder</option>
                                <option value="Co-Leader">Co-Leader</option>
                            </select>
                        </div>
                        <div class="loading-spinner" id="register-spinner"></div>
                        <button type="submit" class="btn btn-primary" style="width: 100%;">Register</button>
                    </form>
                    <div class="text-center">
                        Already have an account? 
                        <button class="btn-link" id="goto-login-btn">Login here</button>
                    </div>
                </div>
            </div>

            <div class="page" id="page-home">
                <div class="card">
                    <h1>Welcome, <span id="home-username">Guest</span>!</h1>
                    <p>This is the Clan Command Hub. Use the sidebar to navigate.</p>
                    <p>You can view rules, rankings, and notices as a guest. To chat, vote, or use your dashboard, please log in or register.</p>
                </div>
                <div class="card">
                    <h3>Pinned Message (General)</h3>
                    <p id="pinned-message-ga">Loading...</p>
                </div>
                <div class="card">
                    <h3>Pinned Message (Special Assembly)</h3>
                    <p id="pinned-message-sa">Loading...</p>
                </div>
            </div>

            <div class="page" id="page-chat-general">
                <h2>General Chat</h2>
                <div class="assembly-layout">
                    <aside class="player-list-sidebar">
                        <h3>Active Players</h3>
                        <div id="player-list-ga">
                            </div>
                    </aside>
                    
                    <div class="chat-main">
                        <div class="pinned-message" id="pinned-message-bar-ga">
                            <div class="pinned-message-content">
                                <strong>📌 PINNED:</strong> <span id="pinned-content-ga">Loading...</span>
                            </div>
                            <button class="unpin-btn hidden" id="unpin-btn-ga" data-action="unpin-message" data-chat="ga">&times;</button>
                        </div>
                        
                        <div class="chat-window" id="chat-window-ga">
                            <div class="chat-messages" id="chat-messages-ga">
                                </div>
                        </div>
                        
                        <div class="chat-controls-container hidden" id="chat-controls-ga">
                            </div>
                        
                        <form id="chat-form-ga" class="chat-input-form hidden">
                            <label for="file-upload-ga" class="btn attach-btn">
                                📎 <input type="file" id="file-upload-ga" accept="image/*,video/*">
                            </label>
                            <input type="text" id="chat-input-ga" class="form-control" placeholder="Type a message... (or attaching file)">
                            <button type="submit" class="btn btn-primary">Send</button>
                        </form>
                        <div class="loading-spinner" id="chat-spinner-ga"></div>
                        
                        <div class="login-prompt-overlay" id="chat-login-prompt-ga">
                            <p>Please <button class="btn-link" data-page="login">Login</button> or <button class="btn-link" data-page="register">Register</button> to join the chat.</p>
                        </div>
                    </div>
                </div>
            </div>
            
            <div class="page" id="page-chat-special">
                <h2>Special Assembly (Elders+)</h2>
                <div class="assembly-layout">
                    <aside class="player-list-sidebar">
                        <h3>Assembly Members</h3>
                        <div id="player-list-sa">
                            </div>
                    </aside>
                    
                    <div class="chat-main">
                        <div class="pinned-message" id="pinned-message-bar-sa">
                            <div class="pinned-message-content">
                                <strong>📌 PINNED:</strong> <span id="pinned-content-sa">Loading...</span>
                            </div>
                            <button class="unpin-btn hidden" id="unpin-btn-sa" data-action="unpin-message" data-chat="sa">&times;</button>
                        </div>
                        
                        <div class="chat-window" id="chat-window-sa">
                            <div class="chat-messages" id="chat-messages-sa">
                                </div>
                        </div>
                        
                        <div class="chat-controls-container hidden" id="chat-controls-sa">
                            </div>
                        
                        <form id="chat-form-sa" class="chat-input-form">
                            <label for="file-upload-sa" class="btn attach-btn">
                                📎 <input type="file" id="file-upload-sa" accept="image/*,video/*">
                            </label>
                            <input type="text" id="chat-input-sa" class="form-control" placeholder="Type a message...">
                            <button type="submit" class="btn btn-primary">Send</button>
                        </form>
                        <div class="loading-spinner" id="chat-spinner-sa"></div>
                        <div class="error-message" id="sa-post-error"></div>
                    </div>
                </div>
            </div>
            <div class="page" id="page-rules">
                <h2>Clan Rules & Laws</h2>
                <div id="rules-list">
                    <p>Loading rules...</p>
                </div>
            </div>

            <div class="page" id="page-notice-board">
                <h2>Notice Board</h2>
                
                <div class="card hidden" id="new-notice-form-container">
                    <h3>Post New Notice</h3>
                    <form id="new-notice-form">
                        <div class="form-group">
                            <label for="notice-title">Title</label>
                            <input type="text" id="notice-title" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="notice-content">Content</label>
                            <textarea id="notice-content" class="form-control" rows="5" required></textarea>
                        </div>
                        <button type="submit" class="btn btn-primary">Post Notice</button>
                    </form>
                </div>
                
                <div id="notice-list">
                    <p>Loading notices...</p>
                </div>
            </div>

            <div class="page" id="page-rankings-pdf">
                <h2>PDF Rankings</h2>
                <div class="ranking-list-pdf" id="pdf-rankings-list">
                    <p>Loading PDF rankings...</p>
                </div>
            </div>

            <div class="page" id="page-rankings-image">
                <h2>Image Rankings</h2>
                <div class="ranking-grid-image" id="image-rankings-list">
                    <p>Loading image rankings...</p>
                </div>
            </div>

            <div class="page" id="page-drafts-list">
                <h2>Proposals & Drafts</h2>
                <div class="draft-list" id="drafts-list-container">
                    <p>Loading drafts...</p>
                </div>
            </div>

            <div class="page" id="page-draft-detail">
                <button class="btn btn-link" id="back-to-drafts-list">&larr; Back to Drafts List</button>
                <div class="card">
                    <h2 id="draft-detail-title">Loading Draft...</h2>
                    <span class="draft-status" id="draft-detail-status"></span>
                    
                    <div id="draft-detail-content">
                        <pre id="draft-detail-desc"></pre> <div id="draft-advice-section" class="hidden">
                            <h3>Advice Phase</h3>
                            <div class="countdown-timer" id="draft-advice-timer"></div>
                            <form id="draft-advice-form" class="hidden">
                                <div class="form-group">
                                    <label for="draft-advice-input">Submit Your Advice</label>
                                    <textarea id="draft-advice-input" class="form-control" rows="3"></textarea>
                                </div>
                                <button type="submit" class="btn btn-primary">Submit Advice</button>
                            </form>
                            <div class="login-prompt-overlay" id="draft-advice-login-prompt">
                                <p>Please <button class="btn-link" data-page="login">Login</button> or <button class="btn-link" data-page="register">Register</button> to submit advice.</p>
                            </div>
                            <h4>Existing Advice:</h4>
                            <ul id="draft-advice-list"></ul>
                        </div>
                        
                        <div id="draft-voting-section" class="hidden">
                            <h3>Voting Phase</h3>
                            <div class="countdown-timer" id="draft-voting-timer"></div>
                            <div id="draft-vote-buttons" class="vote-buttons hidden">
                                <button class="btn btn-success" data-vote="yes">✅ Yes</button>
                                <button class="btn btn-danger" data-vote="no">❌ No</button>
                                <button class="btn btn-warning" data-vote="absent">⚪ Absent</button>
                            </div>
                            <p id="draft-voted-message" class="hidden"></p>
                            <div class="login-prompt-overlay" id="draft-voting-login-prompt">
                                <p>Please <button class="btn-link" data-page="login">Login</button> or <button class="btn-link" data-page="register">Register</button> to vote.</p>
                            </div>
                        </div>
                        
                        <div id="draft-result-section" class="hidden">
                            <h3>Result</h3>
                            <pre id="draft-result-summary"></pre>
                        </div>
                        
                        <div id="draft-leader-activation-section" class="hidden">
                            <h3>Leader Action Required</h3>
                            <p>This law has passed and is pending activation.</p>
                            <button class="btn btn-success" id="draft-activate-law-btn">ACTIVATE LAW</button>
                        </div>
                    </div>
                </div>
            </div>

            <div class="page" id="page-leader-dm">
                <h2>Leader Private Message</h2>
                <div class="card">
                    <form id="leader-dm-form" class="hidden">
                        <h3>Send a Private Message to the Leader</h3>
                        <p>This message will be sent to the Leader's private "Quarry Inbox" and is not visible to other players.</p>
                        <div class="form-group">
                            <label for="dm-subject">Subject</label>
                            <input type="text" id="dm-subject" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="dm-message">Message</label>
                            <textarea id="dm-message" class="form-control" rows="5" required></textarea>
                        </div>
                        <button type="submit" class="btn btn-primary">Send Message</button>
                    </form>
                    <div class="login-prompt-overlay" id="dm-login-prompt">
                        <p>Please <button class="btn-link" data-page="login">Login</button> or <button class="btn-link" data-page="register">Register</button> to send a private message.</p>
                    </div>
                </div>
            </div>

            <div class="page" id="page-advisory">
                <h2>Give Advice</h2>
                <div class="card">
                    <form id="advisory-form" class="hidden">
                        <h3>Submit to Advisory Inbox</h3>
                        <p>This advice will be sent to the Leader's private "Advisory Inbox" for consideration.</p>
                        <div class="form-group">
                            <label for="advisory-subject">Subject</label>
                            <input type="text" id="advisory-subject" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="advisory-message">Your Advice</label>
                            <textarea id="advisory-message" class="form-control" rows="5" required></textarea>
                        </div>
                        <button type="submit" class="btn btn-primary">Submit Advice</button>
                    </form>
                    <div class="login-prompt-overlay" id="advisory-login-prompt">
                        <p>Please <button class="btn-link" data-page="login">Login</button> or <button class="btn-link" data-page="register">Register</button> to submit advice.</p>
                    </div>
                </div>
            </div>
            
            <div class="page" id="page-player-dashboard">
                <h2>My Dashboard</h2>
                
                <div class="widget" id="player-dash-guest">
                    <h3>Guest</h3>
                    <div class="login-prompt-overlay" style="margin-top: 0;">
                         <p>Please <button class="btn-link" data-page="login">Login</button> or <button class="btn-link" data-page="register">Register</button> to view your dashboard.</p>
                    </div>
                </div>
                
                <div class="widget hidden" id="player-dash-member">
                    <h3>Member Dashboard</h3>
                    <p>Welcome, <span class="player-name"></span>!</p>
                    <p><strong>Role:</strong> Member</p>
                    <p><strong>Clan:</strong> <span class="player-clan"></span></p>
                    <p>You have no special powers. Participate in chat and voting to rank up!</p>
                </div>
                
                <div class="widget hidden" id="player-dash-elder">
                    <h3>Elder Dashboard</h3>
                    <p>Welcome, <span class="player-name"></span>!</p>
                    <p><strong>Role:</strong> Elder</p>
                    <p><strong>Clan:</strong> <span class="player-clan"></span></p>
                    <h4>Elder Powers:</h4>
                    <strong>View General Chat Activity (Last 10)</strong>
                    <div class="chat-log" id="elder-chat-log-ga"></div>
                </div>
                
                <div class="widget hidden" id="player-dash-coleader">
                    <h3>Co-Leader Dashboard</h3>
                    <p>Welcome, <span class="player-name"></span>!</p>
                    <p><strong>Role:</strong> Co-Leader ⭐</p>
                    <p><strong>Clan:</strong> <span class="player-clan"></span></p>
                    <h4>Co-Leader Powers:</h4>
                    <div class="form-group">
                        <strong>Mute Player (General Chat)</strong>
                        <form id="co-leader-mute-form">
                            <label for="mute-player-id">Player ID to Mute</label>
                            <input type="text" id="mute-player-id" class="form-control" placeholder="#PLAYERID">
                            <label for="mute-duration">Duration</label>
                            <select id="mute-duration" class="form-control">
                                <option value="1">1 Hour</option>
                                <option value="24">24 Hours</option>
                            </select>
                            <button type="submit" class="btn btn-warning" style="margin-top: 10px;">Apply Mute</button>
                        </form>
                    </div>
                    <strong>View General Chat Activity (Last 10)</strong>
                    <div class="chat-log" id="coleader-chat-log-ga"></div>
                    <strong>View Special Assembly Activity (Last 10)</strong>
                    <div class="chat-log" id="coleader-chat-log-sa"></div>
                </div>
            </div>
            
            <div class="page" id="page-leader-dashboard">
                <div id="leader-dash-main" class="leader-section active">
                    <h2>Leader Dashboard</h2>
                    <div class="dashboard-grid">
                        <div class="dashboard-grid-btn" data-section="new-registrations">New Registrations</div>
                        <div class="dashboard-grid-btn" data-section="player-management">Player Management</div>
                        <div class="dashboard-grid-btn" data-section="pdf-management">PDF Rankings</div>
                        <div class="dashboard-grid-btn" data-section="image-management">Image Rankings</div>
                        <div class="dashboard-grid-btn" data-section="draft-management">Drafts & Rules</div>
                        <div class="dashboard-grid-btn" data-section="cabinet-management">Cabinet</div>
                        <div class="dashboard-grid-btn" data-section="inbox-quarry">Quarry Inbox</div>
                        <div class="dashboard-grid-btn" data-section="inbox-advisory">Advisory Inbox</div>
                        <div class="dashboard-grid-btn" id="forcefully-btn" style="background-color: #dc3545; color: white; grid-column: 1 / -1;">
                            Forcefully Button
                        </div>
                    </div>
                </div>

                <div id="leader-section-new-registrations" class="leader-section card">
                    <button class="btn btn-link leader-back-btn">&larr; Back to Dashboard</button>
                    <h3>New Registrations</h3>
                    <div id="new-registrations-list"></div>
                </div>
                
                <div id="leader-section-player-management" class="leader-section card">
                    <button class="btn btn-link leader-back-btn">&larr; Back to Dashboard</button>
                    <h3>Player Management</h3>
                    <div style="overflow-x: auto;">
                        <table class="mgmt-table" id="player-management-table">
                            <thead>
                                <tr><th>Player</th><th>Role</th><th>Status</th><th>Actions</th></tr>
                            </thead>
                            <tbody></tbody>
                        </table>
                    </div>
                </div>

                <div id="leader-section-pdf-management" class="leader-section card">
                    <button class="btn btn-link leader-back-btn">&larr; Back to Dashboard</button>
                    <h3>Manage PDF Rankings</h3>
                    <form id="pdf-upload-form" class="card" style="background: #f9f9f9;">
                        <h4>Upload New PDF</h4>
                        <div class="form-group">
                            <label for="pdf-upload-title">Title</label>
                            <input type="text" id="pdf-upload-title" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="pdf-upload-desc">Description</label>
                            <input type="text" id="pdf-upload-desc" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="pdf-upload-file">PDF File</label>
                            <input type="file" id="pdf-upload-file" class="form-control" accept=".pdf" required>
                        </div>
                        <div class="upload-progress-container" id="pdf-upload-progress"></div> <button type="submit" class="btn btn-primary">Upload PDF</button>
                    </form>
                    <h4>Existing PDFs</h4>
                    <div id="pdf-management-list"></div>
                </div>

                <div id="leader-section-image-management" class="leader-section card">
                    <button class="btn btn-link leader-back-btn">&larr; Back to Dashboard</button>
                    <h3>Manage Image Rankings</h3>
                    <form id="image-upload-form" class="card" style="background: #f9f9f9;">
                        <h4>Upload New Image</h4>
                        <div class="form-group">
                            <label for="image-upload-title">Title</label>
                            <input type="text" id="image-upload-title" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="image-upload-file">Image File (will be compressed)</label>
                            <input type="file" id="image-upload-file" class="form-control" accept="image/*" required>
                        </div>
                        <div class="upload-progress-container" id="image-upload-progress"></div> <button type="submit" class="btn btn-primary">Upload Image</button>
                    </form>
                    <h4>Existing Images</h4>
                    <div id="image-management-list" class="ranking-grid-image"></div>
                </div>
                
                <div id="leader-section-draft-management" class="leader-section card">
                    <button class="btn btn-link leader-back-btn">&larr; Back to Dashboard</button>
                    <h3>Manage Drafts & Rules</h3>
                    <form id="draft-create-form" class="card" style="background: #f9f9f9;">
                        <h4>Create New Draft</h4>
                        <div class="form-group">
                            <label for="draft-create-title">Title</label>
                            <input type="text" id="draft-create-title" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="draft-create-desc">Description / Content (supports newlines)</label>
                            <textarea id="draft-create-desc" class="form-control" rows="5" required></textarea>
                        </div>
                        <button type="submit" class="btn btn-primary">Create & Publish Draft</button>
                    </form>
                    <h4>Existing Drafts</h4>
                    <p>Go to the <a href="#" class="nav-link" data-page="drafts-list">Public Drafts List</a> to manage or activate them.</p>
                </div>
                
                <div id="leader-section-cabinet-management" class="leader-section card">
                    <button class="btn btn-link leader-back-btn">&larr; Back to Dashboard</button>
                    <h3>Manage Cabinet</h3>
                    <p>Select up to 5 Elders or Co-Leaders for the Cabinet.</p>
                    <form id="cabinet-form">
                        <div id="cabinet-checkbox-list"></div>
                        <button type="submit" class="btn btn-primary">Save Cabinet</button>
                    </form>
                </div>
                
                <div id="leader-section-inbox-quarry" class="leader-section card">
                    <button class="btn btn-link leader-back-btn">&larr; Back to Dashboard</button>
                    <h3>Quarry Inbox (Private DMs)</h3>
                    <div id="inbox-quarry-list"><p>Loading messages...</p></div>
                </div>
                
                <div id="leader-section-inbox-advisory" class="leader-section card">
                    <button class="btn btn-link leader-back-btn">&larr; Back to Dashboard</button>
                    <h3>Advisory Inbox</h3>
                    <div id="inbox-advisory-list"><p>Loading messages...</p></div>
                </div>
            </div>

            <div class="page" id="page-force-mode-dashboard">
                <div class="card" style="border: 3px solid var(--color-danger);">
                    <h2 style="color: var(--color-danger); text-align: center;">🚨 FORCE MODE ACTIVE 🚨</h2>
                    <p style="text-align: center; color: var(--color-danger);">All actions are logged. Misuse will result in consequences.</p>
                    <button class="btn btn-link" id="force-mode-exit-btn">&larr; Exit Force Mode & Return to Main Dashboard</button>
                </div>

                <div class="card">
                    <h3>Full Player Management (Force Mode)</h3>
                    <p>You can now edit all player data. Be careful.</p>
                    <div style="overflow-x: auto;">
                        <table class="mgmt-table" id="force-player-management-table">
                            <thead>
                                <tr><th>Player</th><th>Role</th><th>Status</th><th>Chat</th><th>Actions</th></tr>
                            </thead>
                            <tbody></tbody>
                        </table>
                    </div>
                </div>
                
                <div class="card">
                    <h3>Global Chat Moderation (Force Mode)</h3>
                    <p>Delete any message from any chat.</p>
                    <h4>General Chat Log</h4>
                    <div class="chat-log" id="force-chat-log-ga"></div>
                    <h4 style="margin-top: 1rem;">Special Assembly Log</h4>
                    <div class="chat-log" id="force-chat-log-sa"></div>
                </div>
                
                <div class="card">
                    <h3>View All Private Inboxes (Force Mode)</h3>
                    <h4>All Quarry (DM) Messages</h4>
                    <div class="chat-log" id="force-inbox-quarry"></div>
                    <h4 style="margin-top: 1rem;">All Advisory Messages</h4>
                    <div class="chat-log" id="force-inbox-advisory"></div>
                </div>
            </div>

        </main> </div> <div class="modal-overlay hidden" id="modal-force-verify-1">
        <div class="modal-content">
            <h3>Step 1/6: Re-enter Credentials</h3>
            <p>To proceed, please re-authenticate.</p>
            <div class="error-message" id="force-modal-error-1"></div>
            <form id="force-form-1">
                <div class="form-group">
                    <label for="force-id-1">Player ID</label>
                    <input type="text" id="force-id-1" class="form-control" required>
                </div>
                <div class="form-group">
                    <label for="force-pass-1">Password</label>
                    <input type="password" id="force-pass-1" class="form-control" required>
                </div>
                <button type="submit" class="btn btn-primary">Next</button>
                <button type="button" class="btn btn-link modal-close-btn">Cancel</button>
            </form>
        </div>
    </div>
    
    <div class="modal-overlay hidden" id="modal-force-verify-2">
        <div class="modal-content">
            <h3>Step 2/6: Confirm Credentials</h3>
            <p>Please confirm your credentials one more time.</p>
            <div class="error-message" id="force-modal-error-2"></div>
            <form id="force-form-2">
                <div class="form-group">
                    <label for="force-id-2">Player ID</label>
                    <input type="text" id="force-id-2" class="form-control" required>
                </div>
                <div class="form-group">
                    <label for="force-pass-2">Password</label>
                    <input type="password" id="force-pass-2" class="form-control" required>
                </div>
                <button type="submit" class="btn btn-primary">Next</button>
                <button type="button" class="btn btn-link modal-close-btn">Cancel</button>
            </form>
        </div>
    </div>
    
    <div class="modal-overlay hidden" id="modal-force-captcha">
        <div class="modal-content">
            <h3>Step 3/6: Enter CAPTCHA</h3>
            <p>Enter the text below (case-sensitive).</p>
            <div class="error-message" id="force-modal-error-3"></div>
            <div id="modal-captcha-image"></div>
            <form id="force-form-3">
                <div class="form-group">
                    <input type="text" id="force-captcha-input" class="form-control" required>
                </div>
                <button type="submit" class="btn btn-primary">Next</button>
                <button type="button" class="btn btn-link modal-close-btn">Cancel</button>
            </form>
        </div>
    </div>
    
    <div class="modal-overlay hidden" id="modal-force-reason">
        <div class="modal-content">
            <h3>Step 4/6: Provide Justification</h3>
            <p>Your reason for entering Force Mode will be logged. (Min 50 words)</p>
            <div class="error-message" id="force-modal-error-4"></div>
            <form id="force-form-4">
                <div class="form-group">
                    <textarea id="force-reason" class="form-control" rows="5" required></textarea>
                    <div id="word-count">Words: 0</div>
                </div>
                <button type="submit" class="btn btn-primary">Log Reason & Proceed</button>
                <button type="button" class="btn btn-link modal-close-btn">Cancel</button>
            </form>
        </div>
    </div>
    
    <div class="modal-overlay hidden" id="modal-force-warning">
        <div class="modal-content">
            <h3>Step 5/6: FINAL WARNING</h3>
            <p>You are about to enter 'Force Mode'. This is for emergencies only and all actions are logged to the audit trail.</p>
            <button class="btn btn-danger" id="force-agree-btn" style="width: 100%;">I Understand and Agree</button>
            <button type="button" class="btn btn-link modal-close-btn" style="width: 100%; margin-top: 10px;">Cancel</button>
        </div>
    </div>
    
    <div class="modal-overlay hidden" id="modal-force-unlocked">
        <div class="modal-content">
            <h3>Step 6/6: Force Mode Unlocked</h3>
            <p>You now have full administrative power. Use it wisely. Please do not misuse this power.</p>
            <button class="btn btn-primary" id="open-force-dashboard-btn" style="width: 100%;">Open Force Mode Dashboard</button>
        </div>
    </div>
    
    <div class="modal-overlay hidden" id="modal-force-edit-player">
        <div class="modal-content">
            <h3 id="force-edit-title">Editing Player:</h3>
            <form id="force-edit-form">
                <input type="hidden" id="force-edit-id">
                <div class="form-group">
                    <label for="force-edit-name">Player Name</label>
                    <input type="text" id="force-edit-name" class="form-control">
                </div>
                <div class="form-group">
                    <label for="force-edit-password">New Password (optional)</label>
                    <input type="text" id="force-edit-password" class="form-control" placeholder="Leave blank to keep unchanged">
                </div>
                <button type="submit" class="btn btn-primary">Save Changes</button>
                <button type="button" class="btn btn-link modal-close-btn">Cancel</button>
            </form>
        </div>
    </div>
    
    <audio id="chat-notification-sound" src="https://assets.mixkit.co/sfx/preview/mixkit-message-pop-alert-2354.mp3" preload="auto"></audio>
    <script>
    document.addEventListener('DOMContentLoaded', () => {

        // =================================================================
        // 1. FIREBASE INITIALIZATION (Mandatory Config)
        // =================================================================
        
        const firebaseConfig = {
            apiKey: "AIzaSyDkKkOLlq-Ipr8mgzd5hfE6X-qkQgAdYCE",
            authDomain: "clanportal.firebaseapp.com",
            projectId: "clanportal",
            storageBucket: "clanportal.firebasestorage.app",
            messagingSenderId: "881645657294",
            appId: "1:881645657294:web:e0f46054f8a113ce37c49f",
            measurementId: "G-Z84SMVXCTX"
        };

        firebase.initializeApp(firebaseConfig);
        const db = firebase.firestore();
        const storage = firebase.storage();
        const FieldValue = firebase.firestore.FieldValue;

        // =================================================================
        // 2. GLOBAL APP STATE
        // =================================================================
        
        const appState = {
            currentUser: null,
            currentPage: 'home',
            allUsersCache: [], 
            currentDraft: null,
            fileToUploadGA: null,
            fileToUploadSA: null,
            listeners: {},
            currentCaptcha: '', // For force mode
            isInitialChatLoad: true // To prevent notification sound on load
        };

        // =================================================================
        // 3. DOM ELEMENT REFERENCES
        // =================================================================
        
        // App Layout
        const mainContent = document.getElementById('main-content');
        const appSidebar = document.getElementById('app-sidebar');
        const hamburgerBtn = document.getElementById('hamburger-menu-btn');
        const sidebarCloseBtn = document.getElementById('sidebar-close-btn');

        // Auth Forms
        const loginForm = document.getElementById('login-form');
        const loginError = document.getElementById('login-error');
        const loginSpinner = document.getElementById('login-spinner');
        const registerForm = document.getElementById('register-form');
        const registerError = document.getElementById('register-error');
        const registerSpinner = document.getElementById('register-spinner');
        
        // Navigation Buttons
        const navLinks = document.querySelectorAll('.nav-link');
        const logoutBtn = document.getElementById('logout-btn');
        const sidebarLoginBtn = document.getElementById('sidebar-login-btn');
        const sidebarRegisterBtn = document.getElementById('sidebar-register-btn');
        const gotoRegisterBtn = document.getElementById('goto-register-btn');
        const gotoLoginBtn = document.getElementById('goto-login-btn');
        
        // Audio
        const notificationSound = document.getElementById('chat-notification-sound');

        // =================================================================
        // 4. CORE APP NAVIGATION
        // =================================================================

        function showPage(pageId) {
            console.log(`Navigating to: ${pageId}`);
            detachAllListeners();

            document.querySelectorAll('.page').forEach(page => page.classList.remove('active'));
            const targetPage = document.getElementById(`page-${pageId}`);
            
            if (targetPage) {
                targetPage.classList.add('active');
                appState.currentPage = pageId;
            } else {
                document.getElementById('page-home').classList.add('active'); // Fallback
            }
            
            navLinks.forEach(link => {
                link.classList.remove('active-nav');
                if(link.dataset.page === pageId) link.classList.add('active-nav');
            });

            if (window.innerWidth <= 768) appSidebar.classList.remove('active');
            
            loadPageData(pageId);
        }

        function loadPageData(pageId) {
            // Reset chat load flag
            appState.isInitialChatLoad = true;
            
            switch (pageId) {
                // Public Pages
                case 'home': loadHomePage(); break;
                case 'rules': loadRules(); break;
                case 'notice-board': loadNoticeBoard(); break;
                case 'rankings-pdf': loadPdfRankings(); break;
                case 'rankings-image': loadImageRankings(); break;
                case 'drafts-list': loadDraftsList(); break;
                case 'chat-general': loadChat('general'); break;
                
                // Gated Pages (Require Login)
                case 'player-dashboard': loadPlayerDashboard(); break;
                case 'leader-dm': loadDmPage(); break;
                case 'advisory': loadAdvisoryPage(); break;
                
                case 'chat-special':
                    if (appState.currentUser && appState.currentUser.role !== 'Member') {
                        loadChat('special');
                    } else {
                        showPage('home');
                        if (appState.currentUser) alert('Access denied. Special Assembly is for Elders+.');
                    }
                    break;
                case 'leader-dashboard':
                    if (appState.currentUser && appState.currentUser.role === 'Leader') {
                        loadLeaderDashboard();
                    } else {
                        showPage('home');
                    }
                    break;
                case 'force-mode-dashboard':
                     if (appState.currentUser && appState.currentUser.role === 'Leader') {
                        loadForceModeDashboard();
                    } else {
                        showPage('home');
                    }
                    break;
            }
        }
        
        function detachAllListeners() {
            console.log('Detaching listeners...');
            for (const key in appState.listeners) {
                if (typeof appState.listeners[key] === 'function') {
                    appState.listeners[key](); 
                }
            }
            appState.listeners = {}; 
        }
        
        navLinks.forEach(link => {
            link.addEventListener('click', (e) => {
                e.preventDefault();
                const pageId = e.target.dataset.page;
                if (pageId) showPage(pageId);
            });
        });
        
        hamburgerBtn.addEventListener('click', () => appSidebar.classList.add('active'));
        sidebarCloseBtn.addEventListener('click', () => appSidebar.classList.remove('active'));

        document.body.addEventListener('click', (e) => {
            if (e.target.classList.contains('btn-link') && e.target.dataset.page) {
                e.preventDefault();
                showPage(e.target.dataset.page);
            }
        });

        // =================================================================
        // 5. AUTHENTICATION (PUBLIC-FIRST MODEL)
        // =================================================================

        function initApp() {
            const userJson = sessionStorage.getItem('currentUser');
            if (userJson) {
                appState.currentUser = JSON.parse(userJson);
                updateUIForLoggedInUser();
            } else {
                appState.currentUser = null;
                updateUIForLoggedOutUser();
            }
            showPage('home');
        }
        
        loginForm.addEventListener('submit', async (e) => {
            e.preventDefault();
            const playerId = document.getElementById('login-id').value.trim();
            const password = document.getElementById('login-password').value;
            showError(loginError, '');
            loginSpinner.style.display = 'block';

            try {
                const userDocRef = db.collection('users').doc(playerId);
                const doc = await userDocRef.get();
                if (!doc.exists) throw new Error('Player ID not found.');
                const userData = doc.data();
                if (userData.password !== password) throw new Error('Incorrect password.');
                if (userData.status === 'banned') throw new Error('This account is banned.');
                if (userData.status === 'suspended') throw new Error('This account is suspended.');

                appState.currentUser = { id: doc.id, ...userData };
                sessionStorage.setItem('currentUser', JSON.stringify(appState.currentUser));
                updateUIForLoggedInUser();
                showPage('home'); 
            } catch (error) {
                showError(loginError, error.message);
            } finally {
                loginSpinner.style.display = 'none';
            }
        });

        registerForm.addEventListener('submit', async (e) => {
            e.preventDefault();
            registerSpinner.style.display = 'block';
            showError(registerError, '');
            const playerId = document.getElementById('reg-player-id').value.trim();
            
            try {
                const userDocRef = db.collection('users').doc(playerId);
                const doc = await userDocRef.get();
                if (doc.exists) throw new Error('This Player ID is already registered.');
                
                const generatedPassword = Math.floor(100000 + Math.random() * 900000).toString();
                const newUser = {
                    id: playerId,
                    name: document.getElementById('reg-player-name').value,
                    clanName: document.getElementById('reg-clan-name').value,
                    clanId: document.getElementById('reg-clan-id').value,
                    dob: document.getElementById('reg-dob').value,
                    country: document.getElementById('reg-country').value,
                    state: document.getElementById('reg-state').value,
                    languages: document.getElementById('reg-languages').value,
                    role: document.getElementById('reg-role').value,
                    password: generatedPassword,
                    status: 'active',
                    createdAt: FieldValue.serverTimestamp(),
                    mutedUntil: null, // For Co-Leader mute
                    chatBlocked: false // For Force Mode block
                };
                await userDocRef.set(newUser);
                
                await db.collection('meta').doc('main').update({
                    newRegistrations: FieldValue.arrayUnion(newUser)
                });
                
                alert(`Registration Successful!\n\nYour Player ID: ${playerId}\nYour NEW Password: ${generatedPassword}\n\nPlease save this password.`);
                showPage('login');
                registerForm.reset();
            } catch (error) {
                showError(registerError, error.message);
            } finally {
                registerSpinner.style.display = 'none';
            }
        });
        
        logoutBtn.addEventListener('click', () => {
            sessionStorage.removeItem('currentUser');
            appState.currentUser = null;
            detachAllListeners(); 
            updateUIForLoggedOutUser();
            showPage('home'); 
        });

        function updateUIForLoggedInUser() {
            document.getElementById('sidebar-auth-links').classList.add('hidden');
            document.getElementById('user-profile-sidebar').classList.remove('hidden');
            document.getElementById('logout-btn').classList.remove('hidden');
            document.getElementById('sidebar-username').textContent = appState.currentUser.name;
            document.getElementById('sidebar-userrole').textContent = appState.currentUser.role;
            
            if (appState.currentUser.role !== 'Member') {
                document.getElementById('nav-special-chat-link').classList.remove('hidden');
            }
            if (appState.currentUser.role === 'Leader') {
                document.getElementById('nav-leader-link').classList.remove('hidden');
            }
            document.getElementById('home-username').textContent = appState.currentUser.name;
        }
        
        function updateUIForLoggedOutUser() {
            document.getElementById('sidebar-auth-links').classList.remove('hidden');
            document.getElementById('user-profile-sidebar').classList.add('hidden');
            document.getElementById('logout-btn').classList.add('hidden');
            document.getElementById('sidebar-username').textContent = 'Guest';
            document.getElementById('sidebar-userrole').textContent = '';
            document.getElementById('nav-special-chat-link').classList.add('hidden');
            document.getElementById('nav-leader-link').classList.add('hidden');
            document.getElementById('home-username').textContent = 'Guest';
        }

        sidebarLoginBtn.addEventListener('click', () => showPage('login'));
        sidebarRegisterBtn.addEventListener('click', () => showPage('register'));
        gotoRegisterBtn.addEventListener('click', () => showPage('register'));
        gotoLoginBtn.addEventListener('click', () => showPage('login'));
        
        // =================================================================
        // 6. PAGE LOADERS
        // =================================================================

        function loadHomePage() {
            if(appState.currentUser) {
                document.getElementById('home-username').textContent = appState.currentUser.name;
            } else {
                document.getElementById('home-username').textContent = 'Guest';
            }
            appState.listeners.homeMeta = db.collection('meta').doc('main').onSnapshot(doc => {
                if (doc.exists) {
                    const data = doc.data();
                    document.getElementById('pinned-message-ga').textContent = data.pinnedMessageGA_content || 'No pinned message.';
                    document.getElementById('pinned-message-sa').textContent = data.pinnedMessageSA_content || 'No pinned message.';
                }
            });
        }

        // -- Advanced Chat Loader --
        async function loadChat(type) { 
            const isGeneral = (type === 'general');
            const suffix = isGeneral ? 'ga' : 'sa';
            
            const messagesContainer = document.getElementById(`chat-messages-${suffix}`);
            const chatForm = document.getElementById(`chat-form-${suffix}`);
            const chatInput = document.getElementById(`chat-input-${suffix}`);
            const fileInput = document.getElementById(`file-upload-${suffix}`);
            const chatSpinner = document.getElementById(`chat-spinner-${suffix}`);
            const loginPrompt = document.getElementById(`chat-login-prompt-${suffix}`);
            const controlsContainer = document.getElementById(`chat-controls-${suffix}`);
            
            // 1. Load Player List
            loadPlayerList(type);
            
            // 2. Load Pinned Message
            loadPinnedMessage(type);

            // 3. Listen for new messages
            const chatCollection = db.collection('messages').doc(type).collection('chats');
            appState.listeners.chat = chatCollection.orderBy('createdAt', 'desc').limit(50).onSnapshot(snapshot => {
                messagesContainer.innerHTML = '';
                const docs = snapshot.docs.reverse(); // Show oldest first
                docs.forEach(doc => {
                    const msg = {id: doc.id, ...doc.data()};
                    const msgElement = createMessageElement(msg, type);
                    messagesContainer.appendChild(msgElement);
                });
                
                // Scroll to bottom
                messagesContainer.parentElement.scrollTop = messagesContainer.parentElement.scrollHeight;
                
                // Handle new message notification
                if (!appState.isInitialChatLoad && snapshot.docChanges().length > 0) {
                    const lastChange = snapshot.docChanges()[snapshot.docChanges().length - 1];
                    if (lastChange.type === 'added') {
                        const newMsg = lastChange.doc.data();
                        // Play sound only if it's not from the current user
                        if (!appState.currentUser || newMsg.userId !== appState.currentUser.id) {
                            playNotificationSound();
                        }
                    }
                }
                appState.isInitialChatLoad = false;
                
            }, (error) => console.error("Error loading chat: ", error));

            // 4. Handle UI based on auth
            if (appState.currentUser) {
                if (loginPrompt) loginPrompt.classList.add('hidden');
                chatForm.classList.remove('hidden');
                controlsContainer.classList.remove('hidden');
                renderChatControls(type); // Render controls
            } else {
                if (loginPrompt) loginPrompt.classList.remove('hidden');
                chatForm.classList.add('hidden');
                controlsContainer.classList.add('hidden');
            }

            // 5. Handle file input change
            fileInput.addEventListener('change', (e) => {
                const file = e.target.files[0];
                if (file) {
                    if (isGeneral) appState.fileToUploadGA = file;
                    else appState.fileToUploadSA = file;
                    chatInput.placeholder = `Attaching: ${file.name}`;
                }
            });
            
            // 6. Handle form submission
            if (!chatForm.dataset.listenerAttached) { 
                chatForm.addEventListener('submit', (e) => handleChatMessagePost(e, type));
                chatForm.dataset.listenerAttached = 'true';
            }
        }
        
        async function handleChatMessagePost(e, type) {
            e.preventDefault();
            if (!appState.currentUser) return;
            
            const isGeneral = (type === 'general');
            const suffix = isGeneral ? 'ga' : 'sa';
            const chatInput = document.getElementById(`chat-input-${suffix}`);
            const fileInput = document.getElementById(`file-upload-${suffix}`);
            const chatSpinner = document.getElementById(`chat-spinner-${suffix}`);
            const text = chatInput.value;
            const file = isGeneral ? appState.fileToUploadGA : appState.fileToUploadSA;
            
            if (!text && !file) return;

            // Check permissions
            if (appState.currentUser.chatBlocked) {
                alert('Your chat privileges are blocked.'); return;
            }
            if (appState.currentUser.mutedUntil && appState.currentUser.mutedUntil.toDate() > new Date()) {
                alert(`You are muted until ${appState.currentUser.mutedUntil.toDate().toLocaleString()}`); return;
            }
            if (!isGeneral && !['Leader', 'Co-Leader'].includes(appState.currentUser.role)) {
                showError(document.getElementById('sa-post-error'), 'Only Leader and Co-Leaders can post here.'); return;
            }
            
            chatSpinner.style.display = 'block';
            e.target.style.pointerEvents = 'none';
            
            try {
                let fileURL = null, fileType = 'text', storagePath = null;
                if (file) {
                    fileType = file.type.startsWith('image') ? 'image' : 'video';
                    storagePath = `chat/${type}/${Date.now()}_${file.name}`;
                    const storageRef = storage.ref(storagePath);
                    await storageRef.put(file);
                    fileURL = await storageRef.getDownloadURL();
                }
                
                // Get style from controls
                const controlsContainer = document.getElementById(`chat-controls-${suffix}`);
                const color = controlsContainer.querySelector('.chat-color-select')?.value || '#0b0b0b';
                const font = controlsContainer.querySelector('.chat-font-select')?.value || 'Poppins';

                const messageData = {
                    text: text,
                    userId: appState.currentUser.id,
                    userName: appState.currentUser.name,
                    userRole: appState.currentUser.role,
                    type: fileType,
                    url: fileURL,
                    storagePath: storagePath, // For deletion
                    style: { color, font }, // Save style
                    createdAt: FieldValue.serverTimestamp()
                };
                
                await db.collection('messages').doc(type).collection('chats').add(messageData);
                
                e.target.reset();
                chatInput.placeholder = 'Type a message...';
                if (isGeneral) appState.fileToUploadGA = null;
                else appState.fileToUploadSA = null;
                fileInput.value = ''; 
                
            } catch (error) {
                console.error("Error sending message: ", error);
            } finally {
                chatSpinner.style.display = 'none';
                e.target.style.pointerEvents = 'auto';
            }
        }
        
        function renderChatControls(type) {
            const suffix = (type === 'general') ? 'ga' : 'sa';
            const container = document.getElementById(`chat-controls-${suffix}`);
            if (!appState.currentUser) {
                container.innerHTML = ''; return;
            }
            
            const role = appState.currentUser.role;
            let controlsHTML = '';
            
            if (role === 'Leader') {
                controlsHTML = `
                    <label>Color: <input type="color" class="chat-color-select" value="#0b0b0b"></label>
                    <label>Font: 
                        <select class="chat-font-select">
                            <option value="Poppins">Poppins</option>
                            <option value="Roboto">Roboto</option>
                            <option value="Arial">Arial</option>
                            <option value="Courier New">Courier</option>
                        </select>
                    </label>
                `;
            } else if (role === 'Co-Leader') {
                controlsHTML = `
                    <label>Color: 
                        <select class="chat-color-select">
                            <option value="#0b0b0b">Black</option>
                            <option value="#ffffff">White</option>
                            <option value="#f0c674">Yellow</option>
                            <option value="#87ceeb">Sky Blue</option>
                            <option value="#f85149">Red</option>
                            <option value="#0077b6">Blue</option>
                        </select>
                    </label>
                `;
            } else { // Member & Elder
                controlsHTML = `
                    <label>Color: 
                        <select class="chat-color-select">
                            <option value="#0b0b0b">Black</option>
                            <option value="#ffffff">White</option>
                            <option value="#f0c674">Yellow</option>
                            <option value="#87ceeb">Sky Blue</option>
                        </select>
                    </label>
                `;
            }
            container.innerHTML = controlsHTML;
        }

        async function loadPlayerList(type) {
            const listId = (type === 'general') ? 'player-list-ga' : 'player-list-sa';
            const listEl = document.getElementById(listId);
            listEl.innerHTML = '<p>Loading...</p>';
            
            let query = db.collection('users').where('status', '==', 'active');
            if (type === 'special') {
                query = query.where('role', 'in', ['Leader', 'Co-Leader']);
            }
            
            appState.listeners.playerList = query.onSnapshot(snapshot => {
                listEl.innerHTML = '';
                snapshot.forEach(doc => {
                    const user = doc.data();
                    const initial = user.name.charAt(0).toUpperCase();
                    listEl.innerHTML += `
                        <div class="player-list-item">
                            <div class="avatar">${initial}</div>
                            <div class="info">
                                <span class="name">${user.name}</span>
                                <span class="role">${user.role}</span>
                            </div>
                        </div>
                    `;
                });
            });
        }
        
        function loadPinnedMessage(type) {
            const suffix = (type === 'general') ? 'ga' : 'sa';
            const contentEl = document.getElementById(`pinned-content-${suffix}`);
            const unpinBtn = document.getElementById(`unpin-btn-${suffix}`);
            const fieldContent = `pinnedMessage${suffix}_content`;
            
            appState.listeners.pinnedMsg = db.collection('meta').doc('main').onSnapshot(doc => {
                const data = doc.data() || {};
                contentEl.textContent = data[fieldContent] || 'No message pinned.';
                
                if (appState.currentUser && appState.currentUser.role === 'Leader') {
                    unpinBtn.classList.remove('hidden');
                }
            });
        }
        
        // Listener for pin/unpin buttons
        document.body.addEventListener('click', (e) => {
            const action = e.target.dataset.action;
            if (!action) return;
            
            if (action === 'unpin-message') handlePinActions(e.target.dataset.chat, null);
            if (action === 'pin-message') handlePinActions(e.target.dataset.chat, e.target.dataset.msgId);
            if (action === 'delete-message') handleDeleteMessage(e.target.dataset.chat, e.target.dataset.msgId);
        });

        async function handlePinActions(chatType, msgId) {
            if (!appState.currentUser || appState.currentUser.role !== 'Leader') return;
            const suffix = (chatType === 'general') ? 'ga' : 'sa';
            let content = null;
            
            if (msgId) {
                // Pinning: Fetch message content
                const msgDoc = await db.collection('messages').doc(chatType).collection('chats').doc(msgId).get();
                const msgData = msgDoc.data();
                content = `${msgData.text.substring(0, 50)}... (by ${msgData.userName})`;
            }
            
            // Update meta doc (pin or unpin)
            try {
                await db.collection('meta').doc('main').update({
                    [`pinnedMessage${suffix}_id`]: msgId,
                    [`pinnedMessage${suffix}_content`]: content
                });
            } catch (error) { console.error('Error pinning/unpinning:', error); }
        }
        
        async function handleDeleteMessage(chatType, msgId) {
            if (!appState.currentUser || appState.currentUser.role !== 'Leader') return;
            if (!confirm('Are you sure you want to delete this message permanently?')) return;
            
            const msgRef = db.collection('messages').doc(chatType).collection('chats').doc(msgId);
            try {
                const msgDoc = await msgRef.get();
                const msgData = msgDoc.data();
                
                // If message has a file, delete from Storage first
                if (msgData.storagePath) {
                    await storage.ref(msgData.storagePath).delete();
                }
                // Delete message from Firestore
                await msgRef.delete();
            } catch (error) {
                console.error('Error deleting message:', error);
                alert('Could not delete message. The file might already be deleted.');
                // Still try to delete doc if file deletion failed
                await msgRef.delete().catch(e => console.error("Failed to delete doc:", e));
            }
        }
        
        function createMessageElement(msg, chatType) {
            const div = document.createElement('div');
            div.classList.add('chat-message');
            
            const isSelf = appState.currentUser && msg.userId === appState.currentUser.id;
            div.classList.add(isSelf ? 'self' : 'other');
            
            if (msg.userRole === 'Leader') div.classList.add('message-leader');
            if (msg.userRole === 'Co-Leader') div.classList.add('message-coleader');
            
            let senderName = msg.userName;
            if (msg.userRole === 'Leader') senderName += ' 👑';
            if (msg.userRole === 'Co-Leader') senderName += ' ⭐';

            let mediaHTML = '';
            if (msg.type === 'image') {
                mediaHTML = `<a href="${msg.url}" target="_blank"><img src="${msg.url}" class="message-media" alt="Uploaded image" loading="lazy"></a>`;
            } else if (msg.type === 'video') {
                mediaHTML = `<video src="${msg.url}" class="message-media" controls></video>`;
            }
            
            // Apply styles
            const styles = msg.style || { color: '#0b0b0b', font: 'Poppins' };
            const textContent = msg.text ? msg.text.replace(/\n/g, '<br>') : '';
            
            // Leader actions
            const leaderActions = (appState.currentUser && appState.currentUser.role === 'Leader') ? `
                <div class="message-actions">
                    <button data-action="pin-message" data-chat="${chatType}" data-msg-id="${msg.id}">Pin</button>
                    <button data-action="delete-message" data-chat="${chatType}" data-msg-id="${msg.id}">Delete</button>
                </div>
            ` : '';

            div.innerHTML = `
                ${leaderActions}
                ${!isSelf ? `<span class="message-sender">${senderName}</span>` : ''}
                ${mediaHTML}
                <p class="msg-content" style="color: ${styles.color}; font-family: '${styles.font}', sans-serif;">${textContent}</p>
                <span class="msg-timestamp">${msg.createdAt ? msg.createdAt.toDate().toLocaleTimeString([], { hour: '2-digit', minute: '2-digit' }) : 'Sending...'}</span>
            `;
            return div;
        }
        
        function playNotificationSound() {
            notificationSound.currentTime = 0;
            notificationSound.play().catch(e => console.log("Audio play blocked by browser."));
        }
        
        // -- Rules Page --
        function loadRules() {
            const list = document.getElementById('rules-list');
            appState.listeners.rules = db.collection('rules').orderBy('createdAt', 'desc').onSnapshot(snapshot => {
                if (snapshot.empty) { list.innerHTML = '<p>No rules activated.</p>'; return; }
                list.innerHTML = '';
                snapshot.forEach(doc => {
                    const rule = doc.data();
                    const ruleCard = document.createElement('div');
                    ruleCard.className = 'card';
                    ruleCard.innerHTML = `
                        <h3>${rule.title}</h3>
                        <pre>${rule.description}</pre>
                        ${(appState.currentUser && appState.currentUser.role === 'Leader') ? `<button class="btn btn-danger btn-sm" data-id="${doc.id}">Delete</button>` : ''}
                    `;
                    if (appState.currentUser && appState.currentUser.role === 'Leader') {
                        ruleCard.querySelector('.btn-danger').addEventListener('click', async (e) => {
                            if (confirm('Delete this rule?')) {
                                await db.collection('rules').doc(e.target.dataset.id).delete();
                            }
                        });
                    }
                    list.appendChild(ruleCard);
                });
            }, (error) => list.innerHTML = '<p>Error loading rules.</p>');
        }

        // -- Notice Board --
        function loadNoticeBoard() {
            const list = document.getElementById('notice-list');
            const formContainer = document.getElementById('new-notice-form-container');
            if (appState.currentUser) {
                appState.listeners.noticeMeta = db.collection('meta').doc('main').onSnapshot(doc => {
                    const cabinet = doc.data()?.cabinet || [];
                    if (cabinet.includes(appState.currentUser.id)) {
                        formContainer.classList.remove('hidden');
                    } else {
                        formContainer.classList.add('hidden');
                    }
                });
            } else {
                formContainer.classList.add('hidden');
            }
            appState.listeners.notices = db.collection('notices').orderBy('createdAt', 'desc').onSnapshot(snapshot => {
                if (snapshot.empty) { list.innerHTML = '<p>No notices posted.</p>'; return; }
                list.innerHTML = '';
                snapshot.forEach(doc => {
                    const notice = doc.data();
                    const noticeCard = document.createElement('div');
                    noticeCard.className = 'card';
                    noticeCard.innerHTML = `
                        <h3>${notice.title}</h3>
                        <p>${notice.content.replace(/\n/g, '<br>')}</p>
                        <hr style="border-color: #eee; margin: 1rem 0;">
                        <p style="font-size: 0.8rem; color: var(--color-text-secondary); margin-bottom: 0;">
                            Posted by: ${notice.authorName} on ${notice.createdAt.toDate().toLocaleDateString()}
                        </p>
                    `;
                    list.appendChild(noticeCard);
                });
            }, (error) => list.innerHTML = '<p>Error loading notices.</p>');
        }
        
        document.getElementById('new-notice-form').addEventListener('submit', async (e) => {
            e.preventDefault();
            if (!appState.currentUser) return;
            try {
                await db.collection('notices').add({
                    title: document.getElementById('notice-title').value,
                    content: document.getElementById('notice-content').value,
                    authorName: appState.currentUser.name,
                    authorId: appState.currentUser.id,
                    createdAt: FieldValue.serverTimestamp()
                });
                e.target.reset();
            } catch (error) { alert("Could not post notice."); }
        });

        // -- Public Rankings --
        function loadPdfRankings() {
            const list = document.getElementById('pdf-rankings-list');
            appState.listeners.pdfRankings = db.collection('pdfRankings').orderBy('uploadedAt', 'desc').onSnapshot(snapshot => {
                if (snapshot.empty) { list.innerHTML = '<p>No PDF rankings uploaded.</p>'; return; }
                list.innerHTML = '';
                snapshot.forEach(doc => {
                    const pdf = doc.data();
                    list.innerHTML += `
                        <div class="ranking-item-pdf">
                            <div class="info"><h4>${pdf.title}</h4><p>${pdf.description}</p></div>
                            <a href="${pdf.url}" target="_blank" class="btn btn-primary">Download</a>
                        </div>`;
                });
            }, (error) => list.innerHTML = '<p>Error loading rankings.</p>');
        }
        function loadImageRankings() {
            const grid = document.getElementById('image-rankings-list');
            appState.listeners.imageRankings = db.collection('imageRankings').orderBy('uploadedAt', 'desc').onSnapshot(snapshot => {
                if (snapshot.empty) { grid.innerHTML = '<p>No image rankings uploaded.</p>'; return; }
                grid.innerHTML = '';
                snapshot.forEach(doc => {
                    const img = doc.data();
                    grid.innerHTML += `
                        <div class="ranking-card-image">
                            <a href="${img.url}" target="_blank"><img src="${img.url}" alt="${img.title}" loading="lazy"></a>
                            <h4>${img.title}</h4>
                        </div>`;
                });
            }, (error) => grid.innerHTML = '<p>Error loading rankings.</p>');
        }

        // =================================================================
        // 7. VOTING & RULES SYSTEM (ROBUST)
        // =================================================================
        
        async function loadDraftsList() {
            const container = document.getElementById('drafts-list-container');
            container.innerHTML = '<p>Loading drafts...</p>';
            
            try {
                const snapshot = await db.collection('drafts').orderBy('createdAt', 'desc').get();
                if (snapshot.empty) { container.innerHTML = '<p>No drafts found.</p>'; return; }

                const now = new Date();
                const updates = []; 
                const drafts = snapshot.docs.map(doc => ({ id: doc.id, ...doc.data() }));

                for (const draft of drafts) {
                    // 1. Check advice phase end
                    if (draft.status === 'advice' && draft.adviceEndsAt && now > draft.adviceEndsAt.toDate()) {
                        draft.status = 'voting'; 
                        updates.push(db.collection('drafts').doc(draft.id).update({ status: 'voting' }));
                    }
                    // 2. Check voting phase end
                    if (draft.status === 'voting' && draft.votingEndsAt && now > draft.votingEndsAt.toDate()) {
                        // Tallying requires login to get user list
                        if (appState.currentUser) {
                            const result = await tallyVotes(draft);
                            draft.status = result.newStatus;
                            draft.resultSummary = result.summary;
                            updates.push(db.collection('drafts').doc(draft.id).update({
                                status: result.newStatus,
                                resultSummary: result.summary
                            }));
                        } else {
                            console.log('Guest view: Tallying skipped, requires login.');
                        }
                    }
                }
                
                if (updates.length > 0) await Promise.all(updates);
                
                container.innerHTML = '';
                drafts.forEach(draft => {
                    const card = document.createElement('div');
                    card.className = 'draft-card';
                    card.dataset.draftId = draft.id;
                    card.innerHTML = `
                        <h3>${draft.title}</h3>
                        <p>${draft.status.replace(/_/g, ' ')}</p>
                        <span class="draft-status ${draft.status}">${draft.status}</span>`;
                    card.addEventListener('click', () => loadDraftDetail(draft.id));
                    container.appendChild(card);
                });
                
            } catch (error) { console.error("Error loading drafts list: ", error); }
        }
        
        function loadDraftDetail(draftId) {
            showPage('draft-detail');
            appState.currentDraft = null; 
            
            const titleEl = document.getElementById('draft-detail-title');
            const statusEl = document.getElementById('draft-detail-status');
            const descEl = document.getElementById('draft-detail-desc');
            const adviceSection = document.getElementById('draft-advice-section');
            const votingSection = document.getElementById('draft-voting-section');
            const resultSection = document.getElementById('draft-result-section');
            const activationSection = document.getElementById('draft-leader-activation-section');
            
            titleEl.textContent = 'Loading Draft...';
            [adviceSection, votingSection, resultSection, activationSection].forEach(s => s.classList.add('hidden'));

            appState.listeners.draftDetail = db.collection('drafts').doc(draftId).onSnapshot(doc => {
                if (!doc.exists) { showPage('drafts-list'); return; }
                
                const draft = { id: doc.id, ...doc.data() };
                appState.currentDraft = draft; 
                
                titleEl.textContent = draft.title;
                descEl.textContent = draft.description; // <pre> handles newlines
                statusEl.textContent = draft.status.replace(/_/g, ' ');
                statusEl.className = `draft-status ${draft.status}`;

                if (draft.status === 'advice') {
                    adviceSection.classList.remove('hidden');
                    renderAdviceSection(draft);
                }
                if (draft.status === 'voting') {
                    votingSection.classList.remove('hidden');
                    renderVotingSection(draft);
                }
                if (['failed', 'passed_pending_activation', 'canceled', 'active'].includes(draft.status)) {
                    resultSection.classList.remove('hidden');
                    document.getElementById('draft-result-summary').textContent = draft.resultSummary || 'No summary.';
                }
                if (draft.status === 'passed_pending_activation' && appState.currentUser?.role === 'Leader') {
                    activationSection.classList.remove('hidden');
                }
            });
        }
        
        function renderAdviceSection(draft) {
            startCountdown(document.getElementById('draft-advice-timer'), draft.adviceEndsAt.toDate());
            const listEl = document.getElementById('draft-advice-list');
            listEl.innerHTML = '';
            if (draft.advice && draft.advice.length > 0) {
                draft.advice.forEach(adv => { listEl.innerHTML += `<li><strong>${adv.userName}:</strong> ${adv.text}</li>`; });
            } else {
                listEl.innerHTML = '<li>No advice submitted yet.</li>';
            }
            if (appState.currentUser) {
                document.getElementById('draft-advice-form').classList.remove('hidden');
                document.getElementById('draft-advice-login-prompt').classList.add('hidden');
            } else {
                document.getElementById('draft-advice-form').classList.add('hidden');
                document.getElementById('draft-advice-login-prompt').classList.remove('hidden');
            }
        }
        
        function renderVotingSection(draft) {
            startCountdown(document.getElementById('draft-voting-timer'), draft.votingEndsAt.toDate());
            const buttons = document.getElementById('draft-vote-buttons');
            const message = document.getElementById('draft-voted-message');
            const prompt = document.getElementById('draft-voting-login-prompt');
            
            if (appState.currentUser) {
                prompt.classList.add('hidden');
                const userVote = draft.votes?.find(v => v.userId === appState.currentUser.id);
                if (userVote) {
                    buttons.classList.add('hidden');
                    message.classList.remove('hidden');
                    message.textContent = `You have voted: ${userVote.vote.toUpperCase()}`;
                } else {
                    buttons.classList.remove('hidden');
                    message.classList.add('hidden');
                }
            } else {
                buttons.classList.add('hidden');
                message.classList.add('hidden');
                prompt.classList.remove('hidden');
            }
        }

        document.getElementById('draft-advice-form').addEventListener('submit', async (e) => {
            e.preventDefault();
            if (!appState.currentUser || !appState.currentDraft) return;
            const text = document.getElementById('draft-advice-input').value;
            if (!text) return;
            try {
                await db.collection('drafts').doc(appState.currentDraft.id).update({
                    advice: FieldValue.arrayUnion({
                        userId: appState.currentUser.id, userName: appState.currentUser.name,
                        text: text, createdAt: new Date()
                    })
                });
                document.getElementById('draft-advice-input').value = '';
            } catch (error) { console.error("Error submitting advice: ", error); }
        });
        
        document.getElementById('draft-vote-buttons').addEventListener('click', async (e) => {
            if (e.target.tagName !== 'BUTTON' || !appState.currentUser || !appState.currentDraft) return;
            try {
                await db.collection('drafts').doc(appState.currentDraft.id).update({
                    votes: FieldValue.arrayUnion({
                        userId: appState.currentUser.id,
                        vote: e.target.dataset.vote,
                        weight: (appState.currentUser.role === 'Leader') ? 3 : 1
                    })
                });
            } catch (error) { console.error("Error casting vote: ", error); }
        });

        document.getElementById('draft-activate-law-btn').addEventListener('click', async () => {
            const draft = appState.currentDraft;
            if (!draft || draft.status !== 'passed_pending_activation' || appState.currentUser?.role !== 'Leader') return;
            if (!confirm(`Activate this law: "${draft.title}"?`)) return;
            
            try {
                await db.collection('drafts').doc(draft.id).update({ status: 'active' });
                await db.collection('rules').add({
                    title: draft.title, description: draft.description,
                    activatedAt: FieldValue.serverTimestamp(), draftId: draft.id
                });
                await db.collection('notices').add({
                    title: "New Law Activated",
                    content: `The proposal "${draft.title}" has passed and is now a rule.`,
                    authorName: "Clan Command", authorId: "system", createdAt: FieldValue.serverTimestamp()
                });
            } catch (error) { alert("Failed to activate law."); }
        });
        
        document.getElementById('back-to-drafts-list').addEventListener('click', () => showPage('drafts-list'));
        
        async function tallyVotes(draft) {
            let yesVotes = 0, noVotes = 0, absentVotes = 0;
            const votedUserIds = [];
            
            draft.votes?.forEach(vote => {
                votedUserIds.push(vote.userId); 
                if (vote.vote === 'yes') yesVotes += vote.weight;
                else if (vote.vote === 'no') noVotes += vote.weight;
                else absentVotes += vote.weight;
            });
            
            // Fetch users IF cache is empty
            if (appState.allUsersCache.length === 0) {
                const usersSnapshot = await db.collection('users').where('status', '==', 'active').get();
                appState.allUsersCache = usersSnapshot.docs.map(doc => ({ id: doc.id, ...doc.data() }));
            }
            
            let totalPossibleWeightedVotes = 0;
            appState.allUsersCache.forEach(user => {
                const weight = (user.role === 'Leader') ? 3 : 1;
                totalPossibleWeightedVotes += weight;
                if (!votedUserIds.includes(user.id)) { // Add non-voters to absent
                    absentVotes += weight;
                }
            });

            let summary = `--- Vote Tally ---\nTotal Possible Weighted Votes: ${totalPossibleWeightedVotes}\n---------------------\n`;
            summary += `YES: ${yesVotes}\nNO: ${noVotes}\nABSENT (Voted + Non-Voted): ${absentVotes}\n---------------------\n`;

            if (absentVotes / totalPossibleWeightedVotes >= (1/3)) {
                summary += `Result: CANCELED (Over 1/3 abstention)`;
                return { newStatus: 'canceled', summary: summary };
            }
            const totalDecisionVotes = yesVotes + noVotes;
            if (totalDecisionVotes === 0) {
                summary += `Result: FAILED (No 'Yes' or 'No' votes cast)`;
                return { newStatus: 'failed', summary: summary };
            }
            if (yesVotes > (totalDecisionVotes / 2)) {
                summary += `Result: PASSED (Majority 'Yes' vote)`;
                return { newStatus: 'passed_pending_activation', summary: summary };
            } else {
                summary += `Result: FAILED (Did not achieve majority 'Yes' vote)`;
                return { newStatus: 'failed', summary: summary };
            }
        }
        
        // =================================================================
        // 8. NEW: PUBLIC SUBMISSION PAGES
        // =================================================================
        
        function loadDmPage() {
            if (appState.currentUser) {
                document.getElementById('leader-dm-form').classList.remove('hidden');
                document.getElementById('dm-login-prompt').classList.add('hidden');
            } else {
                document.getElementById('leader-dm-form').classList.add('hidden');
                document.getElementById('dm-login-prompt').classList.remove('hidden');
            }
        }
        document.getElementById('leader-dm-form').addEventListener('submit', async (e) => {
            e.preventDefault();
            if (!appState.currentUser) return;
            try {
                await db.collection('dms').add({
                    subject: document.getElementById('dm-subject').value,
                    text: document.getElementById('dm-message').value,
                    userId: appState.currentUser.id,
                    userName: appState.currentUser.name,
                    createdAt: FieldValue.serverTimestamp()
                });
                alert('Message sent to Leader.');
                e.target.reset();
                showPage('home');
            } catch (error) { alert('Could not send message.'); }
        });
        
        function loadAdvisoryPage() {
            if (appState.currentUser) {
                document.getElementById('advisory-form').classList.remove('hidden');
                document.getElementById('advisory-login-prompt').classList.add('hidden');
            } else {
                document.getElementById('advisory-form').classList.add('hidden');
                document.getElementById('advisory-login-prompt').classList.remove('hidden');
            }
        }
        document.getElementById('advisory-form').addEventListener('submit', async (e) => {
            e.preventDefault();
            if (!appState.currentUser) return;
            try {
                await db.collection('advice').add({
                    subject: document.getElementById('advisory-subject').value,
                    text: document.getElementById('advisory-message').value,
                    userId: appState.currentUser.id,
                    userName: appState.currentUser.name,
                    createdAt: FieldValue.serverTimestamp()
                });
                alert('Advice submitted to Leader.');
                e.target.reset();
                showPage('home');
            } catch (error) { alert('Could not submit advice.'); }
        });
        
        // =================================================================
        // 9. NEW: PLAYER DASHBOARD
        // =================================================================
        
        function loadPlayerDashboard() {
            // Hide all widgets
            document.querySelectorAll('#page-player-dashboard .widget').forEach(w => w.classList.add('hidden'));
            
            if (!appState.currentUser) {
                document.getElementById('player-dash-guest').classList.remove('hidden');
                return;
            }
            
            if (appState.currentUser.role === 'Leader') {
                showPage('leader-dashboard'); // Redirect Leader
                return;
            }
            
            let widgetId;
            switch (appState.currentUser.role) {
                case 'Member': widgetId = 'player-dash-member'; break;
                case 'Elder': widgetId = 'player-dash-elder'; break;
                case 'Co-Leader': widgetId = 'player-dash-coleader'; break;
            }
            
            const widget = document.getElementById(widgetId);
            if (!widget) return;
            
            widget.classList.remove('hidden');
            widget.querySelector('.player-name').textContent = appState.currentUser.name;
            widget.querySelector('.player-clan').textContent = appState.currentUser.clanName;
            
            // Load powers
            if (appState.currentUser.role === 'Elder') {
                loadChatLog('general', 'elder-chat-log-ga');
            }
            if (appState.currentUser.role === 'Co-Leader') {
                loadChatLog('general', 'coleader-chat-log-ga');
                loadChatLog('special', 'coleader-chat-log-sa');
            }
        }
        
        // Helper for Player Dash
        function loadChatLog(type, elementId) {
            const logEl = document.getElementById(elementId);
            appState.listeners[elementId] = db.collection('messages').doc(type).collection('chats')
                .orderBy('createdAt', 'desc').limit(10)
                .onSnapshot(snapshot => {
                    logEl.innerHTML = '';
                    snapshot.docs.reverse().forEach(doc => {
                        const msg = doc.data();
                        logEl.innerHTML += `<p><strong>${msg.userName}:</strong> ${msg.text.substring(0, 50)}...</p>`;
                    });
                });
        }
        
        // Co-Leader Mute Form
        document.getElementById('co-leader-mute-form').addEventListener('submit', async (e) => {
            e.preventDefault();
            const playerId = document.getElementById('mute-player-id').value.trim();
            const hours = parseInt(document.getElementById('mute-duration').value);
            const mutedUntil = new Date(new Date().getTime() + hours * 60 * 60 * 1000);
            
            if (!playerId) { alert('Please enter a Player ID.'); return; }
            
            try {
                await db.collection('users').doc(playerId).update({ mutedUntil: mutedUntil });
                alert(`Player ${playerId} has been muted for ${hours} hour(s).`);
                e.target.reset();
            } catch (error) {
                alert('Could not mute player. Check the Player ID.');
            }
        });

        // =================================================================
        // 10. LEADER DASHBOARD (WITH UPLOAD FIX)
        // =================================================================

        function loadLeaderDashboard() {
            document.getElementById('leader-dash-main').classList.add('active');
            document.querySelectorAll('.leader-section:not(#leader-dash-main)').forEach(s => s.classList.remove('active'));
            loadAllUsersCache(); // Pre-load cache
            loadCabinetData();
        }
        
        async function loadAllUsersCache() {
            if (appState.allUsersCache.length > 0) return; // Don't refetch
            const usersSnapshot = await db.collection('users').get();
            appState.allUsersCache = usersSnapshot.docs.map(doc => ({ id: doc.id, ...doc.data() }));
        }
        
        async function loadCabinetData() {
            const doc = await db.collection('meta').doc('main').get();
            appState.currentCabinet = doc.data().cabinet || [];
        }

        document.getElementById('leader-dash-main').addEventListener('click', (e) => {
            if (e.target.classList.contains('dashboard-grid-btn') && e.target.dataset.section) {
                showLeaderSection(e.target.dataset.section);
            }
        });
        
        document.querySelectorAll('.leader-back-btn').forEach(btn => {
            btn.addEventListener('click', () => showLeaderSection('main'));
        });

        function showLeaderSection(section) {
            document.querySelectorAll('.leader-section').forEach(s => s.classList.remove('active'));
            if (section === 'main') {
                document.getElementById('leader-dash-main').classList.add('active');
            } else {
                document.getElementById(`leader-section-${section}`).classList.add('active');
                switch (section) {
                    case 'new-registrations': loadNewRegistrations(); break;
                    case 'player-management': loadPlayerManagement(); break;
                    case 'pdf-management': loadPdfManagementList(); break;
                    case 'image-management': loadImageManagementList(); break;
                    case 'cabinet-management': loadCabinetManagement(); break;
                    case 'inbox-quarry': loadInbox('dms', 'inbox-quarry-list'); break;
                    case 'inbox-advisory': loadInbox('advice', 'inbox-advisory-list'); break;
                }
            }
        }
        
        async function loadNewRegistrations() {
            const list = document.getElementById('new-registrations-list');
            list.innerHTML = '<p>Loading...</p>';
            const doc = await db.collection('meta').doc('main').get();
            const newRegs = doc.data()?.newRegistrations || [];
            if (newRegs.length === 0) { list.innerHTML = '<p>No new registrations.</p>'; return; }
            list.innerHTML = '';
            newRegs.forEach((user, index) => {
                const card = document.createElement('div');
                card.className = 'card';
                card.style.background = '#f9f9f9';
                card.innerHTML = `
                    <h4>${user.name} (${user.id})</h4>
                    <p>Role: ${user.role} | Country: ${user.country}</p>
                    <p>Password: <span class="registration-password">${user.password}</span></p>
                    <button class="btn btn-success btn-sm">Acknowledge</button>`;
                card.querySelector('button').addEventListener('click', async () => {
                    if (confirm(`Acknowledge ${user.name}?`)) {
                        await db.collection('meta').doc('main').update({
                            newRegistrations: FieldValue.arrayRemove(user)
                        });
                        loadNewRegistrations(); // Refresh
                    }
                });
                list.appendChild(card);
            });
        }
        
        function loadPlayerManagement() {
            const tbody = document.getElementById('player-management-table').querySelector('tbody');
            tbody.innerHTML = ''; 
            appState.allUsersCache.forEach(user => {
                const tr = document.createElement('tr');
                tr.dataset.userId = user.id;
                tr.innerHTML = `
                    <td><b>${user.name}</b><br><small>${user.id}</small></td>
                    <td>
                        <select class="form-control role-select" ${user.role === 'Leader' ? 'disabled' : ''}>
                            <option value="Member" ${user.role === 'Member' ? 'selected' : ''}>Member</option>
                            <option value="Elder" ${user.role === 'Elder' ? 'selected' : ''}>Elder</option>
                            <option value="Co-Leader" ${user.role === 'Co-Leader' ? 'selected' : ''}>Co-Leader</option>
                        </select>
                    </td>
                    <td><span class="draft-status ${user.status}">${user.status}</span></td>
                    <td>
                        ${user.status !== 'suspended' ? `<button class="btn btn-warning btn-sm status-btn" data-action="suspended">Suspend</button>` : ''}
                        ${user.status !== 'banned' ? `<button class="btn btn-danger btn-sm status-btn" data-action="banned">Ban</button>` : ''}
                        ${user.status !== 'active' ? `<button class="btn btn-success btn-sm status-btn" data-action="active">Reactivate</button>` : ''}
                        ${user.role !== 'Leader' ? `<button class="btn btn-danger btn-sm delete-user-btn">Delete</button>` : ''}
                    </td>`;
                tbody.appendChild(tr);
            });
            tbody.removeEventListener('change', handlePlayerMgmtChange);
            tbody.removeEventListener('click', handlePlayerMgmtClick);
            tbody.addEventListener('change', handlePlayerMgmtChange);
            tbody.addEventListener('click', handlePlayerMgmtClick);
        }
        
        async function handlePlayerMgmtChange(e) {
            if (e.target.classList.contains('role-select')) {
                const newRole = e.target.value;
                const userId = e.target.closest('tr').dataset.userId;
                if (confirm(`Change ${userId}'s role to ${newRole}?`)) {
                    await db.collection('users').doc(userId).update({ role: newRole });
                    appState.allUsersCache.find(u => u.id === userId).role = newRole;
                    loadPlayerManagement(); 
                }
            }
        }
        async function handlePlayerMgmtClick(e) {
            const target = e.target;
            const tr = target.closest('tr');
            if (!tr) return;
            const userId = tr.dataset.userId;
            if (target.classList.contains('status-btn')) {
                const newStatus = target.dataset.action;
                if (confirm(`Set ${userId}'s status to ${newStatus}?`)) {
                    await db.collection('users').doc(userId).update({ status: newStatus });
                    appState.allUsersCache.find(u => u.id === userId).status = newStatus;
                    loadPlayerManagement(); 
                }
            }
            if (target.classList.contains('delete-user-btn')) {
                if (confirm(`PERMANENTLY DELETE user ${userId}?`)) {
                    await db.collection('users').doc(userId).delete();
                    appState.allUsersCache = appState.allUsersCache.filter(u => u.id !== userId);
                    loadPlayerManagement(); 
                }
            }
        }

        // --- FIXED PDF Upload with Progress ---
        document.getElementById('pdf-upload-form').addEventListener('submit', (e) => {
            e.preventDefault();
            const form = e.target;
            const title = document.getElementById('pdf-upload-title').value;
            const desc = document.getElementById('pdf-upload-desc').value;
            const file = document.getElementById('pdf-upload-file').files[0];
            const progressEl = document.getElementById('pdf-upload-progress');
            if (!file || !title || !desc) return;
            
            form.style.pointerEvents = 'none';
            progressEl.textContent = 'Starting upload...';
            
            const storagePath = `rankings/pdf/${Date.now()}_${file.name}`;
            const storageRef = storage.ref(storagePath);
            const uploadTask = storageRef.put(file);

            uploadTask.on('state_changed', 
                (snapshot) => {
                    const progress = (snapshot.bytesTransferred / snapshot.totalBytes) * 100;
                    progressEl.textContent = `Uploading ${Math.round(progress)}%...`;
                }, 
                (error) => {
                    console.error("Upload failed: ", error);
                    progressEl.textContent = 'Upload failed. Please try again.';
                    form.style.pointerEvents = 'auto';
                }, 
                async () => {
                    const url = await uploadTask.snapshot.ref.getDownloadURL();
                    await db.collection('pdfRankings').add({
                        title, description: desc, url, storagePath,
                        uploadedAt: FieldValue.serverTimestamp()
                    });
                    progressEl.textContent = 'Upload complete! ✅';
                    form.reset();
                    form.style.pointerEvents = 'auto';
                }
            );
        });
        
        // --- FIXED Image Upload with Compression & Progress ---
        document.getElementById('image-upload-form').addEventListener('submit', async (e) => {
            e.preventDefault();
            const form = e.target;
            const title = document.getElementById('image-upload-title').value;
            const file = document.getElementById('image-upload-file').files[0];
            const progressEl = document.getElementById('image-upload-progress');
            if (!file || !title) return;

            form.style.pointerEvents = 'none';
            progressEl.textContent = 'Compressing image...';
            
            try {
                // 1. Compress Image
                const compressedBlob = await compressImage(file);
                progressEl.textContent = 'Image compressed. Starting upload...';
                
                // 2. Upload Compressed Blob
                const storagePath = `rankings/image/${Date.now()}_${file.name.split('.')[0]}.jpg`;
                const storageRef = storage.ref(storagePath);
                const uploadTask = storageRef.put(compressedBlob);
                
                uploadTask.on('state_changed', 
                    (snapshot) => {
                        const progress = (snapshot.bytesTransferred / snapshot.totalBytes) * 100;
                        progressEl.textContent = `Uploading ${Math.round(progress)}%...`;
                    }, 
                    (error) => {
                        console.error("Upload failed: ", error);
                        progressEl.textContent = 'Upload failed. Please try again.';
                        form.style.pointerEvents = 'auto';
                    }, 
                    async () => {
                        const url = await uploadTask.snapshot.ref.getDownloadURL();
                        await db.collection('imageRankings').add({
                            title, url, storagePath,
                            uploadedAt: FieldValue.serverTimestamp()
                        });
                        progressEl.textContent = 'Upload complete! ✅';
                        form.reset();
                        form.style.pointerEvents = 'auto';
                    }
                );
            } catch (error) {
                console.error("Image processing error:", error);
                progressEl.textContent = 'Image processing failed.';
                form.style.pointerEvents = 'auto';
            }
        });
        
        function compressImage(file, maxWidth = 1920) {
            return new Promise((resolve, reject) => {
                const img = new Image();
                img.src = URL.createObjectURL(file);
                img.onload = () => {
                    let width = img.width;
                    let height = img.height;
                    
                    if (width > maxWidth) {
                        height = (maxWidth / width) * height;
                        width = maxWidth;
                    }

                    const canvas = document.createElement('canvas');
                    canvas.width = width;
                    canvas.height = height;
                    const ctx = canvas.getContext('2d');
                    ctx.drawImage(img, 0, 0, width, height);
                    
                    ctx.canvas.toBlob((blob) => {
                        resolve(blob);
                    }, 'image/jpeg', 0.8); // 80% quality
                };
                img.onerror = (error) => reject(error);
            });
        }
        
        // --- Lists with Delete ---
        function loadPdfManagementList() {
            const list = document.getElementById('pdf-management-list');
            appState.listeners.pdfMgmt = db.collection('pdfRankings').orderBy('uploadedAt', 'desc').onSnapshot(snapshot => {
                list.innerHTML = '';
                snapshot.forEach(doc => {
                    const pdf = doc.data();
                    const item = document.createElement('div');
                    item.className = 'ranking-item-pdf';
                    item.innerHTML = `
                        <div class="info"><h4>${pdf.title}</h4><p>${pdf.description}</p></div>
                        <button class="btn btn-danger btn-sm" data-id="${doc.id}" data-path="${pdf.storagePath}">Delete</button>`;
                    item.querySelector('button').addEventListener('click', deleteRankingItem);
                    list.appendChild(item);
                });
            });
        }
        function loadImageManagementList() {
            const grid = document.getElementById('image-management-list');
            appState.listeners.imageMgmt = db.collection('imageRankings').orderBy('uploadedAt', 'desc').onSnapshot(snapshot => {
                grid.innerHTML = '';
                snapshot.forEach(doc => {
                    const img = doc.data();
                    const item = document.createElement('div');
                    item.className = 'ranking-card-image';
                    item.innerHTML = `
                        <img src="${img.url}" alt="${img.title}"><h4>${img.title}</h4>
                        <button class="btn btn-danger btn-sm" data-id="${doc.id}" data-path="${img.storagePath}" style="width: 90%; margin: 0 5% 10px 5%;">Delete</button>`;
                    item.querySelector('button').addEventListener('click', deleteRankingItem);
                    grid.appendChild(item);
                });
            });
        }
        async function deleteRankingItem(e) {
            const { id: docId, path: storagePath } = e.target.dataset;
            const collectionName = storagePath.includes('/pdf/') ? 'pdfRankings' : 'imageRankings';
            if (!confirm(`Delete this item?`)) return;
            try {
                await storage.ref(storagePath).delete();
                await db.collection(collectionName).doc(docId).delete();
            } catch (error) { alert("Delete failed. File might be missing."); }
        }
        
        // --- Draft Management & Publish ---
        document.getElementById('draft-create-form').addEventListener('submit', async (e) => {
            e.preventDefault();
            const title = document.getElementById('draft-create-title').value;
            const desc = document.getElementById('draft-create-desc').value;
            const now = new Date();
            const adviceEnds = new Date(now.getTime() + 5 * 60 * 60 * 1000); // 5 hours
            const votingEnds = new Date(now.getTime() + 13 * 60 * 60 * 1000); // 13 hours
            
            try {
                // 1. Create Draft
                await db.collection('drafts').add({
                    title, description: desc, status: 'advice',
                    createdAt: FieldValue.serverTimestamp(),
                    adviceEndsAt: adviceEnds, votingEndsAt: votingEnds,
                    createdBy: appState.currentUser.id, votes: [], advice: []
                });
                
                // 2. Publish system message to chats
                const systemMessage = {
                    text: `New Draft Published: "${title}". Go to the Voting page to participate.`,
                    userId: 'system', userName: 'Clan Command', userRole: 'System',
                    type: 'text', url: null, createdAt: FieldValue.serverTimestamp()
                };
                await db.collection('messages').doc('general').collection('chats').add(systemMessage);
                await db.collection('messages').doc('special').collection('chats').add(systemMessage);
                
                alert('Draft created and published to chats!');
                e.target.reset();
                showPage('drafts-list');
            } catch (error) { alert("Failed to create draft."); }
        });
        
        // --- Cabinet Management ---
        function loadCabinetManagement() {
            const list = document.getElementById('cabinet-checkbox-list');
            list.innerHTML = '';
            const candidates = appState.allUsersCache.filter(u => ['Elder', 'Co-Leader'].includes(u.role));
            if (candidates.length === 0) { list.innerHTML = '<p>No Elders or Co-Leaders found.</p>'; return; }
            candidates.forEach(user => {
                const isChecked = appState.currentCabinet.includes(user.id);
                list.innerHTML += `
                    <div class="form-group">
                        <input type="checkbox" id="cab-${user.id}" value="${user.id}" ${isChecked ? 'checked' : ''}>
                        <label for="cab-${user.id}">${user.name} (${user.role})</label>
                    </div>`;
            });
        }
        document.getElementById('cabinet-form').addEventListener('submit', async (e) => {
            e.preventDefault();
            const selectedIds = Array.from(e.target.querySelectorAll('input:checked')).map(cb => cb.value);
            if (selectedIds.length > 5) { alert('Max 5 members.'); return; }
            try {
                await db.collection('meta').doc('main').update({ cabinet: selectedIds });
                appState.currentCabinet = selectedIds; 
                alert('Cabinet updated.');
            } catch (error) { alert('Failed to update.'); }
        });
        
        // --- Inboxes ---
        function loadInbox(collectionName, elementId) {
            const list = document.getElementById(elementId);
            list.innerHTML = '<p>Loading...</p>';
            appState.listeners[elementId] = db.collection(collectionName).orderBy('createdAt', 'desc').limit(20)
                .onSnapshot(snapshot => {
                    if (snapshot.empty) { list.innerHTML = '<p>Inbox empty.</p>'; return; }
                    list.innerHTML = '';
                    snapshot.forEach(doc => {
                        const msg = doc.data();
                        const card = document.createElement('div');
                        card.className = 'card';
                        card.innerHTML = `
                            <h4>From: ${msg.userName} (${msg.userId})</h4>
                            <p><strong>Subject:</strong> ${msg.subject}</p>
                            <p>${msg.text}</p>
                            <small>${msg.createdAt.toDate().toLocaleString()}</small><br>
                            <button class="btn btn-sm btn-danger" data-id="${doc.id}">Delete</button>`;
                        card.querySelector('button').addEventListener('click', async () => {
                            if (confirm('Delete?')) {
                                await db.collection(collectionName).doc(doc.id).delete();
                            }
                        });
                        list.appendChild(card);
                    });
                });
        }
        
        // =================================================================
        // 11. NEW: FORCE MODE / GOD MODE
        // =================================================================
        
        const forceBtn = document.getElementById('forcefully-btn');
        const forceModals = {
            1: document.getElementById('modal-force-verify-1'),
            2: document.getElementById('modal-force-verify-2'),
            3: document.getElementById('modal-force-captcha'),
            4: document.getElementById('modal-force-reason'),
            5: document.getElementById('modal-force-warning'),
            6: document.getElementById('modal-force-unlocked')
        };
        const forceModalErrors = {
            1: document.getElementById('force-modal-error-1'),
            2: document.getElementById('force-modal-error-2'),
            3: document.getElementById('force-modal-error-3'),
            4: document.getElementById('force-modal-error-4')
        };
        
        forceBtn.addEventListener('click', () => showForceModal(1));
        
        document.querySelectorAll('.modal-close-btn').forEach(btn => {
            btn.addEventListener('click', () => {
                Object.values(forceModals).forEach(modal => modal.classList.add('hidden'));
            });
        });

        function showForceModal(step) {
            Object.values(forceModals).forEach(modal => modal.classList.add('hidden'));
            if (forceModals[step]) {
                forceModals[step].classList.remove('hidden');
                // Special setup for captcha
                if (step === 3) generateCaptcha();
            }
        }
        
        function forceAuthCheck(step) {
            const id = document.getElementById(`force-id-${step}`).value.trim();
            const pass = document.getElementById(`force-pass-${step}`).value;
            const errEl = forceModalErrors[step];
            
            if (id !== appState.currentUser.id || pass !== appState.currentUser.password) {
                showError(errEl, 'Invalid credentials.');
                return false;
            }
            showError(errEl, '');
            return true;
        }

        document.getElementById('force-form-1').addEventListener('submit', (e) => {
            e.preventDefault();
            if (forceAuthCheck(1)) showForceModal(2);
        });
        document.getElementById('force-form-2').addEventListener('submit', (e) => {
            e.preventDefault();
            if (forceAuthCheck(2)) showForceModal(3);
        });
        
        function generateCaptcha() {
            appState.currentCaptcha = Math.random().toString(36).substring(2, 8).replace(/[ilI1oO0]/g, 'a'); // Avoid confusing chars
            document.getElementById('modal-captcha-image').textContent = appState.currentCaptcha;
        }
        
        document.getElementById('force-form-3').addEventListener('submit', (e) => {
            e.preventDefault();
            const input = document.getElementById('force-captcha-input').value;
            if (input === appState.currentCaptcha) {
                showError(forceModalErrors[3], '');
                showForceModal(4);
            } else {
                showError(forceModalErrors[3], 'CAPTCHA does not match.');
                generateCaptcha();
            }
        });
        
        const reasonTextarea = document.getElementById('force-reason');
        reasonTextarea.addEventListener('input', () => {
            const words = reasonTextarea.value.trim().split(/\s+/).filter(Boolean).length;
            document.getElementById('word-count').textContent = `Words: ${words}`;
        });
        
        document.getElementById('force-form-4').addEventListener('submit', async (e) => {
            e.preventDefault();
            const reason = reasonTextarea.value;
            const words = reason.trim().split(/\s+/).filter(Boolean).length;
            if (words < 50) {
                showError(forceModalErrors[4], `Justification must be at least 50 words. (Current: ${words})`);
                return;
            }
            showError(forceModalErrors[4], '');
            
            try {
                await db.collection('auditLogs').add({
                    type: 'ForceModeAccess',
                    userId: appState.currentUser.id,
                    reason: reason,
                    timestamp: FieldValue.serverTimestamp()
                });
                showForceModal(5);
            } catch (error) {
                showError(forceModalErrors[4], 'Failed to log reason. Cannot proceed.');
            }
        });
        
        document.getElementById('force-agree-btn').addEventListener('click', () => showForceModal(6));
        document.getElementById('open-force-dashboard-btn').addEventListener('click', () => {
            Object.values(forceModals).forEach(modal => modal.classList.add('hidden'));
            showPage('force-mode-dashboard');
        });
        
        // --- Force Mode Dashboard ---
        function loadForceModeDashboard() {
            document.getElementById('force-mode-exit-btn').onclick = () => showPage('leader-dashboard');
            loadForcePlayerManagement();
            loadForceChatLog('general', 'force-chat-log-ga');
            loadForceChatLog('special', 'force-chat-log-sa');
            loadForceInbox('dms', 'force-inbox-quarry');
            loadForceInbox('advice', 'force-inbox-advisory');
        }
        
        function loadForcePlayerManagement() {
            const tbody = document.getElementById('force-player-management-table').querySelector('tbody');
            tbody.innerHTML = '';
            appState.allUsersCache.forEach(user => {
                const tr = document.createElement('tr');
                tr.dataset.userId = user.id;
                const isLeader = user.role === 'Leader';
                tr.innerHTML = `
                    <td><b>${user.name}</b><br><small>${user.id}</small></td>
                    <td>
                        <select class="form-control force-role-select" ${isLeader ? 'disabled' : ''}>
                            <option value="Member" ${user.role === 'Member' ? 'selected' : ''}>Member</option>
                            <option value="Elder" ${user.role === 'Elder' ? 'selected' : ''}>Elder</option>
                            <option value="Co-Leader" ${user.role === 'Co-Leader' ? 'selected' : ''}>Co-Leader</option>
                            <option value="Leader" ${user.role === 'Leader' ? 'selected' : ''}>Leader</option>
                        </select>
                    </td>
                    <td><span class="draft-status ${user.status}">${user.status}</span></td>
                    <td><span class="draft-status ${user.chatBlocked ? 'banned' : 'active'}">${user.chatBlocked ? 'Blocked' : 'Active'}</span></td>
                    <td>
                        <button class="btn btn-sm btn-primary force-edit-btn">Edit</button>
                        <button class="btn btn-sm ${user.chatBlocked ? 'btn-success' : 'btn-warning'} force-chat-block-btn">${user.chatBlocked ? 'Unblock' : 'Block'}</button>
                    </td>`;
                tbody.appendChild(tr);
            });
            
            tbody.removeEventListener('click', handleForceMgmtClick);
            tbody.removeEventListener('change', handleForceMgmtChange);
            tbody.addEventListener('click', handleForceMgmtClick);
            tbody.addEventListener('change', handleForceMgmtChange);
        }
        
        async function handleForceMgmtClick(e) {
            const target = e.target;
            const tr = target.closest('tr');
            if (!tr) return;
            const userId = tr.dataset.userId;

            if (target.classList.contains('force-edit-btn')) {
                const user = appState.allUsersCache.find(u => u.id === userId);
                document.getElementById('force-edit-title').textContent = `Editing Player: ${user.name}`;
                document.getElementById('force-edit-id').value = user.id;
                document.getElementById('force-edit-name').value = user.name;
                document.getElementById('force-edit-password').value = '';
                document.getElementById('modal-force-edit-player').classList.remove('hidden');
            }
            if (target.classList.contains('force-chat-block-btn')) {
                const user = appState.allUsersCache.find(u => u.id === userId);
                const newBlockStatus = !user.chatBlocked;
                if (confirm(`${newBlockStatus ? 'Block' : 'Unblock'} chat for ${user.name}?`)) {
                    await db.collection('users').doc(userId).update({ chatBlocked: newBlockStatus });
                    user.chatBlocked = newBlockStatus; // Update cache
                    loadForcePlayerManagement();
                }
            }
        }
        async function handleForceMgmtChange(e) {
            if (e.target.classList.contains('force-role-select')) {
                const newRole = e.target.value;
                const userId = e.target.closest('tr').dataset.userId;
                if (confirm(`FORCE CHANGE ${userId}'s role to ${newRole}?`)) {
                    await db.collection('users').doc(userId).update({ role: newRole });
                    appState.allUsersCache.find(u => u.id === userId).role = newRole;
                    loadForcePlayerManagement();
                }
            }
        }
        
        document.getElementById('force-edit-form').addEventListener('submit', async (e) => {
            e.preventDefault();
            const userId = document.getElementById('force-edit-id').value;
            const newName = document.getElementById('force-edit-name').value;
            const newPass = document.getElementById('force-edit-password').value;
            
            const updates = { name: newName };
            if (newPass) updates.password = newPass;
            
            if (confirm(`Save changes for ${userId}?`)) {
                await db.collection('users').doc(userId).update(updates);
                const user = appState.allUsersCache.find(u => u.id === userId);
                user.name = newName;
                if (newPass) user.password = newPass;
                loadForcePlayerManagement();
                document.getElementById('modal-force-edit-player').classList.add('hidden');
            }
        });

        function loadForceChatLog(type, elementId) {
            const logEl = document.getElementById(elementId);
            appState.listeners[elementId] = db.collection('messages').doc(type).collection('chats')
                .orderBy('createdAt', 'desc').limit(50).onSnapshot(snapshot => {
                    logEl.innerHTML = '';
                    snapshot.forEach(doc => {
                        const msg = {id: doc.id, ...doc.data()};
                        logEl.innerHTML += `
                        <p style="border-bottom: 1px solid #eee; padding-bottom: 5px; margin-bottom: 5px;">
                            <strong>${msg.userName}:</strong> ${msg.text.substring(0, 100)}...
                            <button class="btn btn-danger btn-sm" style="float: right;" data-chat="${type}" data-id="${msg.id}">Delete</button>
                        </p>`;
                    });
                    logEl.querySelectorAll('button').forEach(btn => {
                        btn.addEventListener('click', () => handleDeleteMessage(btn.dataset.chat, btn.dataset.id));
                    });
                });
        }
        
        function loadForceInbox(collectionName, elementId) {
            const list = document.getElementById(elementId);
            list.innerHTML = '<p>Loading...</p>';
            appState.listeners[elementId] = db.collection(collectionName).orderBy('createdAt', 'desc').limit(50)
                .onSnapshot(snapshot => {
                    if (snapshot.empty) { list.innerHTML = '<p>Inbox empty.</p>'; return; }
                    list.innerHTML = '';
                    snapshot.forEach(doc => {
                        const msg = doc.data();
                        list.innerHTML += `
                        <p style="border-bottom: 1px solid #eee; padding-bottom: 5px; margin-bottom: 5px;">
                            <strong>From: ${msg.userName}</strong> (Subject: ${msg.subject})<br>
                            ${msg.text.substring(0, 100)}...
                        </p>`;
                    });
                });
        }

        // =================================================================
        // 12. HELPER FUNCTIONS
        // =================================================================

        function showError(element, message) {
            if (element) {
                element.textContent = message;
                element.style.display = message ? 'block' : 'none';
            } else { console.error(message); }
        }
        
        function startCountdown(element, endTime) {
            if (element.timerInterval) clearInterval(element.timerInterval);
            function updateTimer() {
                const distance = endTime.getTime() - new Date().getTime();
                if (distance < 0) {
                    clearInterval(element.timerInterval);
                    element.textContent = "Time's Up!";
                    return;
                }
                const d = Math.floor(distance / (1000 * 60 * 60 * 24));
                const h = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
                const m = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
                const s = Math.floor((distance % (1000 * 60)) / 1000);
                element.textContent = `${d}d ${h}h ${m}m ${s}s remaining`;
            }
            updateTimer();
            element.timerInterval = setInterval(updateTimer, 1000);
        }

        // =================================================================
        // 13. INITIALIZE THE APP
        // =================================================================
        
        initApp();

    });
    </script>

</body>
</html>
