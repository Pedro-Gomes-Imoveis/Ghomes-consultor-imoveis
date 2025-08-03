<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pedro Gomes Imóveis - Encontre seu lar perfeito</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&family=Playfair+Display:wght@700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #005792;
            --secondary: #00bbf0;
            --accent: #ff6b6b;
            --light: #f8f9fa;
            --dark: #212529;
            --transition: all 0.3s ease;
        }

        body {
            font-family: 'Poppins', sans-serif;
            line-height: 1.6;
            color: var(--dark);
            background-color: #f5f7fa;
            overflow-x: hidden;
        }

        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header Styles */
        header {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            padding: 20px 0;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 15px rgba(0, 0, 0, 0.1);
        }

        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo-icon {
            font-size: 2rem;
            color: white;
        }

        .logo-text {
            font-family: 'Playfair Display', serif;
            font-size: 1.8rem;
            font-weight: 700;
            color: white;
            letter-spacing: 1px;
        }

        .nav-menu {
            display: flex;
            gap: 30px;
        }

        .nav-link {
            color: white;
            text-decoration: none;
            font-weight: 500;
            font-size: 1.1rem;
            transition: var(--transition);
            position: relative;
        }

        .nav-link:hover {
            color: var(--light);
        }

        .nav-link::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background-color: white;
            transition: var(--transition);
        }

        .nav-link:hover::after {
            width: 100%;
        }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url('https://images.unsplash.com/photo-1560448204-e02f11c3d0e2?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80') center/cover no-repeat;
            min-height: 90vh;
            display: flex;
            align-items: center;
            position: relative;
        }

        .hero-content {
            max-width: 650px;
            color: white;
            padding: 40px;
            animation: fadeInUp 1s ease;
        }

        .hero-title {
            font-family: 'Playfair Display', serif;
            font-size: 3.5rem;
            line-height: 1.2;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
        }

        .hero-subtitle {
            font-size: 1.5rem;
            margin-bottom: 30px;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);
        }

        .cta-button {
            display: inline-block;
            background: var(--accent);
            color: white;
            padding: 15px 40px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            font-size: 1.1rem;
            transition: var(--transition);
            box-shadow: 0 4px 15px rgba(255, 107, 107, 0.4);
            border: 2px solid var(--accent);
        }

        .cta-button:hover {
            background: transparent;
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(255, 107, 107, 0.6);
        }

        /* Services Section */
        .services {
            padding: 80px 0;
            background-color: white;
        }

        .section-title {
            text-align: center;
            margin-bottom: 60px;
            font-family: 'Playfair Display', serif;
            color: var(--primary);
            font-size: 2.5rem;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: var(--secondary);
            border-radius: 2px;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .service-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
            transition: var(--transition);
            text-align: center;
            padding: 40px 30px;
        }

        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.12);
        }

        .service-icon {
            font-size: 3rem;
            color: var(--secondary);
            margin-bottom: 20px;
        }

        .service-title {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--primary);
        }

        .service-description {
            color: #666;
        }

        /* Properties Section */
        .properties {
            padding: 80px 0;
            background-color: #f5f7fa;
        }

        .properties-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 40px;
        }

        .filter-options {
            display: flex;
            gap: 15px;
        }

        .filter-btn {
            padding: 8px 20px;
            border: 1px solid #ddd;
            background: white;
            border-radius: 30px;
            cursor: pointer;
            transition: var(--transition);
        }

        .filter-btn:hover, .filter-btn.active {
            background: var(--primary);
            color: white;
            border-color: var(--primary);
        }

        .properties-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 40px;
        }

        .property-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
            transition: var(--transition);
        }

        .property-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.12);
        }

        .property-image {
            height: 250px;
            width: 100%;
            background-color: #ddd;
            overflow: hidden;
            position: relative;
        }

        .property-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .property-card:hover .property-image img {
            transform: scale(1.05);
        }

        .property-badge {
            position: absolute;
            top: 20px;
            right: 20px;
            background: var(--accent);
            color: white;
            padding: 5px 15px;
            border-radius: 30px;
            font-weight: 600;
            z-index: 2;
        }

        .property-details {
            padding: 25px;
        }

        .property-price {
            color: var(--primary);
            font-size: 1.8rem;
            font-weight: 700;
            margin-bottom: 10px;
        }

        .property-address {
            color: #666;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .property-features {
            display: flex;
            justify-content: space-between;
            padding: 15px 0;
            border-top: 1px solid #eee;
            border-bottom: 1px solid #eee;
            margin: 20px 0;
        }

        .feature {
            display: flex;
            align-items: center;
            gap: 5px;
        }

        .btn-view {
            display: block;
            width: 100%;
            text-align: center;
            background: var(--primary);
            color: white;
            padding: 12px;
            border-radius: 8px;
            text-decoration: none;
            font-weight: 600;
            transition: var(--transition);
        }

        .btn-view:hover {
            background: var(--secondary);
        }

        /* Stats Section */
        .stats {
            padding: 80px 0;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            text-align: center;
        }

        .stat-item {
            padding: 30px;
        }

        .stat-number {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 10px;
            font-family: 'Playfair Display', serif;
        }

        .stat-text {
            font-size: 1.2rem;
            opacity: 0.9;
        }

        /* Testimonials */
        .testimonials {
            padding: 80px 0;
            background-color: white;
        }

        .testimonials-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
        }

        .testimonial-card {
            background: #f8f9fa;
            border-radius: 15px;
            padding: 30px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.05);
            position: relative;
        }

        .testimonial-card::before {
            content: '"';
            position: absolute;
            top: 20px;
            left: 20px;
            font-size: 5rem;
            font-family: 'Playfair Display', serif;
            color: var(--secondary);
            opacity: 0.2;
            line-height: 1;
        }

        .testimonial-content {
            margin-bottom: 20px;
            font-style: italic;
            position: relative;
            z-index: 1;
        }

        .testimonial-author {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .author-avatar {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background-color: #ddd;
            overflow: hidden;
        }

        .author-info h4 {
            color: var(--primary);
            margin-bottom: 5px;
        }

        /* Contact Section */
        .contact {
            padding: 80px 0;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
        }

        .contact-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 50px;
        }

        .contact-info h3 {
            font-size: 2rem;
            margin-bottom: 30px;
            font-family: 'Playfair Display', serif;
        }

        .contact-detail {
            display: flex;
            gap: 15px;
            margin-bottom: 25px;
            align-items: flex-start;
        }

        .contact-icon {
            font-size: 1.5rem;
            color: var(--accent);
            margin-top: 5px;
        }

        .contact-text h4 {
            font-size: 1.2rem;
            margin-bottom: 5px;
        }

        .contact-form {
            background: white;
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.15);
        }

        .form-title {
            color: var(--primary);
            font-size: 1.8rem;
            margin-bottom: 25px;
            text-align: center;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-control {
            width: 100%;
            padding: 15px;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-family: 'Poppins', sans-serif;
            font-size: 1rem;
            transition: var(--transition);
        }

        .form-control:focus {
            border-color: var(--secondary);
            outline: none;
            box-shadow: 0 0 0 3px rgba(0, 187, 240, 0.2);
        }

        textarea.form-control {
            min-height: 120px;
            resize: vertical;
        }

        .submit-btn {
            background: var(--accent);
            color: white;
            border: none;
            padding: 15px 30px;
            border-radius: 8px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            width: 100%;
            transition: var(--transition);
            box-shadow: 0 4px 15px rgba(255, 107, 107, 0.4);
        }

        .submit-btn:hover {
            background: #ff5252;
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(255, 107, 107, 0.6);
        }

        /* Footer */
        footer {
            background: var(--dark);
            color: white;
            padding: 60px 0 30px;
        }

        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-col h4 {
            font-size: 1.3rem;
            margin-bottom: 25px;
            position: relative;
            padding-bottom: 10px;
        }

        .footer-col h4::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 50px;
            height: 2px;
            background: var(--secondary);
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 12px;
        }

        .footer-links a {
            color: #aaa;
            text-decoration: none;
            transition: var(--transition);
        }

        .footer-links a:hover {
            color: var(--secondary);
            padding-left: 5px;
        }

        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }

        .social-link {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background: #333;
            color: white;
            border-radius: 50%;
            transition: var(--transition);
        }

        .social-link:hover {
            background: var(--secondary);
            transform: translateY(-5px);
        }

        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid #333;
            color: #aaa;
            font-size: 0.9rem;
        }

        /* Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }

        .modal-content {
            background: white;
            padding: 40px;
            border-radius: 15px;
            max-width: 500px;
            width: 90%;
            position: relative;
            animation: modalFadeIn 0.5s;
        }

        .close-modal {
            position: absolute;
            top: 15px;
            right: 15px;
            font-size: 1.5rem;
            cursor: pointer;
            color: #666;
            transition: var(--transition);
        }

        .close-modal:hover {
            color: var(--accent);
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

        @keyframes modalFadeIn {
            from {
                opacity: 0;
                transform: translateY(-50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Responsive Styles */
        @media (max-width: 992px) {
            .hero-title {
                font-size: 3rem;
            }
            
            .nav-menu {
                gap: 20px;
            }
        }

        @media (max-width: 768px) {
            .mobile-menu-btn {
                display: block;
            }
            
            .nav-menu {
                position: fixed;
                top: 80px;
                left: -100%;
                flex-direction: column;
                background: var(--primary);
                width: 100%;
                text-align: center;
                padding: 20px 0;
                gap: 15px;
                transition: var(--transition);
            }
            
            .nav-menu.active {
                left: 0;
            }
            
            .hero-title {
                font-size: 2.5rem;
            }
            
            .hero-subtitle {
                font-size: 1.2rem;
            }
            
            .properties-header {
                flex-direction: column;
                gap: 20px;
            }
            
            .filter-options {
                flex-wrap: wrap;
                justify-content: center;
            }
        }

        @media (max-width: 576px) {
            .hero-content {
                padding: 20px;
            }
            
            .hero-title {
                font-size: 2rem;
            }
            
            .section-title {
                font-size: 2rem;
            }
            
            .contact-form {
                padding: 25px;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container header-container">
            <div class="logo">
                <i class="fas fa-home logo-icon"></i>
                <span class="logo-text">Pedro Gomes Imóveis</span>
            </div>
            <nav>
                <button class="mobile-menu-btn">
                    <i class="fas fa-bars"></i>
                </button>
                <ul class="nav-menu">
                    <li><a href="#home" class="nav-link">Início</a></li>
                    <li><a href="#services" class="nav-link">Serviços</a></li>
                    <li><a href="#properties" class="nav-link">Imóveis</a></li>
                    <li><a href="#stats" class="nav-link">Resultados</a></li>
                    <li><a href="#contact" class="nav-link">Contato</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <div class="hero-content">
                <h1 class="hero-title">Encontre o lar dos seus sonhos</h1>
                <p class="hero-subtitle">A Pedro Gomes Imóveis oferece as melhores opções de imóveis para compra, venda e locação com atendimento personalizado.</p>
                <a href="#contact" class="cta-button">Solicitar Consulta</a>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section class="services" id="services">
        <div class="container">
            <h2 class="section-title">Nossos Serviços</h2>
            <div class="services-grid">
                <div class="service-card">
                    <i class="fas fa-home service-icon"></i>
                    <h3 class="service-title">Compra de Imóveis</h3>
                    <p class="service-description">Encontre a casa perfeita para você e sua família com nosso amplo portfólio de propriedades selecionadas.</p>
                </div>
                <div class="service-card">
                    <i class="fas fa-dollar-sign service-icon"></i>
                    <h3 class="service-title">Venda de Imóveis</h3>
                    <p class="service-description">Venda seu imóvel com rapidez e pelo melhor preço do mercado com nossa assessoria especializada.</p>
                </div>
                <div class="service-card">
                    <i class="fas fa-key service-icon"></i>
                    <h3 class="service-title">Locação</h3>
                    <p class="service-description">Alugue o imóvel ideal para suas necessidades com contratos seguros e todo suporte necessário.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Properties Section -->
    <section class="properties" id="properties">
        <div class="container">
            <div class="properties-header">
                <h2 class="section-title">Imóveis em Destaque</h2>
                <div class="filter-options">
                    <button class="filter-btn active">Todos</button>
                    <button class="filter-btn">Venda</button>
                    <button class="filter-btn">Aluguel</button>
                    <button class="filter-btn">Casas</button>
                    <button class="filter-btn">Apartamentos</button>
                </div>
            </div>
            <div class="properties-grid">
                <div class="property-card">
                    <div class="property-image">
                        <img src="https://images.unsplash.com/photo-1574362848149-11496d93a7c7?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1084&q=80" alt="Modern Apartment">
                        <span class="property-badge">Aluguel</span>
                    </div>
                    <div class="property-details">
                        <div class="property-price">R$ 2.800/mês</div>
                        <div class="property-address">
                            <i class="fas fa-map-marker-alt"></i>
                            <span>Av. Paulista, 1000 - São Paulo, SP</span>
                        </div>
                        <div class="property-features">
                            <div class="feature">
                                <i class="fas fa-bed"></i>
                                <span>3 Quartos</span>
                            </div>
                            <div class="feature">
                                <i class="fas fa-bath"></i>
                                <span>2 Banheiros</span>
                            </div>
                            <div class="feature">
                                <i class="fas fa-ruler-combined"></i>
                                <span>120m²</span>
                            </div>
                        </div>
                        <a href="#" class="btn-view">Ver Detalhes</a>
                    </div>
                </div>
                <div class="property-card">
                    <div class="property-image">
                        <img src="https://images.unsplash.com/photo-1600585154340-be6161a56a0c?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80" alt="Luxury House">
                        <span class="property-badge">Venda</span>
                    </div>
                    <div class="property-details">
                        <div class="property-price">R$ 1.850.000</div>
                        <div class="property-address">
                            <i class="fas fa-map-marker-alt"></i>
                            <span>Alphaville - Barueri, SP</span>
                        </div>
                        <div class="property-features">
                            <div class="feature">
                                <i class="fas fa-bed"></i>
                                <span>4 Quartos</span>
                            </div>
                            <div class="feature">
                                <i class="fas fa-bath"></i>
                                <span>3 Banheiros</span>
                            </div>
                            <div class="feature">
                                <i class="fas fa-ruler-combined"></i>
                                <span>320m²</span>
                            </div>
                        </div>
                        <a href="#" class="btn-view">Ver Detalhes</a>
                    </div>
                </div>
                <div class="property-card">
                    <div class="property-image">
                        <img src="https://images.unsplash.com/photo-1600596542815-ffad4c1539a9?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1175&q=80" alt="Modern House">
                        <span class="property-badge">Venda</span>
                    </div>
                    <div class="property-details">
                        <div class="property-price">R$ 950.000</div>
                        <div class="property-address">
                            <i class="fas fa-map-marker-alt"></i>
                            <span>Moema - São Paulo, SP</span>
                        </div>
                        <div class="property-features">
                            <div class="feature">
                                <i class="fas fa-bed"></i>
                                <span>3 Quartos</span>
                            </div>
                            <div class="feature">
                                <i class="fas fa-bath"></i>
                                <span>2 Banheiros</span>
                            </div>
                            <div class="feature">
                                <i class="fas fa-ruler-combined"></i>
                                <span>180m²</span>
                            </div>
                        </div>
                        <a href="#" class="btn-view">Ver Detalhes</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Stats Section -->
    <section class="stats" id="stats">
        <div class="container">
            <div class="stats-grid">
                <div class="stat-item">
                    <div class="stat-number">15+</div>
                    <div class="stat-text">Anos de Experiência</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">1200+</div>
                    <div class="stat-text">Clientes Satisfeitos</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">500+</div>
                    <div class="stat-text">Imóveis Vendidos</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">98%</div>
                    <div class="stat-text">Taxa de Satisfação</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Testimonials Section -->
    <section class="testimonials" id="testimonials">
        <div class="container">
            <h2 class="section-title">O Que Nossos Clientes Dizem</h2>
            <div class="testimonials-grid">
                <div class="testimonial-card">
                    <p class="testimonial-content">"A Pedro Gomes Imóveis me ajudou a encontrar o apartamento perfeito para minha família. Profissionais extremamente competentes e atenciosos!"</p>
                    <div class="testimonial-author">
                        <div class="author-avatar"></div>
                        <div class="author-info">
                            <h4>Carlos Silva</h4>
                            <p>Comprador de Imóvel</p>
                        </div>
                    </div>
                </div>
                <div class="testimonial-card">
                    <p class="testimonial-content">"Consegui vender meu imóvel em tempo recorde e por um valor acima do que esperava. Recomendo a todos que precisam de serviços imobiliários."</p>
                    <div class="testimonial-author">
                        <div class="author-avatar"></div>
                        <div class
