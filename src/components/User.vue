<template>
    <div class="component">
        <h1>The User Component</h1>
        <p>I'm an awesome User!</p>
        <button @click="changeName"> change my name </button>
        <hr>
        <div class="row">
            <div class="col-xs-12 col-sm-6">
                <app-user-detail :userAge="age" :name="name" @nameToBeChange="name = $event" ></app-user-detail>
            </div>
            <div class="col-xs-12 col-sm-6">
                <app-user-edit :userAge="age"></app-user-edit>
            </div>
        </div>
    </div>
</template>

<script>
    import UserDetail from './UserDetail.vue';
    import UserEdit from './UserEdit.vue';

    export default {
        data: function() {
            return {
                name : 'just mary',
                age : 25,
            };
        },
        components : { 
            appUserDetail : UserDetail,
            appUserEdit : UserEdit
        },
        methods: {
            changeName() {
                this.name = 'Art Mary'
            }
        }
    }
</script>

<style scoped>
    div {
        background-color: lightblue;
    }
</style>
