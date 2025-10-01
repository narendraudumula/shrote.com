<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Shrote | Digital Agency</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
  <style>
    /* Reset */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    /* Body */
    body {
      font-family: Arial, sans-serif;
      line-height: 1.6;
      color: #333;
      overflow-x: hidden;
    }

    /* Navbar */
    .navbar {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 20px;
      background: transparent;
      position: fixed;
      width: 100%;
      top: 0;
      z-index: 10;
      transition: background-color 0.3s, color 0.3s;
    }

    .navbar.scrolled {
      background: #fff;
      box-shadow: 0 2px 8px rgba(0,0,0,0.15);
    }

    .nav-right {
      display: flex;
      align-items: center;
      gap: 20px;
    }

    /* Logo styling */
    .logo {
      font-size: 1.5rem;
      font-weight: bold;
    }

    .logo span {
      color: #1e90ff; /* Blue for "S" */
    }

    .navbar .logo {
      color: #000; /* Black for "hrote" */
    }

    .nav-links {
      list-style: none;
      display: flex;
      gap: 20px;
    }

    .nav-links a {
      text-decoration: none;
      color: #fff;
      transition: color 0.3s;
    }

    .navbar.scrolled .nav-links a {
      color: #333;
    }

    .nav-links a:hover,
    .nav-links a.active {
      color: #1e90ff;
    }

    .btn {
      padding: 10px 20px;
      border-radius: 20px;
      background: linear-gradient(45deg, #6a5af9, #1e90ff);
      color: #fff;
      text-decoration: none;
      transition: opacity 0.3s, background 0.3s;
    }

    .navbar.scrolled .btn {
      background: linear-gradient(45deg, #1e90ff, #6a5af9);
    }

    .btn:hover {
      opacity: 0.9;
    }

    /* Hamburger Menu */
    .hamburger {
      display: none;
      cursor: pointer;
      z-index: 12;
      background: transparent;
      border: none;
    }

    .hamburger i {
      font-size: 1.5rem;
      color: #fff;
      transition: color 0.3s;
    }

    .navbar.scrolled .hamburger i {
      color: #333;
    }

    /* Mobile Styles */
    @media (max-width: 768px) {
      .hamburger {
        display: block;
      }
      
      .nav-right {
        position: fixed;
        top: 0;
        right: -100%;
        height: 100vh;
        width: 70%;
        max-width: 300px;
        background: #fff;
        flex-direction: column;
        justify-content: flex-start;
        align-items: flex-start;
        padding: 80px 30px 30px;
        transition: right 0.3s ease;
        box-shadow: -5px 0 15px rgba(0,0,0,0.1);
      }
      
      .nav-right.active {
        right: 0;
      }
      
      .nav-links {
        flex-direction: column;
        width: 100%;
        gap: 0;
      }
      
      .nav-links li {
        width: 100%;
        border-bottom: 1px solid #f0f0f0;
      }
      
      .nav-links a {
        display: block;
        padding: 15px 0;
        color: #333;
        width: 100%;
      }
      
      .nav-right .btn {
        margin-top: 20px;
        width: 100%;
        text-align: center;
      }
      
      .navbar.scrolled .nav-links a {
        color: #333;
      }
    }

    /* Hero */
    .hero {
      height: 100vh;
      position: relative;
      background: 
        linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)),
        url('https://images.unsplash.com/photo-1550745165-9bc0b252726f?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80') no-repeat center center/cover;
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      color: white;
      padding: 0 20px;
      z-index: 1;
    }

    .hero-content {
      position: relative;
      z-index: 2;
    }
    .typing span{font-size: 20px; border-right: 3px solid #f4b400; display: inline-block; animation: blink 0.7s step-end infinite; }
    @keyframes blink { 50% { border-color: transparent; } }


    .hero h1 {
      font-size: 2.5rem;
      margin-bottom: 20px;
    }

    .highlight {
      color: #1e90ff;
    }

    .hero p {
      font-size: 1.1rem;
      margin-bottom: 20px;
    }

    .hero-buttons {
      display: flex;
      gap: 15px;
      justify-content: center;
      flex-wrap: wrap;
    }

    .btn.primary {
      background: #007bff;
    }

    .btn.secondary {
      background: #fff;
      color: #333;
    }

    /* Services */
    .services {
      padding: 80px 20px;
      text-align: center;
      background: #fff;
    }

    .services h2 {
      font-size: 2rem;
      margin-bottom: 15px;
      color: #333;
    }

    .services p {
      max-width: 700px;
      margin: 0 auto 50px;
      font-size: 1rem;
      color: #555;
    }

    .service-cards {
      display: flex;
      justify-content: center;
      gap: 20px;
      flex-wrap: wrap;
    }

    .card {
      position: relative;
      border-radius: 10px;
      overflow: hidden;
      width: 100%;
      max-width: 300px;
      height: 200px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    }

    .card img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      display: block;
    }

    /* Overlay text */
    .card-text {
      position: absolute;
      bottom: 0;
      left: 0;
      width: 100%;
      padding: 15px;
      background: none;
      color: #fff;
      font-size: 1.1rem;
      font-weight: bold;
      text-align: left;
      transition: background 0.3s;
    }

    /* Why Choose Section */
    .why-choose {
      background: #fff;
      padding: 80px 20px;
    }

    .why-container {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      flex-wrap: wrap;
      gap: 50px;
      max-width: 1200px;
      margin: 0 auto;
    }

    .why-left {
      flex: 1;
      min-width: 300px;
    }

    .why-left h2 {
      font-size: 1.8rem;
      margin-bottom: 20px;
      color: #222;
    }

    .why-left p {
      font-size: 1rem;
      color: #555;
      margin-bottom: 30px;
      max-width: 600px;
    }

    .why-features {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 15px 40px;
      margin-bottom: 30px;
    }

    .feature {
      font-size: 0.9rem;
      color: #333;
      position: relative;
      padding-left: 25px;
    }

    .feature::before {
      content: "✔️";
      position: absolute;
      left: 0;
      color: #1e90ff;
      font-weight: bold;
    }

    .cta-btn {
      background: linear-gradient(45deg, #1e90ff, #6a5af9);
      color: #fff;
      padding: 12px 25px;
      font-size: 1rem;
      font-weight: bold;
      border-radius: 8px;
      text-decoration: none;
      transition: background 0.3s ease;
    }

    .cta-btn:hover {
      background: linear-gradient(45deg, #6a5af9, #1e90ff);
    }

    /* Right Card */
    .why-right {
      flex: 1;
      min-width: 300px;
      display: flex;
      justify-content: center;
    }

    .expertise-card {
      background: #f9f9f9;
      padding: 30px;
      border-radius: 12px;
      box-shadow: 0 4px 15px rgba(0,0,0,0.08);
      width: 100%;
      max-width: 350px;
    }

    .expertise-card h3 {
      margin-bottom: 20px;
      color: #222;
    }

    .expertise-card ul {
      list-style: none;
      padding: 0;
      margin: 0;
    }

    .expertise-card li {
      font-size: 0.9rem;
      margin-bottom: 12px;
      color: #555;
      position: relative;
      padding-left: 20px;
    }

    .expertise-card li::before {
      content: "•";
      position: absolute;
      left: 0;
      color: #1e90ff;
      font-size: 1.2rem;
    }

    /* Our Services Section */
    #services {
      padding: 80px 20px;
      background: white;
      text-align: center;
    }

    .section-title {
      font-size: 2rem;
      font-weight: bold;
      margin-bottom: 50px;
      color: black;
    }

    .services-container {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 30px;
      max-width: 1200px;
      margin: 0 auto;
    }

    .service-card {
      position: relative;
      height: 250px;
      border-radius: 12px;
      overflow: hidden;
      background: var(--bg-image) center/cover no-repeat;
      cursor: pointer;
      box-shadow: 0 6px 20px rgba(0,0,0,0.15);
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }

    .service-card::before {
      content: "";
      position: absolute;
      inset: 0;
      background: rgba(0, 0, 0, 0.7);
      transition: opacity 0.5s ease;
      z-index: 1;
    }

    .service-card:hover::before {
      opacity: 0.5;
    }

    .service-card .overlay {
      position: absolute;
      inset: 0;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      color: #fff;
      padding: 20px;
      z-index: 2;
    }

    .service-card h3 {
      margin-bottom: 10px;
      font-size: 1.4rem;
      font-weight: bold;
    }

    .service-card p {
      font-size: 0.9rem;
      line-height: 1.5;
    }

    /* Hover lift effect */
    .service-card:hover {
      transform: translateY(-5px);
      box-shadow: 0 12px 30px rgba(0,0,0,0.25);
    }

    /* Portfolio Section */
    #portfolio {
      padding: 80px 20px;
      background: #fff;
      text-align: center;
    }

    .portfolio-container {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 30px;
      max-width: 1100px;
      margin: 0 auto;
    }

    .portfolio-card {
      position: relative;
      border-radius: 12px;
      overflow: hidden;
      height: 250px;
      box-shadow: 0 6px 20px rgba(0,0,0,0.15);
      cursor: pointer;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }

    .portfolio-card:hover {
      transform: translateY(-5px);
      box-shadow: 0 12px 30px rgba(0,0,0,0.25);
    }

    .portfolio-card img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      display: block;
    }

    /* Text overlay at bottom */
    .portfolio-text {
      position: absolute;
      bottom: 0;
      left: 0;
      width: 100%;
      padding: 12px;
      background: none;
      color: white;
      font-size: 0.9rem;
      font-weight: bold;
      text-align: left;
    }

    /* Testimonials Section */
    #testimonials {
      background: rgba(0,0,0,0.8);
      padding: 80px 20px;
      text-align: center;
    }

    .testimonial-wrapper {
      position: relative;
      max-width: 800px;
      margin: 0 auto;
    }

    .testimonial-container {
      position: relative;
      overflow: hidden;
    }

    /* Testimonial box */
    .testimonial {
      display: none;
      background: #fff;
      color: #333;
      padding: 30px;
      border-radius: 12px;
      box-shadow: 0 6px 20px rgba(0,0,0,0.15);
      min-height: 180px;
    }

    .testimonial.active {
      display: block;
    }

    /* Arrows */
    .arrow {
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      background: #fff;
      border: none;
      color: #1e90ff;
      font-size: 1.5rem;
      padding: 10px 15px;
      cursor: pointer;
      border-radius: 50%;
      font-weight: bold;
      transition: 0.3s;
    }

    .arrow:hover {
      background: #1e90ff;
      color: #fff;
    }

    .arrow.left { left: -50px; }
    .arrow.right { right: -50px; }

    /* Footer Styles */
    /* Bubble Footer */
    .footer {
      position: relative;
      background: #1d40cc;
      color: #fff;
      padding: 60px 20px 20px;
      overflow: hidden;
      text-align: center;
    }

    .footer .footer-content {
      position: relative;
      z-index: 2;
      display: flex;
      justify-content: space-around;
      flex-wrap: wrap;
      gap: 30px;
    }

    .footer-left, .footer-center, .footer-right {
      min-width: 250px;
    }

    .footer h3 span {
      color: #1e90ff; /* Blue S */
    }

    .social-icons a {
      color: #fff;
      font-size: 1.4rem;
      margin: 0 10px;
      transition: 0.3s;
    }

    .social-icons a:hover {
      color: #6ab6ff;
    }

    /* Bubble animation */
    .bubbles {
      position: absolute;
      bottom: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      overflow: hidden;
    }

    .bubble {
      position: absolute;
      bottom: -150px;
      width: 40px;
      height: 40px;
      background: rgba(255,255,255,0.2);
      border-radius: 50%;
      animation: rise 15s infinite ease-in;
    }

    .bubble:nth-child(1) { left: 10%; animation-duration: 12s; width: 25px; height: 25px; }
    .bubble:nth-child(2) { left: 20%; animation-duration: 18s; width: 35px; height: 35px; }
    .bubble:nth-child(3) { left: 30%; animation-duration: 10s; }
    .bubble:nth-child(4) { left: 40%; animation-duration: 22s; width: 20px; height: 20px; }
    .bubble:nth-child(5) { left: 50%; animation-duration: 16s; }
    .bubble:nth-child(6) { left: 60%; animation-duration: 25s; width: 30px; height: 30px; }
    .bubble:nth-child(7) { left: 70%; animation-duration: 14s; }
    .bubble:nth-child(8) { left: 80%; animation-duration: 20s; width: 25px; height: 25px; }
    .bubble:nth-child(9) { left: 90%; animation-duration: 17s; }
    .bubble:nth-child(10){ left: 95%; animation-duration: 19s; width: 20px; height: 20px; }

    @keyframes rise {
      0% { transform: translateY(0) scale(1); opacity: 0.8; }
      50% { opacity: 0.5; }
      100% { transform: translateY(-800px) scale(0.5); opacity: 0; }
    }

    /* Mobile responsive adjustments */
    @media (max-width: 768px) {
      .hero h1 {
        font-size: 2rem;
      }
      
      .hero p {
        font-size: 1rem;
      }
      
      .why-features {
        grid-template-columns: 1fr;
      }
      
      .arrow.left {
        left: 10px;
      }
      
      .arrow.right {
        right: 10px;
      }
    }
  </style>
