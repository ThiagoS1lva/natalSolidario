<template>
  <div>
    <nav class="navbar">
      <h1>Natal Solidário</h1>
    </nav>
    <div class="video-container">
      <video controls width="420" height="600">
        <source src="./assets/video1.mp4" type="video/mp4" />
        Seu navegador não suporta o elemento de vídeo.
      </video>
    </div>
    <div style="margin-bottom: 2em; width: 100%;">
      <h2 style="text-align: center;"> Só clicar na criança que você gostaria de apadrinhar! </h2>
    </div>
    <div class="image-row">
      <div class="image-column" v-for="(item, index) in images" :key="index">
        <a :href="`https://api.whatsapp.com/send?phone=5522999330628&text=Eu%20quero%20apadrinhar%3A%20${item.alt}`"><img :src="item.src" :alt="item.alt" /></a>
        <p>{{ item.text }}</p>
      </div>
    </div>
    <div class="footer">
      <p>Feliz natal!</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      images: [
      { src: "/Maria Alice.jpg", alt: "Maria Alice", text: "Maria Alice - Maquiagem, boneca reborn ou caderno de desenho com canetinha e lapis de cor!" },
      { src: "/Jhonatan.jpg", alt: "Jhonatan", text: "Jhonatan - (Apadrinhado)" },
      { src: "/Yasmin.jpg", alt: "Yasmin", text: "Yasmin - Um Brinquedo para bebê!" },
      { src: "/Anna Vallentyna.png", alt: "Anna Vallentyna", text: "Anna Vallentyna - (Apadrinhada)" },
      { src: "/b1.jpg", alt: "b1", text: "Umas roupinhas ou um brinquedo!" },
      { src: "/Mellynda.png", alt: "Mellynda", text: "Mellynda - (Apadrinhada)" },
      { src: "/Ravi.jpg", alt: "Ravi", text: "Ravi - Brinquedos de animais de fazenda!" },
      { src: "/Hevellyn.jpg", alt: "Hevellyn", text: "Hevellyn - Maquiagem!" },
      { src: "/Sophya.jpg", alt: "Sophya", text: "Sophya - Boneca!" },
        { src: "/Levi.jpg", alt: "Levi", text: "Levi - Meu sonho é ganhar uma bicicleta ou roupas!" },
        { src: "/AnnaLiz.png", alt: "Anna Liz", text: "Anna Liz - Brinquedo ou roupa de 3 anos veste 2 anos(18-24)!" },
        { src: "/Fernanda.jpg", alt: "Fernanda", text: "Fernanda - Uma bermuda tamanho 42 infantil ou kit maquiagem!" },
        { src: "/Gael.jpg", alt: "Gael", text: "Gael - Um cavalo de brinquedo!" },
        { src: "/JoaoLucas.png", alt: "João Lucas", text: "João Lucas - Tenho 10 anos e gostaria de uma roupa!" },
        { src: "/Victor Hugo.jpg", alt: "Victor Hugo", text: "Victor Hugo - Uma moto de brinquedo da grande!" },
        { src: "/Pietro.jpg", alt: "Pietro", text: "Pietro - Um boneco do homem aranha!" },
        { src: "/Julia.jpg", alt: "Julia", text: "Julia - Roupa 38, short ou blusa!" },
        { src: "/Giovanna.jpg", alt: "Giovanna", text: "Giovanna - Papete com brilho 37/38 ou roupa 14 anos!" },
        { src: "/Maria Tereza.png", alt: "Maria Tereza", text: "Maria Tereza - (Apadrinhada)!" },
        { src: "/Raquelly.jpg", alt: "Raquelly", text: "Raquelly - Conjunto Lilo & Stitch!" },
        { src: "/Rodolfo.jpg", alt: "Rodolfo", text: "Rodolfo - Uma roupa da Nike!" },
        { src: "/Rafael.jpg", alt: "Rafael", text: "Rafael - Uma bola!" },
        { src: "/Clarice.jpg", alt: "Clarice", text: "Clarice - Um relógio e brincos!" },
        { src: "/Alana.jpg", alt: "Alana", text: "Alana - Boneca!" },
        { src: "/Maria Eduarda.jpg", alt: "Maria Eduarda", text: "Maria Eduarda - Roupas tamanho 36 ou sandália tamanho 37!" },
        { src: "/Lavynia.jpg", alt: "Lavynia", text: "Lavynia - Uma bicicleta!" }
      ]
    };
  }
};
</script>

<style scoped>
.footer {
  background-color: #ff4d4d;
  color: #fff;
  text-align: center;
  padding: 1rem;
}
.footer p {
  font-size: 1.5em;
}

/* Centraliza o contêiner e ajusta o tamanho do vídeo */
.video-container {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 2rem; /* espaço entre o vídeo e a fileira de imagens */
}

video {
  width: 220px;
  height: 400px;
  border-radius: 8px;
}

/* Estilo da barra de navegação */
.navbar {
  background-color: #ff4d4d; /* cor de fundo */
  padding: 1rem;
  width: 100vw;
  text-align: center;
}

.navbar h1 {
  color: #fff;
  font-size: 2rem;
  margin: 0;
}

/* Estilo para a fileira de imagens */
.image-row {
  display: grid;
  grid-template-columns: repeat(3, 1fr); /* 3 colunas em telas maiores */
  gap: 1rem;
  justify-items: center;
}

.image-column {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 200px; /* Define a largura fixa das colunas */
}

.image-column img {
  width: 200px;
  height: auto;
  max-height: 250px; /* Define uma altura máxima para as imagens */
  object-fit: cover; /* Ajusta a imagem para cobrir o espaço, mantendo o centro */
  border-radius: 8px;
}

.image-column p {
  margin-top: 0.5rem;
  text-align: center;
  font-size: 1.2rem;
}

/* Responsividade para telas menores */
@media (max-width: 768px) {
  .image-row {
    grid-template-columns: 1fr; /* Altera para uma coluna */
  }
  
  .video-container video {
    width: 90%; /* Ajusta o vídeo para a largura completa em dispositivos móveis */
    height: auto;
  }
}
</style>
