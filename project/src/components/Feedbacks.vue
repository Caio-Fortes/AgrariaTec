<template>
    <section id="feedback-carousel">
        <div id="containerFeedbacks" ref="containerFeedbacks">
            <div v-for="feedback in feedbacks" :key="feedback.id" class="feedback-item">
                <div class="feedback-content">
                    <p class="testimonial">"{{ feedback.text }}"</p>
                    <div class="person-details">
                        <img v-if="feedback.photo" :src="feedback.photo" alt="Photo" class="photo" />
                        <div>
                            <p class="name">{{ feedback.name }}</p>
                            <p class="carrer">{{ feedback.carrer }}</p>
                        </div>
                    </div>
                </div>
            </div>
            <div class="container-buttons">
                <button @click="buttonLeftRight('left')" class="buttons-carrossel-feedback">
                    <i class="fa-solid fa-angle-left"></i>
                </button>
                <button @click="buttonLeftRight('right')" class="buttons-carrossel-feedback">
                    <i class="fa-solid fa-angle-right"></i>
                </button>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    data() {
        return {
            feedbacks: [
                {
                    id: 1, text: `Ficamos muitos satisfeitos, com a visibilidade que esse evento trouxe 
                    para a nossa cidade e principalmente colocando Lavras como um município que promove 
                    o agronegócio.`, name: "Gláucia Vale", carrer: "Analista do Sebrae", photo: '/images/feedbacks-pessoas/glaucia.PNG'
                },
                {
                    id: 2, text: `Com uma boa participação de público, realizamos vários negócios. 
                    O Agráriatec atendeu bem as expectativas e desejamos que 2025 estejamos juntos novamente.`, 
                    name: "José Antônio", carrer: "Diretor Lavras Irrigação", photo: '/images/feedbacks-pessoas/jose.PNG'
                },
            ],
        };
    },
    methods: {
        buttonLeftRight(direction) {
            const container = this.$refs.containerFeedbacks;
            const itemWidth = container.firstElementChild.clientWidth;
            const scrollAmount = itemWidth;
            container.scrollBy({
                left: direction === 'left' ? -scrollAmount : scrollAmount,
                behavior: 'smooth',
            });
        },
    },
};
</script>

<style scoped>
#feedback-carousel {
    padding: 2rem 10%;
    overflow-x: hidden;
    position: relative;
}

#containerFeedbacks {
    display: flex;
    overflow-x: scroll;
    scroll-snap-type: x mandatory;
    gap: 1rem;
    scroll-behavior: smooth;
}

#containerFeedbacks::-webkit-scrollbar {
    display: none;
}

.feedback-item {
    flex: 0 0 100%;
    scroll-snap-align: center;
    background: #f9f9f9;
    padding: 2rem;
    border-radius: 10px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
    text-align: center;
}

.feedback-content {
    max-width: 600px;
    margin: 0 auto;
}

.testimonial {
    font-size: 1.2rem;
    font-style: italic;
    color: #333;
    padding: 10px;
}

.person-details {
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 1rem;
}

.photo {
    width: 5rem;
    height: 5rem;
    border-radius: 50%;
    margin-right: 1rem;
    object-fit: cover;
}

.name {
    font-weight: bold;
    margin-bottom: 0.2rem;
}

.carrer {
    font-size: 0.9rem;
    color: #777;
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
    margin: 0rem 2rem;
}

.buttons-carrossel-feedback {
    background-color: #356b34;
    color: #fff;
    border: none;
    cursor: pointer;
    font-size: 20px;
    padding: 15px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    transition: transform 0.1s ease, box-shadow 0.3s ease;
}

.buttons-carrossel-feedback:hover {
    transform: scale(1.1);
    box-shadow: 0 6px 12px rgba(0, 0, 0, 0.3);
    background-color: #2b5230;
}

.buttons-carrossel-feedback:active {
    transform: scale(0.95);
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
}

.container-buttons {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    left: 0;
    right: 0;
    display: flex;
    justify-content: space-between;
    z-index: 10;
    pointer-events: none;
}

.buttons-carrossel-feedback {
    pointer-events: all;
}

@media (max-width: 1000px) {
    .container-buttons {
        display: none;
    }
}
</style>
