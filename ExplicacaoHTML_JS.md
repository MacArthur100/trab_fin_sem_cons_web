<!DOCTYPE html> <!-- Declara o tipo de documento HTML5 -->
<html lang="pt-br"> <!-- Define o idioma da página como português do Brasil -->
<head> <!-- Início do cabeçalho do documento -->
  <meta charset="UTF-8"> <!-- Define a codificação de caracteres como UTF-8 -->
  <meta name="viewport" content="width=device-width, initial-scale=1.0"> <!-- Faz o site se ajustar a diferentes tamanhos de tela -->
  <title>index</title> <!-- Título da aba do navegador -->
  <link rel="stylesheet" href="css/style.css"> <!-- Conecta o arquivo CSS externo -->
  <style> /* Início do CSS interno */
    #quadrado { /* Seleciona o elemento com id "quadrado" */
      width: 50px; /* Largura do quadrado */
      height: 50px; /* Altura do quadrado */
      background: orange; /* Cor de fundo laranja */
      position: absolute; /* Posição absoluta na tela */
      left: 10px; /* Distância inicial da esquerda */
      top: 5px; /* Distância inicial do topo */
      transition: background 0.3s, border-radius 0.3s; /* Transição suave para cor e bordas */
      z-index: 1000; /* Fica acima dos outros elementos */
    }
  </style> <!-- Fim do CSS interno -->
</head> <!-- Fim do cabeçalho -->

<body> <!-- Início do corpo da página -->
  <nav> <!-- Início do menu de navegação -->
    <ul> <!-- Lista não ordenada -->
      <li><a href="index.html">Home</a></li> <!-- Link para a página inicial -->
      <li><a href="formulario.html">Formulário</a></li> <!-- Link para o formulário -->
      <li><a href="servicos.html">Serviços</a></li> <!-- Link para serviços -->
      <li><a href="orcamento.html">Orçamento</a></li> <!-- Link para orçamento -->
      <li><a href="login.html">Login</a></li> <!-- Link para login -->
      <li><a href="sobre-nos.html">Sobre Nós</a></li> <!-- Link para página sobre nós -->
    </ul>
  </nav> <!-- Fim da navegação -->

  <header> <!-- Cabeçalho principal do site -->
    <img src="img/faça sua empresa decolar na internet.png" alt="banner do Site" class="banner"> <!-- Banner principal -->
  </header>

  <img src="img/foguete (1).png" id="foguete" alt="Foguete"> <!-- Imagem do foguete que será animado -->

  <section class="video"> <!-- Seção com vídeo -->
    <h2>Nosso Vídeo</h2> <!-- Título da seção -->
    <video controls width="600"> <!-- Elemento de vídeo com controles -->
      <source src="video/VIDEO TRFABALHO FINAL PRIMEIRO SEMESTRE.mp4" type="video/mp4"> <!-- Fonte do vídeo -->
    </video>
  </section>

  <section class="colunas"> <!-- Seção com duas colunas de conteúdo -->
    <div class="coluna"> <!-- Primeira coluna -->
      <h3>Identidade Visual Personalizada para Empresas</h3> <!-- Título -->
      <p>Criação de Identidades Visuais Exclusivas...</p> <!-- Texto explicativo -->
    </div>
    <div class="coluna"> <!-- Segunda coluna -->
      <h3>Soluções Criativas para Marcas Inesquecíveis</h3>
      <p>Loja de Produtos Personalizados e Branding...</p>
    </div>
  </section>

  <div class="carrossel-container"> <!-- Contêiner do carrossel de imagens -->
    <input type="radio" name="carrossel" id="slide1" checked> <!-- Botão de rádio para o slide 1 -->
    <input type="radio" name="carrossel" id="slide2"> <!-- Slide 2 -->
    <input type="radio" name="carrossel" id="slide3"> <!-- Slide 3 -->

    <div class="slides"> <!-- Área que contém as imagens -->
        <div class="carrossel-slide" id="img1">
            <img src="img/Instagram post de gestão empresarial corporativo azul (800 x 400 px).png" alt="Imagem 1"> <!-- Primeira imagem -->
        </div>
        <div class="carrossel-slide" id="img2">
            <img src="img/é caro contratar um site.png" alt="Imagem 2"> <!-- Segunda imagem -->
        </div>
        <div class="carrossel-slide" id="img3">
            <img src="img/os melhores sites do país (1600 x 800 px).png" alt="Imagem 3"> <!-- Terceira imagem -->
        </div>
    </div>

    <div class="navegacao"> <!-- Pontos de navegação do carrossel -->
        <label for="slide1" class="nav-btn"></label> <!-- Botão que ativa o slide 1 -->
        <label for="slide2" class="nav-btn"></label> <!-- Botão que ativa o slide 2 -->
        <label for="slide3" class="nav-btn"></label> <!-- Botão que ativa o slide 3 -->
    </div>
  </div>

  <footer> <!-- Rodapé do site -->
    <p>Contato: (19)99746 9752</p> <!-- Telefone -->
    <p>Email: contato@sitedominium.site</p> <!-- E-mail -->
    <p>Endereço: Rua Coronel José Pereira Lima, 1029 Mococa-SP</p> <!-- Endereço físico -->
  </footer>

  <script> // Início do script em JavaScript
    const foguete = document.getElementById("foguete"); // Pega o elemento do foguete pelo ID

    const largura = window.innerWidth; // Captura a largura da tela
    const altura = window.innerHeight; // Captura a altura da tela

    const centroX = largura / 2; // Define o centro X da tela
    const centroY = altura / 2; // Define o centro Y da tela
    const raioX = largura / 2 - 100; // Define o raio horizontal da elipse
    const raioY = altura / 2 - 100; // Define o raio vertical da elipse

    let angulo = 0; // Começa o ângulo da rotação do foguete em 0

    foguete.style.position = "absolute"; // Define posição absoluta
    foguete.style.width = "400px"; // Largura do foguete
    foguete.style.height = "auto"; // Altura automática
    foguete.style.zIndex = "1000"; // Fica sobre outros elementos

    function animarFoguete() { // Função que anima o movimento do foguete
      const x = centroX + raioX * Math.cos(angulo); // Calcula a posição X com base no ângulo
      const y = centroY + raioY * Math.sin(angulo); // Calcula a posição Y com base no ângulo

      foguete.style.left = x + "px"; // Atualiza a posição horizontal
      foguete.style.top = y + "px"; // Atualiza a posição vertical
      foguete.style.transform = "translate(-50%, -50%)"; // Centraliza o foguete no ponto

      angulo += 0.01; // Aumenta o ângulo para continuar o movimento

      if (angulo > 2 * Math.PI) { // Se o ângulo ultrapassar 360 graus
        angulo = 0; // Reinicia a rotação
      }

      requestAnimationFrame(animarFoguete); // Chama a função novamente para continuar a animação
    }

    animarFoguete(); // Inicia a animação do foguete
  </script>
</body>
</html>
