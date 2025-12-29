[index.html](https://github.com/user-attachments/files/24375362/index.html)
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SwiftTrack Pro - Shipping Tracker</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* ===== ENHANCED STYLES ===== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary: #1a365d;
            --secondary: #2b6cb0;
            --accent: #e53e3e;
            --light: #f7fafc;
            --success: #38a169;
            --warning: #d69e2e;
            --gray-100: #edf2f7;
            --gray-200: #e2e8f0;
        }

        body {
            background-color: var(--light);
            color: #2d3748;
            line-height: 1.6;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* ===== ENHANCED HEADER WITH MENU ===== */
        header {
            background-color: white;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.08);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 0;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 12px;
            font-size: 1.8rem;
            font-weight: 800;
            color: var(--primary);
            text-decoration: none;
        }

        .logo-icon {
            color: var(--secondary);
            font-size: 2rem;
        }

        /* Main Navigation Menu */
        .main-nav {
            display: flex;
            gap: 2rem;
        }

        .nav-link {
            color: #4a5568;
            text-decoration: none;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 8px;
            padding: 0.5rem 1rem;
            border-radius: 6px;
            transition: all 0.3s;
        }

        .nav-link:hover {
            background-color: var(--gray-100);
            color: var(--primary);
        }

        .nav-link.active {
            background-color: var(--secondary);
            color: white;
        }

        /* User Menu */
        .user-menu {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        #adminLoginBtn {
            background-color: var(--primary);
            color: white;
            border: none;
            padding: 0.6rem 1.5rem;
            border-radius: 6px;
            font-weight: 600;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 8px;
            transition: background-color 0.3s;
        }

        #adminLoginBtn:hover {
            background-color: #2d3748;
        }

        /* ===== HERO SECTION WITH IMAGE ===== */
        .hero-section {
            background: linear-gradient(rgba(26, 54, 93, 0.85), rgba(43, 108, 176, 0.9)), 
                        url('https://images.unsplash.com/photo-1556742049-0cfed4f6a45d?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80');
            background-size: cover;
            background-position: center;
            color: white;
            padding: 5rem 0;
            text-align: center;
            border-radius: 0 0 20px 20px;
            margin-bottom: 3rem;
        }

        .hero-content h1 {
            font-size: 3.2rem;
            margin-bottom: 1.2rem;
            font-weight: 800;
        }

        .hero-content p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 2rem;
            opacity: 0.95;
        }

        /* ===== TRACKING INPUT SECTION ===== */
        .tracking-section {
            background: white;
            padding: 2.5rem;
            border-radius: 12px;
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.08);
            margin-bottom: 3rem;
            border: 1px solid var(--gray-200);
        }

        .section-title {
            color: var(--primary);
            margin-bottom: 1.8rem;
            display: flex;
            align-items: center;
            gap: 12px;
            font-size: 1.6rem;
        }

        .tracking-form {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
        }

        .form-group {
            display: flex;
            flex-direction: column;
            gap: 0.5rem;
        }

        .form-group label {
            font-weight: 600;
            color: var(--primary);
        }

        .tracking-input {
            display: flex;
            gap: 10px;
        }

        .tracking-input input {
            flex: 1;
            padding: 15px;
            border: 2px solid var(--gray-200);
            border-radius: 8px;
            font-size: 1rem;
            transition: border-color 0.3s;
        }

        .tracking-input input:focus {
            border-color: var(--secondary);
            outline: none;
        }

        .track-btn {
            background-color: var(--secondary);
            color: white;
            border: none;
            padding: 0 2rem;
            border-radius: 8px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: background-color 0.3s;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            height: 53px;
        }

        .track-btn:hover {
            background-color: #2c5282;
        }

        /* ===== SHIPMENT STATUS ICONS ===== */
        .status-icons {
            display: flex;
            justify-content: space-between;
            margin: 2rem 0;
            padding: 1.5rem;
            background-color: var(--gray-100);
            border-radius: 10px;
        }

        .status-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            gap: 10px;
            flex: 1;
        }

        .status-icon {
            width: 60px;
            height: 60px;
            background: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            color: var(--secondary);
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        }

        /* ===== TRACKING RESULTS ===== */
        .tracking-results {
            background-color: white;
            padding: 2.5rem;
            border-radius: 12px;
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.08);
            margin-bottom: 3rem;
            border: 1px solid var(--gray-200);
            display: none;
        }

        .results-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 2rem;
            padding-bottom: 1.5rem;
            border-bottom: 1px solid var(--gray-200);
        }

        .tracking-id {
            font-size: 1.3rem;
            font-weight: 700;
            color: var(--primary);
        }

        .status-badge {
            padding: 8px 20px;
            border-radius: 20px;
            font-weight: 700;
            font-size: 0.9rem;
        }

        .status-pending {
            background-color: #fff3e0;
            color: var(--warning);
        }

        .status-in-transit {
            background-color: #e1f5fe;
            color: var(--secondary);
        }

        .status-delivered {
            background-color: #e8f5e9;
            color: var(--success);
        }

        .status-on-hold {
            background-color: #ffebee;
            color: var(--accent);
        }

        /* ===== PROGRESS TRACKING ===== */
        .progress-container {
            position: relative;
            margin: 2.5rem 0;
        }

        .progress-line {
            position: absolute;
            top: 25px;
            left: 0;
            right: 0;
            height: 4px;
            background-color: var(--gray-200);
            z-index: 1;
        }

        .progress-fill {
            position: absolute;
            top: 25px;
            left: 0;
            height: 4px;
            background-color: var(--secondary);
            z-index: 2;
            transition: width 0.5s ease;
        }

        .progress-steps {
            display: flex;
            justify-content: space-between;
            position: relative;
            z-index: 3;
        }

        .step {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            width: 120px;
        }

        .step-icon {
            width: 50px;
            height: 50px;
            background-color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            border: 3px solid var(--gray-200);
            margin-bottom: 12px;
            color: #a0aec0;
            font-size: 1.2rem;
            transition: all 0.3s;
        }

        .step.active .step-icon {
            background-color: var(--secondary);
            border-color: var(--secondary);
            color: white;
            transform: scale(1.1);
        }

        .step.completed .step-icon {
            background-color: var(--success);
            border-color: var(--success);
            color: white;
        }

        .step-title {
            font-weight: 600;
            font-size: 0.9rem;
            margin-bottom: 5px;
            color: var(--primary);
        }

        .step-date {
            font-size: 0.8rem;
            color: #718096;
        }

        /* ===== SHIPMENT DETAILS ===== */
        .shipment-details {
            margin-top: 2.5rem;
        }

        .details-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 1.5rem;
            margin-top: 1.5rem;
        }

        .detail-card {
            background-color: var(--gray-100);
            padding: 1.5rem;
            border-radius: 10px;
            border-left: 4px solid var(--secondary);
            transition: transform 0.3s;
        }

        .detail-card:hover {
            transform: translateY(-5px);
        }

        .detail-title {
            font-weight: 600;
            color: #718096;
            font-size: 0.9rem;
            margin-bottom: 8px;
        }

        .detail-value {
            font-size: 1.2rem;
            font-weight: 700;
            color: var(--primary);
        }

        /* ===== ADMIN SECTION (PROTECTED) ===== */
        .admin-section {
            background: white;
            padding: 2.5rem;
            border-radius: 12px;
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.08);
            margin-bottom: 3rem;
            border: 1px solid var(--gray-200);
            display: none;
        }

        .admin-controls {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            margin-bottom: 2rem;
        }

        .admin-btn {
            padding: 12px 24px;
            background-color: var(--gray-100);
            border: none;
            border-radius: 8px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .admin-btn:hover {
            background-color: var(--gray-200);
            transform: translateY(-2px);
        }

        .btn-primary {
            background-color: var(--secondary);
            color: white;
        }

        .btn-primary:hover {
            background-color: #2c5282;
        }

        .btn-danger {
            background-color: var(--accent);
            color: white;
        }

        .btn-danger:hover {
            background-color: #c53030;
        }

        /* ===== FOOTER ENHANCEMENT ===== */
        .main-footer {
            background-color: var(--primary);
            color: white;
            padding: 3rem 0 1.5rem;
            margin-top: auto;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2.5rem;
            margin-bottom: 2.5rem;
        }

        .footer-logo {
            font-size: 1.8rem;
            font-weight: 700;
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .footer-links h3 {
            margin-bottom: 1.2rem;
            font-size: 1.2rem;
        }

        .footer-links ul {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 0.7rem;
        }

        .footer-links a {
            color: #cbd5e0;
            text-decoration: none;
            transition: color 0.3s;
        }

        .footer-links a:hover {
            color: white;
        }

        .copyright {
            text-align: center;
            padding-top: 1.5rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 0.9rem;
            opacity: 0.7;
        }

        /* ===== ADMIN LOGIN MODAL ===== */
        .login-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 2000;
            align-items: center;
            justify-content: center;
        }

        .login-form {
            background: white;
            width: 90%;
            max-width: 400px;
            padding: 2.5rem;
            border-radius: 12px;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.2);
        }

        .login-form h3 {
            color: var(--primary);
            margin-bottom: 1.5rem;
            text-align: center;
        }

        .login-form .form-group {
            margin-bottom: 1.5rem;
        }

        .login-form .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
            color: var(--primary);
        }

        .login-form .form-group input {
            width: 100%;
            padding: 0.9rem;
            border: 2px solid var(--gray-200);
            border-radius: 8px;
            font-size: 1rem;
            transition: border-color 0.3s;
        }

        .login-form .form-group input:focus {
            border-color: var(--secondary);
            outline: none;
        }

        /* ===== MODAL ===== */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }

        .modal-content {
            background-color: white;
            width: 90%;
            max-width: 500px;
            border-radius: 12px;
            padding: 2rem;
            position: relative;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.2);
        }

        .close-modal {
            position: absolute;
            top: 15px;
            right: 15px;
            font-size: 1.5rem;
            cursor: pointer;
            color: #718096;
        }

        .modal h3 {
            margin-bottom: 1.5rem;
            color: var(--primary);
        }

        /* ===== RESPONSIVE DESIGN ===== */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                gap: 1.2rem;
            }
            
            .main-nav {
                gap: 1rem;
            }
            
            .hero-content h1 {
                font-size: 2.4rem;
            }
            
            .status-icons {
                flex-wrap: wrap;
                gap: 1.5rem;
            }
            
            .status-item {
                flex: 0 0 calc(50% - 1rem);
            }
            
            .tracking-input {
                flex-direction: column;
            }
            
            .track-btn {
                width: 100%;
                padding: 15px;
            }
            
            .progress-steps {
                flex-wrap: wrap;
                gap: 1.5rem;
            }
            
            .step {
                width: calc(50% - 1rem);
            }
        }

        /* ===== ANIMATIONS ===== */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .fade-in {
            animation: fadeIn 0.5s ease forwards;
        }
    </style>
