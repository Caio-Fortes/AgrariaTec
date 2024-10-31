<script setup>
import Separator from './components/Separator.vue';
import TheHeader from './components/TheHeader.vue';
import Capa from './components/Capa.vue';
import QuemSomos from './components/QuemSomos.vue';
import Pesquisas from './components/Pesquisas.vue';
import ProgramacaoEvento from './components/Programacao.vue';
import Contato from './components/Contato.vue';
import Parceiros from './components/Parceiros.vue';
import localizacao from './components/localizacao.vue';
import Galeria from './components/Galeria.vue'
import MediaPlayer from './components/MediaPlayer.vue'
</script>

<template>
  <TheHeader />
  <Capa />
  <QuemSomos /> 
  <Separator />
  <Pesquisas />
  <Galeria />
  <MediaPlayer />
  <ProgramacaoEvento />
  <localizacao />
  <Separator />
  <Parceiros />  
  <Separator />
  <Contato />
</template>