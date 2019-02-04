<template>
    <div class="task"
         :class="stateClass"
    >
        <span @click="$emit('taskDeleted',task)" class="close">x</span>
        <p>{{ task.name }}</p>
    </div>
</template>

<script>
    export default {
        props:{
            task:{
                type: Object,
                required: true
            }
        },
        computed:{
            stateClass(){
                return{
                    pending: this.task.pending,
                    done: !this.task.pending
                }
            }
        }
    }
</script>

<style scoped>
    .task{
        position: relative;
        box-sizing: border-box;
        width: 15rem;
        height: 7rem;
        padding: .5rem;
        border-radius: .5rem;
        font-size: 2rem;
        font-weight: 300;
        cursor: pointer;
        user-select: none;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .pending{
        border-left: .8rem solid #B73229;
        background-color: #F44336;
    }

    .done{
        color: #DDD;
        border-left: .8rem solid #0A8F0B;
        background-color: #4CAF50;
        text-decoration: line-through;
    }

    .pending .close{
        background-color: #B73229;
    }

    .done .close{
        background-color: #0A8F08;
    }

    .close{
        position: absolute;
        right: 10px;
        top: 10px;
        font-size: .9rem;
        font-weight: 600;
        height: 1.5rem;
        width: 1.5rem;
        border-radius: .8rem;
        display: flex;
        justify-content: center;
    }

</style>