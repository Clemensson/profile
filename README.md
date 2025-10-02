<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Seu Nome - Desenvolvedor</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* Reset e configurações gerais */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary-color: #2563eb;
            --secondary-color: #1e40af;
            --text-color: #1f2937;
            --light-text: #6b7280;
            --background: #ffffff;
            --light-background: #f9fafb;
            --border-color: #e5e7eb;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            color: var(--text-color);
            line-height: 1.6;
            background-color: var(--background);
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
        }

        section {
            padding: 5rem 0;
        }

        h1, h2, h3, h4 {
            margin-bottom: 1rem;
            line-height: 1.2;
        }

        h1 {
            font-size: 3rem;
            font-weight: 700;
        }

        h2 {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 3rem;
        }

        p {
            margin-bottom: 1.5rem;
            color: var(--light-text);
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        .btn {
            display: inline-block;
            padding: 0.8rem 1.5rem;
            border-radius: 0.375rem;
            font-weight: 600;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .btn-primary {
            background-color: var(--primary-color);
            color: white;
            border: none;
        }

        .btn-primary:hover {
            background-color: var(--secondary-color);
            transform: translateY(-2px);
        }

        .btn-outline {
            background-color: transparent;
            color: var(--primary-color);
            border: 1px solid var(--primary-color);
        }

        .btn-outline:hover {
            background-color: var(--primary-color);
            color: white;
        }

        /* Header e Navegação */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background-color: rgba(255, 255, 255, 0.95);
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            z-index: 1000;
            transition: all 0.3s ease;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1.5rem 0;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary-color);
        }

        .nav-links {
            display: flex;
            list-style: none;
        }

        .nav-links li {
            margin-left: 2rem;
        }

        .nav-links a {
            font-weight: 500;
            transition: color 0.3s ease;
        }

        .nav-links a:hover {
            color: var(--primary-color);
        }

        .menu-toggle {
            display: none;
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            padding-top: 10rem;
            padding-bottom: 5rem;
            background: linear-gradient(135deg, #f0f9ff 0%, #e0f2fe 100%);
        }

        .hero-content {
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .hero-text {
            flex: 1;
            padding-right: 2rem;
        }

        .hero-text h1 {
            margin-bottom: 1.5rem;
        }

        .hero-text p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
        }

        .hero-buttons {
            display: flex;
            gap: 1rem;
        }

        .hero-image {
            flex: 1;
            text-align: center;
        }

        .profile-img {
            width: 300px;
            height: 300px;
            border-radius: 50%;
            object-fit: cover;
            border: 5px solid white;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
        }

        /* Sobre */
        .about {
            background-color: var(--light-background);
        }

        .about-content {
            display: flex;
            align-items: center;
            gap: 3rem;
        }

        .about-text {
            flex: 2;
        }

        .about-skills {
            flex: 1;
        }

        .skill-item {
            margin-bottom: 1.5rem;
        }

        .skill-name {
            display: flex;
            justify-content: space-between;
            margin-bottom: 0.5rem;
        }

        .skill-bar {
            height: 8px;
            background-color: var(--border-color);
            border-radius: 4px;
            overflow: hidden;
        }

        .skill-level {
            height: 100%;
            background-color: var(--primary-color);
        }

        /* Projetos */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
        }

        .project-card {
            background-color: white;
            border-radius: 0.5rem;
            overflow: hidden;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .project-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
        }

        .project-img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .project-info {
            padding: 1.5rem;
        }

        .project-title {
            font-size: 1.25rem;
            margin-bottom: 0.5rem;
        }

        .project-description {
            margin-bottom: 1rem;
            font-size: 0.9rem;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 1rem;
        }

        .tech-tag {
            background-color: var(--light-background);
            color: var(--primary-color);
            padding: 0.25rem 0.5rem;
            border-radius: 0.25rem;
            font-size: 0.8rem;
            font-weight: 500;
        }

        .project-links {
            display: flex;
            gap: 1rem;
        }

        /* Contato */
        .contact {
            background-color: var(--light-background);
        }

        .contact-content {
            display: flex;
            gap: 3rem;
        }

        .contact-info {
            flex: 1;
        }

        .contact-item {
            display: flex;
            align-items: center;
            margin-bottom: 1.5rem;
        }

        .contact-icon {
            width: 40px;
            height: 40px;
            background-color: var(--primary-color);
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 1rem;
        }

        .contact-form {
            flex: 1;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-control {
            width: 100%;
            padding: 0.75rem;
            border: 1px solid var(--border-color);
            border-radius: 0.375rem;
            font-size: 1rem;
            transition: border-color 0.3s ease;
        }

        .form-control:focus {
            outline: none;
            border-color: var(--primary-color);
        }

        textarea.form-control {
            min-height: 150px;
            resize: vertical;
        }

        /* Footer */
        footer {
            background-color: var(--text-color);
            color: white;
            padding: 3rem 0;
        }

        .footer-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .social-links {
            display: flex;
            gap: 1rem;
        }

        .social-link {
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: background-color 0.3s ease;
        }

        .social-link:hover {
            background-color: var(--primary-color);
        }

        .copyright {
            color: #9ca3af;
            font-size: 0.9rem;
        }

        /* Responsividade */
        @media (max-width: 992px) {
            .hero-content, .about-content, .contact-content {
                flex-direction: column;
            }
            
            .hero-text, .about-text, .contact-info {
                padding-right: 0;
                margin-bottom: 2rem;
            }
            
            h1 {
                font-size: 2.5rem;
            }
            
            h2 {
                font-size: 2rem;
            }
        }

        @media (max-width: 768px) {
            .nav-links {
                display: none;
                position: absolute;
                top: 100%;
                left: 0;
                width: 100%;
                background-color: white;
                flex-direction: column;
                padding: 1rem 0;
                box-shadow: 0 5px 10px rgba(0, 0, 0, 0.1);
            }
            
            .nav-links.active {
                display: flex;
            }
            
            .nav-links li {
                margin: 0;
                text-align: center;
                padding: 0.75rem 0;
            }
            
            .menu-toggle {
                display: block;
            }
            
            .hero-buttons {
                flex-direction: column;
                align-items: flex-start;
            }
            
            .footer-content {
                flex-direction: column;
                gap: 1.5rem;
            }
        }
    </style>
</head>
<body>
    <!-- Header e Navegação -->
    <header>
        <div class="container">
            <nav>
                <a href="#" class="logo">SeuNome</a>
                <ul class="nav-links">
                    <li><a href="#home">Início</a></li>
                    <li><a href="#about">Sobre</a></li>
                    <li><a href="#projects">Projetos</a></li>
                    <li><a href="#contact">Contato</a></li>
                </ul>
                <div class="menu-toggle">
                    <i class="fas fa-bars"></i>
                </div>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="container">
            <div class="hero-content">
                <div class="hero-text">
                    <h1>Olá, eu sou <span style="color: var(--primary-color);">Seu Nome</span></h1>
                    <p>Desenvolvedor Full Stack apaixonado por criar soluções digitais inovadoras e eficientes.</p>
                    <div class="hero-buttons">
                        <a href="#projects" class="btn btn-primary">Ver Projetos</a>
                        <a href="#contact" class="btn btn-outline">Entrar em Contato</a>
                    </div>
                </div>
                <div class="hero-image">
                    <img src="https://via.placeholder.com/300" alt="Seu Nome" class="profile-img">
                </div>
            </div>
        </div>
    </section>

    <!-- Sobre -->
    <section id="about" class="about">
        <div class="container">
            <h2>Sobre Mim</h2>
            <div class="about-content">
                <div class="about-text">
                    <p>Sou um desenvolvedor full stack com experiência em criar aplicações web modernas e responsivas. Minha paixão é transformar ideias em soluções digitais funcionais e elegantes.</p>
                    <p>Com background em [sua formação], tenho trabalhado com diversas tecnologias e frameworks para entregar produtos de alta qualidade que atendem às necessidades dos usuários.</p>
                    <p>Quando não estou codando, gosto de [seus hobbies/interesses], que me ajudam a manter a criatividade e o equilíbrio.</p>
                </div>
                <div class="about-skills">
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>JavaScript</span>
                            <span>90%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-level" style="width: 90%;"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>React</span>
                            <span>85%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-level" style="width: 85%;"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Node.js</span>
                            <span>80%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-level" style="width: 80%;"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>CSS/HTML</span>
                            <span>95%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-level" style="width: 95%;"></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Projetos -->
    <section id="projects" class="projects">
        <div class="container">
            <h2>Meus Projetos</h2>
            <div class="projects-grid">
                <!-- Projeto 1 -->
                <div class="project-card">
                    <img src="https://via.placeholder.com/300x200" alt="Projeto 1" class="project-img">
                    <div class="project-info">
                        <h3 class="project-title">Sistema de Gerenciamento</h3>
                        <p class="project-description">Uma aplicação web completa para gerenciamento de tarefas e projetos com interface intuitiva e funcionalidades avançadas.</p>
                        <div class="project-tech">
                            <span class="tech-tag">React</span>
                            <span class="tech-tag">Node.js</span>
                            <span class="tech-tag">MongoDB</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="btn btn-primary">Ver Demo</a>
                            <a href="#" class="btn btn-outline">Código</a>
                        </div>
                    </div>
                </div>
                
                <!-- Projeto 2 -->
                <div class="project-card">
                    <img src="https://via.placeholder.com/300x200" alt="Projeto 2" class="project-img">
                    <div class="project-info">
                        <h3 class="project-title">E-commerce Responsivo</h3>
                        <p class="project-description">Loja virtual completa com carrinho de compras, sistema de pagamento e painel administrativo.</p>
                        <div class="project-tech">
                            <span class="tech-tag">Vue.js</span>
                            <span class="tech-tag">Express</span>
                            <span class="tech-tag">MySQL</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="btn btn-primary">Ver Demo</a>
                            <a href="#" class="btn btn-outline">Código</a>
                        </div>
                    </div>
                </div>
                
                <!-- Projeto 3 -->
                <div class="project-card">
                    <img src="https://via.placeholder.com/300x200" alt="Projeto 3" class="project-img">
                    <div class="project-info">
                        <h3 class="project-title">App de Finanças Pessoais</h3>
                        <p class="project-description">Aplicativo para controle de gastos e orçamento pessoal com gráficos interativos e relatórios detalhados.</p>
                        <div class="project-tech">
                            <span class="tech-tag">React Native</span>
                            <span class="tech-tag">Firebase</span>
                            <span class="tech-tag">Chart.js</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="btn btn-primary">Ver Demo</a>
                            <a href="#" class="btn btn-outline">Código</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contato -->
    <section id="contact" class="contact">
        <div class="container">
            <h2>Entre em Contato</h2>
            <div class="contact-content">
                <div class="contact-info">
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-envelope"></i>
                        </div>
                        <div>
                            <h3>Email</h3>
                            <p>seuemail@exemplo.com</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-phone"></i>
                        </div>
                        <div>
                            <h3>Telefone</h3>
                            <p>(11) 99999-9999</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-map-marker-alt"></i>
                        </div>
                        <div>
                            <h3>Localização</h3>
                            <p>São Paulo, Brasil</p>
                        </div>
                    </div>
                </div>
                <div class="contact-form">
                    <form id="contactForm">
                        <div class="form-group">
                            <input type="text" class="form-control" placeholder="Seu Nome" required>
                        </div>
                        <div class="form-group">
                            <input type="email" class="form-control" placeholder="Seu Email" required>
                        </div>
                        <div class="form-group">
                            <input type="text" class="form-control" placeholder="Assunto" required>
                        </div>
                        <div class="form-group">
                            <textarea class="form-control" placeholder="Sua Mensagem" required></textarea>
                        </div>
                        <button type="submit" class="btn btn-primary">Enviar Mensagem</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="social-links">
                    <a href="#" class="social-link"><i class="fab fa-github"></i></a>
                    <a href="#" class="social-link"><i class="fab fa-linkedin-in"></i></a>
                    <a href="#" class="social-link"><i class="fab fa-twitter"></i></a>
                    <a href="#" class="social-link"><i class="fab fa-instagram"></i></a>
                </div>
                <p class="copyright">&copy; 2023 Seu Nome. Todos os direitos reservados.</p>
            </div>
        </div>
    </footer>

    <script>
        // Menu toggle para mobile
        document.querySelector('.menu-toggle').addEventListener('click', function() {
            document.querySelector('.nav-links').classList.toggle('active');
        });

        // Fechar menu ao clicar em um link (mobile)
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                document.querySelector('.nav-links').classList.remove('active');
            });
        });

        // Header com efeito de scroll
        window.addEventListener('scroll', function() {
            const header = document.querySelector('header');
            if (window.scrollY > 100) {
                header.style.background = 'rgba(255, 255, 255, 0.98)';
                header.style.boxShadow = '0 2px 10px rgba(0, 0, 0, 0.1)';
            } else {
                header.style.background = 'rgba(255, 255, 255, 0.95)';
                header.style.boxShadow = '0 2px 10px rgba(0, 0, 0, 0.1)';
            }
        });

        // Form submission
        document.getElementById('contactForm').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('Obrigado pela mensagem! Entrarei em contato em breve.');
            this.reset();
        });
    </script>
</body>
</html>
