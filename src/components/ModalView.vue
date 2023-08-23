<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="ModalView" :class="{ sale: theme === 'sale'}">
            <slot>Fallback Content</slot>
            <div class="actions">
                <slot name="links"></slot>
            </div>

        </div>
    </div>
</template>

<script>
    export default {
        name: "ModalView",
        props: ['theme', 'handle', 'toggleModal'],
        methods: {
            closeModal(){
                this.$emit('close');
            }
        }
    }
</script>

<style >
    .ModalView {
        width: 400px;
        padding: 20px;
        margin: 200px auto;
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

    .actions{
        display: flex;
        justify-content: space-between;
        text-align: center;
    }

    .actions a{
        padding: 12px;

        border: 1px solid #eee;
        border-radius: 5px;

        font-size: 1.2em;
        font-weight: 600;
        
        color: #aaa;
        text-decoration: none;
    }
</style>