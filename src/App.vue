<script lang="ts" setup>
  import content from "./components/content/content.vue"
  import visualisator from "./components/visualisator/visualisator.vue"
  import headerC from "./components/header/header.vue"
</script>

<template>
    <div class="background">
      <img src="" alt="background image">
    </div>
    <headerC/>
    <div class="content">
      <content/>
    </div>
</template>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;

  --back-main-color: rgb(24, 23, 23);
}
body{
  height: 100vh;
  width: 100vw;
}
#app {
  height: 100%;
  width: 100%;
  background-color: var(--back-main-color);
}
.content {
  display: flex;
  justify-content: center;
  height: auto;
  width: 100%;
}
</style>
