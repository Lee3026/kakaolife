<template>
  <div class="card">
    <a href="javascript:;" class="card__img" 
      :style="{ backgroundImage : `url(${card.image})`}"
      v-for="item in list"
      v-bind="item" :key="item.id"
      >
        <div>
          <strong class="card__title">{{label}}</strong>
          <p class="card__address">{{content}}</p>
        </div>
      </a>
  </div>
</template>
<script>
export default {
  props: {
    id: Number,
    label: String,
    value: Number
  },
  data() {
    return {
        card: [
        { id: 1, label: '카카오 본사', content: '제주특별자치도 제주시 첨단로 242' },
        { id: 2, label: '판교아지트', content: '경기도 성남시 분당구 판교역로166 지하 1층' },
      ]
    }
  },
}
</script>