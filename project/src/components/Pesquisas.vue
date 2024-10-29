<template>
    <section id="impacto-aprovacao">
        <div class="container-image-text-default">
            <div class="text-right">
                <h1 class="title-component">Impacto e Aprovação</h1>
                <h4 class="subtitle-component">Os números que comprovam o impacto da nossa primeira edição.</h4>
                <ul>
                    <li class="list-style">
                        <p class="responsive-text">
                            Presença de quase <strong>20 cidades</strong> 
                            e <strong> de 1500 pessoas. </strong>
                        </p>
                    </li>
                    <li class="list-style">
                        <p class="responsive-text">
                            Como avalia a organização? <br />
                            <strong>95%,3</strong> de Aprovação
                        </p>
                    </li>
                    <li class="list-style">
                        <p class="responsive-text">
                            Como avalia a estrutura? <br />
                            <strong>98%,2</strong> de Aprovação
                        </p>
                    </li>
                    <li class="list-style">
                        <p class="responsive-text">
                            Como avalia a presença de empresas? <br />
                            <strong>91%,6</strong> de Aprovação
                        </p>
                    </li>
                    <li class="list-style">
                        <p class="responsive-text">
                            Indicaria o evento para uma empresa parceira? <br />
                            <strong>98%,1</strong> de sim
                        </p>
                    </li>
                    <li class="list-style">
                        <p class="responsive-text">
                            Voltaria em uma próxima edição? <br />
                            <strong>100%</strong> de sim
                        </p>
                    </li>
                </ul>
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
                "/images/impacto1.jpg",
                "/images/impacto3.jpg",
                "/images/impacto2.jpg",
            ],
            currentIndex: 0,
            fading: false,
            intervalId: null,
        };
    },
    methods: {
        goToSlide(index) {
            this.fading = true;
            setTimeout(() => {
                this.currentIndex = index;
                this.fading = false;

                clearInterval(this.intervalId);
                this.startAutoSlide();
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
        startAutoSlide() {
            this.intervalId = setInterval(() => {
                this.nextSlide();
            }, 4000);
        },
    },
    mounted() {
        this.startAutoSlide();
    },
    beforeDestroy() {
        clearInterval(this.intervalId);
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
        display: inline-block;
    }

    .images-left {
        width: 100%;
        height: 100%;
        margin-top: 15px;
    }

    .title-component {
        font-size: 8vw;
        margin-top: 0px;
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

    .title-component {
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

.list-style{
    list-style-type: disclosure-closed;
    font-family: "bold";
    color: #ffcc00;
}
</style>
