<template>
    <div class="container">
        <div class="shadow"></div>
        <div class="flex">
            <div class="barContainer">

            </div>
            <div class="content about">
                <div class="title">
                    bastien<span class="styleColor">.about()</span>
                </div>
                <div class="description">
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam reprehenderit ipsa id quam labore odio. Dolor, veniam fugiat, dicta porro quae perferendis repudiandae eveniet autem nam commodi accusantium accusamus reiciendis.
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
        border-radius: 5px;
        overflow-y: scroll;
        position: relative;
        border: 1px solid white;
    }
    .flex{
        display: flex;
        height: 100%;
    }
    .barContainer{
        height: 80%;
        width: 50px;
        margin-top: 5px;
        margin-left: 10px;
        border: 1px solid white;
    }
    .shadow{
        background-image: linear-gradient(to bottom, transparent 20%, var(--back-main-color));
        position: fixed;
        height: 100px;
        width: 100%;
        bottom: 0;
    }
    .content{
        margin-left: 25px;
    }
    .container::-webkit-scrollbar{
        display: none;
    }
    .title{
        font-size: 3em;
        font-family: var(--text-font);
        color: var(--white-text-color);
        letter-spacing: 2px;
    }
    .description{
        margin-top: 0.5em;
        color: var(--white-text-color);
        letter-spacing: 2px;
        font-size: 1.1em;
        font-family: var(--text-font);
        margin-left: 1em;
        width: 70%;
    }
    .styleColor{
        color: var(--style-color);
    }
</style>