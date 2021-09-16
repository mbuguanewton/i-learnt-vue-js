<template>
    <div class="container">
        <Header
            title="Task Tracker"
            @toggle-add-task="toggleAddTask"
            :showAddTask="showAddTask"
        />

        <router-view :showAddTask="showAddTask"></router-view>
        <Footer />
    </div>
</template>

<script>
import Header from './components/Header'
import Footer from './components/Footer'

export default {
    name: 'App',
    components: {
        Header,
        Footer,
    },
    data() {
        return {
            tasks: [],
            showAddTask: false,
        }
    },
    methods: {
        toggleAddTask() {
            this.showAddTask = !this.showAddTask
        },
    },
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400;1,700&display=swap');

#app {
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
* {
    margin: 0;
    padding: 0;
}

html {
    font-family: 'Space Mono', monospace;
}

h1,
h2,
h3,
h4,
h5,
h6 {
    font-weight: 700;
}

a,
p,
small,
span,
li {
    font-weight: 400;
}

// common styles
.container {
    height: auto;
    margin: 1rem auto;
    border: 1px solid #eee;
    padding: 20px;
    border-radius: 10px;
    width: 50%;
}

@media screen and (max-width: 768px) {
    .container {
        width: 70%;
    }
}
@media screen and (min-width: 768px) {
    .container {
        width: 50%;
    }
}
@media screen and (min-width: 1056px) {
    .container {
        width: 30%;
    }
}
</style>
