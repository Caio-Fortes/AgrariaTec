<template>
  <div class="video-player">
    <iframe ref="video" :src="videoUrl" frameborder="0" allowfullscreen></iframe>
  </div>
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
.video-player {
  padding: 5% 10% 0% 10%;
  width: 80%;
  height: 80%;
}

.video-player iframe {
  width: 100%;
  height: 30vw; /* Mantém a proporção do vídeo */
  border-radius: 10px;
  margin-bottom: 1rem;
}
</style>
