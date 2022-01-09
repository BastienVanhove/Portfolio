<script lang="ts" setup>
  import content from "./components/content/content.vue"
  import visualisator from "./components/visualisator/visualisator.vue"
  import headerC from "./components/header/header.vue"
  import footerC from "./components/footer/footer.vue"
</script>

<template>
    <div class="background">
      <div class="filter"></div>
      <img src="./assets/images/back.jpg" alt="background image">
    </div>
    <headerC/>
    <div class="content">
      <content/>
    </div>
    <footerC/>
</template>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;

  --back-main-color: rgb(41, 39, 39);
  --style-color: rgb(172, 31, 31);
}
body{
  height: 100vh;
  width: 100vw;
  background-color: var(--back-main-color);
  overflow-x: hidden;
}
#app {
  height: 100%;
  width: 100%;
}
.background{
  position: absolute;
  z-index: -1;
  pointer-events: none;
  user-select: none;
}
.filter{
  position: absolute;
  background: rgba(19, 18, 18, 0.233);
  height: 100%;
  width: 100%;
}
.background>img{
  width: 100vw;
}
.content {
  display: flex;
  justify-content: center;
  height: auto;
  width: 100%;
}
</style>
