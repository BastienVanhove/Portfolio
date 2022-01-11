<template>
    <div class="container">
        <div class="shadow"></div>
        <div class="flex">
            <div class="barContainer">
                <div class="filed">
                    <div class="bar bar1"></div>
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
                        Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam reprehenderit ipsa id quam labore odio. Dolor, veniam fugiat, dicta porro quae perferendis repudiandae eveniet autem nam commodi accusantium accusamus reiciendis.
                        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Cumque totam dolor ad. Obcaecati deleniti consequuntur quo alias, vitae aliquid praesentium? Incidunt facere saepe beatae, est necessitatibus id aut suscipit provident.
                    </div>
                </div>
                <div class="content contact marginContent">
                    <div class="title">
                        Bastien
                        <span class="styleColor">
                            .contact()
                        </span>
                    </div>
                    <div class="description">
                        Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam reprehenderit ipsa id quam labore odio. Dolor, veniam fugiat, dicta porro quae perferendis repudiandae eveniet autem nam commodi accusantium accusamus reiciendis.
                    </div>
                </div>
                <div class="content project marginContent">
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
                <div class="content social marginContent">
                    <div class="title">
                        Bastien
                        <span class="styleColor">
                            .social()
                        </span>
                    </div>
                    <div class="description">
                        Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam reprehenderit ipsa id quam labore odio. Dolor, veniam fugiat, dicta porro quae perferendis repudiandae eveniet autem nam commodi accusantium accusamus reiciendis.
                    </div>
                </div>
                <div class="void"></div>
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
        border: 2px solid var(--style-color);
    }
    .void{
        height: 40vh;
        width: 100%;
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
        width: 2px;
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
        --sizeBar: 21px;
        height: var(--sizeBar);
        width: var(--sizeBar);
        position: absolute;
        border: 2px solid var(--style-color);
        border-radius: 50%;
        margin-left: -9px;
        background-color: var(--back-main-color);
        transition: 0.1s;
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
        transform: scale(1.25);
    }
    .shadow{
        background-image: linear-gradient(to bottom, transparent 20%, var(--back-main-color));
        position: fixed;
        height: 100px;
        width: 100%;
        bottom: 0;
    }
    .marginContent{
        margin-top: 60vh;
    }
    .about{
        margin-top: 5px;
    }
    .content{
        margin-left: 25px;
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