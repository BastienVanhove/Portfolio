<template>
    <div class="container">
        <div class="shadow"></div>
        <div class="flex">
            <div class="barContainer">
                <div class="filed">
                    <div class="bar bar1 active"></div>
                    <div class="bar bar2"></div>
                    <div class="bar bar3"></div>
                    <div class="bar bar4"></div>
                </div>
            </div>
            <div class="container-content">
                <div class="content about">
                    <div class="title">
                        Bastien
                        <span class="styleColor">
                            .about()
                        </span>
                    </div>
                    <div class="description">
                        <div class="containerProfile">
                            <div class="containerProfileImg">
                                <img src="../../assets/images/van.jpg">
                            </div>
                            <div class="name">
                                Bastien Vanhove (NONE)
                            </div>
                        </div>
                        <p class="profileText">
                            Lorem ipsum, dolor sit amet consectetur adipisicing elit. Expedita enim sequi, nam nesciunt excepturi ut corporis eos, quae esse nisi facere voluptas! Id ipsam sunt ad dolorem assumenda distinctio eveniet.
                        </p>
                    </div>
                </div>
                <div class="content project">
                    <div class="title">
                        Bastien
                        <span class="styleColor">
                            .project()
                        </span>
                    </div>
                    <div class="description">
                        <p>i like programming chess thing blabla but ...</p>
                    </div>
                    <div class="contentChessAndBut">
                        <div class="chessContainer">
                            <div v-for="x in 8"  :key= "x" class="chessLine">
                                <div v-for="y in 8" :key="y" class="chessCase">
                                    <div v-if="(x + y) % 2 == 0" class="chessUpCase" style="background-color: black"></div>
                                    <div v-else class="chessUpCase" style="background-color: white"></div>
                                </div>
                            </div>
                        </div>
                        <div class="gitButton">
                            Show on GitHub
                        </div>
                    </div>
                </div>
                <div class="content contact">
                    <div class="title">
                        Bastien
                        <span class="styleColor">
                            .contact()
                        </span>
                    </div>
                    <div class="description">
                        <div class="flex mail">
                            <i class="fas fa-envelope"></i>
                            <p>mails : bastienv.capital@gmail.com</p>
                        </div>
                        <br>
                        <p>
                            Lorem ipsum dolor sit amet consectetur adipisicing elit. Ducimus sapiente nemo ut assumenda soluta suscipit alias voluptate nihil aliquam rem. Consectetur nemo natus sapiente ipsam dolore illum soluta fuga atque!
                        </p>
                    </div>
                </div>
                <div class="content social">
                    <div class="title">
                        Bastien
                        <span class="styleColor">
                            .social()
                        </span>
                    </div>
                    <div class="description">
                        <div class="socialList">
                            <i class="fab fa-twitter-square"></i>
                            <i class="fab fa-instagram-square"></i>
                            <i class="fab fa-linkedin"></i>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
    .container{
        width: 45%;
        height: 60vh;
        margin-left: 14vw;
        margin-top: 40vh;
        overflow-y: scroll;
        position: relative;
        border: 3px solid var(--style-color);
        z-index: 2;
        border-radius: 5px;
        background: rgba(0, 0, 0, 0.356);
    }
    .socialList{
        width: 200px;
        display: flex;
        justify-content: space-around;
    }
    .socialList>i{
        color: var(--style-color);
        font-size: 3em;
    }
    .containerProfile{
        margin-top: 25px;
        height: auto;
        width: 90%;
        display: flex;
    }
    .containerProfileImg{
        margin-top:auto;
        margin-bottom: auto;
        border: 5px solid var(--style-color);
        height: 150px;
        width: 150px;
        border-radius: 25px;
        margin-left: 10px;
        margin-right: auto;
        overflow: hidden;
        user-select: none;
    }
    .name{
        margin-left:auto;
        margin-right: auto;
        text-align: center;
        margin-top: auto;
        margin-bottom: auto;
        color: var(--style-color);
        font-size: calc(0.5em + 0.5vw);
        font-family: var(--title-font);
        border: 3px solid var(--style-color);
        padding: 10px;
    }
    .containerGithub{
        margin-top: 10px;
        width: 95%;
        height: 20%;
        border-radius: 5px;
        border: 2px solid var(--style-color);
        text-align: center;
        display: flex;
        justify-content: space-around;
        flex-direction: column;
        color: white;
        font-size: 1.25em;
    }
    .contentChessAndBut{
        margin-top: 25px;
        height: 50%;
        width: 100%;
        display: flex;
        border: 1px solid red;
    }
    .gitButton{
        background: var(--style-color);
        height: 35px;
        color: white;
        display: flex;
        justify-content: space-around;
        flex-direction: column;
        text-align: center;
        padding: 5px;
    }
    .chessContainer{
        margin-top: 25px;
        margin-left: 15px;
        height: 80%;
        aspect-ratio: 1;
        display: flex;
        justify-content: space-around;
        flex-wrap: wrap;
        transition: 0.5s;
    }
    .chessContainer:hover{
        transform: scale(1.05);
    }
    .chessLine{
        display: flex;
        justify-content: space-around;
        height: 12.5%;
        width: 100%;
    }
    .chessCase{
        height: 90%;
        aspect-ratio: 1;
        background: var(--style-color);
        margin-top: auto;
        margin-bottom: auto;
        display: flex;
        justify-content: space-around;
        transition: 0.25s;
    }
    .chessUpCase{
        background: var(--back-main-color);
        margin-top: auto;
        margin-bottom: auto;
        height: 85%;
        width: 85%;
        transition: 0.25s;
    }
    .blackCase{
        background: var(--style-color);
    }
    .whiteCase{
        background: var(--white-text-color);
    }
    .containerProfileImg:hover >img{
        transform: scale(1.5)
    }
    .containerProfileImg>img{
        width: 100%;
        transition: 1s;
    }
    .mail{
    }
    .mail>i{
        font-size: 1.25em;
        color: var(--style-color);
    }
    .mail>p{
        margin-top: auto;
        margin-bottom: auto;
        margin-left: 10px;
    }
    .profileText{
        margin-top: 25px;
        margin-left: auto;
        margin-right: auto;
    }
    @media screen and (max-width: 900px) {
        .container{
            margin-top: 10vh;
            height: 80vh;
            width: 100%;
            margin-left: 0;
            border: none;
            background: none;
        }
    }
    .flex{
        display: flex;
        height: 100%;
    }
    .container-content{
        margin-left: 25px;
        position: relative;
    }
    .barContainer{
        height: 50vh;
        width: 1px;
        margin-top: 15px;
        margin-left: 20px;
        display: flex;
        position: fixed;
    }
    .filed{
        background: var(--style-color);
        height: 100%;
        width: 100%;
        margin-top: auto;
        border-radius: 5px;
    }
    .bar{
        --sizeBar: 17px;
        height: var(--sizeBar);
        width: var(--sizeBar);
        position: absolute;
        border: 2px solid var(--style-color);
        border-radius: 5px;
        margin-left: -8px;
        background-color: var(--back-main-color);
        transition: 0.25s;
    }
    .active{
        background: var(--style-color);
        border: 2px solid var(--white-text-color);
    }
    .bar1{
        top: calc(12.5% - (var(--sizeBar) / 2) );
    }
    .bar2{
        top: calc(37.5% - (var(--sizeBar) / 2) );
    }
    .bar3{
        top: calc(62.5% - (var(--sizeBar) / 2) )
    }
    .bar4{
        top: calc(87.5% - (var(--sizeBar) / 2) );
    }
    .bar:hover{
        transform: scale(1.5);
    }
    .shadow{
        background-image: linear-gradient(to bottom, transparent 20%, var(--back-main-color));
        position: fixed;
        height: 100px;
        width: 45%;
        bottom: 0;
        z-index: 1000;
        pointer-events: none;
    }
    .about{
        margin-top: 5px;
    }
    .content{
        margin-left: 25px;
        height: 60vh;
    }
    .container::-webkit-scrollbar{
        display: none;
    }
    .title{
        font-size: 3em;
        font-family: var(--title-font);
        color: var(--white-text-color);
        letter-spacing: 2px;
    }
    .title>span{
        font-family: var(--text-font);
    }
    .description{
        margin-top: 0.8em;
        color: var(--white-text-color);
        letter-spacing: 2px;
        font-size: 1.1em;
        font-family: var(--text-font);
        margin-left: 1em;
        width: 95%;
    }
    .styleColor{
        color: var(--style-color);
    }
