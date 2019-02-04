<template>
    <div class="new-task">
        <input
                v-model="name"
                @keydown.enter="add"
                class="form-element"
                placeholder="Nova tarefa?"
                type="text">
        <button
                class="form-element"
                @click="add">+</button>
    </div>
</template>

<script>
    export default {
        data(){
            return{
                name: ''
            }
        },
        methods:{
            add(){
                this.$emit('taskAdded',{name: this.name})
                this.name = ''
            }
        }
    }
</script>

<style scoped>
    .new-task{
        margin: 2rem;
    }

    .form-element{
        outline: none;
        font-size: 2rem;
        border: 1px solid #FFF;
        padding: .5rem .8rem .5rem;
        color: #FFF;
    }

    input.form-element{
        width: 500px;
        background: #FFF2;
        border-top-left-radius: .5rem;
        border-bottom-left-radius: .5rem;
    }

    button.form-element{
        border-left: none;
        background-color: #2196F3;
        border-top-right-radius: .5rem;
        border-bottom-right-radius: .5rem;
    }
</style>