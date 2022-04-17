<template>
    <div class="door" id="">
        <div class="door-flap" :class="{ spotlight: chosen && !showContent }" >
            <div type="button" v-if="!showContent" class="door-leaf" @click="chosen = !chosen">
                <p class="door-number">{{ number }}</p>
                <button class="door-handle" @click="showContent = true"></button> <!-- .stop irá parar a propagação do evento clique-->
            </div>
        </div>
        <GiftPart v-if="doorawarded && showContent" />
        <div class="door-sill"></div>
    </div>
</template>

<script>
import GiftPart from './GiftPart.vue'

export default {
    name: "DoorPart",
    props: {
        number: { type: Number },
        doorawarded: { type: Boolean }
    },
    data() {
        return {
            showContent: false,
            chosen: false
        }
    },
    components: {
        GiftPart
    }
};
</script>

<style scoped>
    :root{
        --wood-flap: #6e3c3e;
        
    }

    .door{
        background-color: rgba(36, 34, 34, 0.404);
        position: relative;
        width: 130px;
        height: 220px;
        margin-bottom: 2rem;
        margin-right: 1rem;
    }

    .door-flap{
        padding: 0;
        cursor: pointer;
        outline: inherit;
        border-top: 6px solid #6e3c3e;
        border-left: 6px solid #6e3c3e;
        border-right: 6px solid #6e3c3e;
        background: transparent;
        box-sizing: border-box;
        font-family: inherit;
        display: block;
        transition: .5s;
        height: 100%;
        width: 100%;
        z-index: 0;
    }

    .door-flap.spotlight{
        border-top: 6px solid yellow;
        border-left: 6px solid yellow;
        border-right: 6px solid yellow;
    }

    .door-flap.spotlight .door-number{
        color: yellow;
    }

    .door-flap.spotlight .door-handle{
        background-color: yellow;
    }

    .door-leaf{
        background-color: #c56d35;
        box-sizing: border-box;
        position: relative;
        transition: .5s;
        width: 100%;
        height: 100%;
    }

    .door-handle{
        background: none;
        border: none;
        padding: 0;
        cursor: pointer;
        outline: inherit;
        background-color: #6e3c3e;
        border-radius: 50%;
        position: absolute;
        bottom: 100px;
        left: 0.5rem;
        height: 1rem;
        width: 1rem;
    }

    .door-number{
        color: #fff;
        margin: 0;
        font-weight: 700;
        font-size: 2rem;
        padding-top: 1rem;
        text-align: center;
    }

    .door-sill{
        background-color: #a8aaaa;
        left: -5%;
        position: relative;
        height: 5px;
        width: 110%;
    }
</style>