</head>
<body>
    <!-- ===== HEADER WITH MENU ===== -->
    <header>
        <div class="container header-content">
            <a href="#" class="logo">
                <i class="fas fa-shipping-fast logo-icon"></i>
                <span>SwiftTrack Pro</span>
            </a>
            
            <nav class="main-nav">
                <a href="#" class="nav-link active">
                    <i class="fas fa-home"></i> Home
                </a>
                <a href="#" class="nav-link">
                    <i class="fas fa-map-marker-alt"></i> Track
                </a>
                <a href="#" class="nav-link">
                    <i class="fas fa-question-circle"></i> Help
                </a>
                <a href="#" class="nav-link">
                    <i class="fas fa-phone-alt"></i> Contact
                </a>
            </nav>
            
            <div class="user-menu">
                <button id="adminLoginBtn">
                    <i class="fas fa-sign-in-alt"></i> Admin Login
                </button>
            </div>
        </div>
    </header>

    <!-- ===== HERO SECTION ===== -->
    <section class="hero-section">
        <div class="container hero-content">
            <h1>Global Shipping & Tracking Solutions</h1>
            <p>Track your shipments in real-time with our advanced tracking system. Get instant updates from pickup to delivery.</p>
            <div class="tracking-input" style="max-width: 600px; margin: 0 auto;">
                <input type="text" id="trackingId" placeholder="Enter your tracking number (e.g., ST-789456123)" value="ST-789456123">
                <button class="track-btn" id="trackBtn">
                    <i class="fas fa-search"></i> Track Shipment
                </button>
            </div>
        </div>
    </section>

    <div class="container">
        <!-- ===== SHIPMENT STATUS ICONS ===== -->
        <div class="status-icons">
            <div class="status-item">
                <div class="status-icon">
                    <i class="fas fa-box"></i>
                </div>
                <div>
                    <div style="font-weight: 600;">Order Received</div>
                    <div style="font-size: 0.9rem; color: #718096;">Step 1</div>
                </div>
            </div>
            <div class="status-item">
                <div class="status-icon">
                    <i class="fas fa-cog"></i>
                </div>
                <div>
                    <div style="font-weight: 600;">Processing</div>
                    <div style="font-size: 0.9rem; color: #718096;">Step 2</div>
                </div>
            </div>
            <div class="status-item">
                <div class="status-icon">
                    <i class="fas fa-plane"></i>
                </div>
                <div>
                    <div style="font-weight: 600;">In Transit</div>
                    <div style="font-size: 0.9rem; color: #718096;">Step 3</div>
                </div>
            </div>
            <div class="status-item">
                <div class="status-icon">
                    <i class="fas fa-truck"></i>
                </div>
                <div>
                    <div style="font-weight: 600;">Out for Delivery</div>
                    <div style="font-size: 0.9rem; color: #718096;">Step 4</div>
                </div>
            </div>
        </div>

        <!-- ===== TRACKING RESULTS ===== -->
        <section class="tracking-results" id="trackingResults">
            <div class="results-header">
                <div>
                    <div class="tracking-id">Tracking ID: <span id="displayTrackingId">ST-789456123</span></div>
                    <div style="font-size: 0.9rem; color: #718096; margin-top: 5px;">
                        Last updated: <span id="lastUpdated">Today, 10:30 AM</span>
                    </div>
                </div>
                <div class="status-badge status-in-transit" id="statusBadge">In Transit</div>
            </div>

            <!-- Progress Tracking -->
            <div class="progress-container">
                <div class="progress-line"></div>
                <div class="progress-fill" id="progressFill" style="width: 60%;"></div>
                <div class="progress-steps" id="progressSteps">
                    <!-- Steps will be dynamically added here -->
                </div>
            </div>

            <!-- Shipment Details -->
            <div class="shipment-details">
                <h3 class="section-title">
                    <i class="fas fa-info-circle"></i> Shipment Details
                </h3>
                <div class="details-grid">
                    <div class="detail-card">
                        <div class="detail-title">Origin</div>
                        <div class="detail-value" id="detailOrigin">New York, USA</div>
                    </div>
                    <div class="detail-card">
                        <div class="detail-title">Destination</div>
                        <div class="detail-value" id="detailDestination">London, UK</div>
                    </div>
                    <div class="detail-card">
                        <div class="detail-title">Weight</div>
                        <div class="detail-value" id="detailWeight">5.2 kg</div>
                    </div>
                    <div class="detail-card">
                        <div class="detail-title">Estimated Delivery</div>
                        <div class="detail-value" id="detailDelivery">Dec 28, 2023</div>
                    </div>
                </div>
            </div>

            <!-- Shipment History -->
            <div class="shipment-details" style="margin-top: 2rem;">
                <h3 class="section-title">
                    <i class="fas fa-history"></i> Shipment History
                </h3>
                <div id="shipmentHistory">
                    <!-- History items will be added here -->
                </div>
            </div>
        </section>

        <!-- ===== ADMIN SECTION (PROTECTED) ===== -->
        <section class="admin-section" id="adminSection">
            <h2 class="section-title">
                <i class="fas fa-user-shield"></i> Admin Controls
            </h2>
            <p style="margin-bottom: 1.5rem; color: #718096;">
                Manage shipments, update statuses, and generate tracking IDs. This section requires admin login.
            </p>
            
            <div class="admin-controls">
                <button class="admin-btn btn-primary" id="generateTrackingBtn">
                    <i class="fas fa-plus-circle"></i> Generate Tracking ID
                </button>
                <button class="admin-btn" id="updateStatusBtn">
                    <i class="fas fa-edit"></i> Update Status
                </button>
                <button class="admin-btn btn-danger" id="resetDemoBtn">
                    <i class="fas fa-redo"></i> Reset Database 
                </button>
            </div>
            
            <div id="adminMessage" style="padding: 1rem; background-color: #f1f8e9; border-radius: 8px; display: none;">
                <!-- Admin messages will appear here -->
            </div>
        </section>
    </div>

    <!-- ===== FOOTER ===== -->
    <footer class="main-footer">
        <div class="container">
            <div class="footer-content">
                <div class="footer-links">
                    <div class="footer-logo">
                        <i class="fas fa-shipping-fast"></i> SwiftTrack Pro
                    </div>
                    <p>Real-time tracking solutions for businesses and individuals. We make shipping transparent and reliable.</p>
                </div>
                <div class="footer-links">
                    <h3>Quick Links</h3>
                    <ul>
                        <li><a href="#">Track Shipment</a></li>
                        <li><a href="#">Shipping Rates</a></li>
                        <li><a href="#">Service Guide</a></li>
                        <li><a href="#">Locations</a></li>
                    </ul>
                </div>
                <div class="footer-links">
                    <h3>Contact Us</h3>
                    <ul>
                        <li><i class="fas fa-envelope"></i> swifttrackpro@gmail.com</li>
                        <li><i class="fas fa-phone"></i> +1 (800) 123-4567</li>
                        <li><i class="fas fa-map-marker-alt"></i> 123 Shipping St, Logistics City</li>
                    </ul>
                </div>
                <div class="footer-links">
                    <h3>Business Hours</h3>
                    <ul>
                        <li>Mon-Fri: 8am-8pm EST</li>
                        <li>Sat-Sun: 9am-5pm EST</li>
                        <li>24/7 Tracking Available</li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                &copy; 2023 SwiftTrack Pro. All rights reserved.
            </div>
        </div>
    </footer>

    <!-- ===== ADMIN LOGIN MODAL ===== -->
    <div class="login-modal" id="loginModal">
        <div class="login-form">
            <h3><i class="fas fa-lock"></i> Admin Login</h3>
            <form id="loginForm">
                <div class="form-group">
                    <label for="username">Username</label>
                    <input type="text" id="username" placeholder="Enter admin username" required>
                </div>
                <div class="form-group">
                    <label for="password">Password</label>
                    <input type="password" id="password" placeholder="Enter password" required>
                </div>
                <div style="color: #e53e3e; margin-bottom: 1rem; display: none;" id="loginError">
                    <i class="fas fa-exclamation-circle"></i> Invalid username or password
                </div>
                <button type="submit" class="track-btn" style="width: 100%;">
                    <i class="fas fa-sign-in-alt"></i> Login
                </button>
            </form>
            <p style="text-align: center; margin-top: 1rem; font-size: 0.9rem; color: #718096;">
                Demo credentials: <strong>admin003</strong> / <strong>password123</strong>
            </p>
        </div>
    </div>

    <!-- ===== ADMIN ACTION MODAL ===== -->
    <div class="modal" id="adminModal">
        <div class="modal-content">
            <span class="close-modal" id="closeModal">&times;</span>
            <h3 id="modalTitle">Update Shipment Status</h3>
            <div id="modalContent">
                <!-- Modal content will be dynamically added -->
            </div>
        </div>
    </div>

    <script>
        // ===== CONFIGURATION =====
        const API_BASE_URL = 'http://localhost:3000/api';
        const ADMIN_CREDENTIALS = {
            username: 'admin',
            password: 'uwgu-daniel'
        };

        // ===== DOM ELEMENTS =====
        const trackBtn = document.getElementById('trackBtn');
        const trackingIdInput = document.getElementById('trackingId');
        const trackingResults = document.getElementById('trackingResults');
        const displayTrackingId = document.getElementById('displayTrackingId');
        const lastUpdated = document.getElementById('lastUpdated');
        const statusBadge = document.getElementById('statusBadge');
        const progressFill = document.getElementById('progressFill');
        const progressSteps = document.getElementById('progressSteps');
        const shipmentHistory = document.getElementById('shipmentHistory');
        const adminSection = document.getElementById('adminSection');
        const generateTrackingBtn = document.getElementById('generateTrackingBtn');
        const updateStatusBtn = document.getElementById('updateStatusBtn');
        const resetDemoBtn = document.getElementById('resetDemoBtn');
        const adminMessage = document.getElementById('adminMessage');
        const adminModal = document.getElementById('adminModal');
        const closeModal = document.getElementById('closeModal');
        const modalTitle = document.getElementById('modalTitle');
        const modalContent = document.getElementById('modalContent');
        const adminLoginBtn = document.getElementById('adminLoginBtn');
        const loginModal = document.getElementById('loginModal');
        const loginForm = document.getElementById('loginForm');
        const loginError = document.getElementById('loginError');

        // ===== ADMIN LOGIN SYSTEM =====
        function checkLoginStatus() {
            const isLoggedIn = localStorage.getItem('adminLoggedIn') === 'true';
            if (isLoggedIn) {
                adminSection.style.display = 'block';
                adminLoginBtn.innerHTML = '<i class="fas fa-user-shield"></i> Admin Panel';
                adminLoginBtn.style.backgroundColor = 'var(--success)';
            } else {
                adminSection.style.display = 'none';
                adminLoginBtn.innerHTML = '<i class="fas fa-sign-in-alt"></i> Admin Login';
                adminLoginBtn.style.backgroundColor = 'var(--primary)';
            }
        }

        adminLoginBtn.addEventListener('click', function() {
            const isLoggedIn = localStorage.getItem('adminLoggedIn') === 'true';
            
            if (isLoggedIn) {
                adminSection.scrollIntoView({ behavior: 'smooth' });
            } else {
                loginModal.style.display = 'flex';
                loginError.style.display = 'none';
                document.getElementById('username').value = '';
                document.getElementById('password').value = '';
            }
        });

        loginForm.addEventListener('submit', function(e) {
            e.preventDefault();
            
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;
            
            if (username === ADMIN_CREDENTIALS.username && password === ADMIN_CREDENTIALS.password) {
                localStorage.setItem('adminLoggedIn', 'true');
                loginModal.style.display = 'none';
                checkLoginStatus();
                showAdminMessage('Successfully logged in as administrator', 'success');
                adminSection.scrollIntoView({ behavior: 'smooth' });
            } else {
                loginError.style.display = 'block';
                document.getElementById('password').value = '';
            }
        });

        loginModal.addEventListener('click', function(e) {
            if (e.target === loginModal) {
                loginModal.style.display = 'none';
            }
        });

        // ===== SHIPMENT TRACKING FUNCTIONS =====
        trackBtn.addEventListener('click', async function() {
            const trackingId = trackingIdInput.value.trim().toUpperCase();
            
            if (!trackingId) {
                showAdminMessage("Please enter a tracking ID", "error");
                return;
            }
            
            try {
                const response = await fetch(`${API_BASE_URL}/shipments/${trackingId}`);
                
                if (!response.ok) {
                    if (response.status === 404) {
                        showAdminMessage(`Tracking ID "${trackingId}" not found.`, "error");
                    } else {
                        showAdminMessage("Error fetching shipment data", "error");
                    }
                    return;
                }
                
                const shipment = await response.json();
                displayTrackingData(shipment);
                trackingResults.style.display = 'block';
                trackingResults.classList.add('fade-in');
                
                trackingResults.scrollIntoView({ behavior: 'smooth' });
            } catch (error) {
                console.error('Error:', error);
                showAdminMessage("Could not connect to server. Make sure the backend is running.", "error");
            }
        });

        trackingIdInput.addEventListener('keyup', function(event) {
            if (event.key === 'Enter') {
                trackBtn.click();
            }
        });

        function displayTrackingData(shipment) {
            // Update basic info
            displayTrackingId.textContent = shipment.tracking_id;
            lastUpdated.textContent = formatDate(shipment.updated_at);
            
            // Update status badge
            const statusText = {
                "pending": "Pending",
                "in-transit": "In Transit",
                "delivered": "Delivered",
                "on-hold": "On Hold"
            };
            
            const statusClasses = {
                "pending": "status-pending",
                "in-transit": "status-in-transit",
                "delivered": "status-delivered",
                "on-hold": "status-on-hold"
            };
            
            statusBadge.textContent = statusText[shipment.status] || shipment.status;
            statusBadge.className = `status-badge ${statusClasses[shipment.status] || 'status-pending'}`;
            
            // Update progress based on status
            let progress = 20;
            if (shipment.status === 'in-transit') progress = 60;
            if (shipment.status === 'on-hold') progress = 40;
            if (shipment.status === 'delivered') progress = 100;
            
            progressFill.style.width = `${progress}%`;
            
            // Update progress steps
            progressSteps.innerHTML = '';
            const steps = getStepsForStatus(shipment.status, shipment.estimated_delivery);
            
            steps.forEach(step => {
                const stepElement = document.createElement('div');
                stepElement.className = `step ${step.completed ? 'completed' : ''} ${step.active ? 'active' : ''}`;
                
                stepElement.innerHTML = `
                    <div class="step-icon">
                        <i class="fas fa-${step.icon}"></i>
                    </div>
                    <div class="step-title">${step.title}</div>
                    <div class="step-date">${step.date}</div>
                `;
                
                progressSteps.appendChild(stepElement);
            });
            
            // Update shipment details
            document.getElementById('detailOrigin').textContent = shipment.origin;
            document.getElementById('detailDestination').textContent = shipment.destination;
            document.getElementById('detailWeight').textContent = `${shipment.weight} kg`;
            document.getElementById('detailDelivery').textContent = formatDate(shipment.estimated_delivery, true);
            
            // Update shipment history
            shipmentHistory.innerHTML = '';
            if (shipment.history && shipment.history.length > 0) {
                shipment.history.forEach(item => {
                    const historyItem = document.createElement('div');
                    historyItem.style.padding = '1rem';
                    historyItem.style.borderBottom = '1px solid var(--gray-200)';
                    historyItem.style.display = 'flex';
                    historyItem.style.gap = '1rem';
                    
                    historyItem.innerHTML = `
                        <div style="min-width: 120px; color: #718096; font-size: 0.9rem;">${formatDate(item.created_at)}</div>
                        <div style="flex: 1;">
                            <div style="font-weight: 600; color: var(--primary);">${item.location}</div>
                            <div style="color: #4a5568; margin-top: 3px;">${item.description}</div>
                        </div>
                    `;
                    
                    shipmentHistory.appendChild(historyItem);
                });
            } else {
                shipmentHistory.innerHTML = '<p style="color: #718096; text-align: center; padding: 2rem;">No tracking history available.</p>';
            }
        }

        // ===== ADMIN FUNCTIONS =====
        generateTrackingBtn.addEventListener('click', function() {
            modalTitle.textContent = "Generate New Tracking ID";
            modalContent.innerHTML = `
                <div class="form-group">
                    <label for="newOrigin">Origin</label>
                    <input type="text" id="newOrigin" class="tracking-input" style="width: 100%;" placeholder="e.g. Chicago, USA">
                </div>
                <div class="form-group">
                    <label for="newDestination">Destination</label>
                    <input type="text" id="newDestination" class="tracking-input" style="width: 100%;" placeholder="e.g. Paris, France">
                </div>
                <div class="form-group">
                    <label for="newWeight">Weight (kg)</label>
                    <input type="number" id="newWeight" class="tracking-input" style="width: 100%;" placeholder="e.g. 3.5" step="0.1">
                </div>
                <button id="confirmGenerate" class="track-btn" style="width: 100%; margin-top: 1rem;">
                    <i class="fas fa-plus-circle"></i> Generate Tracking ID
                </button>
            `;
            
            adminModal.style.display = 'flex';
            
            document.getElementById('confirmGenerate').addEventListener('click', async function() {
                const origin = document.getElementById('newOrigin').value.trim();
                const destination = document.getElementById('newDestination').value.trim();
                const weight = document.getElementById('newWeight').value.trim();
                
                if (!origin || !destination || !weight) {
                    alert("Please fill in all fields");
                    return;
                }
                
                try {
                    const response = await fetch(`${API_BASE_URL}/shipments`, {
                        method: 'POST',
                        headers: {
                            'Content-Type': 'application/json',
                        },
                        body: JSON.stringify({ origin, destination, weight })
                    });
                    
                    if (!response.ok) {
                        throw new Error('Failed to create shipment');
                    }
                    
                    const data = await response.json();
                    
                    trackingIdInput.value = data.trackingId;
                    
                    adminModal.style.display = 'none';
                    
                    const shipmentResponse = await fetch(`${API_BASE_URL}/shipments/${data.trackingId}`);
                    const shipment = await shipmentResponse.json();
                    
                    displayTrackingData(shipment);
                    trackingResults.style.display = 'block';
                    trackingResults.classList.add('fade-in');
                    
                    showAdminMessage(`New tracking ID <strong>${data.trackingId}</strong> generated successfully!`, "success");
                } catch (error) {
                    console.error('Error:', error);
                    alert("Failed to generate tracking ID. Check console for details.");
                }
            });
        });

        updateStatusBtn.addEventListener('click', async function() {
            try {
                const response = await fetch(`${API_BASE_URL}/shipments`);
                const shipments = await response.json();
                
                modalTitle.textContent = "Update Shipment Status";
                modalContent.innerHTML = `
                    <div class="form-group">
                        <label for="selectTrackingId">Tracking ID</label>
                        <select id="selectTrackingId" class="tracking-input" style="width: 100%; padding: 12px;">
                            ${shipments.map(shipment => 
                                `<option value="${shipment.tracking_id}">${shipment.tracking_id} - ${shipment.status}</option>`
                            ).join('')}
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="selectStatus">New Status</label>
                        <select id="selectStatus" class="tracking-input" style="width: 100%; padding: 12px;">
                            <option value="pending">Pending</option>
                            <option value="in-transit" selected>In Transit</option>
                            <option value="on-hold">On Hold</option>
                            <option value="delivered">Delivered</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="statusLocation">Location</label>
                        <input type="text" id="statusLocation" class="tracking-input" style="width: 100%;" placeholder="e.g. New York, USA">
                    </div>
                    <div class="form-group">
                        <label for="statusNote">Status Note (Optional)</label>
                        <textarea id="statusNote" class="tracking-input" style="width: 100%; padding: 12px; height: 100px;" placeholder="Add details about the status update..."></textarea>
                    </div>
                    <button id="confirmUpdate" class="track-btn" style="width: 100%; margin-top: 1rem;">
                        <i class="fas fa-save"></i> Update Status
                    </button>
                `;
                
                adminModal.style.display = 'flex';
                
                document.getElementById('confirmUpdate').addEventListener('click', async function() {
                    const trackingId = document.getElementById('selectTrackingId').value;
                    const newStatus = document.getElementById('selectStatus').value;
                    const location = document.getElementById('statusLocation').value.trim();
                    const description = document.getElementById('statusNote').value.trim();
                    
                    if (!location) {
                        alert("Please enter a location");
                        return;
                    }
                    
                    try {
                        const response = await fetch(`${API_BASE_URL}/shipments/${trackingId}/status`, {
                            method: 'PUT',
                            headers: {
                                'Content-Type': 'application/json',
                            },
                            body: JSON.stringify({
                                status: newStatus,
                                location: location,
                                description: description || `Status updated to ${newStatus}`
                            })
                        });
                        
                        if (!response.ok) {
                            throw new Error('Failed to update status');
                        }
                        
                        adminModal.style.display = 'none';
                        
                        if (trackingId === trackingIdInput.value.trim().toUpperCase()) {
                            const shipmentResponse = await fetch(`${API_BASE_URL}/shipments/${trackingId}`);
                            const shipment = await shipmentResponse.json();
                            displayTrackingData(shipment);
                        }
                        
                        showAdminMessage(`Status for <strong>${trackingId}</strong> updated to <strong>${newStatus}</strong>`, "success");
                    } catch (error) {
                        console.error('Error:', error);
                        alert("Failed to update status. Check console for details.");
                    }
                });
            } catch (error) {
                console.error('Error:', error);
                alert("Failed to load shipments. Check console for details.");
            }
        });

        resetDemoBtn.addEventListener('click', function() {
            if (confirm("This will reset the demo data. Are you sure?")) {
                fetch(`${API_BASE_URL}/seed`)
                    .then(response => response.json())
                    .then(data => {
                        showAdminMessage(data.message, "success");
                        if (trackingIdInput.value.trim().toUpperCase() === 'ST-789456123') {
                            trackBtn.click();
                        }
                    })
                    .catch(error => {
                        console.error('Error:', error);
                        showAdminMessage("Failed to reset demo data", "error");
                    });
            }
        });

        closeModal.addEventListener('click', function() {
            adminModal.style.display = 'none';
        });

        window.addEventListener('click', function(event) {
            if (event.target === adminModal) {
                adminModal.style.display = 'none';
            }
        });

        function showAdminMessage(message, type) {
            adminMessage.innerHTML = message;
            adminMessage.style.display = 'block';
            
            if (type === "success") {
                adminMessage.style.backgroundColor = "#f1f8e9";
                adminMessage.style.color = "#2e7d32";
            } else if (type === "error") {
                adminMessage.style.backgroundColor = "#ffebee";
                adminMessage.style.color = "#c62828";
            } else {
                adminMessage.style.backgroundColor = "#e3f2fd";
                adminMessage.style.color = "#1565c0";
            }
            
            adminSection.scrollIntoView({ behavior: 'smooth' });
            
            setTimeout(() => {
                adminMessage.style.display = 'none';
            }, 5000);
        }

        // ===== HELPER FUNCTIONS =====
        function formatDate(dateString, dateOnly = false) {
            if (!dateString) return "N/A";
            
            const date = new Date(dateString);
            
            if (dateOnly) {
                return date.toLocaleDateString('en-US', { 
                    year: 'numeric', 
                    month: 'short', 
                    day: 'numeric' 
                });
            }
            
            return date.toLocaleString('en-US', {
                month: 'short',
                day: 'numeric',
                year: 'numeric',
                hour: '2-digit',
                minute: '2-digit'
            });
        }

        function getStepsForStatus(status, estimatedDelivery) {
            const now = new Date();
            const estDate = new Date(estimatedDelivery);
            
            const dates = {
                orderReceived: new Date(now.getTime() - 5 * 24 * 60 * 60 * 1000),
                processing: new Date(now.getTime() - 3 * 24 * 60 * 60 * 1000),
                inTransit: now,
                customs: new Date(now.getTime() + 2 * 24 * 60 * 60 * 1000),
                outForDelivery: new Date(estDate.getTime() - 1 * 24 * 60 * 60 * 1000),
                delivered: estDate
            };
            
            const steps = [
                { id: 1, title: "Order Received", date: formatDate(dates.orderReceived, true), icon: "clipboard-check", completed: true, active: false },
                { id: 2, title: "Processing", date: formatDate(dates.processing, true), icon: "cog", completed: status !== "pending", active: false },
                { id: 3, title: "In Transit", date: formatDate(dates.inTransit, true), icon: "plane", completed: status === "in-transit" || status === "delivered", active: status === "in-transit" },
                { id: 4, title: "Customs", date: formatDate(dates.customs, true), icon: "passport", completed: status === "delivered", active: false },
                { id: 5, title: "Out for Delivery", date: formatDate(dates.outForDelivery, true), icon: "truck", completed: status === "delivered", active: false },
                { id: 6, title: "Delivered", date: formatDate(dates.delivered, true), icon: "home", completed: status === "delivered", active: false }
            ];
            
            return steps;
        }

        // ===== INITIALIZATION =====
        window.addEventListener('DOMContentLoaded', function() {
            checkLoginStatus();
            
            // Auto-load first shipment if available
            fetch(`${API_BASE_URL}/shipments`)
                .then(response => response.json())
                .then(shipments => {
                    if (shipments.length > 0) {
                        const firstShipment = shipments[0];
                        trackingIdInput.value = firstShipment.tracking_id;
                        trackBtn.click();
                    }
                })
                .catch(error => {
                    console.log('No shipments in database yet');
                });
        });

        // Add logout button to admin controls
        const logoutBtn = document.createElement('button');
        logoutBtn.className = 'admin-btn';
        logoutBtn.id = 'logoutBtn';
        logoutBtn.innerHTML = '<i class="fas fa-sign-out-alt"></i> Logout';
        logoutBtn.style.marginLeft = 'auto';
        
        logoutBtn.addEventListener('click', function() {
            localStorage.removeItem('adminLoggedIn');
            checkLoginStatus();
            showAdminMessage('You have been logged out', "info");
        });
        
        document.querySelector('.admin-controls').appendChild(logoutBtn);
    </script>
</body>
</html>
