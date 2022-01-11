<script lang="ts" setup>
  import content from "./components/content/content.vue"
  import navbarC from "./components/navbar/navbar.vue"
</script>

<template>
    <div class="mouse">
      <div class="innerMouse"></div>
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
.mouse{
  height: 30px;
  width: 30px;
  border: 5px solid var(--style-color);
  margin: 100px;
  position: absolute;
  z-index: 9999;
  animation: 3s rotate infinite linear;
  pointer-events: none;
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
@keyframes rotate {
  from {
    transform: rotate(0deg)
  }
  to{
    transform: rotate(360deg)
  }
}
</style>

<script lang="ts">
  export default{
    mounted(){
      const mouse : any = document.querySelector('.mouse')
      const innerMouse : any = document.querySelector('.innerMouse')
      const size = mouse.getBoundingClientRect().height / 2
      let boolLag = true;
      window.addEventListener('mousemove',(e)=>{
        let x = e.clientX
        let y = e.clientY
        mouse.style.marginLeft = `${x - size}px`
        mouse.style.marginTop = `${y - size *2}px`
        let hoverElement = e.path[0]
        console.log(hoverElement.class)
        if(hoverElement.className == 'hoverable'){
          mouse.style.height = '25px'
          mouse.style.width = '25px'
          mouse.style.borderRadius = '5px'
          boolLag = false
        }
        else{
          mouse.style.height = '30px'
          mouse.style.width = '30px'
          mouse.style.borderRadius = '0px'
        }
      })
      window.addEventListener('click',()=>{
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









