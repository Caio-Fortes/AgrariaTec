<template>
    <div class="video-player">
      <iframe
        :src="videoUrl"
        frameborder="0"
        allowfullscreen
      ></iframe>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        videoLink: 'https://www.youtube.com/watch?v=6IdEhqprcsg', 
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
      }
    }
  };
  </script>
  
  <style scoped>
  .video-player {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100vw;
    height: 100vh;
    overflow: hidden;
  }
  
  .video-player iframe {
    width: 80%;
    height: 80%;
  }
  </style>
  