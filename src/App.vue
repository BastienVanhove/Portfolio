<script lang="ts" setup>
  import content from "./components/content/content.vue"
  import visualisator from "./components/visualisator/visualisator.vue"
  import footerC from "./components/footer/footer.vue"
</script>

<template>
    <div class="content">
      <content/>
    </div>
    <footerC/>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Abril+Fatface&family=Roboto:wght@300&display=swap');
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  
  --style-font: 'Abril Fatface', cursive;
  --title-font: 'Abril Fatface', cursive;
  --text-font: 'Roboto', sans-serif;

  --back-main-color: rgb(42, 40, 40);
  --back-second-color: rgb(167, 161, 161);
  --style-color: rgb(172, 31, 31);
  --white-text-color: rgb(212, 201, 201);
  --style-white-color: white;
}
body{
  width: 100vw;
  height: auto;
  background-color: var(--back-second-color);
  overflow-x: hidden;
}
#app {
  width: 100%;
  height: auto;
}
.background{
  position: absolute;
  z-index: -1;
  pointer-events: none;
  user-select: none;
  height: 100vh;
  overflow-y: hidden;
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
  margin-top: 20px;
}
</style>
