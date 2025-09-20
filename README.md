<!DOCTYPE html>
<html lang="pt-BR" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>IBCAPPA - Cursos, Livros e Perícia Especializada</title>
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Google Fonts: Poppins -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    
    <!-- Swiper.js for Carousel -->
    <link rel="stylesheet" href="https://unpkg.com/swiper/swiper-bundle.min.css" />
    
    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>

    <style>
        /* Estilização base com a fonte Poppins */
        body {
            font-family: 'Poppins', sans-serif;
            background-color: #0a0a0a;
            color: #e5e7eb; /* Cinza claro para textos */
        }

        /* Cores personalizadas da marca */
        .bg-brand-dark { background-color: #0d1117; }
        .bg-brand-gold { background-color: #d4af37; }
        .text-brand-gold { color: #d4af37; }
        .border-brand-gold { border-color: #d4af37; }
        .ring-brand-gold { --tw-ring-color: #d4af37; }

        /* Estilos para o Swiper Carousel */
        .swiper-container {
            width: 100%;
            height: 45vh; /* Ajustado para 45% da altura da tela */
        }
        .swiper-slide {
            text-align: center;
            font-size: 18px;
            background: #fff;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        .swiper-button-next, .swiper-button-prev {
            color: #d4af37 !important;
        }
        .swiper-pagination-bullet-active {
            background: #d4af37 !important;
        }

        /* Gradiente para o Hero Section */
        .hero-gradient-1 {
            background-image: linear-gradient(to bottom, rgba(13, 17, 23, 0.9), rgba(13, 17, 23, 1)), url('https://placehold.co/1920x1080/0d1117/d4af37?text=IBCAPPA');
        }
        .hero-gradient-2 {
            background-image: linear-gradient(to bottom, rgba(13, 17, 23, 0.9), rgba(13, 17, 23, 1)), url('https://placehold.co/1920x1080/1a202c/d4af37?text=Expertise');
        }
        .hero-gradient-3 {
            background-image: linear-gradient(to bottom, rgba(13, 17, 23, 0.9), rgba(13, 17, 23, 1)), url('https://placehold.co/1920x1080/2d3748/d4af37?text=Precisão');
        }
        .hero-slide {
            background-size: cover;
            background-position: center;
        }

        /* Animações de entrada */
        .reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.8s ease-out, transform 0.6s ease-out;
        }
        .reveal.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* Efeito de brilho em botões e cards */
        .glow-on-hover {
            position: relative;
            overflow: hidden;
            z-index: 1;
        }
        .glow-on-hover:before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 300%;
            height: 300%;
            background: radial-gradient(circle, rgba(212, 175, 55, 0.2), transparent 70%);
            transform: translate(-50%, -50%) scale(0);
            transition: transform 0.7s ease;
            z-index: -1;
        }
        .glow-on-hover:hover:before {
            transform: translate(-50%, -50%) scale(1);
        }

        /* Estilo da barra de rolagem */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #0d1117;
        }
        ::-webkit-scrollbar-thumb {
            background-color: #d4af37;
            border-radius: 10px;
            border: 2px solid #0d1117;
        }
    </style>
</head>
<body class="bg-brand-dark">

    <!-- Cabeçalho -->
    <header id="header" class="fixed top-0 left-0 right-0 z-50 transition-all duration-300">
        <div class="container mx-auto px-6 py-4">
            <div class="flex items-center justify-between">
                <a href="#" class="text-2xl font-bold text-white">
                    IB<span class="text-brand-gold">CAPPA</span>
                </a>
                <nav class="hidden md:flex items-center space-x-8">
                    <a href="#inicio" class="text-gray-300 hover:text-brand-gold transition-colors duration-300">Início</a>
                    <a href="#destaques" class="text-gray-300 hover:text-brand-gold transition-colors duration-300">Destaques</a>
                    <a href="#servicos" class="text-gray-300 hover:text-brand-gold transition-colors duration-300">Serviços</a>
                    <a href="#sobre" class="text-gray-300 hover:text-brand-gold transition-colors duration-300">Quem Somos</a>
                    <a href="#depoimentos" class="text-gray-300 hover:text-brand-gold transition-colors duration-300">Depoimentos</a>
                    <a href="#contato" class="text-gray-300 hover:text-brand-gold transition-colors duration-300">Contato</a>
                </nav>
                <a href="#contato" class="hidden md:inline-block bg-brand-gold text-brand-dark font-semibold px-5 py-2 rounded-lg shadow-lg hover:bg-opacity-90 transition-all duration-300 glow-on-hover">
                    Fale Conosco
                </a>
                <button id="mobile-menu-button" class="md:hidden text-white">
                    <i data-lucide="menu"></i>
                </button>
            </div>
        </div>
        <!-- Menu Mobile -->
        <div id="mobile-menu" class="hidden md:hidden bg-brand-dark/95 backdrop-blur-sm">
             <a href="#inicio" class="block text-center py-3 text-gray-300 hover:text-brand-gold hover:bg-gray-800 transition-colors duration-300">Início</a>
             <a href="#destaques" class="block text-center py-3 text-gray-300 hover:text-brand-gold hover:bg-gray-800 transition-colors duration-300">Destaques</a>
             <a href="#servicos" class="block text-center py-3 text-gray-300 hover:text-brand-gold hover:bg-gray-800 transition-colors duration-300">Serviços</a>
             <a href="#sobre" class="block text-center py-3 text-gray-300 hover:text-brand-gold hover:bg-gray-800 transition-colors duration-300">Quem Somos</a>
             <a href="#depoimentos" class="block text-center py-3 text-gray-300 hover:text-brand-gold hover:bg-gray-800 transition-colors duration-300">Depoimentos</a>
             <a href="#contato" class="block text-center py-3 text-gray-300 hover:text-brand-gold hover:bg-gray-800 transition-colors duration-300">Contato</a>
        </div>
    </header>

    <main>
        <!-- Seção Hero com Carrossel -->
        <section id="inicio" class="relative">
            <div class="swiper-container">
                <div class="swiper-wrapper">
                    <!-- Slide 1 -->
                    <div class="swiper-slide hero-slide hero-gradient-1">
                        <div class="container mx-auto px-6 text-center reveal">
                            <h1 class="text-3xl md:text-4xl font-extrabold text-white leading-tight mb-4">
                                Transformando Dados em <span class="text-brand-gold">Decisões Estratégicas</span>
                            </h1>
                            <p class="text-base md:text-lg text-gray-300 max-w-3xl mx-auto mb-6">
                                Oferecemos perícias, cursos e publicações com precisão técnica e rigor analítico para garantir o seu sucesso.
                            </p>
                            <a href="#destaques" class="bg-brand-gold text-brand-dark font-bold px-6 py-3 rounded-lg shadow-xl hover:scale-105 transition-all duration-300 inline-block glow-on-hover">
                                Conheça os Destaques
                            </a>
                        </div>
                    </div>
                    <!-- Slide 2 -->
                    <div class="swiper-slide hero-slide hero-gradient-2">
                         <div class="container mx-auto px-6 text-center">
                            <h1 class="text-3xl md:text-4xl font-extrabold text-white leading-tight mb-4">
                                Expertise Jurídica e <span class="text-brand-gold">Financeira ao Seu Lado</span>
                            </h1>
                            <p class="text-base md:text-lg text-gray-300 max-w-3xl mx-auto mb-6">
                                Capacite sua carreira com nossos cursos e publicações, desenvolvidos por especialistas renomados no mercado.
                            </p>
                            <a href="#servicos" class="bg-brand-gold text-brand-dark font-bold px-6 py-3 rounded-lg shadow-xl hover:scale-105 transition-all duration-300 inline-block glow-on-hover">
                                Nossos Serviços
                            </a>
                        </div>
                    </div>
                    <!-- Slide 3 -->
                    <div class="swiper-slide hero-slide hero-gradient-3">
                         <div class="container mx-auto px-6 text-center">
                            <h1 class="text-3xl md:text-4xl font-extrabold text-white leading-tight mb-4">
                                Precisão e Clareza em <span class="text-brand-gold">Cada Laudo Pericial</span>
                            </h1>
                            <p class="text-base md:text-lg text-gray-300 max-w-3xl mx-auto mb-6">
                                Nossa metodologia rigorosa e tecnologia de ponta garantem a confiança que você precisa para tomar as melhores decisões.
                            </p>
                            <a href="#contato" class="bg-brand-gold text-brand-dark font-bold px-6 py-3 rounded-lg shadow-xl hover:scale-105 transition-all duration-300 inline-block glow-on-hover">
                                Fale com um Especialista
                            </a>
                        </div>
                    </div>
                </div>
                <!-- Add Pagination -->
                <div class="swiper-pagination"></div>
                <!-- Add Navigation -->
                <div class="swiper-button-next"></div>
                <div class="swiper-button-prev"></div>
            </div>
        </section>

        <!-- Seção Destaques -->
        <section id="destaques" class="py-20 md:py-32 bg-black">
            <div class="container mx-auto px-6">
                <div class="text-center mb-16 reveal">
                    <h2 class="text-3xl md:text-4xl font-bold text-white">Nossos <span class="text-brand-gold">Destaques</span></h2>
                    <p class="text-gray-400 mt-4 max-w-2xl mx-auto">Conheça os cursos e livros mais procurados por profissionais que buscam a excelência.</p>
                </div>
                <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
                    <!-- Card Curso 1 -->
                    <div class="bg-[#161b22] border border-gray-800 rounded-lg overflow-hidden reveal glow-on-hover hover:-translate-y-2 transition-transform duration-300 relative">
                        <span class="absolute top-4 left-4 bg-brand-gold text-brand-dark text-xs font-bold px-3 py-1 rounded-full">MAIS VENDIDO</span>
                        <img src="https://ibcappa.com.br/cursos/comunidade-pericia-trabalhista/" alt="Imagem do Curso de Perícia" class="w-full h-48 object-cover">
                        <div class="p-6">
                            <h3 class="text-xl font-bold text-white mb-2">Formação Completa em Perícia Judicial</h3>
                            <p class="text-gray-400 text-sm mb-4">Aprenda do zero ao avançado para se tornar um perito de sucesso.</p>
                            <a href="#" class="inline-block bg-brand-gold text-brand-dark font-semibold px-4 py-2 rounded-md text-sm hover:bg-opacity-90 transition-colors">Saiba Mais</a>
                        </div>
                    </div>
                    <!-- Card Curso 2 -->
                    <div class="bg-[#161b22] border border-gray-800 rounded-lg overflow-hidden reveal glow-on-hover hover:-translate-y-2 transition-transform duration-300 relative" style="transition-delay: 150ms;">
                        <span class="absolute top-4 left-4 bg-brand-gold text-brand-dark text-xs font-bold px-3 py-1 rounded-full">MAIS VENDIDO</span>
                        <img src="https://placehold.co/600x400/0d1117/d4af37?text=Cálculos+Trabalhistas" alt="Imagem do Curso de Cálculos" class="w-full h-48 object-cover">
                        <div class="p-6">
                            <h3 class="text-xl font-bold text-white mb-2">Cálculos Trabalhistas na Prática</h3>
                            <p class="text-gray-400 text-sm mb-4">Domine os cálculos de verbas rescisórias e horas extras.</p>
                            <a href="#" class="inline-block bg-brand-gold text-brand-dark font-semibold px-4 py-2 rounded-md text-sm hover:bg-opacity-90 transition-colors">Saiba Mais</a>
                        </div>
                    </div>
                    <!-- Card Livro 1 -->
                    <div class="text-center reveal" style="transition-delay: 300ms;">
                         <div class="relative">
                            <img src="https://placehold.co/300x450/161b22/d4af37?text=Livro+1" alt="Capa do Livro 1" class="w-full h-auto object-cover rounded-lg shadow-lg mb-4 border-4 border-transparent hover:border-brand-gold transition-all duration-300">
                             <span class="absolute top-4 left-4 bg-brand-gold text-brand-dark text-xs font-bold px-3 py-1 rounded-full">MAIS VENDIDO</span>
                        </div>
                        <h3 class="font-bold text-white mt-2">Manual da Perícia Contábil</h3>
                        <p class="text-sm text-gray-500">Dr. Nome do Autor</p>
                    </div>
                     <!-- Card Livro 2 -->
                    <div class="text-center reveal" style="transition-delay: 450ms;">
                         <div class="relative">
                            <img src="https://placehold.co/300x450/161b22/d4af37?text=Livro+2" alt="Capa do Livro 2" class="w-full h-auto object-cover rounded-lg shadow-lg mb-4 border-4 border-transparent hover:border-brand-gold transition-all duration-300">
                             <span class="absolute top-4 left-4 bg-brand-gold text-brand-dark text-xs font-bold px-3 py-1 rounded-full">MAIS VENDIDO</span>
                        </div>
                        <h3 class="font-bold text-white mt-2">Desvendando o PJe-Calc</h3>
                        <p class="text-sm text-gray-500">Dra. Nome da Autora</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Seção de Serviços -->
        <section id="servicos" class="py-20 md:py-32 bg-brand-dark">
            <div class="container mx-auto px-6">
                <div class="text-center mb-16 reveal">
                    <h2 class="text-3xl md:text-4xl font-bold text-white">Nossas <span class="text-brand-gold">Áreas de Atuação</span></h2>
                    <p class="text-gray-400 mt-4 max-w-2xl mx-auto">Análises detalhadas para cada necessidade específica, da esfera bancária à tributária.</p>
                </div>

                <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
                    <!-- Card de Serviço -->
                    <div class="bg-[#161b22] border border-gray-800 p-8 rounded-lg text-center reveal glow-on-hover hover:-translate-y-2 transition-transform duration-300">
                        <div class="inline-block p-4 bg-brand-gold/10 rounded-full mb-4">
                            <i data-lucide="landmark" class="text-brand-gold h-10 w-10"></i>
                        </div>
                        <h3 class="text-xl font-bold text-white mb-2">Perícia Bancária</h3>
                        <p class="text-gray-400 text-sm">Análise de contratos, juros abusivos e cálculos de financiamentos para garantir seus direitos.</p>
                    </div>

                    <!-- Card de Serviço -->
                    <div class="bg-[#161b22] border border-gray-800 p-8 rounded-lg text-center reveal glow-on-hover hover:-translate-y-2 transition-transform duration-300" style="transition-delay: 100ms;">
                        <div class="inline-block p-4 bg-brand-gold/10 rounded-full mb-4">
                            <i data-lucide="briefcase" class="text-brand-gold h-10 w-10"></i>
                        </div>
                        <h3 class="text-xl font-bold text-white mb-2">Perícia Trabalhista</h3>
                        <p class="text-gray-400 text-sm">Cálculos de verbas rescisórias, horas extras e adicionais, assegurando justiça nas relações de trabalho.</p>
                    </div>

                    <!-- Card de Serviço -->
                    <div class="bg-[#161b22] border border-gray-800 p-8 rounded-lg text-center reveal glow-on-hover hover:-translate-y-2 transition-transform duration-300" style="transition-delay: 200ms;">
                        <div class="inline-block p-4 bg-brand-gold/10 rounded-full mb-4">
                            <i data-lucide="receipt" class="text-brand-gold h-10 w-10"></i>
                        </div>
                        <h3 class="text-xl font-bold text-white mb-2">Perícia Tributária</h3>
                        <p class="text-gray-400 text-sm">Revisão e recuperação de créditos tributários, otimizando a carga fiscal da sua empresa.</p>
                    </div>
                    
                    <!-- Card de Serviço -->
                    <div class="bg-[#161b22] border border-gray-800 p-8 rounded-lg text-center reveal glow-on-hover hover:-translate-y-2 transition-transform duration-300" style="transition-delay: 300ms;">
                        <div class="inline-block p-4 bg-brand-gold/10 rounded-full mb-4">
                            <i data-lucide="user-check" class="text-brand-gold h-10 w-10"></i>
                        </div>
                        <h3 class="text-xl font-bold text-white mb-2">Perícia Previdenciária</h3>
                        <p class="text-gray-400 text-sm">Análise e planejamento de aposentadorias e benefícios para um futuro mais tranquilo.</p>
                    </div>

                    <!-- Card de Serviço -->
                    <div class="bg-[#161b22] border border-gray-800 p-8 rounded-lg text-center reveal glow-on-hover hover:-translate-y-2 transition-transform duration-300" style="transition-delay: 400ms;">
                        <div class="inline-block p-4 bg-brand-gold/10 rounded-full mb-4">
                            <i data-lucide="calculator" class="text-brand-gold h-10 w-10"></i>
                        </div>
                        <h3 class="text-xl font-bold text-white mb-2">Perícia Contábil</h3>
                        <p class="text-gray-400 text-sm">Apuração de haveres, avaliação de empresas (valuation) e investigações de fraudes.</p>
                    </div>

                    <!-- Card de Serviço -->
                    <div class="bg-[#161b22] border border-gray-800 p-8 rounded-lg text-center reveal glow-on-hover hover:-translate-y-2 transition-transform duration-300" style="transition-delay: 500ms;">
                        <div class="inline-block p-4 bg-brand-gold/10 rounded-full mb-4">
                            <i data-lucide="award" class="text-brand-gold h-10 w-10"></i>
                        </div>
                        <h3 class="text-xl font-bold text-white mb-2">Consultoria Especializada</h3>
                        <p class="text-gray-400 text-sm">Assistência técnica em processos judiciais e elaboração de quesitos estratégicos.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Seção Sobre Nós -->
        <section id="sobre" class="py-20 md:py-32 bg-black">
            <div class="container mx-auto px-6 text-center">
                <div class="max-w-3xl mx-auto">
                    <div class="reveal">
                        <h2 class="text-3xl md:text-4xl font-bold mb-4 text-white">Confiança Baseada em <span class="text-brand-gold">Resultados</span></h2>
                        <p class="text-gray-400 mb-8">
                            Nascemos da união de especialistas para fornecer laudos precisos e consultoria de alto nível. Com tecnologia de ponta e metodologia rigorosa, transformamos dados complexos em clareza e confiança para advogados e empresas.
                        </p>
                        <div class="flex justify-center space-x-8 md:space-x-16">
                            <div class="text-center">
                                <p class="text-4xl font-bold text-brand-gold">+1000</p>
                                <p class="text-gray-500">Casos de Sucesso</p>
                            </div>
                            <div class="text-center">
                                <p class="text-4xl font-bold text-brand-gold">+20</p>
                                <p class="text-gray-500">Anos de Experiência</p>
                            </div>
                             <div class="text-center">
                                <p class="text-4xl font-bold text-brand-gold">98%</p>
                                <p class="text-gray-500">de Satisfação</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Seção de Depoimentos -->
        <section id="depoimentos" class="py-20 md:py-32 bg-brand-dark">
            <div class="container mx-auto px-6">
                <div class="text-center mb-16 reveal">
                    <h2 class="text-3xl md:text-4xl font-bold text-white">O que nossos <span class="text-brand-gold">Clientes Dizem</span></h2>
                    <p class="text-gray-400 mt-4 max-w-2xl mx-auto">A parceria que gera resultados e fortalece a advocacia.</p>
                </div>
                <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
                    <!-- Depoimento 1 -->
                    <div class="bg-[#161b22] border border-gray-800 p-8 rounded-lg reveal" style="transition-delay: 100ms;">
                        <i data-lucide="quote" class="text-brand-gold/30 h-12 w-12 mb-4"></i>
                        <p class="text-gray-300 mb-6">"A precisão dos laudos do IBCAPPA foi decisiva para o sucesso do nosso caso mais complexo. Indispensável para qualquer escritório sério."</p>
                        <div>
                            <p class="font-bold text-white">Dr. Carlos Andrade</p>
                            <p class="text-sm text-brand-gold">Advogado Tributarista</p>
                        </div>
                    </div>
                    <!-- Depoimento 2 -->
                    <div class="bg-[#161b22] border border-gray-800 p-8 rounded-lg reveal" style="transition-delay: 200ms;">
                        <i data-lucide="quote" class="text-brand-gold/30 h-12 w-12 mb-4"></i>
                        <p class="text-gray-300 mb-6">"O curso de PJe-Calc superou minhas expectativas. A didática é excelente e o conteúdo é extremamente prático. Recomendo fortemente!"</p>
                        <div>
                            <p class="font-bold text-white">Ana Paula Martins</p>
                            <p class="text-sm text-brand-gold">Advogada Trabalhista</p>
                        </div>
                    </div>
                    <!-- Depoimento 3 -->
                    <div class="bg-[#161b22] border border-gray-800 p-8 rounded-lg reveal" style="transition-delay: 300ms;">
                        <i data-lucide="quote" class="text-brand-gold/30 h-12 w-12 mb-4"></i>
                        <p class="text-gray-300 mb-6">"Finalmente encontrei uma consultoria que entende as nuances da perícia bancária. A equipe é ágil, competente e sempre disponível."</p>
                        <div>
                            <p class="font-bold text-white">Fernando Costa</p>
                            <p class="text-sm text-brand-gold">Diretor Financeiro</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Seção de Contato -->
        <section id="contato" class="py-20 md:py-32 bg-black">
            <div class="container mx-auto px-6">
                <div class="text-center mb-16 reveal">
                    <h2 class="text-3xl md:text-4xl font-bold text-white">Pronto para <span class="text-brand-gold">Fortalecer seu Caso?</span></h2>
                    <p class="text-gray-400 mt-4 max-w-2xl mx-auto">Entre em contato e descubra como nossa expertise pode ser o diferencial que você busca.</p>
                </div>

                <div class="max-w-4xl mx-auto grid md:grid-cols-2 gap-8 bg-[#161b22] p-8 md:p-12 rounded-lg border border-gray-800 reveal">
                    <div>
                        <h3 class="text-2xl font-bold text-white mb-4">Informações de Contato</h3>
                        <p class="text-gray-400 mb-6">Estamos à disposição para agendar uma consulta e entender suas necessidades.</p>
                        <div class="space-y-4">
                            <div class="flex items-center space-x-3">
                                <i data-lucide="mail" class="text-brand-gold h-5 w-5"></i>
                                <span class="text-gray-300">contato@ibcappa.com.br</span>
                            </div>
                             <div class="flex items-center space-x-3">
                                <i data-lucide="phone" class="text-brand-gold h-5 w-5"></i>
                                <span class="text-gray-300">(62) 99999-9999</span>
                            </div>
                             <div class="flex items-start space-x-3">
                                <i data-lucide="map-pin" class="text-brand-gold h-5 w-5 mt-1"></i>
                                <span class="text-gray-300">Av. Exemplo, 1234, Sala 56<br>Goiânia - GO, Brasil</span>
                            </div>
                        </div>
                    </div>
                    <form id="contact-form" class="space-y-4">
                        <div>
                            <label for="name" class="sr-only">Nome</label>
                            <input type="text" id="name" name="name" placeholder="Seu Nome Completo" class="w-full bg-gray-800 text-white p-3 rounded-md border border-gray-700 focus:ring-2 focus:ring-brand-gold focus:border-transparent outline-none transition-all">
                        </div>
                        <div>
                            <label for="email" class="sr-only">Email</label>
                            <input type="email" id="email" name="email" placeholder="Seu Melhor E-mail" class="w-full bg-gray-800 text-white p-3 rounded-md border border-gray-700 focus:ring-2 focus:ring-brand-gold focus:border-transparent outline-none transition-all">
                        </div>
                         <div>
                            <label for="message" class="sr-only">Mensagem</label>
                            <textarea id="message" name="message" rows="4" placeholder="Descreva sua necessidade..." class="w-full bg-gray-800 text-white p-3 rounded-md border border-gray-700 focus:ring-2 focus:ring-brand-gold focus:border-transparent outline-none transition-all"></textarea>
                        </div>
                        <button type="submit" class="w-full bg-brand-gold text-brand-dark font-bold py-3 rounded-lg shadow-lg hover:bg-opacity-90 transition-all duration-300 glow-on-hover">
                            Enviar Mensagem
                        </button>
                        <p id="form-status" class="text-center text-sm mt-2"></p>
                    </form>
                </div>
            </div>
        </section>
    </main>

    <!-- Rodapé -->
    <footer class="bg-black border-t border-gray-900">
        <div class="container mx-auto px-6 py-8">
            <div class="flex flex-col md:flex-row justify-between items-center text-center md:text-left space-y-4 md:space-y-0">
                <p class="text-sm text-gray-500">&copy; 2024 IBCAPPA. Todos os direitos reservados.</p>
                <div class="flex justify-center space-x-4">
                    <a href="#" class="text-gray-500 hover:text-brand-gold transition-colors"><i data-lucide="facebook"></i></a>
                    <a href="#" class="text-gray-500 hover:text-brand-gold transition-colors"><i data-lucide="instagram"></i></a>
                    <a href="#" class="text-gray-500 hover:text-brand-gold transition-colors"><i data-lucide="linkedin"></i></a>
                </div>
                 <p class="text-sm text-gray-600">
                    Desenvolvido com expertise.
                </p>
            </div>
        </div>
    </footer>
    
    <!-- Swiper.js -->
    <script src="https://unpkg.com/swiper/swiper-bundle.min.js"></script>

    <script>
        // Inicializa Lucide Icons
        lucide.createIcons();

        // Inicializa o Swiper Carousel
        const swiper = new Swiper('.swiper-container', {
            loop: true,
            effect: 'fade',
            fadeEffect: {
                crossFade: true
            },
            autoplay: {
                delay: 7000,
                disableOnInteraction: false,
            },
            pagination: {
                el: '.swiper-pagination',
                clickable: true,
            },
            navigation: {
                nextEl: '.swiper-button-next',
                prevEl: '.swiper-button-prev',
            },
        });

        // Lógica do Menu Mobile
        const mobileMenuButton = document.getElementById('mobile-menu-button');
        const mobileMenu = document.getElementById('mobile-menu');
        mobileMenuButton.addEventListener('click', () => {
            mobileMenu.classList.toggle('hidden');
        });

        // Efeito do cabeçalho ao rolar
        const header = document.getElementById('header');
        window.addEventListener('scroll', () => {
            if (window.scrollY > 50) {
                header.classList.add('bg-brand-dark/95', 'shadow-lg', 'backdrop-blur-sm');
            } else {
                header.classList.remove('bg-brand-dark/95', 'shadow-lg', 'backdrop-blur-sm');
            }
        });

        // Animação de revelação ao rolar
        const revealElements = document.querySelectorAll('.reveal');
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                    // Opcional: para de observar depois que a animação acontece
                    // observer.unobserve(entry.target);
                }
            });
        }, {
            threshold: 0.1 // Ativa quando 10% do elemento está visível
        });

        revealElements.forEach(el => {
            observer.observe(el);
        });

        // Simulação de envio de formulário
        const contactForm = document.getElementById('contact-form');
        const formStatus = document.getElementById('form-status');
        contactForm.addEventListener('submit', (e) => {
            e.preventDefault();
            formStatus.textContent = 'Enviando sua mensagem...';
            formStatus.classList.remove('text-green-500', 'text-red-500');
            formStatus.classList.add('text-brand-gold');

            setTimeout(() => {
                formStatus.textContent = 'Mensagem enviada com sucesso! Entraremos em contato em breve.';
                formStatus.classList.remove('text-brand-gold');
                formStatus.classList.add('text-green-500');
                contactForm.reset();
            }, 2000);
        });
        
        // Fechar menu mobile ao clicar em um link
        const mobileLinks = document.querySelectorAll('#mobile-menu a');
        mobileLinks.forEach(link => {
            link.addEventListener('click', () => {
                mobileMenu.classList.add('hidden');
            });
        });

    </script>
</body>
</html>

