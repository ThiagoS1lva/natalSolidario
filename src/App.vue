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
        <img :src="item.src" :alt="item.alt" />
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
        { src: "./assets/Yasmin.jpg", alt: "Yasmin", text: "Yasmin - Um Brinquedo para bebê" },
        { src: "./assets/Yasmin.jpg", alt: "Yasmin", text: "Yasmin - Um Brinquedo para bebê" },
        { src: "./assets/Yasmin.jpg", alt: "Yasmin", text: "Yasmin - Um Brinquedo para bebê" }
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
  text-align: center;
}

.navbar h1 {
  color: #fff;
  font-size: 1.5rem;
  margin: 0;
}

/* Estilo para a fileira de imagens */
.image-row {
  display: flex;
  justify-content: center;
  gap: 1rem;
}

.image-column {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 150px; /* Define a largura fixa das colunas */
}

.image-column img {
  width: 100%;
  height: auto;
  max-height: 150px; /* Define uma altura máxima para as imagens */
  object-fit: cover; /* Ajusta a imagem para cobrir o espaço, mantendo o centro */
  border-radius: 8px;
}

.image-column p {
  margin-top: 0.5rem;
  text-align: center;
  font-size: 1rem;
}
</style>
