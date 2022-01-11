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
        transform: scale(1.1)
    }
    .active{
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
        background-image: linear-gradient(to top, transparent, var(--back-main-color))
    }
</style>

<script lang="ts">
    export default{
        mounted(){
            const mouse = document.querySelector('.mouse')
            console.log(mouse, 'from navbar')
        }
    }
</script>