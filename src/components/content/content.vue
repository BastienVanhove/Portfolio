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
                        <p>Hi, I'm Bastien Vanhove</p>
                        <br>
                        <p>Web Developer | Self taught</p>
                        <br>
                        <p>
                            J'ai commencer a code en 2020
                        </p>
                        <br>
                        <p>photo de moi TETE</p>
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
                        Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam reprehenderit ipsa id quam labore odio. Dolor, veniam fugiat, dicta porro quae perferendis repudiandae eveniet autem nam commodi accusantium accusamus reiciendis.
                        <p>mails : bastienv.capital@gmail.com</p>
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
                        Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam reprehenderit ipsa id quam labore odio. Dolor, veniam fugiat, dicta porro quae perferendis repudiandae eveniet autem nam commodi accusantium accusamus reiciendis.
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
                        <p>Liste de reseau avec logo</p>
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
        margin-left: 20%;
        margin-top: 40vh;
        overflow-y: scroll;
        position: relative;
        border: 3px solid var(--style-color);
        z-index: 2;
        border-radius: 5px;
        background: rgba(0, 0, 0, 0.356);
    }
    @media screen and (max-width: 900px) {
        .container{
            margin-top: 20vh;
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
        border-radius: 50%;
        margin-left: -8px;
        background-color: var(--back-main-color);
        transition: 0.25s;
    }
    .active{
        background: var(--style-color);
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
    .marginContent{
        margin-top: 60vh;
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