<template>
    <form @submit="onSubmit" class="add-form">
        <div class="form-control">
            <label>Task</label>
            <input
                type="text"
                v-model="text"
                name="text"
                placeholder="Add Task"
            />
        </div>
        <div class="form-control">
            <label>Day & Time</label>
            <input
                type="text"
                v-model="day"
                name="day"
                placeholder="Add Day & Time"
            />
        </div>
        <div class="form-control-check">
            <input type="checkbox" v-model="reminder" name="reminder" />
            <label>Set Reminder</label>
        </div>

        <input type="submit" value="Save Task" class="btn btn-block" />
    </form>
</template>

<script>
export default {
    name: 'AddTask',
    data() {
        return {
            text: '',
            day: '',
            reminder: false,
        }
    },

    methods: {
        onSubmit(e) {
            e.preventDefault()

            if (!this.text) {
                alert('Please add task')
            }

            const newTask = {
                id: Math.floor(Math.random() * 10000),
                text: this.text,
                day: this.day,
                reminder: this.reminder,
            }

            this.$emit('add-task', newTask)

            this.text = ''
            this.day = ''
            this.reminder = false
        },
    },
}
</script>

<style lang="scss" scoped>
.add-form {
    padding: 0;
    margin-bottom: 40px;
    width: 100%;
}
.form-control {
    width: 100%;
    margin: 10px 0;
    display: flex;
    flex-direction: column;
    align-items: flex-start;

    & label {
        display: block;
        text-align: left;
        margin-bottom: 5px;
    }

    & input {
        width: 95%;
        height: 2rem;
        padding: 5px;
        padding-left: 10px;
        border: 1px solid #eee;
        background: #f2f2f2;
        border-radius: 5px;
        font-size: 1rem;
        font-family: 'Space Mono';

        &:focus {
            outline-color: #2c3e50;
            border-radius: 10px;
        }
    }
}
.form-control-check {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    margin-bottom: 10px;
    padding: 5px;
    height: 2.5rem;
}

.btn {
    width: 100%;
    height: 3rem;
    border: none;
    border-radius: 10px;
    background: #2c3e50;
    color: #fff;
    font-family: 'Space Mono';
    font-size: 1rem;
}
</style>
