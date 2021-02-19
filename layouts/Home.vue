<template>
    <div class="home">
        <div class="header">
            <div class="title">{{ title }}</div>
            <div class="shortcuts">
                <router-link class="shortcut" v-for="(item, index) in shortcuts" :key="index" :to="item.link">{{ item.text }}</router-link>
            </div>
        </div>
        <div class="content"></div>
    </div>
</template>

<script>
export default {
    computed: {
        title() {
            return this.$site.title;
        },
        shortcuts() {
            console.log(`获取到的themeConfig是${JSON.stringify(this.$themeConfig)}`);
            return this.$themeConfig.shortcuts;
        }
    }
}
</script>

<style lang="stylus" scoped>
$spacing = 20rem;

.home
    width: 100vw;
    height: 100vh;
    background-color: gray;

.header
    display: flex;
    align-items: center;
    box-sizing: border-box;
    height: 66px;
    padding: 10px;
    background-color: indianred;
    font-size: 20px;

.title
    margin-left: $spacing;
    line-height: 46px;

.shortcuts
    margin-right: $spacing;
    margin-left: auto;

.shortcut
    display: inline-block;
    line-height: 46px;
    padding: 0 1rem;
    color: black;
    text-decoration: none;

.content
    min-height: calc(100vh - 66px);
</style>