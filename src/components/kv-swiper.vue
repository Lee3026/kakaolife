<template>
<div class="kvSwiper">
  <div class="title">
    <h3 class="title__h3">{{swiperTitle}}</h3>
  </div>
  <div class="inner">
    <swiper class="swiper-wrapper" :options="swiperOptions" @swiper="onSwiper" @slideChange="onSlideChange">
      <swiper-slide class="swiper-slide" v-for="(name, index) in images" :key="index">
        <div class="contents">
          <div class="contents__text">
            <em>카카오스러움 첫번째.</em>
            <strong>가보지 않은 길을<br>두려워 하지 않습니다.</strong>
            <p>“가보지 않은 길은 위험하잖아?”<br>배는 정박해 있을 때 가장 안전하지만<br>그것은 배의 존재 이유가 아닙니다. 가보지 않은 길은<br>실패의 위험이 따르지만 우리는 개선보다 혁신의 길을<br>가는 사람들입니다. 문제 자체를 다시 정의하고<br>새로운 해답을 찾는 것에 집중합니다.<br>도전이 두렵기만 하다면 카카오를 떠날 때 입니다.</p>
            <div class="tag">
              <span>#개선아닌혁신</span>
              <span>#도전은거침없이</span>
            </div>
          </div>
          <div class="contents__visual">
            <video class="video" autoplay="" muted="" playsinline="" loop="">
              <source :src="require(`@/assets/img/${name}`)" type="video/mp4">
            </video>
          </div>
        </div>
      </swiper-slide>
    </swiper>
    <div  class="navigation">
      <button class="swiper-button-prev swiperBtn" slot="button-prev"></button>
      <div class="swiper-pagination" slot="pagination"></div>
      <button class="swiper-button-next swiperBtn" slot="button-next"></button> 
    </div>
  </div>
</div>
</template>

<script>
  import { Swiper, SwiperSlide, Pagination } from 'vue-awesome-swiper'
  import 'swiper/css/swiper.css'

  export default {
    name: 'swiper-example-pagination-fraction',
    title: 'Fraction pagination',
    props: {
        swiperTitle:{
            type: String,
            default: ""
        }
    },
    components: {
      Swiper,
      SwiperSlide
    },
     setup() {
      return {
        modules: [Pagination]
      };
    },
    data() {
      return {
        images: ['vod_culture1.mp4','vod_culture2.mp4','vod_culture3.mp4'],
        swiperOptions: {
          // centerPadding: '103px',
          centeredSlides: false,
          slidesPerView: 1.2,
          spaceBetween: 20,
          loop: false,
          navigation: {
            nextEl: '.swiper-button-next',
            prevEl: '.swiper-button-prev'
          },
          pagination: {
            el: '.swiper-pagination',
            type: 'fraction',
          },
        }
      }
    }
  }
</script>
<style lang="scss" scoped>
.kvSwiper{
  .title{
    display: block;
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
  .inner{
    min-width: 1259px;
    .swiper-wrapper {
      overflow: initial;
      padding-bottom: 37px;
      .swiper-slide {
        position: relative;
        top: 0;
        left: 0;
        display: block;
        margin-left: auto;
      }
      .contents{
        overflow: hidden;
        display: inline-flex;
        border-radius: 18px;
        box-shadow: 4px 12px 40px 6px rgb(0 0 0 / 9%);
        &__text{
        display: flex;
        flex-direction: column;
        width: 579px;
        padding: 84px 84px 72px;
        box-sizing: border-box;
        border-radius: 18px 0 0 18px;
        em{
          display: block;
          font-size: 14px;
          font-weight: 700;
          line-height: 20px;
          color: #999;
          letter-spacing: -0.2px;
        }
        strong{
          display: block;
          margin-top: 14px;
          font-size: 36px;
          line-height: 50px;
          font-weight: 700;
          letter-spacing: -0.8px;
        }
        p{
          display: flex;
          align-items: flex-end;
          flex: 1;
          padding-bottom: 36px;
          font-size: 16px;
          line-height: 28px;
          letter-spacing: -0.5px;
          color: #333;
        }
      
        }
        &__visual{
          .video{
            display: block;
            width: 100%;
            height: 100%;
            border-radius: 0 18px 18px 0;
          }
        }
      }
    }
    .navigation{
      display: block;
      position: relative;
      width: 171px;
      margin: 0 auto 72px;
      .swiperBtn{
        border: none;
        appearance: none;
        background: url('../assets/img/ico_jobs.png') 0 0 no-repeat;
        background-size: 260px 251px;
        position: absolute;
        bottom: auto;
        left: auto;
        width: 26px;
        height: 26px;
        background-position: -40px -160px;
        &::after {
          display: none;
        }
      }
      .swiper-button-prev{
        right: auto;
        left: 0;
        transform: rotate(180deg);
        &.swiper-button-disabled{
          background-position-x: -71px;
          cursor: default;
        }
      }
     .swiper-button-next {
        background-position: -40px -160px;
        &.swiper-button-disabled{
          background-position-x: -71px;
          cursor: default;
        }
      }
      .swiper-pagination {
        font-size: 16px;
        line-height: 26px;
        font-weight: 700;
        text-align: center;
        position: absolute;
        bottom: auto;
        left: auto;
        width: 100%;
        height: 100%;
      }
    }
  } 
}  
</style>