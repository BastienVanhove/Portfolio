<template>
    <div class="navbar">
        <a href="https://github.com/BastienVanhove" class="githubLogo" title="Show my Github!">
            <i class="fab fa-github"></i>
        </a>
        <ul class="menu">
            <li class="hoverable active">.about()</li>
            <li class="hoverable">.contact()</li>
            <li class="hoverable">.project()</li>
            <li class="hoverable">.social()</li>
        </ul>
    </div>
</template>

<style scoped>
    ul{
        display:flex;
        margin-left: auto;
        margin-right: 45px;
        user-select: none;
    }
    li{
        color: var(--white-text-color);
        text-decoration: none;
        list-style: none;
        padding-left: 25px;
        font-size: 1.25em;
        font-family: var(--title-font);
        margin-top: auto;
        margin-bottom: auto;
        letter-spacing: 2px;
        transition: 0.25s;
    }
    li:hover{
        transform: scale(1.1);
        color: var(--style-color)
    }
    .active{
        transform: scale(1.25);
        color: var(--style-color);
    }
    .githubLogo{
        color: var(--style-color);
        font-size: 2.8em;
        margin-left: 45px;
        margin-top: 10px;
        transition: 0.25s;
        cursor: none;
    }
    .githubLogo:hover{
        transform: scale(1.1)
    }
    .navbar{
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 50px;
        display: flex;
        z-index: 1000;
        background-image: linear-gradient(to top, transparent, var(--back-main-color))
    }
    .hoverable>span{
        transition: 0.25s;
    }
    .hoverable>span:hover{
        color: var(--style-color)
    }
</style>

<script lang="ts">
    export default{
        mounted(){
            const mouse : any = document.querySelector('.mouse')
            const hoverable : any = document.querySelectorAll('.hoverable')
            const mouseScale : any = document.querySelector('.mouseScale')
            const githubLogo : any = document.querySelector('.githubLogo')

            let hoverFunction = () =>{
                mouseScale.style.transform = 'scale(1)'
                mouse.style.borderRadius = '10px'
            }
            let OutFunction = () =>{
                mouseScale.style.transform = 'scale(0.65)'
                mouse.style.borderRadius = '0px'
            }
            hoverable.forEach(function(h : any){
                h.addEventListener('mouseover', hoverFunction)
                h.addEventListener('mouseout', OutFunction)
            })
            githubLogo.addEventListener('mouseover', hoverFunction)
            githubLogo.addEventListener('mouseout', OutFunction)

            const containerContent : any = document.querySelector('.container')
            
            for(let i = 0; i<hoverable.length; i++) {
                hoverable[i].addEventListener('click',()=>{
                    const size = window.innerHeight * 0.60
                    let marginTop = size * i
                    containerContent.scrollTo({
                        top: marginTop + 10,
                        behavior: 'smooth'
                    })
                })
            }
        }
    }
</script>