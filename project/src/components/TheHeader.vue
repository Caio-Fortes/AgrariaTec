<template>
    <div id="headerContainerWhite" :class="headerFixedStyle">
        <div id="headerBar">
            <div id="logoContainer">
                <img src="/images/logo.png" />
            </div>
            <ul id="containerLinks">
                <li v-for="(link, index) in linksHeader" :key="index" class="container-links-header">
                    <a 
                        href="#" @click.prevent="scrollToSection(link.link, link.offset)" 
                        class="links-header">{{ link.label }}
                    </a>
                </li>
                <li id="linkHeaderSubscribe" @click="buttonInscrever">
                    Inscrever-se
                </li>
            </ul>
        </div>
        <div id="backgroundHeader"> 
            <img src="/images/fundoheader.png" />
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            headerFixedStyle: 'default',
            linksHeader: [
                { label: 'Inicio', link: 'inicio', offset: 0 },
                { label: 'Quem Somos', link: 'quem-somos', offset: 110 },
                { label: 'O que vou encontrar?', link: 'programacao', offset: 90 },
                { label: 'Contato', link: 'contato', offset: 110 },
            ]
        }
    },
    mounted() {
        window.addEventListener('scroll', this.handleScroll);
    },
    beforeDestroy() {
        window.removeEventListener('scroll', this.handleScroll);
    },
    methods: {
        handleScroll() {
            const element = document.querySelector('.images-capas-container');
            const rect = element.getBoundingClientRect();
            if (window.scrollY > (rect.height / 2)) {
                this.headerFixedStyle = 'fixed';
            } else if (window.scrollY > (rect.height - 400)) {
                this.headerFixedStyle = 'scrolled';
            } else {
                this.headerFixedStyle = 'default';
            }
        },
        scrollToSection(sectionId, offset) {
            const section = document.getElementById(sectionId);
            if (section) {
                const sectionPosition = section.getBoundingClientRect().top + window.scrollY;
                const targetPosition = sectionPosition - offset;
                window.scrollTo({ top: targetPosition, behavior: 'smooth' });
            }
        },
        buttonInscrever(){
            window.open('https://forms.gle/g8Xit6GvF5TMXvUp8', '_blank');
        }
    }
}
</script>
