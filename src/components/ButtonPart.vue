<template>
    <button class="button" type="button">{{ text }}</button>
</template>

<script>
export default {
    name: 'ButtonPart',
    props: {
        text: String
    }
}
</script>

<style scoped>
.button{
    box-sizing: border-box;
    background: none;
    background-color: rgba(255, 255, 255, 0.596);
    border: none;
    border-radius: 0.2rem;
    display: block;
    cursor: pointer;
    font-family: inherit;
    font-weight: 700;
    margin: 0 auto;
    outline: inherit;
    padding: 0.5rem 1rem;
    transition: .3s;
    width: 100px;
}

.button:hover{
    background-color: transparent;
    color: #fff;
}
</style>