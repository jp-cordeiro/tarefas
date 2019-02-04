<template>
    <div class="task-grid">
        <template v-if="tasks.length > 0">
            <Task
                    v-for="(task,i) in tasks"
                    :key="task.name"
                    @taskDeleted="$emit('taskDeleted',i)"
                    :task="task"/>
        </template>
        <template v-else>
            <span>Sua vida está em dia :D</span>
        </template>
    </div>
</template>

<script>

    import Task from './Task'

    export default {
        components:{
            Task
        },
        props:{
            tasks:{
                type: Array,
                required: true
            }
        }
    }
</script>

<style scoped>
    .task-grid{
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
    }

    .task-grid .task{
        margin: .8rem;
    }
</style>