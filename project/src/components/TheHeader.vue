<script>
    export default {
        data(){
            return{
                linksHeader: [
                    {label: 'Inicio', link: ''},
                    {label: 'Quem Somos', link: ''},
                    {label: 'Programação', link: ''},
                    {label: 'Contato', link: ''},
                ]
            }
        }
    }
</script>

<template>
    <div>
        <div id="headerContainerWhite">
            <div id="headerBar">
                <div id="logoContainer">
                    <img src="/images/Logo.jpg"/>
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
            <div> 
                <img src="/images/fundoheader.png" />
            </div>
        </div>
        <div id="headerContainerTransparent"></div>
    </div>
</template>

<script setup>

</script>
