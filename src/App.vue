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
    <div class="button">
      <span v-for="letters in buttonText" :key="letters">{{letters}}</span>
    </div>
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
div::selection{
  background: var(--style-color);
}
span::selection{
  background: var(--style-color);
  color: white;
}
p::selection{
  background: var(--style-color);
  color: white;
}
#app {
  width: 100vw;
  height: 100vh;
  height: auto;
  display: flex;
  flex-direction: column
}
.button{
  position: absolute;
  margin-left: 15vw;
  margin-top: calc(40vh - 55px);
  border: 3px solid var(--style-color);
  color:  var(--white-text-color);
  border-radius: 0px;
  padding: 10px;
  font-size: 1.05em;
  background: rgba(0, 0, 0, 0.356);
  animation: 3s floaty infinite;
  z-index: 1000;
  cursor: pointer;
  user-select: none;
  transition: 0.15s;
  font-family: var(--text-font);
}
.button>span{
  transition: 0.25s;
}
.button:hover{
  background: var(--white-text-color);
  color: var(--back-main-color);
}
.button>span:hover{
  color: var(--style-color);
  transform: scale(1.25)
}
@keyframes floaty {
  to{
    transform: translateY(0px);
  }
  50%{
    transform: translateY(5px);
  }
  from{
    transform: translateY(0px);
  }
}
@media screen and (max-width: 900px){
  .button{
    display: none;
  }
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
  animation: 3s bounce infinite linear;
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
  transition: 0.35s;
}
@keyframes bounce {
  from {
    transform: scale(1) rotate(0deg);
  }
  25%{
    transform: scale(1.2) rotate(90deg);
  }
  50%{
    transform: scale(0.8) rotate(180deg);
  }
  75%{
    transform: scale(1.1) rotate(270deg);
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
      const mouseScale : any = document.querySelector('.mouseScale')
      const mouse : any = document.querySelector('.mouse')
      const button : any = document.querySelector('.button')

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
        },200)
      })

      let hoverFunction = () =>{
          mouseScale.style.transform = 'scale(1)'
          mouse.style.borderRadius = '10px'
      }
      let OutFunction = () =>{
          mouseScale.style.transform = 'scale(0.65)'
          mouse.style.borderRadius = '0px'
      }
      button.addEventListener('mouseover', hoverFunction)
      button.addEventListener('mouseout', OutFunction)
    },
    methods: {
      
    }, 
    data(){
      return{
        buttonText : "I don't care, show me your Projects".split(''),
      }
    },
  }
</script>









