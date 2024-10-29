<template>
    <div class="partners-section">
      <h2 class="partners-title">Parceiros</h2>
      <div class="partners-container">
        <div class="partner" v-for="partner in partners" :key="partner.id">
          <img :src="partner.logo" :alt="partner.name" />
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        partners: [
          { id: 1, name: 'Governo Lavras', logo: '/images/parceiros/governo_logo.png' },
          { id: 2, name: 'Sebrae', logo: '/images/parceiros/sebrae_logo.png' },
          { id: 3, name: 'Emater Minas Gerais', logo: '/images/parceiros/emater_logo.png' },
          { id: 4, name: 'Ufla', logo: '/images/parceiros/ufla_logo.png' },
          { id: 5, name: 'Epamig', logo: '/images/parceiros/epamig_logo.png' },
          { id: 6, name: 'Faemg', logo: '/images/parceiros/faemg_logo.png' }
        ]
      };
    }
  };
  </script>
  
  <style scoped>
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
    gap: 20px; 
  }
  
  .partner {
    flex: 1 1 calc(33.333% - 20px); 
    max-width: calc(33.333% - 20px);
    display: flex;
    justify-content: center;
  }
  
  .partner img {
    max-width: 100%;
    height: auto;
    width: 150px;
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
  