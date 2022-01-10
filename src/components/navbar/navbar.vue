<template>
    <div class="navbar">
        <div class="githubLogo" title="show project on my github">
            <i class="fab fa-github"></i>
        </div>
        <ul class="menu">
            <li>.about()</li>
            <li>.contact()</li>
            <li>.project()</li>
            <li>.social()</li>
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
    }
    .githubLogo{
        color: var(--style-color);
        font-size: 2.8em;
        margin-left: 45px;
        margin-top: 10px;
        transition: 0.25s;
        cursor: pointer;
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
    }
</style>