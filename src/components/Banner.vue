<template>
    <div id="main-banner">
        <h1>Make Your Burger</h1>
    </div>

</template>


<script>
    export default {
        name: 'Banner'
    }

</script>

<style scoped>
    #main-banner {
        display: flex;
        height: 500px;
        width: 100%;

        align-items: center;
        justify-content: flex-start;

        background-image: url('../../public/img/burger.jpg');
        background-position: 0;
        background-size: cover;
    }

    #main-banner h1 {
        color: #FFF;
        text-align: center;
        font-size: 60px;
        padding: 20px 40px;
    }

</style>