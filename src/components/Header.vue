<template>
    <header>
        <h1>{{ title }}</h1>
        <Button
            v-show="homePage"
            :label="showAddTask ? 'Close' : 'Add Task'"
            color="#2c3e50"
            @btn-click="$emit('toggle-add-task')"
        />
    </header>
</template>

<script>
import Button from './Button'

export default {
    name: 'Header',
    props: {
        title: String,
        showAddTask: Boolean,
    },

    components: {
        Button,
    },
    computed: {
        homePage() {
            if (this.$route.path === '/') {
                return true
            } else {
                return false
            }
        },
    },
}
</script>

<style lang="scss" scoped>
header {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;

    & h1 {
        font-size: 1.5rem;
    }
}
</style>
