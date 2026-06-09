<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Feliz Dia dos Pais! ❤️</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Segoe UI', Arial, sans-serif;
            /* Fundo festivo com degradê moderno e padrão geométrico de festa */
            background-color: #1a2a6c;
            background-image: 
                radial-gradient(circle at 20% 30%, rgba(241, 196, 15, 0.15) 1px, transparent 1px),
                radial-gradient(circle at 75% 60%, rgba(231, 76, 60, 0.15) 2px, transparent 2px),
                linear-gradient(135deg, #1a2a6c, #275d8c, #b21f1f);
            background-size: 40px 40px, 60px 60px, 100% 100%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            overflow: hidden;
            color: #fff;
            padding: 20px;
        }

        /* Cabeçalho Festivo */
        .header-container {
            text-align: center;
            margin-bottom: 25px;
            animation: bounceIn 1.2s ease;
            z-index: 10;
        }

        .header-container h1 {
            font-size: 2.2rem;
            font-weight: 800;
            text-shadow: 2px 2px 8px rgba(0, 0, 0, 0.5);
            letter-spacing: 1px;
        }

        .header-container p {
            font-size: 1.1rem;
            opacity: 0.9;
            margin-top: 5px;
            font-style: italic;
            text-shadow: 1px 1px 4px rgba(0, 0, 0, 0.4);
        }

        /* Ícones decorativos flutuantes */
        .decor {
            font-size: 24px;
            display: inline-block;
            margin: 0 8px;
            animation: pulse 2s infinite alternate;
        }

        /* Container do Carrossel */
        .slideshow-container {
            width: 100%;
            max-width: 650px;
            position: relative;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(8px);
            -webkit-backdrop-filter: blur(8px);
            border-radius: 20px;
            padding: 15px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.4);
            border: 2px solid rgba(255, 255, 255, 0.2);
            animation: fadeInUp 1s ease;
        }

        /* Oculta as imagens por padrão */
        .mySlides {
            display: none;
            text-align: center;
        }

        .mySlides img {
            width: 100%;
            max-height: 60vh;
            object-fit: cover;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
            animation: fade 1s;
        }

        /* Efeitos de transição e animação */
        @keyframes fade {
            from { opacity: 0.5; transform: scale(0.98); } 
            to { opacity: 1; transform: scale(1); }
        }

        @keyframes bounceIn {
            0% { opacity: 0; transform: translateY(-30px); }
            70% { transform: translateY(5px); }
            100% { opacity: 1; transform: translateY(0); }
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes pulse {
            from { transform: scale(1); }
            to { transform: scale(1.15); }
        }

        /* Botões de avançar e voltar estilizados */
        .prev, .next {
            cursor: pointer;
            position: absolute;
            top: 50%;
            width: 45px;
            height: 45px;
            margin-top: -22px;
            color: white;
            font-weight: bold;
            font-size: 20px;
            transition: 0.3s ease;
            border-radius: 50%;
            user-select: none;
            background-color: rgba(0, 0, 0, 0.4);
            border: 1px solid rgba(255, 255, 255, 0.3);
            display: flex;
            justify-content: center;
            align-items: center;
            text-decoration: none;
        }

        .prev { left: 25px; }
        .next { right: 25px; }
        .prev:hover, .next:hover { 
            background-color: #f1c40f; 
            color: #111;
            transform: scale(1.1);
            border-color: #f1c40f;
        }

        /* Rodapé carinhoso */
        .footer-note {
            margin-top: 25px;
            font-size: 0.9rem;
            opacity: 0.8;
            text-align: center;
            z-index: 10;
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.5);
        }
    </style>
</head>
<body>

<div class="header-container">
    <h1><span class="decor">👔</span>Feliz Dia dos Pais!<span class="decor">👨🏻‍💼</span></h1>
    <p>Com todo o meu amor, ontem, hoje e sempre.</p>
</div>

<div class="slideshow-container">

    <div class="mySlides">
        <img src="https://picsum.photos/800/600?random=1" alt="Nossa Memória 1">
    </div>

    <div class="mySlides">
        <img src="https://picsum.photos/800/600?random=2" alt="Nossa Memória 2">
    </div>

    <div class="mySlides">
        <img src="https://picsum.photos/800/600?random=3" alt="Nossa Memória 3">
    </div>

    <a class="prev" onclick="plusSlides(-1)">&#10094;</a>
    <a class="next" onclick="plusSlides(1)">&#10095;</a>
</div>

<div class="footer-note">
    <p>Feito especialmente para o melhor pai do mundo. ❤️</p>
</div>

<script>
    let slideIndex = 0;
    let slideTimeout;
    
    showSlides();

    function showSlides() {
        let i;
        let slides = document.getElementsByClassName("mySlides");
        
        for (i = 0; i < slides.length; i++) {
            slides[i].style.display = "none";  
        }
        
        slideIndex++;
        
        if (slideIndex > slides.length) {
            slideIndex = 1;
        }    
        
        slides[slideIndex - 1].style.display = "block";  
        slideTimeout = setTimeout(showSlides, 4000); 
    }

    function plusSlides(n) {
        clearTimeout(slideTimeout); 
        slideIndex += (n - 1);
        
        let slides = document.getElementsByClassName("mySlides");
        
        if (slideIndex < 0) {
            slideIndex = slides.length - 1;
        } else if (slideIndex >= slides.length) {
            slideIndex = 0;
        }
        
        showSlides();
    }
</script>

</body>
</html>
