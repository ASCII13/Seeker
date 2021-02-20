<template>
    <div class="error">
        <img :src="require('../assets/404.svg')" />
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
    font-size: 1.5rem;

    & > :last-child
        margin-top: 2rem;
        
    & > img
        width: 300px;
</style>