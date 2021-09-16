<template>
    <button @click="toggle()" :style="{ background: color }" class="btn">
        {{ label }}
    </button>
</template>

<script>
export default {
    name: 'Button',
    props: {
        color: String,
        label: String,
    },
    methods: {
        toggle() {
            this.$emit('btn-click')
        },
    },
}
</script>
<style lang="scss" scoped>
.btn {
    height: 2.5rem;
    width: auto;
    min-width: 30%;
    border: none;
    border-radius: 5px;
    font-family: 'Space Mono';
    font-size: 1rem;
    color: #fff;
}
</style>
