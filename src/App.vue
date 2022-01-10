<script lang="ts" setup>
  import content from "./components/content/content.vue"
  import navbarC from "./components/navbar/navbar.vue"
</script>

<template>
    <navbarC/>
    <div class="content">
      <content/>
    </div>
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
  --style-white-color: rgba(212, 197, 197, 0.698);
  --yellow-color: rgb(206, 172, 25);
}
body{
  width: 100vw;
  height: 100vh;
  height: auto;
  background-color: var(--back-main-color);
  overflow-x: hidden;
}
#app {
  width: 100%;
  height: auto;
}
.content {
  height: auto;
  width: 100%;
  margin-top: 70px;
  margin-left: 20%;
}
</style>
