<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Focus Coffee</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f5f5f5;
            color: #333;
            line-height: 1.6;
        }

        header {
            background-color: #8B4513; /* Café oscuro */
            color: white;
            padding: 120px 20px;
            text-align: center;
            position: relative;
            overflow: hidden;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
        }

        header h1 {
            font-size: 4rem;
            margin: 0;
            font-weight: bold;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.7);
        }

        header p {
            font-size: 1.5rem;
            margin-top: 10px;
            font-style: italic;
            opacity: 0.9;
        }

        .coffee-icon {
            font-size: 4rem;
            margin-top: 20px;
            color: #FFC107; /* Color dorado */
        }

        nav {
            background-color: #A9A9A9; /* Gris */
            display: flex;
            justify-content: center;
            padding: 15px 0;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
        }

        nav a {
            color: white;
            margin: 0 20px;
            text-decoration: none;
            font-size: 1.2rem;
            transition: background-color 0.3s ease, color 0.3s ease;
            padding: 10px 15px;
            border-radius: 5px;
        }

        nav a:hover {
            background-color: #4E3B31; /* Café más oscuro */
            color: #FFC107; /* Cambia a dorado al pasar el mouse */
        }

        .main-content {
            padding: 40px 20px;
            max-width: 1200px;
            margin: auto;
        }

        h2 {
            font-size: 2.5rem;
            color: #8B4513; /* Café oscuro */
            margin-bottom: 20px;
            border-bottom: 2px solid #A9A9A9; /* Línea gris */
            display: inline-block;
            padding-bottom: 10px;
        }

        p {
            font-size: 1.1rem;
            margin-bottom: 20px;
        }

        .menu-section, .reservation-section, .hours-section, .contact-section, .map-section {
            background-color: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            margin-bottom: 40px;
        }

        .menu-section ul {
            list-style: none;
            padding: 0;
        }

        .menu-section li {
            background-color: #f9f9f9;
            border: 1px solid #A9A9A9;
            margin: 10px 0;
            padding: 15px;
            border-radius: 5px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .menu-section li:hover {
            transform: scale(1.02);
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
        }

        .menu-section li span {
            font-size: 1.2rem;
        }

        .menu-section li strong {
            font-size: 1.3rem;
            color: #8B4513; /* Café oscuro */
        }

        #reservation h2,
        #hours h2,
        #contact h2,
        #map h2 {
            margin-bottom: 20px;
            font-size: 2rem;
            color: #8B4513; /* Café oscuro */
        }

        #reservation form {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
            margin-top: 20px;
        }

        #reservation input, 
        #reservation select {
            padding: 10px;
            border: 1px solid #A9A9A9;
            border-radius: 5px;
            font-size: 1rem;
        }

        #reservation button {
            grid-column: span 2;
            background-color: #8B4513; /* Café oscuro */
            color: white;
            padding: 15px;
            border: none;
            border-radius: 5px;
            font-size: 1.2rem;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        #reservation button:hover {
            background-color: #4E3B31; /* Café más oscuro */
        }

        #hours {
            background-color: #f9f9f9;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            margin-top: 40px;
        }

        .hours-list {
            margin: 0;
            padding: 0;
            list-style: none;
        }

        .hours-list li {
            margin-bottom: 10px;
            font-size: 1.1rem;
        }

        footer {
            background-color: #A9A9A9; /* Gris */
            color: white;
            text-align: center;
            padding: 20px;
        }

        footer p {
            margin: 0;
            font-size: 0.9rem;
        }

        footer .social-icons {
            margin-top: 10px;
        }

        footer .social-icons a {
            color: white;
            margin: 0 10px;
            text-decoration: none;
            font-size: 1.5rem;
        }

        /* Galería */
        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 15px;
            margin-top: 40px;
        }

        .gallery img {
            width: 100%;
            border-radius: 8px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
            transition: transform 0.3s;
        }

        .gallery img:hover {
            transform: scale(1.05);
        }

        /* Responsividad */
        @media (max-width: 768px) {
            header h1 {
                font-size: 2.5rem;
            }

            nav {
                flex-direction: column;
            }

            nav a {
                margin: 10px 0;
            }

            .main-content {
                padding: 20px;
            }

            .gallery {
                grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
            }
        }

        /* Estilo para el mapa */
        .map {
            height: 400px;
            width: 100%;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
        }
    </style>
</head>
<body>

<header>
    <h1>Focus Coffee</h1>
    <p>El lugar perfecto para disfrutar de un buen café</p>
    <i class="fas fa-coffee coffee-icon"></i>
</header>

<nav>
    <a href="#menu">Menú</a>
    <a href="#testimonials">Testimonios</a>
    <a href="#gallery">Galería</a>
    <a href="#hours">Horarios</a>
    <a href="#reservation">Reservar Mesa</a>
    <a href="#map">Mapa</a>
    <a href="#contact">Contacto</a>
</nav>

