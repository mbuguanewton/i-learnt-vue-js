<template>
    <div :class="[task.reminder ? 'reminder' : '', 'task']">
        <div
            class="task__wrapper"
            @dblclick="$emit('toggle-reminder', task.id)"
        >
            <h3>{{ task.text }}</h3>
            <p>{{ task.day }}</p>
        </div>
        <i @click="$emit('delete-task', task.id)" class="fas fa-trash"></i>
    </div>
</template>

<script>
export default {
    name: 'TaskItem',
    props: {
        task: Object,
    },
}
</script>

<style lang="scss" scoped>
.reminder {
    border-left: 6px solid #56bd8d;
}
.task {
    height: auto;
    padding: 10px 20px;
    background: #f2f2f2;
    border-radius: 10px;
    margin-bottom: 0.8rem;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;

    &__wrapper {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        height: 100%;
        width: 100%;

        h3 {
            margin-bottom: 5px;
        }
    }

    & .fas {
        transition: 0.2s ease-in;
        &:hover {
            color: #be2342;
        }
    }
}
</style>
