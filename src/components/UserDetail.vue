<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Many Details</p>
        <p>User name : {{ name }} </p>
        <p>User age : {{ userAge }} </p>
        <p> name uppercase: {{ changepropName() }} </p>
        <button @click="resetName"> reset me </button>
    </div>
</template>

<script>
import { eventBus } from '../main.js';

export default {
    props: {
        name : String,
        userAge : Number
    },
    methods: {
        changepropName() {
            return this.name.toUpperCase();
        },
        resetName() {
            this.name = 'Max';  
            this.$emit('nameToBeChange', this.name);
        }
    },
    created() {
        eventBus.$on('editAgeSibilings', (data)=> {
            this.userAge = data;
        });
    }
}
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>
