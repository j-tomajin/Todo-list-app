<template>
    <div 
        v-for="task in tasks"
        :key="task.id"
        class="tasks"
    >
        <Task 
            @toggle-complete="$emit('toggle-complete', task.id)"
            :task="task" /> 
    </div>
</template>

<script>
    import Task from './Task.vue';

    export default {
        name: 'Tasks',
        props: {
            tasks: Array,
        },
        components: {
            Task,
        },
        emits: ['toggle-complete']
    }
</script>

<style lang="scss" scoped></style>