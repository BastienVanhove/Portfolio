<script lang="ts" setup>
  import content from "./components/content/content.vue"
  import navbarC from "./components/navbar/navbar.vue"
</script>

<template>
    <div class="mouse"></div>
    <navbarC/>
    <content/>
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

  --back-main-color: #181616;
  --back-second-color: rgb(167, 161, 161);
  --style-color: #6138c6;
  --white-text-color: rgb(212, 201, 201);
  --style-white-color: rgba(212, 197, 197, 0.698);
  --yellow-color: rgb(206, 172, 25);
}
body{
  width: 100vw;
  height: 100vh;
  height: auto;
  background-color: var(--back-main-color);
  overflow: hidden;
}
#app {
  width: 100vw;
  height: 100vh;
  height: auto;
  display: flex;
  flex-direction: column
}
.mouse{
  height: 50px;
  width: 50px;
  border: 5px solid var(--style-color);
  margin: 100px;
  position: absolute;
}
</style>