</head>
<body>

 <header>
    <nav class="navbar">
      <div class="logo"><span>S</span>hrote</div>

      <!-- Hamburger Menu -->
      <button class="hamburger" id="hamburger">
        <i class="fas fa-bars"></i>
      </button>

      <div class="nav-right" id="nav-menu">
        <ul class="nav-links">
          <li><a href="./index.html" class="active">Home</a></li>
          <li><a href="./about.html">About</a></li>
          <li><a href="./contact.html">Contact</a></li>
          <li><a href="./carrer.html">Career</a></li>
        </ul>
        <a href="#" class="btn">Schedule A Call</a>
      </div>
    </nav>
  </header>

  <!-- Hero Section -->
  <section class="hero">
    <div class="hero-content">
      <span id="typing" class="typing"></span>
      <!-- <h1><span class="highlight">Elevate</span> Your Digital Presence</h1> -->
      <p>We craft exceptional web experiences that drive growth and transform businesses in the digital age.</p>
      <div class="hero-buttons">
        <a href="#" class="btn primary">Get Started</a>
        <a href="#" class="btn secondary">View Our Work</a>
      </div>
    </div>
  </section>

  <!-- Services Section -->
  <section class="services">
    <h2>Transforming Ideas into Digital Reality</h2>
    <p>
      At Shrote, we're more than just a web design and development company — 
      we're your dedicated digital partners.
    </p>

    <div class="service-cards">
      <div class="card">
        <img src="../pictures/e-commeres.jpeg" alt="ERP Solutions" />
        <div class="card-text">ERP Solutions</div>
      </div>
      <div class="card">
        <img src="https://images.unsplash.com/photo-1607082350899-7e105aa886ae?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1172&q=80" alt="E-commerce Solutions" />
        <div class="card-text">E-commerce</div>
      </div>
      <div class="card">
        <img src="https://images.unsplash.com/photo-1552664730-d307ca884978?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80" alt="HRM Solutions" />
        <div class="card-text">HRM Solutions</div>
      </div>
    </div>
  </section>

  <!-- Why Choose Us Section -->
  <section class="why-choose">
    <div class="why-container">
      <!-- Left Side -->
      <div class="why-left">
        <h2>Why Choose Shrote?</h2>
        <p>
          What sets us apart is our commitment to innovation and excellence.
          We specialize in creating websites that are not only visually
          stunning but also highly functional and user-friendly.
        </p>

        <div class="why-features">
          <div class="feature">Custom Web Development</div>
          <div class="feature">SEO Optimization</div>
          <div class="feature">Performance Optimization</div>
          <div class="feature">Responsive Design</div>
          <div class="feature">24/7 Support</div>
          <div class="feature">Security Implementation</div>
        </div>

        <a href="#" class="btn cta-btn">Start Your Project</a>
      </div>

      <!-- Right Side -->
      <div class="why-right">
        <div class="expertise-card">
          <h3>Our Expertise</h3>
          <ul>
            <li>Passionate Team of Experts</li>
            <li>Tailored Solutions</li>
            <li>24/7 Customer Support</li>
            <li>98% Client Satisfaction Rate</li>
          </ul>
        </div>
      </div>
    </div>
  </section>

  <!-- Our Services Section -->
  <section id="services">
    <h2 class="section-title">Our Services</h2>
    <div class="services-container">
      <!-- Service Card 1 -->
      <div class="service-card" style="--bg-image: url('https://images.unsplash.com/photo-1507238691740-187a5b1d37b8?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=455&q=80')">
        <div class="overlay">
          <h3>Web Application</h3>
          <p>
            Experienced web application developer proficient in building
            dynamic, user-focused solutions using modern frameworks.
          </p>
        </div>
      </div>

      <!-- Service Card 2 -->
      <div class="service-card" style="--bg-image: url('https://images.unsplash.com/photo-1545235617-9465d2a55698?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=480&q=80')">
        <div class="overlay">
          <h3>UI/UX Designer</h3>
          <p>
            Creative designer producing visually captivating and impactful
            designs, translating client visions into graphics.
          </p>
        </div>
      </div>

      <!-- Service Card 3 -->
      <div class="service-card" style="--bg-image: url('https://images.unsplash.com/photo-1620641788421-7a1c342ea42e?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1074&q=80')">
        <div class="overlay">
          <h3>WordPress Development</h3>
          <p>
            Expert in crafting appealing, functional websites with
            customization and plugin integration.
          </p>
        </div>
      </div>

      <!-- Service Card 4 -->
      <div class="service-card" style="--bg-image: url('https://images.unsplash.com/photo-1607798748738-b15c40d33d57?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80')">
        <div class="overlay">
          <h3>SEO</h3>
          <p>
            Specialist in enhancing visibility and driving organic growth
            through keyword research & on-page optimization.
          </p>
        </div>
      </div>

      <!-- Service Card 5 -->
      <div class="service-card" style="--bg-image: url('https://images.unsplash.com/photo-1542744173-8e7e53415bb0?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80')">
        <div class="overlay">
          <h3>Consulting</h3>
          <p>
            Providing guidance on web development strategies, technologies,
            and best practices.
          </p>
        </div>
      </div>

      <!-- Service Card 6 -->
      <div class="service-card" style="--bg-image: url('https://images.unsplash.com/photo-1581291518633-83b4ebd1d83e?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80')">
        <div class="overlay">
          <h3>24/7 Support</h3>
          <p>
            Offering continuous support with timely solutions and customer
            satisfaction at the core.
          </p>
        </div>
      </div>
    </div>
  </section>

  <!-- Our Portfolio Section -->
  <section id="portfolio">
    <h2 class="section-title">Our Portfolio</h2>
    <div class="portfolio-container">
      <!-- Portfolio Card 1 -->
      <div class="portfolio-card">
        <img src="../pictures/ai.jpg" alt="Scroll Pedia">
        <div class="portfolio-text">
          <h3>Scroll Pedia</h3>
        </div>
      </div>

      <!-- Portfolio Card 2 -->
      <div class="portfolio-card">
        <img src="https://images.unsplash.com/photo-1511795409834-ef04bbd61622?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1169&q=80" alt="Party Time">
        <div class="portfolio-text">
          <h3>Party Time</h3>
        </div>
      </div>

      <!-- Portfolio Card 3 -->
      <div class="portfolio-card">
        <img src="https://images.unsplash.com/photo-1523961131990-5ea7c61b2107?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1074&q=80" alt="E-Space">
        <div class="portfolio-text">
          <h3>E-Space</h3>
        </div>
      </div>
    </div>
  </section>

  <!-- What Our Clients Say Section -->
  <section id="testimonials">
    <h2 class="section-title">What Our Clients Say</h2>
    <div class="testimonial-wrapper">
      <!-- Left Arrow -->
      <button class="arrow left" onclick="prevTestimonial()">&#10094;</button>
      
      <div class="testimonial-container">
        <div class="testimonial active">
          <p>"Shrote completely transformed our online presence. The team is fantastic!"</p>
          <h4>- Client A</h4>
        </div>
        <div class="testimonial">
          <p>"The ERP solution streamlined our operations. Highly recommended."</p>
          <h4>- Client B</h4>
        </div>
        <div class="testimonial">
          <p>"Our e-commerce sales doubled after Shrote redesigned our store."</p>
          <h4>- Client C</h4>
        </div>
      </div>
      
      <!-- Right Arrow -->
      <button class="arrow right" onclick="nextTestimonial()">&#10095;</button>
    </div>
  </section>

  <!-- Footer Section -->
  <footer class="footer">
  <div class="bubbles">
    <div class="bubble"></div><div class="bubble"></div><div class="bubble"></div>
    <div class="bubble"></div><div class="bubble"></div><div class="bubble"></div>
    <div class="bubble"></div><div class="bubble"></div><div class="bubble"></div>
    <div class="bubble"></div>
  </div>

  <div class="footer-content">
    <div class="footer-left">
      <h3><span>S</span>hrote</h3>
      <p>Elevate your online presence with our expert team's innovative designs and seamless functionality.</p>
    </div>

    <div class="footer-center">
      <h3>Contact Us</h3>
      <p><i class="fa-solid fa-phone"></i> +91 7667983607</p>
      <p><i class="fa-solid fa-envelope"></i> info@shrote.com</p>
    </div>

    <div class="footer-right">
      <h3>Follow Us</h3>
      <div class="social-icons">
        <a href="#"><i class="fab fa-instagram"></i></a>
        <a href="#"><i class="fab fa-x-twitter"></i></a>
        <a href="#"><i class="fab fa-linkedin"></i></a>
        <a href="#"><i class="fab fa-facebook"></i></a>
      </div>
    </div>
  </div>
