<template>
    <section id="inicio">
        <div id="containerCapas" ref="containerCapas">
            <div v-for="capa in CarrosselContent" :key="capa" class="images-capas-container">
                <div class="dark-overlay"></div>
                <img :src="'/images/capas/' + capa.img" />
                <div class="text-overlay">
                    <h2>{{ capa.title }}</h2>
                    <ul>
                        <li class="pWhite">
                            {{ capa.descricao }}
                        </li>
                    </ul>
                </div>
                <div class="container-buttons">
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
            CarrosselContent: [
                { img: 'banner.JPG', title: '', descricao: '' },
                { img: 'trator.jpg', title: '', descricao: '' },
                { img: 'fazenda.jpg', title: '', descricao: '' },
                { img: 'trigo.jpg', title: '', descricao: '' }
            ]
        }
    },
    methods: {
        buttonLeftRight(direction) {
            const container = this.$refs.containerCapas;
            const itemWidth = container.firstElementChild.clientWidth;
            const scrollAmount = itemWidth;

            container.scrollBy({
                left: direction === 'left' ? -scrollAmount : scrollAmount,
                behavior: 'smooth'
            });
        },
    }
}
</script>

<style scoped>
#inicio {
    margin-top: 80px;
    overflow-x: hidden;
}

#containerCapas {
    display: flex;
    overflow-x: scroll;
    scroll-snap-type: x mandatory;
    width: 100%;
    scroll-behavior: smooth;
    max-height: 56vw;
    overflow-y: hidden;
    gap: 0;
    flex-direction: row;
    align-items: center;
    margin-bottom: 2rem;
}

#containerCapas::-webkit-scrollbar {
    display: none;
}

.images-capas-container {
    flex: 0 0 100%;
    position: relative;
    scroll-snap-align: start;
}

.text-overlay {
    position: absolute;
    top: 10%;
    left: 4rem;
    z-index: 2;
    color: white;
    text-shadow: 0 2px 4px rgba(0, 0, 0, 0.8);
}

.container-buttons {
    position: absolute;
    top: 50%;
    left: 0;
    right: 0;
    transform: translateY(-50%);
    display: flex;
    justify-content: space-between;
    padding: 0 10px;
    z-index: 10;
}

@media (max-width: 500px) {
    .buttons-carrossel {
        background-color: rgba(0, 0, 0, 0.5);
        color: #fff;
        border: none;
        cursor: pointer;
        font-size: 15px;
        padding: 8px;
        border-radius: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
        z-index: 10;
        width: 25px;
        height: 25px;
        cursor: pointer;
        margin: 20px;
    }
}

@media (min-width: 500px) {
    .buttons-carrossel {
        background-color: rgba(0, 0, 0, 0.5);
        color: #fff;
        border: none;
        cursor: pointer;
        font-size: 24px;
        padding: 8px;
        border-radius: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
        z-index: 10;
        width: 45px;
        height: 45px;
        cursor: pointer;
        margin: 20px;
    }
}

#containerCapas img {
    width: 100%;
    height: auto;
    display: block;
}
</style>
