<template>
    <section id="galeria">
        <div id="containerCapas" ref="containerCapas">
            <div v-for="img in CarrosselContent" :key="img.img" class="images-capas-container">
                <div class="dark-overlay"></div>
                <img :src="'/images/galeria/' + img.img" />
                <div class="text-overlay">
                    <h2>{{ img.title }}</h2>
                    <ul>
                        <li class="pWhite">
                            {{ img.descricao }}
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
            totalImages: 37,
            CarrosselContent: []
        };
    },
    async mounted() {
        await this.populateCarrosselContent();
    },
    methods: {
        async populateCarrosselContent() {
            const imagePromises = [];

            for (let i = 1; i <= this.totalImages; i++) {
                // Importando as imagens dinamicamente
                imagePromises.push(
                    import(`@/assets/images/galeria/IMG (${i}).jpg`)
                        .then((img) => ({
                            img: `IMG (${i}).jpg`,
                            imgPath: img.default, 
                            title: '',
                            descricao: ''
                        }))
                        .catch(() => ({
                            img: `IMG (${i}).jpg`,
                            imgPath: null,
                            title: '',
                            descricao: ''
                        }))
                );
            }

            this.CarrosselContent = await Promise.all(imagePromises);
        },
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
    padding: 5% 10% 0% 10%;
    width: 80%;
    height: 80%;
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