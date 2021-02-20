<template>
    <div class="home">
        <div class="header">
            <div v-if="$site.title" class="title">{{ $site.title }}</div>
            <div class="shortcuts">
                <router-link class="shortcut" v-for="(item, index) in shortcuts" :key="index" :to="item.link">{{ item.text }}</router-link>
            </div>
        </div>
        <div class="content">
            <img v-if="$themeConfig.avatar" class="avatar" :src="$themeConfig.avatar" />
            <div v-if="$themeConfig.nickname" class="nickname">{{ $themeConfig.nickname }}</div>
            <div v-if="$themeConfig.motto" class="motto">{{ $themeConfig.motto }}</div>
            <div v-if="$themeConfig.externalLinks" class="external-link">
                <a v-for="(item, index) in $themeConfig.externalLinks" :key="index" :href="item.link" target="_blank"><img :src="item.iconPath" /></a>
            </div>
        </div>
        <div class="footer">
            <div>© {{ $themeConfig.nickname }} | Powered by 
                <a target="_blank" href="https://vuepress.vuejs.org/">VuePress</a> & 
                <a target="_blank" href="https://github.com/ASCII13/Explorer">Explorer</a>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    computed: {
        shortcuts() {
            return this.$themeConfig.shortcuts;
        },
    }
}
</script>

<style lang="stylus" scoped>
$spacing = 20rem;

.home
    width: 100vw;
    height: 100vh;
    background-color: white;

.header
    display: flex;
    align-items: center;
    box-sizing: border-box;
    height: 66px;
    padding: 10px;
    font-size: 20px;

.title
    margin-left: $spacing;
    line-height: 46px;
    font-size: 25px;

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
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: calc(100vh - 66px - 6rem);

    & > div
        margin-top: 0.8rem;

.avatar
    height: 128px;
    border-radius: 50%;
    background-color: wheat;
    box-shadow: 0 0 0 0.22em #F2F6FC;

.nickname
    font-size: 1.5rem;

.motto
    font-size: 1.1rem;

.external-link
    & img
        width: 32px;
        height: 32px;
    
    & > a:not(:last-child)
        margin-right: 1rem;

.footer
    height: 6rem;
    line-height: 6rem;
    text-align: center;
    font-size: 1rem;

    & a
        color: black;
        text-decoration: none;
    
    & a:hover
        text-decoration: underline;
</style>