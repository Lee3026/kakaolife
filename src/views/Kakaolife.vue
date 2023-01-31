<template>
  <div class="kakaolife">
    <subTitle :title="title" />
    <kvSwiper :swiperTitle="swiperTitle" />
    <Tab :tabTitle="tabTitle"/>
    <div class="location">
      <h3 class="title">오피스 위치</h3>
      <div class="location__inner">
        <div class="card">
          <a href="javascript:;" class="card__link">
              <div>
                  <strong class="card__title">카카오 본사</strong>
                  <p class="card__address">제주특별자치도 제주시 첨단로 242</p>
              </div>
          </a>
        </div>
        <div class="card">
          <a href="javascript:;" class="card__link link2">
              <div>
                  <strong class="card__title">카카오 본사</strong>
                  <p class="card__address">제주특별자치도 제주시 첨단로 242</p>
              </div>
          </a>
        </div>
      </div>
    </div>
    <LocationCard :card="card"/>
  </div>
</template>
<script>
import subTitle from '../components/sub-title.vue';
import kvSwiper from '../components/kv-swiper.vue';
import Tab from '../components/tab.vue';
import LocationCard from '@/components/location-card.vue';

export default {
  name: 'Kakaolife',
  components: {
    subTitle,
    kvSwiper,
    Tab,
    LocationCard,
  },
  data() {
    return {
      title: "카카오 생활",
      swiperTitle: "카카오 문화",
      tabTitle:"크루 혜택",
      card: [
        { id: 1, label: '카카오 본사', content: '제주특별자치도 제주시 첨단로 242' },
        { id: 2, label: '판교아지트', content: '경기도 성남시 분당구 판교역로166 지하 1층' },
      ]
    }
  },
}
</script>
<style lang="scss" scoped>
.kakaolife{
  width: 1296px;
  margin: 0 auto;
  padding-bottom: 180px;
  .location{
    h3{
      display: block;
        padding: 108px 0 36px;
        font-size: 36px;
        font-weight: 700;
        line-height: 54px;
        letter-spacing: -0.8px;
        text-align: left;
    }
    &__inner{
      display: inline-flex;
      .card{
        &:nth-child(3n-1){
          margin: 0 36px;
        }
        &__link{
          background: url('../assets/img/img_office_jeju.jpg') 0 0 /100% 224px no-repeat;
          display: inline-block;
          width: 408px;
          border-radius: 18px;
          padding-top: 224px;
          box-shadow: 4px 12px 40px 6px rgb(0 0 0 / 9%);
          transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        }
        &__link:hover {
          transform: translateY(-5px);
          box-shadow: 4px 12px 30px 6px rgb(0 0 0 / 18%);
        }
        .link2{
          background: url('../assets/img/img_office_pangyo.jpg') 0 0 /100% 224px no-repeat;
        }
        &__title{
          display: block;
          padding: 24px 24px 12px;
          font-size: 26px;
          line-height: 38px;
          letter-spacing: -0.6px;
          color: #000;
        }
        &__address{
          padding: 0 24px 48px;
          font-size: 16px;
          line-height: 26px;
          color: #333;
          letter-spacing: -0.6px;
        }
      }
    }
  }
}
</style>
