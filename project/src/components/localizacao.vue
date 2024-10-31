<script>
export default {
    mounted() {
        this.initMap();
    },
    methods: {
        initMap() {
            // Define as coordenadas da ExpoLavras em Lavras, MG e o zoom desejado
            const expoLavrasCoordinates = [-21.26790240369815, -44.98225650601228];
            const zoomLevel = 15;  // Ajuste conforme necessário

            // Inicializa o mapa com a localização e o zoom configurados
            this.map = L.map('mapClientes').setView(expoLavrasCoordinates, zoomLevel);
            L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
                attribution: '&copy; OpenStreetMap contributors'
            }).addTo(this.map);

            // Adiciona o ponto (marcador) na localização da ExpoLavras
            L.marker(expoLavrasCoordinates)
                .addTo(this.map)
                .bindPopup("ExpoLavras")
                .openPopup(); // Abre o popup automaticamente
        },
    }
};
</script>

<template>
    <section id="localizacao">
        <h1 class="title-component" style="text-align: center">Localização do Evento</h1>
        <p class="title-component" style="text-align: center">
            <i class="fa-solid fa-location-dot" style="margin-right: 10px;"></i> 
            1252, R. A, 1190 - Aeroporto, Lavras - MG, 37200-000
        </p>
        <div id="container">
            <div id="mapClientes" style="height: 400px; width: 100%; z-index: 0"></div>
        </div>
    </section>
</template>


<style scoped>
#localizacao {
    padding: 5% 10% 0% 10%;
    width: 80%;
    height: 80%;
    overflow-x: hidden;
}

#container {
    display: flex;
    overflow-x: scroll;
    scroll-snap-type: x mandatory;
    width: 100%;
    scroll-behavior: smooth;
    max-height: 29vw;
    overflow-y: hidden;
    gap: 0;
    flex-direction: row;
    align-items: center;
    margin-bottom: 2rem;
    object-fit: cover;
    border-radius: 10px;
}

#container img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
}

#container::-webkit-scrollbar {
    display: none;
}
</style>