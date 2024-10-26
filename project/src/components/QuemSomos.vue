<template>
    <section>
        <div class="container-image-text-default">
            <div class="text-right">
                <h1 class="title-component">Quem Somos</h1>
                <h4 class="subtitle-component">O espaço para inovação e informação.</h4>
                <p class="responsive-text">
                    O AgrariaTec é um amplo e agradável espaço de integração de vários segmentos
                    que compõem e integram: Informação, inovação, produtos e serviços de diversos
                    segmentos empresariais do agronegócio brasileiro, principalmente aqueles
                    inseridos nos conceitos atuais da agricultura conectada, onde mais do que ter
                    vontade de inovar, é preciso que a inovação faça sentido.
                </p>
                <p class="responsive-text">
                    Porque era necessário, em nossa região, um evento do agronegócio brasileiro
                    caracterizado pela inovação e difusão tecnológica de máquinas e produtos agrícolas.
                </p>
                <p class="responsive-text">
                    Porque devemos estar conectados a essa aceleração abrupta na revolução agro 4.0,
                    com aderência cada vez maior de tecnologias dentro e fora do campo de produção.
                </p>
            </div>
            <div class="images-left">
                <img :src="images[currentIndex]" :class="['img-radius', { fade: fading }]" />
                <div class="carousel-indicators">
                    <span v-for="(image, index) in images" :key="index" :class="{ active: index === currentIndex }"
                        @click="goToSlide(index)">
                    </span>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    data() {
        return {
            images: [
                "/images/plantacao.jpg",
                "/images/plantas.jpg",
                "/images/agronoma.jpg",
                "/images/fazendeiro.jpg",
            ],
            currentIndex: 0,
            fading: false,
        };
    },
    methods: {
        goToSlide(index) {
            this.fading = true;
            setTimeout(() => {
                this.currentIndex = index;
                this.fading = false;
            }, 500);
        },
        nextSlide() {
            const nextIndex = (this.currentIndex + 1) % this.images.length;
            this.goToSlide(nextIndex);
        },
        prevSlide() {
            const prevIndex = (this.currentIndex - 1 + this.images.length) % this.images.length;
            this.goToSlide(prevIndex);
        },
    },
    mounted() {
        setInterval(() => {
            this.nextSlide();
        }, 4000);
    },
};
</script>

<style scoped>
@media (max-width: 900px) {
    .container-image-text-default {
        display: flex;
        margin: 0px 40px;
        position: relative;
        height: 50vw;
        min-height: 300px;
        flex-direction: column;
    }

    .images-left {
        width: 100%;
        height: 100%;
        margin-top: 15px;
    }

    .title-component{
        font-size: 8vw;
    }

    .subtitle-component {
        font-size: 5vw;
        line-height: 1.5;
    }

    .responsive-text {
        font-size: 3.5vw;
        line-height: 1.5;
    }

}

@media (min-width: 900px) {
    .container-image-text-default {
        display: flex;
        margin: 30px 40px;
        position: relative;
        height: 50vw;
        min-height: 300px;
        gap: 6rem;
        flex-direction: row-reverse;
    }

    .images-left,
    .text-right {
        width: 45%;
        height: 100%;
    }

    .title-component{
        margin-top: 1rem;
        font-size: 4vw;
    }

    .subtitle-component {
        font-size: 2.3vw;
        line-height: 1.5;
    }

    .responsive-text {
        font-size: 1.5vw;
        line-height: 1.5;
    }

}

.img-radius {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 10px;
    transition: opacity 1s ease-in-out, filter 1s ease-in-out;
}

.img-radius.fade {
    opacity: 0;
    filter: blur(8px);
}

.carousel-indicators {
    display: flex;
    justify-content: center;
    margin-top: 10px;
}

.carousel-indicators span {
    height: 12px;
    width: 12px;
    background-color: #bbb;
    border-radius: 50%;
    display: inline-block;
    margin: 0 5px;
    cursor: pointer;
    transition: background-color 0.3s;
}

.carousel-indicators .active {
    background-color: #333;
}
</style>