</footer>


  <script>
    const typingElement = document.getElementById("typing");
    const text = "Elevate Your Digital Presence ";
    let index = 0;
    function typeEffect() {
      if(index < text.length) {
        typingElement.innerHTML += text.charAt(index);
        index++;
        setTimeout(typeEffect, 100);
      }
    }
    window.onload = typeEffect;

    function toggleMenu() {
      const navMenu = document.getElementById("navMenu");
      navMenu.classList.toggle("show");
    }
    // Mobile Menu Toggle
    const hamburger = document.getElementById('hamburger');
    const navMenu = document.getElementById('nav-menu');
    
    hamburger.addEventListener('click', () => {
      navMenu.classList.toggle('active');
      hamburger.querySelector('i').classList.toggle('fa-bars');
      hamburger.querySelector('i').classList.toggle('fa-times');
    });
    
    // Close mobile menu when clicking on a link
    document.querySelectorAll('.nav-links a').forEach(link => {
      link.addEventListener('click', () => {
        navMenu.classList.remove('active');
        hamburger.querySelector('i').classList.remove('fa-times');
        hamburger.querySelector('i').classList.add('fa-bars');
      });
    });
    
    // Navbar scroll effect
    window.addEventListener('scroll', () => {
      const navbar = document.querySelector('.navbar');
      if (window.scrollY > 50) {
        navbar.classList.add('scrolled');
      } else {
        navbar.classList.remove('scrolled');
      }
    });
    
    // Testimonial slider
    let currentTestimonial = 0;
    const testimonials = document.querySelectorAll('.testimonial');
    
    function showTestimonial(index) {
      testimonials.forEach(testimonial => testimonial.classList.remove('active'));
      testimonials[index].classList.add('active');
    }
    
    function nextTestimonial() {
      currentTestimonial = (currentTestimonial + 1) % testimonials.length;
      showTestimonial(currentTestimonial);
    }
    
    function prevTestimonial() {
      currentTestimonial = (currentTestimonial - 1 + testimonials.length) % testimonials.length;
      showTestimonial(currentTestimonial);
    }
    
    // Auto slide testimonials
    setInterval(nextTestimonial, 5000);
  </script>
</body>
</html>
