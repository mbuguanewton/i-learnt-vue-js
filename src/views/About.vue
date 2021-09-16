<template>
    <div class="about">
        <h3>Version 1.0.0</h3>
        <router-link class="back-home" to="/">Back Home &rarr;</router-link>
    </div>
</template>

<style lang="scss" scoped>
.about {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    margin-top: 2rem;

    & .back-home {
        text-decoration: none;
    }
}
</style>
