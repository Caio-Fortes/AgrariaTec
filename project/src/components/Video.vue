<template>
    <section id="quem-somos">
        <div class="container-image-text-default">
            <div class="text-right">
                <h2 class="title-component">AgrariaTec</h2>
                <p class="responsive-text">
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse eget justo purus. Vivamus
                    pellentesque rutrum nunc, eu vestibulum felis condimentum et. Praesent vel nisl vitae ligula
                    pellentesque ultrices at et tortor.
                </p>
            </div>
            <div class="images-left">
                <iframe ref="video" :src="videoUrl" frameborder="0" allowfullscreen></iframe>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    data() {
        return {
            videoLink: 'https://www.youtube.com/watch?v=vPVO9Rq0gvQ',
        };
    },
    computed: {
        videoUrl() {
            const videoId = this.extractVideoId(this.videoLink);
            return `https://www.youtube.com/embed/${videoId}`;
        }
    },
    methods: {
        extractVideoId(link) {
            const regex = /(?:https?:\/\/)?(?:www\.)?(?:youtube\.com\/(?:[^\/\n\s]+\/\S+\/|(?:v|e(?:mbed)?)\/|.*[?&]v=)|youtu\.be\/)([^&\n]{11})/;
            const match = link.match(regex);
            return match ? match[1] : null;
        },
    }
};
</script>

<style scoped>
@media (max-width: 900px) {
    .container-image-text-default {
        display: flex;
        margin: 0px 40px;
        position: relative;
        height: 20vw;
        min-height: 300px;
        flex-direction: column;
        display: inline-block;
    }

    .images-left {
        width: 100%;
        height: 100%;
        margin-top: 15px;
    }

    .images-left iframe {
        width: 100%;
        height: 100%;
        border-radius: 10px;
        margin-bottom: 1rem;
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
        height: 20vw;
        min-height: 300px;
        gap: 6rem;
        flex-direction: row-reverse;
    }

    .images-left,
    .text-right {
        width: 45%;
        height: 100%;
    }

    .images-left iframe {
        width: 100%;
        height: 100%;
        border-radius: 10px;
        margin-bottom: 1rem;
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
</style>
