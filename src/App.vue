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
        <div>
          <span v-for="letters in buttonText" :key="letters">{{letters}}</span>
          <i class="fas fa-paper-plane"></i>
        </div>
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
  --style-color: #7650d4;
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
  margin-left: 14vw;
  margin-top: calc(40vh - 70px);
  border: 4px solid transparent;
  border-left: 4px solid var(--style-color);
  border-bottom: 4px solid var(--style-color);
  border-top: 2px solid var(--style-color);
  border-right: 2px solid var(--style-color);
  color:  var(--white-text-color);
  font-size: 1.30em;
  background: rgba(0, 0, 0, 0.356);
  animation: 3s floaty infinite;
  z-index: 1000;
  cursor: pointer;
  user-select: none;
  font-family: var(--text-font);
  height: 60px;
  width: 370px;
  text-align: center;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  border-radius: 0px;
  transition: 0.25s;
}
.button>div>i{
  color: var(--style-color);
  font-size: 1em;
  margin-left: 5px;
  transition: 0.5s;
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
      const containerContent : any = document.querySelector('.container')


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

      const hoverFunction = () =>{
          mouseScale.style.transform = 'scale(1)'
          mouse.style.borderRadius = '10px'
      }
      const OutFunction = () =>{
          mouseScale.style.transform = 'scale(0.65)'
          mouse.style.borderRadius = '0px'
      }
      button.addEventListener('mouseover', hoverFunction)
      button.addEventListener('mouseout', OutFunction)

      const plane : any = document.querySelector('.button>div>i')
      const planeFlying = () =>{
        plane.style.transform = 'translate(100px, -55px) rotate(35deg)'
        setTimeout(()=>{
          plane.style.opacity = 0
        },100)
        setTimeout(()=>{
          plane.style.transform = 'translate(0px, 0px) rotate(0)'
        },550)
        setTimeout(()=>{
          plane.style.opacity = 1
        },1000)
      }
      button.addEventListener('click',()=>{
        planeFlying()
        const size : number = window.innerHeight * 0.60
        containerContent.scrollTo({
            top: size,
            behavior: 'smooth'
        })
        window.location = 'https://github.com/BastienVanhove?tab=repositories'
      })
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









