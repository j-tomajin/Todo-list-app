<template>
    <div :class="[task.complete ? 'complete' : '', 'task']">
        <Button 
            class="btn" 
            text="" :bg_color="[task.complete ? 'black' : 'transparent']" 
            @btn-click="$emit('toggle-complete', task.id)"
        />
        <h3>{{ task.text }}</h3>
    </div>
</template>

<script>
    import Button from './Button.vue';

    export default {
        name: 'Task',
        props: {
            task: Object,
        },
        components: {
            Button,
        }
    }
</script>

<style lang="scss" scoped>
    .task {
        display: flex;
        align-items: center;
        justify-content: start;
        gap: 24px;
    }

    .complete {
        color: rgb(112, 112, 112);
        text-decoration: line-through;
    }

    .btn {
        padding: 12px;
        border: 1px solid #444;
        border-radius: 50px;
    }
</style>