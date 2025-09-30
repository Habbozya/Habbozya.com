<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Business</title>
    <style>
        * {margin:0;padding:0;box-sizing:border-box;font-family:'Arial',sans-serif;}
        body {background:#f9f9f9;color:#333;scroll-behavior:smooth;}
        header {background:#007BFF;color:white;padding:20px 0;text-align:center;position:sticky;top:0;z-index:1000;}
        header h1{font-size:2.5rem;}
        nav {margin-top:10px;}
        nav a{color:white;text-decoration:none;margin:0 15px;font-weight:bold;transition:color 0.3s;}
        nav a:hover{color:#FFD700;}
        section{opacity:0;transform:translateY(50px);transition:opacity 0.8s ease, transform 0.8s ease;}
        section.visible{opacity:1;transform:translateY(0);}
        .hero{display:flex;flex-direction:column;justify-content:center;align-items:center;height:80vh;background:linear-gradient(rgba(0,123,255,0.7), rgba(0,123,255,0.7)), url('https://source.unsplash.com/1600x900/?office,business') center/cover no-repeat;color:white;text-align:center;}
        .hero h2{font-size:2rem;margin-bottom:20px;}
        .hero p{font-size:1.2rem;max-width:600px;}
        .hero button{margin-top:20px;padding:10px 25px;font-size:1rem;border:none;background:#FFD700;color:#333;cursor:pointer;border-radius:5px;transition:background 0.3s;}
        .hero button:hover{background:#FFC107;}
        .services{padding:60px 20px;text-align:center;background:#fff;}
        .services h2{font-size:2rem;margin-bottom:40px;color:#007BFF;}
        .service-cards{display:flex;flex-wrap:wrap;justify-content:center;gap:20px;}
        .card{background:#f1f1f1;padding:20px;border-radius:10px;width:250px;box-shadow:0 5px 15px rgba(0,0,0,0.1);transition:transform 0.3s,box-shadow 0.3s;}
        .card:hover{transform:translateY(-10px);box-shadow:0 10px 20px rgba(0,0,0,0.2);}
        .card h3{margin-bottom:15px;color:#007BFF;}
        .card img{width:100%;border-radius:8px;margin-bottom:10px;}
        .card p{font-size:0.95rem;line-height:1.4;}
        .contact{padding:60px 20px;background:#f1f1f1;text-align:center;}
        .contact h2{font-size:2rem;margin-bottom:40px;color:#007BFF;}
        .contact form{max-width:500px;margin:0 auto;display:flex;flex-direction:column;gap:15px;}
        .contact input,.contact textarea{padding:10px;border-radius:5px;border:1px solid #ccc;font-size:1rem;width:100%;}
        .contact button{padding:10px 25px;border:none;background:#007BFF;color:white;cursor:pointer;border-radius:5px;font-size:1rem;transition:background 0.3s;}
        .contact button:hover{background:#0056b3;}
        footer{background:#333;color:white;text-align:center;padding:15px 0;margin-top:40px;}
        #backToTop{position:fixed;bottom:30px;right:30px;display:none;padding:10px 15px;background:#007BFF;color:white;border:none;border-radius:50px;cursor:pointer;font-size:1rem;z-index:1000;transition:background 0.3s,transform 0.3s;}
        #backToTop:hover{background:#0056b3;transform:scale(1.1);}
        @media(max-width:768px){.service-cards{flex-direction:column;align-items:center;}}
    </style>
</head>
<body>

<header>
    <h1>My Business</h1>
    <nav>
        <a href="#hero">Home</a>
        <a href="#services">Services</a>
        <a href="#contact">Contact</a>
    </nav>
</header>

<section class="hero" id="hero">
    <h2>Welcome to My Business</h2>
    <p>We provide top-notch solutions to help your business grow. Our services are tailored to meet your unique needs.</p>
    <button>Get Started</button>
</section>

<section class="services" id="services">
    <h2>Our Services</h2>
    <div class="service-cards">
        <div class="card">
            <img src="https://source.unsplash.com/400x300/?consulting,business" alt="Consulting">
            <h3>Consulting</h3>
            <p>Professional business consulting to improve efficiency and drive growth.</p>
        </div>
        <div class="card">
            <img src="https://source.unsplash.com/400x300/?marketing,business" alt="Marketing">
            <h3>Marketing</h3>
            <p>Creative marketing strategies to enhance your brand and reach new customers.</p>
        </div>
        <div class="card">
            <img src="https://source.unsplash.com/400x300/?technology,IT" alt="IT Solutions">
            <h3>IT Solutions</h3>
            <p>Reliable IT solutions and support to streamline your operations.</p>
        </div>
    </div>
</section>

<section class="contact" id="contact">
    <h2>Contact Us</h2>
    <form action="#" method="POST">
        <input type="text" name="name" placeholder="Your Name" required>
        <input type="email" name="email" placeholder="Your Email" required>
        <textarea name="message" rows="5" placeholder="Your Message" required></textarea>
        <button type="submit">Send Message</button>
    </form>
</section>

<footer>
    &copy; 2025 My Business. All Rights Reserved.
</footer>

<button id="backToTop">↑ Top</button>

<script>
    const sections = document.querySelectorAll('section');
    const observer = new IntersectionObserver(entries => {
        entries.forEach(entry => {
            if(entry.isIntersecting) entry.target.classList.add('visible');
        });
    }, { threshold: 0.1 });
    sections.forEach(section => observer.observe(section));

    document.querySelectorAll('nav a').forEach(link => {
        link.addEventListener('click', function(e){
            e.preventDefault();
            document.querySelector(this.getAttribute('href')).scrollIntoView({ behavior: 'smooth' });
        });
    });

    const backToTop = document.getElementById('backToTop');
    window.addEventListener('scroll', () => {
        backToTop.style.display = (window.scrollY > 300) ? 'block' : 'none';
    });
    backToTop.addEventListener('click', () => {
        window.scrollTo({ top: 0, behavior: 'smooth' });
    });
</script>

</body>
</html>
