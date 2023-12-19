<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" v-bind:class="{ sale: theme === 'sale', 
        someClsss: true, anotherClass: aPropUndefined}">
            <h1>{{ header }}</h1>
            <p>{{ text }}</p>
            <slot>this won't show unless there's no default slot template specified in the parent component</slot>
            <div>
                <slot name="links2"></slot>
            </div>
            <div>
                <slot name="links"></slot>
            </div>
            <p>{{ aHardCodedAttribute }}</p>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['aHardCodedAttribute', 'header', 'text', 'theme', 'aPropUndefined'],
        methods: {
            closeModal() {
                this.$emit('close')
            }
        }
    }
</script>

<style>
    .modal {
        width: 400px;
        padding: 20px;
        margin: 100px auto;
        background: white;
        border-radius: 10px;
    }
    .backdrop {
        top: 0;
        position: fixed;
        background: rgb(0,0,0,0.5);
        width: 100%;
        height: 100%;
    }
    .modal h1 {
        color: #03cfb4;
        border: none;
        padding: 0;
    }
    .modal p {
        font-style: normal;
    }
    .modal.sale {
        background: crimson;
        color: white;
    }
    .modal.sale h1 {
        color: white;
    }
</style>