</style>

<script lang="ts">
    export default{
        mounted(){
            const mouse : any = document.querySelector('.mouse')
            const mouseScale : any = document.querySelector('.mouseScale')
            const bar = document.querySelectorAll('.bar')
            let hoverFunction = () =>{
                mouseScale.style.transform = 'scale(1)'
                mouse.style.borderRadius = '10px'
            }
            let OutFunction = () =>{
                mouseScale.style.transform = 'scale(0.65)'
                mouse.style.borderRadius = '0px'
            }
            bar.forEach(function(h : any){
                h.addEventListener('mouseover', hoverFunction)
                h.addEventListener('mouseout', OutFunction)
            })

            const containerContent : any = document.querySelector('.container')
            const contents : any = document.querySelectorAll('.content')
            const hoverable : any = document.querySelectorAll('.hoverable')
            let size : number = window.innerHeight * 0.60

            for(let i = 0; i<bar.length; i++) {
                bar[i].addEventListener('click',()=>{
                    const bounding = contents[i].getBoundingClientRect()
                    const marginTop = size * i
                    containerContent.scrollTo({
                        top: marginTop + 10,
                        behavior: 'smooth'
                    })
                })
            }

            let hoverFunctionBody= () =>{
                mouseScale.style.transform = 'scale(2.5)'
                mouse.style.borderRadius = '5px'
            }
            let OutFunctionBody = () =>{
                mouseScale.style.transform = 'scale(0.65)'
                mouse.style.borderRadius = '0px'
            }
            const app : any = document.querySelector('#particles-js')
            app.addEventListener('mouseover', hoverFunctionBody)
            app.addEventListener('mouseout', OutFunctionBody)
            
            const containerProfileImg : any = document.querySelector('.containerProfileImg')
            containerProfileImg.addEventListener('mouseover', hoverFunction)
            containerProfileImg.addEventListener('mouseout', OutFunction)

            containerContent.addEventListener('scroll',(e : any)=>{
                size = window.innerHeight * 0.60
                const scrollTop : number = parseInt(containerContent.scrollTop)
                const onSection : number = Math.floor(scrollTop/size)
                const barOnSection : any = bar[onSection]
                const liOnSection : any = hoverable[onSection]
                let liClassName : string = liOnSection.className
                let className : string =  barOnSection.className
                
                const classSplit : string[] = className.split(' ')
                if(!classSplit[2]){
                    bar.forEach(function(b : any){
                        const split : string[] = b.className.split(' ')
                        if(split[2]) {
                            const rec : string = `${split[0]} ${split[1]}`
                            b.className = rec
                        }
                    })
                    hoverable.forEach(function(h : any){
                        const split : string[] = h.className.split(' ')
                        if(split[1]) {
                            const rec : string = `${split[0]}`
                            h.className = rec
                        }
                    })
                    className = className + " active"
                    barOnSection.className = className

                    liClassName = liClassName + "active"
                    liOnSection.className = className
                } 
            })
        },
        data(){
            return {

            }
        }
    }
</script>