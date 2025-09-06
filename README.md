<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Estudiantes en Acción</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            line-height: 1.6;
            color: #333;
            background: linear-gradient(135deg, #f4f4f4 0%, #e8f5e8 100%);
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            background: linear-gradient(135deg, #32cd32, #ffd700);
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            color: white;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .nav-menu {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-menu a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            padding: 0.5rem 1rem;
            border-radius: 25px;
        }

        .nav-menu a:hover {
            background: rgba(255,255,255,0.2);
            transform: translateY(-2px);
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, rgba(50, 205, 50, 0.9), rgba(255, 215, 0, 0.9)),
                        url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 300"><defs><pattern id="smallGrid" width="50" height="50" patternUnits="userSpaceOnUse"><path d="M 50 0 L 0 0 0 50" fill="none" stroke="%23ffffff" stroke-width="1" opacity="0.1"/></pattern></defs><rect width="100%" height="100%" fill="url(%23smallGrid)"/></svg>');
            height: 100vh;
            display: flex;
            align-items: center;
            text-align: center;
            color: white;
            position: relative;
            overflow: hidden;
        }

        .hero-content h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
            text-shadow: 3px 3px 6px rgba(0,0,0,0.3);
            animation: fadeInUp 1s ease;
        }

        .hero-content p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            animation: fadeInUp 1s ease 0.3s both;
        }

        .cta-button {
            display: inline-block;
            background: #ffd700;
            color: #2d5016;
            padding: 1rem 2rem;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            font-size: 1.2rem;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
            animation: fadeInUp 1s ease 0.6s both;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(0,0,0,0.3);
            background: #ffed4e;
        }

        /* Sections */
        section {
            padding: 5rem 0;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: #2d5016;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: linear-gradient(90deg, #32cd32, #ffd700);
            border-radius: 2px;
        }

        /* Presentación */
        .presentacion {
            background: white;
            border-radius: 20px;
            padding: 3rem;
            margin: 2rem 0;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        .team-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .team-member {
            text-align: center;
            padding: 2rem;
            background: linear-gradient(135deg, #f8f8f8, #e8f5e8);
            border-radius: 15px;
            transition: transform 0.3s ease;
        }

        .team-member:hover {
            transform: translateY(-5px);
        }

        .member-avatar {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            background: linear-gradient(135deg, #32cd32, #ffd700);
            margin: 0 auto 1rem;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            color: white;
            font-weight: bold;
        }

        /* Propuestas */
        .propuestas-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .propuesta-card {
            background: white;
            border-radius: 15px;
            padding: 2rem;
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
            border-left: 5px solid #32cd32;
        }

        .propuesta-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.15);
        }

        .propuesta-icon {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: linear-gradient(135deg, #32cd32, #ffd700);
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
        }

        /* Redes Sociales */
        .social-section {
            background: linear-gradient(135deg, #32cd32, #ffd700);
            color: white;
            text-align: center;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-top: 2rem;
        }

        .social-link {
            display: inline-block;
            width: 60px;
            height: 60px;
            background: rgba(255,255,255,0.2);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            text-decoration: none;
            color: white;
            font-size: 1.5rem;
            transition: all 0.3s ease;
        }

        .social-link:hover {
            background: rgba(255,255,255,0.3);
            transform: translateY(-3px) scale(1.1);
        }

        /* Footer */
        footer {
            background: #2d5016;
            color: white;
            text-align: center;
            padding: 2rem 0;
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .nav-menu {
                display: none;
            }
            
            .hero-content h1 {
                font-size: 2.5rem;
            }
            
            .hero-content p {
                font-size: 1.2rem;
            }
            
            .social-links {
                flex-wrap: wrap;
            }
        }

        /* Smooth scrolling */
        html {
            scroll-behavior: smooth;
        }

        body {
            margin-top: 80px;
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <nav>
                <div class="logo">Estudiantes en Acción</div>
                <ul class="nav-menu">
                    <li><a href="#inicio">Inicio</a></li>
                    <li><a href="#presentacion">Presentación</a></li>
                    <li><a href="#propuestas">Propuestas</a></li>
                    <li><a href="#redes">Redes Sociales</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <section id="inicio" class="hero">
        <div class="container">
            <div class="hero-content">
                <h1>Estudiantes en Acción</h1>
                <p>Transformando nuestra educación, construyendo nuestro futuro</p>
                <a href="#propuestas" class="cta-button">Conoce nuestras propuestas</a>
            </div>
        </div>
    </section>

    <section id="presentacion" class="container">
        <h2 class="section-title">Nuestra Presentación</h2>
        <div class="presentacion">
            <p style="font-size: 1.2rem; text-align: center; margin-bottom: 2rem; color: #555;">
                Somos un grupo de estudiantes comprometidos con mejorar la experiencia educativa de todos. 
                Creemos en la participación activa, la transparencia y el trabajo en equipo para construir 
                un centro de estudiantes que realmente represente nuestros intereses y necesidades.
            </p>
            
            <div class="team-grid">
                <div class="team-member">
                    <div class="member-avatar">AV</div>
                    <h3>Ana Villegas</h3>
                    <p><strong>Presidenta</strong></p>
                    <p>Estudiante de 5° año, apasionada por la organización de eventos y la representación estudiantil.</p>
                </div>
                <div class="team-member">
                    <div class="member-avatar">CR</div>
                    <h3>Carlos Rodríguez</h3>
                    <p><strong>Vicepresidente</strong></p>
                    <p>Estudiante de 4° año, especializado en comunicación y gestión de proyectos estudiantiles.</p>
                </div>
                <div class="team-member">
                    <div class="member-avatar">MG</div>
                    <h3>María González</h3>
                    <p><strong>Secretaria</strong></p>
                    <p>Estudiante de 3° año, enfocada en la transparencia y documentación de todas las actividades.</p>
                </div>
                <div class="team-member">
                    <div class="member-avatar">JL</div>
                    <h3>Javier López</h3>
                    <p><strong>Tesorero</strong></p>
                    <p>Estudiante de 4° año, responsable de la gestión financiera y presupuestos del centro.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="propuestas" style="background: #f8f8f8;">
        <div class="container">
            <h2 class="section-title">Nuestras Propuestas</h2>
            <div class="propuestas-grid">
                <div class="propuesta-card">
                    <div class="propuesta-icon">📚</div>
                    <h3>Biblioteca Digital</h3>
                    <p>Implementar una plataforma digital con recursos académicos, libros electrónicos y materiales de estudio accesibles para todos los estudiantes.</p>
                </div>
                <div class="propuesta-card">
                    <div class="propuesta-icon">🎨</div>
                    <h3>Espacios Creativos</h3>
                    <p>Crear áreas dedicadas al arte, música y expresión creativa donde los estudiantes puedan desarrollar sus talentos y pasiones.</p>
                </div>
                <div class="propuesta-card">
                    <div class="propuesta-icon">🏃</div>
                    <h3>Deportes Para Todos</h3>
                    <p>Ampliar las actividades deportivas y recreativas, incluyendo torneos inter-cursos y nuevas disciplinas deportivas.</p>
                </div>
                <div class="propuesta-card">
                    <div class="propuesta-icon">💻</div>
                    <h3>Tecnología Educativa</h3>
                    <p>Mejorar la infraestructura tecnológica del colegio con nuevos equipos y software educativo moderno.</p>
                </div>
                <div class="propuesta-card">
                    <div class="propuesta-icon">🌱</div>
                    <h3>Sustentabilidad</h3>
                    <p>Desarrollar programas de reciclaje, huerta escolar y concientización sobre el cuidado del medio ambiente.</p>
                </div>
                <div class="propuesta-card">
                    <div class="propuesta-icon">🎪</div>
                    <h3>Eventos Estudiantiles</h3>
                    <p>Organizar festivales, obras de teatro, conciertos y actividades que fortalezcan la comunidad estudiantil.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="redes" class="social-section">
        <div class="container">
            <h2 class="section-title" style="color: white;">Síguenos en Redes Sociales</h2>
            <p style="font-size: 1.2rem; margin-bottom: 2rem;">
                Mantente al día con todas nuestras actividades y propuestas
            </p>
            <div class="social-links">
                <a href="#" class="social-link" title="Facebook">📘</a>
                <a href="#" class="social-link" title="Instagram">📷</a>
                <a href="#" class="social-link" title="Twitter">🐦</a>
                <a href="#" class="social-link" title="TikTok">🎵</a>
                <a href="#" class="social-link" title="YouTube">📹</a>
                <a href="#" class="social-link" title="WhatsApp">💬</a>
            </div>
            <p style="margin-top: 2rem; font-size: 1.1rem;">
                📧 Email: estudiantesaccion@colegio.edu<br>
                📱 WhatsApp: +54 9 221 XXX-XXXX
            </p>
        </div>
    </section>

    <footer>
        <div class="container">
            <p>&copy; 2024 Estudiantes en Acción - Centro de Estudiantes. Todos los derechos reservados.</p>
            <p>Juntos construimos un futuro mejor para nuestra educación</p>
        </div>
    </footer>

    <script>
        // Smooth scrolling para los enlaces del menú
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Animaciones al hacer scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        // Observar elementos para animaciones
        document.querySelectorAll('.propuesta-card, .team-member').forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(20px)';
            el.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
            observer.observe(el);
        });
    </script>
</body>
</html>
