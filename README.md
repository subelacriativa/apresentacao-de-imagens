<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Apresentação de Imagens</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: Arial, sans-serif;
            background-color: #111;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            overflow: hidden;
        }

        /* Container do Carrossel */
        .slideshow-container {
            max-width: 100%;
            max-height: 100vh;
            position: relative;
            margin: auto;
        }

        /* Oculta as imagens por padrão */
        .mySlides {
            display: none;
            text-align: center;
        }

        .mySlides img {
            max-width: 100%;
            max-height: 100vh;
            object-fit: contain;
            animation: fade 1.5s;
        }

        /* Efeito de transição suave (Fade) */
        @keyframes fade {
            from { opacity: .4 } 
            to { opacity: 1 }
        }

        /* Botões de avançar e voltar (Opcional) */
        .prev, .next {
            cursor: pointer;
            position: absolute;
            top: 50%;
            width: auto;
            padding: 16px;
            margin-top: -22px;
            color: white;
            font-weight: bold;
            font-size: 18px;
            transition: 0.6s ease;
            border-radius: 0 3px 3px 0;
            user-select: none;
            background-color: rgba(0,0,0,0.3);
        }

        .prev { left: 0; border-radius: 3px 0 0 3px; }
        .next { right: 0; border-radius: 3px 0 0 3px; }
        .prev:hover, .next:hover { background-color: rgba(0,0,0,0.8); }
    </style>
</head>
<body>

<div class="slideshow-container">

    <div class="mySlides">
        <img src="https://picsum.photos/800/600?random=1" alt="Imagem 1">
    </div>

    <div class="mySlides">
        <img src="https://picsum.photos/800/600?random=2" alt="Imagem 2">
    </div>

    <div class="mySlides">
        <img src="https://picsum.photos/800/600?random=3" alt="Imagem 3">
    </div>

    <a class="prev" onclick="plusSlides(-1)">&#10094;</a>
    <a class="next" onclick="plusSlides(1)">&#10095;</a>
</div>

<script>
    let slideIndex = 0;
    let slideTimeout;
    showSlides();

    // Mudança automática de slides (a cada 3 segundos)
    function showSlides() {
        let i;
        let slides = document.getElementsByClassName("mySlides");
        for (i = 0; i < slides.length; i++) {
            slides[i].style.display = "none";  
        }
        slideIndex++;
        if (slideIndex > slides.length) {slideIndex = 1}    
        slides[slideIndex-1].style.display = "block";  
        slideTimeout = setTimeout(showSlides, 3000); // 3000ms = 3 segundos
    }

    // Controle manual (se o usuário clicar nas setas)
    function plusSlides(n) {
        clearTimeout(slideTimeout); // Para o timer automático para não chocar com o clique
        slideIndex += n - 1;
        
        let slides = document.getElementsByClassName("mySlides");
        if (slideIndex >= slides.length) {slideIndex = 0}
        if (slideIndex < 0) {slideIndex = slides.length - 1}
        
        showSlides();
    }
</script>

</body>
</html>
