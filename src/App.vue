<template>
    <div class="home">
        <header class="header">
            <h1 class="header-title">Monty Hall Problem</h1>
        </header>
        <div class="home-define" v-if="!initiated">
            <div class="define">
                <label for="numberOfDoors">Qual a quantidade de portas?</label>
                <input id="numberOfDoors" class="define-input" type="text" v-model.number="quantity" size="3">
            </div> <!-- .number é um modificador que aplicado ao v-model transforma o valor dele no tipo number -->
            <div class="define">
                <label for="awardedDoor">Qual será a porta premiada?</label>
                <input id="awardedDoor" class="define-input" type="text" v-model.number="awarded" size="3">
            </div>
            <ButtonPart text="Iniciar" v-if="!initiated" @click="initiated = true" />
        </div>

        <div class="problem" v-if="initiated" >
            <div class="problem-doors">
                <DoorPart v-for="index in quantity" :key="index" :number="index" :doorawarded="index === awarded" />
            </div>
            <ButtonPart text="Reiniciar" @click="initiated = false" />
        </div>        
        <footer class="footer">
            <p class="footer-text">created by: Merieli Manzano</p>
        </footer>
    </div>
</template>

<script>
import ButtonPart from './components/ButtonPart.vue'
import DoorPart from "./components/DoorPart.vue";

export default {
    name: "HomeView",
    components: {
        ButtonPart,
        DoorPart
    },
    data(){
        return {
            initiated: false,
            quantity: 3,
            awarded: 0
        }
    }
};
</script>


<style>
*{
    font-family: Arial, Helvetica, sans-serif;
    box-sizing: border-box;
}

html{
    height: 100vh;
    width: 100vw;
}

body{
    background-image: linear-gradient(135deg, #37c5ca, #595f8f, #928589); 
    background-position: 50%, 30%, 20%; 
    background-repeat: no-repeat;
    background-size: contain;
    color: white;
}

.header{
    box-sizing: border-box;
    margin: 1.5rem 2rem;
}

.header-link{
    color: white;
    font-weight: 600;
    text-decoration: none;
}

.header-title {
    margin: 0;
    text-align: center;
}

.home-define{
    margin-top: 4rem;
}

.define{
    margin: 0 auto;
    font-size: 1rem;
    text-align: center;
    margin-bottom: 1rem;
    width: 30%;
}

.define-input{
    margin-left: 1rem;
    font-size: 1.1rem;
    font-weight: 700;
}

.footer{
    bottom: 0;
    position: fixed;
    width: 100%;
}

.footer-text{
    text-align: center;
}

.problem-doors{
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    margin: 4rem 4rem 1.5rem 4rem;
}
</style>
