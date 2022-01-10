<template>
    <div class="container">
        <div class="content about">
            <div class="title">
                bastien
                <span class="styleColor">.about()</span>
            </div>
            <div class="description">
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam reprehenderit ipsa id quam labore odio. Dolor, veniam fugiat, dicta porro quae perferendis repudiandae eveniet autem nam commodi accusantium accusamus reiciendis.
            </div>
        </div>
    </div>
</template>

<style scoped>
    @media screen and (max-width: 900px) {
        .container{
            width: 100%;
        }
    }
    .container{
        width: 35%;
        height: 60vh;
        margin-left: 20%;
        margin-top: 40vh;
        border: 1px solid white;
        border-radius: 5px;
        overflow-y: scroll;
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
        font-size: 1.5em;
        font-family: var(--text-font);
        margin-left: 1em;
        width: 70%;
    }
    .styleColor{
        color: var(--style-color);
    }
</style>