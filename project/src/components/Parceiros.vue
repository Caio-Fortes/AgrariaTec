<template>
  <section id="parceiros">
    <div class="partners-section">
      <h1 class="title-component">Parceiros</h1>
      <div class="partners-container">
        <div class="partner" v-for="partner in partners" :key="partner.id">
          <img :src="partner.logo" :alt="partner.name" />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      partners: [
        { id: 3, name: 'Ufla', logo: '/images/parceiros/ufla_logo.png' },
        { id: 4, name: 'Epamig', logo: '/images/parceiros/epamig_logo.png' },
        { id: 2, name: 'Sebrae', logo: '/images/parceiros/sebrae_logo.png' },
        { id: 5, name: 'Emater Minas Gerais', logo: '/images/parceiros/emater_logo.png' },
        { id: 6, name: 'Faemg', logo: '/images/parceiros/sindicato.jpg' },
        { id: 7, name: 'Faemg', logo: '/images/parceiros/faemgsenar.png' },
        { id: 1, name: 'Governo Lavras', logo: 'https://lavras.mg.gov.br/wp-content/uploads/elementor/thumbs/logo_pml_verde-qczrd0ucpxfzc45ljwouon5oqy6asi1klgp8rdsp3u.png' },
      ]
    };
  }
};
</script>

<style scoped>
.title-component {
  font-size: 8vw;
  margin-top: 0px;
}

.partner img {
  max-width: 100%;
  height: auto;
  width: auto;
  max-height: 70px;
  object-fit: contain;
}

.partners-section {
  text-align: center;
  padding: 20px;
}

.partners-title {
  font-size: 24px;
  margin-bottom: 20px;
}

.partners-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 2rem;
}

.partner {
  flex: 1 1 calc(33.333% - 20px);
  max-width: calc(33.333% - 20px);
  display: flex;
  justify-content: center;
}

@media (max-width: 900px) {
  .title-component {
    font-size: 8vw;
    margin: 5rem;
  }
}

@media (min-width: 900px) {
  .title-component {
    margin: 7rem;
    font-size: 3vw;
  }
}

@media (max-width: 768px) {
  .partner {
    flex: 1 1 calc(50% - 20px);
    max-width: calc(50% - 20px);
  }

  .partner img {
    width: 120px;
  }
}

@media (max-width: 480px) {
  .partner {
    flex: 1 1 100%;
    max-width: 100%;
  }

  .partner img {
    width: 100px;
  }
}
</style>