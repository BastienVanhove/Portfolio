<template>
    <div class="container">
        
    </div>
</template>

<style scoped>
    @media screen and (max-width: 900px) {
        .container{
            width: 100%;
        }
    }
    .container{
        width: 900px;
        height: 140vh;
        box-shadow: 0 0 4px 2px var(--back-main-color);
        overflow: hidden;
    }
    .header{
        height: 25vh;
        width: 100%;
    }
    .shadow{
        height: 300px;
        width: 100%;
        background: linear-gradient(to bottom, transparent, var(--back-main-color));
    }
    .content{
        height: 100%;
        width: 100%;
        background: var(--back-main-color);
        display: block;
    }
    .blackSection{
        height: 50%;
        width: 100%;
    }
    .whiteSection{
        height: 50%;
        width: 100%;
        background-color: var(--style-white-color);
    }
</style>