<template>
    <button 
        @click="handleClick()"
        class="btn"
        :style="{background: bg_color}">{{ text }}</button>
</template>

<script>
    export default {
        name: 'Button',
        props: {
            text: {
                type: String,
                default: 'This is a button'
            },
            bg_color: 'green'
        },
        methods: {
            handleClick() {
                this.$emit('btn-click')
            }
        },
    }
</script>

<style lang="scss" scoped>
    .btn {
        outline: 0;
        border: 0;
        // padding: 12px 16px;
        border-radius: 4px;
    }
</style>