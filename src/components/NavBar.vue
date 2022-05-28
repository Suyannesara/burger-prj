<template>
    <div>
        <nav>
            <router-link to="/" id="logo-url">
                <img id="logo" :src="logo" :alt="alt">
            </router-link>
            <router-link to="/">Home</router-link> 
            <router-link to="/requests">Requests</router-link>
        </nav>
    </div>
</template>

<script>
    export default {
        name: 'NavBar',
        props: ['logo', 'alt']
    }
</script>

<style>
    nav {
        display: flex;

        justify-content: flex-end;
        align-items: center;

        background-color: #222;
        border-bottom: 4px solid #111;
        padding: 15px 50px;
    }

    nav #logo-url {
        margin: auto;
        margin-left: 0;
    }

    #logo {
        width: 40px;
        height: 40px;
    }

    nav a {
        color: #FCBA03;
        text-decoration: none;
        margin: 12px;
        transition: 0.5s;
    }

    a:hover {
        color: #FFF;
    }


</style>