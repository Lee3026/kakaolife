<template>
    <div class="themeTitle">
        <h3 class="title__h3">{{themeTitle}}</h3>
    </div>
</template>
<script>
export default {
    name: 'themeTitle',
    props: {
        themeTitle:{
            type: String,
            default: ""
        }
    },
}
</script>
<style lang="scss" scoped>
.themeTitle{
    overflow: hidden;
    display: block;
    width: 1296px;
    margin: 0 auto;
    height: auto;
    color: #000;
    &__h3{
        display: block;
        padding: 108px 0 36px;
        font-size: 36px;
        font-weight: 700;
        line-height: 54px;
        letter-spacing: -0.8px;
        text-align: left;
    }
}   
</style>