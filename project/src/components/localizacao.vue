<script>
export default {
    mounted(){
        this.initMap();
    },
    methods:{
        initMap(){
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
    <div id="mapClientes" style="height: 400px; width: 100%; z-index: 0"></div>
</template>
