<template>
    <div>
        mensagem
        <div>
            <form id="burger-form">
                <div class="input-container">
                    <label for="name">Client name</label>
                    <input v-model="name" id="name" name="name" type="text" placeholder="Type your name">
                </div> 

                <div class="input-container">
                   <label for="bread">Choose the bread</label>
                   <select v-model="bread" name="bread" id="bread">
                        <option value="">Select Bread</option>
                        <option value="">Integral</option>
                   </select>
                </div> 

                <div class="input-container">
                   <label for="meat">Choose the Meat</label>
                   <select v-model="meat" name="meat" id="meat">
                        <option value="">Select Meat</option>
                        <option value="">Maminha</option>
                   </select>
                </div> 

                <div id="optionals container" class="input-container">
                   <label id="optionals-title" for="optionals">Choose the optionals</label>
                   <div class="checkbox-container">
                       <input v-model="optionals" type="checkbox" name="optionals" value="salame">
                       <span>Salame</span>
                   </div>
                </div> 

                <div class="input-container">
                    <input class="submit-btn" type="submit" value="create-my-burger">
                </div>

            </form>
        </div>
    </div>

</template>

<script>
    export default {
        name: 'BurgerForm'
    }
</script>

<style scoped>
    #burger-form {
        max-width: 400px;
        margin: 0 30%;
    }

    .input-container {
        display: flex;
        flex-direction: column;
        margin-bottom: 20px;
    }

    label {
        font-weight: bold;
        margin-bottom: 15px;
        color: #222;
        padding: 5px 10px;
        border-left: 4px solid #FCBA03;
    }

    input, select {
        padding: 5px 10px;
        width: 300px;
    }

    #optionals-container {
        flex-direction: row;
        flex-wrap: wrap;
    }

    #optionals-title {
        width: 100%;
    }

    .checkbox-container {
        display: flex;
        align-items: flex-start;

        width: 50%;
        margin-bottom: 20px;
    }

    .checkbox-container span,
    .checkbox-container input {
        width: auto;
    }

    .checkbox-container span {
        margin-left: 6px;
        font-weight: bold;
    }

    .submit-btn {
        background-color: #222;
        color: #FCBA03;
        font-weight: bold;
        border: 2px solid #222;
        border-radius: 4px;
        font-size: 16px;

        padding: 10px;
        margin: 0 auto;

        cursor: pointer;
        transition: .5s;
    }

    .submit-btn:hover {
        background-color: transparent;
        color: #222;
    }

</style>