<template>
    <div id="headerContainerWhite" :class="headerFixedStyle">
        <div id="headerBar">
            <div id="logoContainer">
                <img src="/images/logo.png"/>
            </div>
            <ul id="containerLinks">
                <li v-for="link in linksHeader" class="container-links-header">
                    <a href="" class="links-header">{{ link.label }}</a>
                </li>
                <li id="linkHeaderSubscribe">
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
        data(){
            return {
                headerFixedStyle: 'default',
                linksHeader: [
                    {label: 'Inicio', link: ''},
                    {label: 'Quem Somos', link: ''},
                    {label: 'Programação', link: ''},
                    {label: 'Contato', link: ''},
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
                if(window.scrollY > (rect.height / 2)){
                    this.headerFixedStyle = 'fixed';
                }
                else if(window.scrollY > (rect.height - 400)){
                    this.headerFixedStyle = 'scrolled';
                } else{
                    this.headerFixedStyle = 'default';
                }
            },
        }
    }
</script>