<div class="main-content">

    <section id="menu" class="menu-section">
        <h2>Nuestro Menú</h2>
        <ul>
            <li>
                <span><strong>Café Americano</strong></span>
                <span>$30</span>
            </li>
            <li>
                <span><strong>Cappuccino</strong></span>
                <span>$35</span>
            </li>
            <li>
                <span><strong>Latte</strong></span>
                <span>$40</span>
            </li>
            <li>
                <span><strong>Mocha</strong></span>
                <span>$45</span>
            </li>
            <li>
                <span><strong>Frappé de Café</strong></span>
                <span>$50</span>
            </li>
            <li>
                <span><strong>Té</strong></span>
                <span>$25</span>
            </li>
            <li>
                <span><strong>Tiramisú</strong></span>
                <span>$50</span>
            </li>
            <li>
                <span><strong>Pastel de Chocolate</strong></span>
                <span>$55</span>
            </li>
            <li>
                <span><strong>Brownie</strong></span>
                <span>$40</span>
            </li>
            <li>
                <span><strong>Ensalada César</strong></span>
                <span>$70</span>
            </li>
            <li>
                <span><strong>Sándwich Caprese</strong></span>
                <span>$65</span>
            </li>
            <li>
                <span><strong>Galletas Variadas</strong></span>
                <span>$20</span>
            </li>
        </ul>
    </section>

    <section id="testimonials">
        <h2>Lo Que Dicen Nuestros Clientes</h2>
        <div class="testimonial">"El mejor café que he probado, y el ambiente es increíble!" - Ana M.</div>
        <div class="testimonial">"Perfecto para estudiar y disfrutar de una buena taza." - Luis R.</div>
        <div class="testimonial">"Un lugar acogedor con el mejor servicio." - Sofia G.</div>
    </section>

    <section id="gallery">
        <h2>Nuestra Galería</h2>
        <div class="gallery">
            <img src="https://upload.wikimedia.org/wikipedia/commons/d/d8/Caffe_Latte_at_Pulse_Cafe.jpg" alt="Café delicioso">
            <img src="https://www.krion.com/uploads/tmp/paredes_de_cafeteria_selva.jpg" alt="Ambiente acogedor">
            <img src="https://okdiario.com/img/2015/10/08/tiramisu-620x349.jpg" alt="Postres tentadores">
            <img src="https://st.depositphotos.com/66375226/56552/i/450/depositphotos_565529984-stock-photo-coffee-cup-glass-milk-table.jpg" alt="Café artesanal">
        </div>
    </section>

    <section id="hours" class="hours-section">
        <h2>Horarios</h2>
        <ul class="hours-list">
            <li>Lunes - Viernes: 8:00 AM - 8:00 PM</li>
            <li>Sábado: 9:00 AM - 10:00 PM</li>
            <li>Domingo: Cerrado</li>
        </ul>
    </section>

    <section id="reservation" class="reservation-section">
        <h2>Reservar Mesa</h2>
        <p>Complete el formulario para reservar su mesa en Focus Coffee.</p>
        <form>
            <input type="text" placeholder="Nombre completo" required>
            <input type="email" placeholder="Correo electrónico" required>
            <input type="tel" placeholder="Teléfono" required>
            <input type="date" required>
            <input type="time" required>
            <select required>
                <option value="" disabled selected>Número de personas</option>
                <option value="1">1</option>
                <option value="2">2</option>
                <option value="3">3</option>
                <option value="4">4</option>
                <option value="5">5</option>
                <option value="6">6</option>
            </select>
            <button type="submit">Reservar Ahora</button>
        </form>
    </section>

    <section id="map" class="map-section">
        <h2>Cómo Llegar</h2>
        <iframe
            src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3168.2531873826313!2d-99.13980268471106!3d19.432609386966075!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x8f7c0ac3a19e7165%3A0x542d8ff1827dcd2f!2sFocus%20Coffee!5e0!3m2!1ses-419!2smx!4v1696599394758!5m2!1ses-419!2smx"
            class="map"
            allowfullscreen=""
            loading="lazy"></iframe>
    </section>

    <section id="contact" class="contact-section">
        <h2>Contacto</h2>
        <p>¡Nos encantaría saber de ti!</p>
        <div class="info">
            <i class="fas fa-map-marker-alt"></i><span>Calle Principal 123, Ciudad</span>
        </div>
        <div class="info">
            <i class="fas fa-phone"></i><span>(123) 456-7890</span>
        </div>
        <div class="info">
            <i class="fas fa-envelope"></i><span>info@focuscoffee.com</span>
        </div>
        <div class="social-icons">
            <a href="#"><i class="fab fa-facebook"></i></a>
            <a href="#"><i class="fab fa-instagram"></i></a>
            <a href="#"><i class="fab fa-twitter"></i></a>
        </div>
    </section>

</div>

<footer>
    <p>&copy; 2024 Focus Coffee. Todos los derechos reservados.</p>
</footer>

</body>
</html>
