<template>
    <section id="inicio">
        <div id="containerCapas" ref="containerCapas">
            <div v-for="capa in imgCapas" :key="capa" class="images-capas-container">
                <img :src="'/images/capas/'+capa" />
                <div class="dark-overlay"></div>
                <div id="containerButtons">
                    <button @click="buttonLeftRight('left')" class="buttons-carrossel">
                        <i class="fa-solid fa-angle-left"></i>   
                    </button>
                    <button @click="buttonLeftRight('right')" class="buttons-carrossel">
                        <i class="fa-solid fa-angle-right"></i>
                    </button>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    data() {
        return {
            imgCapas: ['banner.JPG', 'trator.jpg', 'fazenda.jpg', 'trigo.jpg']
        }
    },
    methods: {
        buttonLeftRight(buttonSelected){
            const container = this.$refs.containerCapas;
            const width = container.clientWidth;
            buttonSelected === 'left' ? container.scrollLeft -= width + 12
            : container.scrollLeft += width + 20;
        },
    }
}
</script>
