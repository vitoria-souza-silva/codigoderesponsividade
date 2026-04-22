# codigoderesponsividade
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NexusPlay | A Arena dos Deuses</title>
    <style>
        /* RESET e ESTILOS GLOBAIS */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: #0a0c12;
            font-family: 'Segoe UI', 'Orbitron', 'Poppins', 'Arial', sans-serif;
            line-height: 1.4;
            color: #eef5ff;
            overflow-x: hidden;
        }

        /* CONTAINER PRINCIPAL RESPONSIVO */
        .container {
            width: 100%;
            max-width: 1280px; /* Limite máximo para telas grandes */
            margin: 0 auto;
            background-color: #0a0c12;
        }

        /* ========== HEADER ========== */
        .main-header {
            background: linear-gradient(135deg, #0f0f1a 0%, #1a1a2f 100%);
            border-bottom: 3px solid #ff3366;
            padding: 15px 5%;
            display: flex;
            flex-wrap: wrap; /* Permite quebrar linha em telas pequenas */
            align-items: center;
            justify-content: space-between;
        }

        .logo-area h1 {
            font-family: 'Orbitron', sans-serif;
            font-size: clamp(24px, 5vw, 32px); /* Tamanho de fonte fluido */
            letter-spacing: 2px;
            background: linear-gradient(135deg, #ff3366, #ffaa44);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        .nav-links {
            display: flex;
            gap: 20px;
        }

        .nav-links a {
            color: #eef5ff;
            text-decoration: none;
            font-weight: 600;
            font-size: 14px;
            transition: 0.2s;
        }

        /* ========== HERO SECTION ========== */
        .hero {
            padding: 60px 5%;
            display: flex;
            flex-direction: row;
            align-items: center;
            justify-content: space-between;
            gap: 40px;
        }

        .hero-text {
            flex: 1;
            max-width: 600px;
        }

        .hero-text h2 {
            font-size: clamp(32px, 8vw, 54px);
            font-weight: 800;
            margin-bottom: 20px;
        }

        .hero-image {
            flex: 1;
            display: flex;
            justify-content: center;
        }

        .hero-image img {
            width: 100%;
            max-width: 480px;
            height: auto;
        }

        /* ========== GRID DE JOGOS ========== */
        .featured {
            padding: 60px 5%;
        }

        .games-grid {
            display: grid;
            /* Cria colunas automáticas que se ajustam ao espaço disponível */
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
        }

        .game-card {
            background: #181c28;
            border-radius: 20px;
            overflow: hidden;
            border: 1px solid #2a2f3f;
        }

        .game-img {
            height: 170px;
            background-size: cover;
            background-position: center;
        }

        /* ========== BANNER PROMO ========== */
        .promo-banner {
            background: linear-gradient(90deg, #1a1c2c, #221f32);
            margin: 20px 5%;
            border-radius: 20px;
            padding: 30px;
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            gap: 20px;
            border-left: 8px solid #ffaa44;
        }

        /* ========== RANKING (TABELA RESPONSIVA) ========== */
        .rank-section {
            padding: 40px 5%;
            overflow-x: auto; /* Permite scroll na tabela se for muito estreito */
        }

        .rank-table {
            width: 100%;
            min-width: 600px; /* Garante que a tabela não esmague o conteúdo */
            border-collapse: collapse;
            background: #10131e;
        }

        /* ========== NEWSLETTER ========== */
        .newsletter {
            padding: 40px 5%;
            text-align: center;
        }

        .form-group {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 15px;
        }

        .form-group input {
            width: 100%;
            max-width: 400px;
            padding: 15px;
            border-radius: 30px;
            border: 1px solid #373e5a;
            background: #0b0e18;
            color: white;
        }

        /* ========== FOOTER ========== */
        .main-footer {
            padding: 40px 5%;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 40px;
            border-top: 1px solid #252a3c;
        }

        /* ========== MEDIA QUERIES (A MÁGICA ACONTECE AQUI) ========== */

        /* Para Tablets e Celulares */
        @media (max-width: 992px) {
            .hero {
                flex-direction: column; /* Texto em cima, imagem embaixo */
                text-align: center;
            }
            .btn-group {
                justify-content: center;
            }
        }

        @media (max-width: 600px) {
            .main-header {
                justify-content: center;
                gap: 15px;
            }
            .nav-links {
                font-size: 12px;
                gap: 10px;
                flex-wrap: wrap;
                justify-content: center;
            }
            .promo-banner {
                padding: 20px;
            }
            .promo-text h4 {
                font-size: 20px;
            }
        }

        /* Estilos de botões que faltavam no refatoramento */
        .btn-primary, .promo-btn {
            background: #ff3366; color: white; border: none; padding: 12px 25px;
            border-radius: 30px; font-weight: bold; cursor: pointer;
        }
        .btn-secondary {
            background: transparent; border: 2px solid #ffaa44; color: #ffaa44;
            padding: 11px 25px; border-radius: 30px; font-weight: bold; cursor: pointer;
        }
    </style>
</head>
<body>

<div class="container">
    <header class="main-header">
        <div class="logo-area">
            <h1>⚡ NEXUSPLAY</h1>
        </div>
        <nav class="nav-links">
            <a href="#">INÍCIO</a>
            <a href="#">JOGOS</a>
            <a href="#">RANKING</a>
            <a href="#">LOJA</a>
        </nav>
    </header>

    <section class="hero">
        <div class="hero-text">
            <h2>DOMINE A <span>ARENA</span> DOS DEUSES</h2>
            <p>Batalhas épicas e gráficos de última geração em qualquer dispositivo.</p>
            <div class="btn-group">
                <button class="btn-primary">JOGAR AGORA</button>
                <button class="btn-secondary">TRAILER</button>
            </div>
        </div>
        <div class="hero-image">
            <img src="https://placehold.co/480x400/1f1a2e/ff6680?text=GUERREIRO" alt="Personagem">
        </div>
    </section>

    <section class="featured">
        <div class="games-grid">
            <div class="game-card">
                <div class="game-img" style="background-image: url('https://placehold.co/280x170/2a1e3c/dd5588?text=Shadow+Legends');"></div>
                <div style="padding:15px"><h3>Shadow Legends</h3><p>MMORPG Sombrio</p></div>
            </div>
            <div class="game-card">
                <div class="game-img" style="background-image: url('https://placehold.co/280x170/1f2c2e/44ffaa?text=Cyber+Strike');"></div>
                <div style="padding:15px"><h3>Cyber Strike</h3><p>FPS Futurista</p></div>
            </div>
            <div class="game-card">
                <div class="game-img" style="background-image: url('https://placehold.co/280x170/261f2a/f0aa44?text=Dragonspire');"></div>
                <div style="padding:15px"><h3>Dragonspire</h3><p>Ação e Dragões</p></div>
            </div>
        </div>
    </section>

    <div class="promo-banner">
        <h4>🏆 PROMOÇÃO DE LANÇAMENTO</h4>
        <button class="promo-btn">RESGATAR OFERTA</button>
    </div>

    <div class="newsletter">
        <h3>📢 Entre na Irmandade</h3>
        <div class="form-group">
            <input type="email" placeholder="Seu e-mail gamer">
            <button class="btn-primary">INSCREVER-SE</button>
        </div>
    </div>

    <footer class="main-footer">
        <div><h4>NEXUS</h4><p>Sobre nós</p></div>
        <div><h4>JOGOS</h4><p>Novidades</p></div>
        <div><h4>SOCIAL</h4><p>Discord</p></div>
    </footer>
</div>

</body>
</html>