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
                        <option v-for="bread in loaves" :key="bread.id" :value="bread.tipo">{{ bread.tipo }}</option>
                    </select>
                </div>

                <div class="input-container">
                    <label for="meat">Choose the Meat</label>
                    <select v-model="meat" name="meat" id="meat">
                        <option value="">Select Meat</option>
                        <option v-for="meat in meats" :key="meat.id" :value="meat.tipo">{{ meat.tipo }}</option>
                    </select>
                </div>

                <div id="optionals container" class="input-container">
                    <label id="optionals-title" for="optionals">Choose the optionals</label>
                    <div class="checkbox-container" v-for="optional in optionals" :key="optional.id" :value="optional.tipo">
                        <input v-model="optionals" type="checkbox" name="optionals" :value="optional.tipo">
                        <span> {{optional.tipo}}</span>
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
    name: 'BurgerForm',
    data() {
        return {
            loaves: null,
            meats: null,
            optionals: null,
            name: null,
            bread: null,
            meat: null,
            optionals: [],
            status: "Solicitado",
            msg: null


        }
    },
    methods: {
        async getIngredients() {
            const req = await fetch("http://localhost:3000/ingredientes")
            const data = await req.json()

            this.loaves = data.paes
            this.meats = data.carnes
            this.optionals = data.opcionais
        }
    },
    mounted(){
        //When the app be mounted, execute the functions
        this.getIngredients()
    }
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

input,
select {
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