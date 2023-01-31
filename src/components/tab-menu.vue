<template>
<div class="tabMenu">
    <ul class="tabList">
        <li @click="$emit('input', id)" :class="[active, 'tabItem']">
            <a href="javascript:;" class="tabLink">{{ label }}</a>
        </li>
    </ul>
</div>
</template>

<script>
export default {
  props: {
    id: Number,
    label: String,
    value: Number
  },
  computed: {
    active() {
      return this.value === this.id ? 'active' : false
    }
  }
}
</script>

<style lang="scss" scoped>
.tabMenu{
  
  ul{
    display: flex;
    margin: 12px 0 48px;
    li{
      margin-right: 12px;
      border-radius: 2px 2px 0 0;
      background: #fff;
      color: #311d0a;
      line-height: 24px;
      &:not(.on) {
        a:hover {
          color: #fff;
          background: #666;
        }
      }
      a{
        color: #333;
        display: block;
        padding: 9px 20px 11px;
        border-radius: 30px;
        font-size: 16px;
        line-height: 24px;
        font-weight: 700;
        letter-spacing: -0.5px;
        background: #eee;
      }
      // a:hover {
      //   border-radius: 2px 2px 0 0;
      //   background: #eeeeee;
      // }
    }
  .active a{
    color: #fff;
    background: #1a1a1a;
    }
  }
}
</style>