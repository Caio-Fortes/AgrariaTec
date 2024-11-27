<template>
    <section id="galeria">
        <div id="containerCapas" ref="containerCapas">
            <div v-for="img in CarrosselContent" :key="img.img" class="images-capas-container">
                <div class="dark-overlay"></div>
                <img :src="'/images/galeria/' + img" />
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
            totalImages: 36,
            CarrosselContent: [
                'IMG (1).jpg',
                'IMG (2).jpg',
                'IMG (3).jpg',
                'IMG (4).jpg',
                'IMG (5).jpg',
                'IMG (7).jpg',
                'IMG (8).jpg',
                'IMG (9).jpg',
                'IMG (10).jpg',
                'IMG (11).jpg',
                'IMG (12).jpg',
                'IMG (13).jpg',
                'IMG (14).jpg',
                'IMG (15).jpg',
                'IMG (16).jpg',
                'IMG (17).jpg',
                'IMG (18).jpg',
                'IMG (19).jpg',
                'IMG (20).jpg',
                'IMG (21).jpg',
                'IMG (22).jpg',
                'IMG (23).jpg',
                'IMG (24).jpg',
                'IMG (25).jpg',
                'IMG (26).jpg',
                'IMG (27).jpg',
                'IMG (28).jpg',
                'IMG (29).jpg',
                'IMG (30).jpg',
                'IMG (31).jpg',
                'IMG (32).jpg'
            ]
        };
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
        }
    }
}
</script>

<style scoped>
#galeria {
    padding: 5% 7% 0% 7%;
    width: 85%;
    height: 80%;
    overflow-x: hidden;
}

#containerCapas {
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

#containerCapas img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
}

#containerCapas::-webkit-scrollbar {
    display: none;
}

.images-capas-container {
    flex: 0 0 100%;
    position: relative;
    scroll-snap-align: start;
    width: 100vw;
    height: 56vw;
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
</style>