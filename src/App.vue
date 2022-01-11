<script lang="ts" setup>
  import content from "./components/content/content.vue"
  import navbarC from "./components/navbar/navbar.vue"
</script>

<template>
    <div class="containerMouse">
      <div class="mouseScale">
        <div class="mouse">
          <div class="innerMouse"></div>
        </div>
      </div>
    </div>
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
  cursor: none;
}
#app {
  width: 100vw;
  height: 100vh;
  height: auto;
  display: flex;
  flex-direction: column
}
.containerMouse{
  position: absolute;
  height: 50px;
  width: 50px;
  display: flex;
  justify-content: space-around;
  pointer-events: none;
  z-index: 9999;
}
.mouseScale{
  margin-top: auto;
  margin-bottom: auto;
  transform: scale(0.65);
  transition: 0.15s;
}
.mouse{
  height: 30px;
  width: 30px;
  border: 5px solid var(--style-color);
  animation: 2s bounce infinite linear;
  margin-top: auto;
  margin-bottom: auto;
  transition: 0.25s;
}
.innerMouse{
  height: 150%;
  margin: -5px;
  transform-origin: 50% 50%;
  transform: scale(0);
  aspect-ratio: 1;
  background-color: var(--style-color);
  transition: 0.15s;
}
@keyframes bounce {
  from {
    transform: scale(0.9) rotate(0deg);
  }
  25%{
    transform: scale(1) rotate(90deg);
  }
  50%{
    transform: scale(0.8) rotate(180deg);
  }
  75%{
    transform: scale(1) rotate(270deg);
  }
  to{
    transform: scale(1) rotate(360deg);
  }
}
</style>

<script lang="ts">
  export default{
    mounted(){
      const containerMouse : any = document.querySelector('.containerMouse')
      const innerMouse : any = document.querySelector('.innerMouse')
      const size = containerMouse.getBoundingClientRect().height / 2
      window.addEventListener('mousemove',(e)=>{
        let x = e.clientX
        let y = e.clientY
        containerMouse.style.marginLeft = `${x - size}px`
        containerMouse.style.marginTop = `${y - size *2}px`
      })
      window.addEventListener('mousedown',()=>{
        innerMouse.style.transform = 'scale(1)'
        setTimeout(()=>{
          innerMouse.style.transform = 'scale(0)'
        },150)
      })
    },
    methods: {
      
    }, 
    data(){
      return{
      }
    },
  }
</script>









