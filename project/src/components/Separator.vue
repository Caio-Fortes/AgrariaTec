<template>
  <div id="containerSeparator">
    <div class="separator"></div>
  </div>
</template>

<script>
export default {
  name: 'Separator'
}
</script>

<style scoped>
#containerSeparator {
  display: flex;
  justify-content: center;

}

#containerSeparator div {
  margin: 4vw 3vw;
}

.separator {
  width: 87%;
  height: 1px;
  background-color: #80808047;
  border-radius: 10px;
}
</style>