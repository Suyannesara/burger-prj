<template>
    <footer id="footer">
        <p>Make Your Burguer &copy; 2022</p>
    </footer>
</template>

<script>
    export default {
        name: 'Footer',
        
    }
</script>

<style scoped>
    footer {
        display: flex;
        height: 200px;
        width: 100%;

        align-items: center;
        justify-content: center;

        background-color: #222;
        border-top: 4px solid #111;
        color: #FCBA03;
    }

</style>