Here is the complete source code for **TrustPoint Tours**. This solution includes a single HTML file containing the structure, CSS for styling, and JavaScript for interactivity.

You can save this code as `index.html` and open it in any web browser.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TrustPoint Tours | Safe & Secure Travel</title>
    
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    
    <!-- Font Awesome for Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <style>
        /* --- CSS VARIABLES & RESET --- */
        :root {
            --primary-color: #0056b3; /* Trust Blue */
            --secondary-color: #004494;
            --accent-color: #ffc107; /* Gold/Yellow */
            --text-dark: #333333;
            --text-light: #666666;
            --white: #ffffff;
            --light-bg: #f8f9fa;
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Poppins', sans-serif;
            line-height: 1.6;
            color: var(--text-dark);
            overflow-x: hidden;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        ul {
            list-style: none;
        }

        img {
            max-width: 100%;
            height: auto;
        }

        /* --- UTILITIES --- */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .section-padding {
            padding: 80px 0;
        }

        .section-title {
            text-align: center;
            margin-bottom: 50px;
        }

        .section-title h2 {
            font-size: 2.5rem;
            color: var(--primary-color);
            margin-bottom: 10px;
        }

        .section-title p {
            color: var(--text-light);
            max-width: 600px;
            margin: 0 auto;
        }

        .btn {
            display: inline-block;
            padding: 12px 30px;
            border-radius: 5px;
            font-weight: 600;
            transition: var(--transition);
            cursor: pointer;
            border: none;
        }

        .btn-primary {
            background-color: var(--primary-color);
            color: var(--white);
        }

        .btn-primary:hover {
            background-color: var(--secondary-color);
            transform: translateY(-2px);
        }

        .btn-outline {
            border: 2px solid var(--white);
            color: var(--white);
            background: transparent;
        }

        .btn-outline:hover {
            background: var(--white);
            color: var(--primary-color);
        }

        /* --- NAVIGATION --- */
        .navbar {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background: var(--white);
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            z-index: 1000;
            padding: 15px 0;
            transition: var(--transition);
        }

        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary-color);
        }

        .logo span {
            color: var(--text-dark);
        }

        .nav-links {
            display: flex;
            gap: 25px;
        }

        .nav-links a {
            font-weight: 500;
            color: var(--text-dark);
            transition: var(--transition);
        }

        .nav-links a:hover {
            color: var(--primary-color);
        }

        .hamburger {
            display: none;
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* --- HERO SECTION --- */
        .hero {
            height: 100vh;
            background: linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)), url('https://images.unsplash.com/photo-1469854523086-cc02fe5d8800?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80');
            background-size: cover;
            background-position: center;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: var(--white);
            padding-top: 80px;
        }

        .hero-content h1 {
            font-size: 3.5rem;
            margin-bottom: 10px;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .hero-content .tagline {
            font-size: 1.2rem;
            font-weight: 300;
            margin-bottom: 20px;
            color: var(--accent-color);
        }

        .hero-content p {
            font-size: 1.1rem;
            margin-bottom: 30px;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
        }

        .hero-buttons {
            display: flex;
            gap: 15px;
            justify-content: center;
        }

        /* --- ABOUT & WHY CHOOSE US --- */
        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            align-items: center;
        }

        .about-text h3 {
            font-size: 1.8rem;
            margin-bottom: 20px;
            color: var(--primary-color);
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-top: 50px;
        }

        .feature-card {
            background: var(--white);
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            text-align: center;
            transition: var(--transition);
        }

        .feature-card:hover {
            transform: translateY(-10px);
        }

        .feature-card i {
            font-size: 2.5rem;
            color: var(--primary-color);
            margin-bottom: 15px;
        }

        /* --- SERVICES --- */
        .services {
            background-color: var(--light-bg);
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .service-card {
            background: var(--white);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            transition: var(--transition);
        }

        .service-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
        }

        .service-img {
            height: 200px;
            background-color: #ddd;
            background-size: cover;
            background-position: center;
        }

        .service-content {
            padding: 20px;
        }

        .service-content h3 {
            margin-bottom: 10px;
            color: var(--primary-color);
        }

        /* --- CARS --- */
        .cars-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .car-card {
            background: var(--white);
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            overflow: hidden;
            text-align: center;
        }

        .car-img {
            height: 220px;
            width: 100%;
            object-fit: cover;
        }

        .car-info {
            padding: 20px;
        }

        .car-info h3 {
            color: var(--primary-color);
            margin-bottom: 10px;
        }

        .car-features {
            margin: 15px 0;
            color: var(--text-light);
            font-size: 0.9rem;
        }

        /* --- PRICING --- */
        .pricing {
            background-color: var(--light-bg);
        }

        .pricing-table {
            width: 100%;
            border-collapse: collapse;
            background: var(--white);
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            border-radius: 10px;
            overflow: hidden;
        }

        .pricing-table th, .pricing-table td {
            padding: 15px 20px;
            text-align: left;
            border-bottom: 1px solid #eee;
        }

        .pricing-table th {
            background-color: var(--primary-color);
            color: var(--white);
        }

        .pricing-table tr:hover {
            background-color: #f1f1f1;
        }

        /* --- BOOKING FORM --- */
        .booking-container {
            max-width: 800px;
            margin: 0 auto;
            background: var(--white);
            padding: 40px;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
        }

        .form-control {
            width: 100%;
            padding: 12px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-family: inherit;
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
        }

        /* --- TESTIMONIALS --- */
        .testimonials {
            background: var(--primary-color);
            color: var(--white);
            text-align: center;
        }

        .testimonial-card {
            background: rgba(255,255,255,0.1);
            padding: 30px;
            border-radius: 10px;
            margin: 20px auto;
            max-width: 700px;
        }

        .testimonial-text {
            font-style: italic;
            font-size: 1.1rem;
            margin-bottom: 15px;
        }

        .testimonial-author {
            font-weight: 700;
        }

        /* --- CONTACT --- */
        .contact-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
        }

        .contact-info-item {
            display: flex;
            align-items: center;
            margin-bottom: 25px;
        }

        .contact-icon {
            width: 50px;
            height: 50px;
            background: var(--light-bg);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--primary-color);
            font-size: 1.2rem;
            margin-right: 15px;
        }

        .map-container {
            width: 100%;
            height: 300px;
            background: #eee;
            border-radius: 10px;
            overflow: hidden;
        }

        /* --- FOOTER --- */
        footer {
            background: #1a1a1a;
            color: #ccc;
            padding: 60px 0 20px;
        }

        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-col h4 {
            color: var(--white);
            margin-bottom: 20px;
            font-size: 1.2rem;
        }

        .footer-links li {
            margin-bottom: 10px;
        }

        .footer-links a:hover {
            color: var(--primary-color);
        }

        .social-icons a {
            display: inline-block;
            width: 35px;
            height: 35px;
            background: #333;
            color: var(--white);
            text-align: center;
            line-height: 35px;
            border-radius: 50%;
            margin-right: 10px;
            transition: var(--transition);
        }

        .social-icons a:hover {
            background: var(--primary-color);
        }

        .copyright {
            text-align: center;
            border-top: 1px solid #333;
            padding-top: 20px;
            font-size: 0.9rem;
        }

        /* --- FLOATING WHATSAPP --- */
        .float-wa {
            position: fixed;
            width: 60px;
            height: 60px;
            bottom: 30px;
            right: 30px;
            background-color: #25d366;
            color: #FFF;
            border-radius: 50px;
            text-align: center;
            font-size: 30px;
            box-shadow: 2px 2px 3px #999;
            z-index: 100;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: var(--transition);
        }

        .float-wa:hover {
            transform: scale(1.1);
            background-color: #20b857;
        }

        /* --- RESPONSIVE MEDIA QUERIES --- */
        @media (max-width: 768px) {
            .nav-links {
                position: absolute;
                top: 70px;
                right: 0;
                width: 100%;
                background: var(--white);
                flex-direction: column;
                align-items: center;
                padding: 20px 0;
                transform: translateY(-150%);
                transition: var(--transition);
                box-shadow: 0 5px 10px rgba(0,0,0,0.1);
            }

            .nav-links.active {
                transform: translateY(0);
            }

            .hamburger {
                display: block;
            }

            .hero-content h1 {
                font-size: 2.2rem;
            }

            .about-grid, .contact-grid, .form-row {
                grid-template-columns: 1fr;
            }

            .form-row {
                gap: 0;
            }
        }
    </style>
</head>
<body>

    <!-- Navigation -->
    <nav class="navbar">
        <div class="container nav-container">
            <a href="#" class="logo">TrustPoint <span>Tours</span></a>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#services">Services</a></li>
                <li><a href="#cars">Cars</a></li>
                <li>
