<template>
    <div class="error">
        <div>404</div>
        <div>Looks like we've got some broken links.</div>
        <router-link to="/">Take me home</router-link>
    </div>
</template>

<style lang="stylus" scoped>
.error
    display: flex;
    flex-direction: column; 
    justify-content: center;
    align-items: center;
    height: 100vh;
    font-size: 2rem;
    & > :not(:first-child)
        margin-top: 2rem;
</style>