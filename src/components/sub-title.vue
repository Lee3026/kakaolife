<template>
    <div class="title">
        <h2 class="title__h2">{{title}}</h2>
    </div>
</template>
<script>
export default {
    name: 'subTitle',
    props: {
        title:{
            type: String,
            default: ""
        }
    },
}
</script>
<style lang="scss" scoped>
.title{
    overflow: hidden;
    display: block;
    width: 1296px;
    margin: 0 auto;
    height: auto;
    margin-top: 108px;
    color: #000;
    &__h2{
        text-align: left;
        display: block;
        font-size: 46px;
        line-height: 56px;
        letter-spacing: -1px;
        &::before{
            content: '';
            width: 66px;
            height: 66px;
            margin: -5px 24px 0 0;
            display: inline-block;
            overflow: hidden;
            background: url(../assets/img/ico_tit_culture.gif) 0 0 no-repeat;
            background-size: 66px 66px;
            vertical-align: top;
        }
    }
}   
</style>