<template>
    <div id="headerContainerWhite" :class="headerFixedStyle">
        <div id="headerBar">
            <div id="logoContainer">
                <img src="/images/logo.png" />
            </div>

            <button @click="toggleMenu" id="menuToggle" class="hamburger-btn">
                &#9776;
            </button>

            <ul id="containerLinks" :class="{ 'open': menuOpen }">
                <li v-for="(link, index) in linksHeader" :key="index" class="container-links-header">
                    <a href="#" @click.prevent="scrollToSection(link.link, link.offset)" class="links-header">{{
                        link.label }}
                    </a>
                </li>
                <li class="container-links-header" id="linkHeaderSubscribe" @click="buttonInscrever">
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
            menuOpen: false,
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
        buttonInscrever() {
            window.open('https://forms.gle/g8Xit6GvF5TMXvUp8', '_blank');
        },
        toggleMenu() {
            this.menuOpen = !this.menuOpen;
        },
    }
}
</script>

<style scoped>
.hamburger-btn {
    display: none;
}

#containerLinks {
    display: flex;
    text-align: center;
    margin-top: -11px;
}

@media (max-width: 768px) {
    .hamburger-btn {
        display: block;
        background: none;
        border: none;
        font-size: 30px;
        cursor: pointer;
    }

    #containerLinks {
        display: none;
        flex-direction: column;
        background-color: white;
        position: absolute;
        top: 100%;
        left: 0;
        width: 100%;
        align-items: center;
        padding: 10px 0;
    }

    #containerLinks.open {
        display: flex;
    }

    #backgroundHeader {
        display: none;
    }
}

@media (min-width: 769px) {
    #backgroundHeader {
        display: block;
    }
}
</style>