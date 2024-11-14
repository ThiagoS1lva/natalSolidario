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
    <div class="image-row">
      <div class="image-column" v-for="(item, index) in images" :key="index">
        <a :href="`https://api.whatsapp.com/send?phone=5522999330628&text=Eu%20quero%20apadrinhar%3A%20${item.alt}`"><img :src="item.src" :alt="item.alt" /></a>
        <p>{{ item.text }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      images: [
        { src: "/Yasmin.jpg", alt: "Yasmin", text: "Yasmin - Um Brinquedo para bebê" },
        { src: "/Levi.jpg", alt: "Levi", text: "Levi - Meu sonho é ganhar uma bicicleta ou roupas" },
        { src: "/AnnaLiz.png", alt: "Anna Liz", text: "Yasmin - Um Brinquedo para bebê" },
        { src: "/Levi.jpg", alt: "Levi", text: "Levi - Meu sonho é ganhar uma bicicleta ou roupas" }
      ]
    };
  }
};
</script>

<style scoped>
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
    width: 100%; /* Ajusta o vídeo para a largura completa em dispositivos móveis */
    height: auto;
  }
}
</style>
