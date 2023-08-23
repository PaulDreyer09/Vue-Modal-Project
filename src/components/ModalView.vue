<template>
    <div class="backdrop">
        <div class="ModalView" :class="{ sale: theme === 'sale'}">
            <h1>{{ header }}</h1>
            <p>{{ text }}</p>
        </div>
    </div>
</template>

<script>
    export default {
        name: "ModalView",
        props: ['header', 'text', 'theme'],
    }
</script>

<style scoped>
    .ModalView {
        width: 400px;
        padding: 20px;
        margin: 100px auto;
        background: white;
        border-radius: 10px;
    }

    .ModalView.sale{
        background: crimson;
        color: white;
    }

    .ModalView.sale h1{
        color: white;
    }

    .backdrop{ 
        top: 0;
        position: fixed;
        background-color: rgba(0,0,0,0.5);
        height: 100%;
        width: 100%;
    }

    h1{
        color:rgb(57, 105, 196);
    }
</style>