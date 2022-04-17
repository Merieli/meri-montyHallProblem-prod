<template>
    <div class="door-gift">
        <div class="gift-cover"></div>
        <div class="gift-tieHorizontal"></div>
        <div class="gift-tieVertical"></div>
    </div>
</template>

<script>
export default {
    name: 'GiftPart'
}
</script>

<style scoped>
    .door-gift{
        background-color: #49c149;
        height: 60px;
        width: 60px;
        position: absolute;
        bottom: 0;
        left: calc((100% - 60px)/ 2);
        z-index: -1;
    }

    .gift-cover{
        background-color: #97e88c;
        left: -10%;
        position: relative;
        height: 15px;
        width: 120%;
    }


    .gift-tieHorizontal{
        position: relative;
        height: 12px;
        width: 100%;
        background-color: red;
        top: 10px;
    }

    .gift-tieVertical{
        position: absolute;
        height: 100%;
        width: 12px;
        background-color: red;
        top: 0;
        left: calc((100% - 12px) /2);
    }
</style>