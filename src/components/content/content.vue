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
        width: 600px;
        height: calc(100vh - 80px);
        border: 1px solid white;
        overflow: hidden;
        border-radius: 5px;
        overflow-y: scroll;
    }
    .container::-webkit-scrollbar{
        display: none;
    }
</style>