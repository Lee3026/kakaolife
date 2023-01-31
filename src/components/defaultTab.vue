<template>
  <div class="mainTab">
      <div class="title">
        <h3 class="title__h3">{{tabTitle}}</h3>
    </div>
    <div class="tabs">
      <tabMenu
        v-for="item in list"
        v-bind="item" :key="item.id"
        v-model="currentId"/>
    </div>
    <div class="contents">
      <transition>
        <div v-show="currentId === 0" class="tab__contents">
            <div>
                <strong class="cont__title title1">카카오 베네핏</strong>
                <p class="cont__desc">크루들의 업무 몰입 뿐 아니라 자기개발, 여가/취미 활동 지원을<br>위한 카카오베네핏! <br>연 360만원까지 사용할 수 있는 개인별 베네핏<br>카드를 지급합니다.</p>
            </div>
            <div>
                <strong class="cont__title title2">복지대출 지원</strong>
                <p class="cont__desc">크루들의 복리증진과 생활안정을 목적으로 주택구입 및 임차,<br>생활안정을 위해 최대 1억 5천만원까지 대출금을 지원하고, 대출자금의<br>2% 초과 이자에 대해 지원합니다.</p>
            </div>
            <div>
                <strong class="cont__title title3">어린이집</strong>
                <p class="cont__desc">아이와 함께하는 출퇴근이 어색하지 않아요!<br>만 0세부터 5세반까지 구성된 학급과 안전한 먹거리, 최고시설의<br>교육환경을 갖추고 있으며, 푸르니 표준보육과정을 기본으로 체육,음악,영어 등<br>카카오만의 특성화 프로그램이 함께 운영되고 있습니다.</p>
            </div>
            <div>
                <strong class="cont__title title4">경조사 지원</strong>
                <p class="cont__desc">크루 및 크루 가족의 경조사 발생 시 축하와 조의의 마음을 전하고자<br>경조휴가와 함께 경조사비/화환/용품 등을 제공합니다.</p>
            </div>
            <div>
                <strong class="cont__title title5">가족사랑지원</strong>
                <p class="cont__desc">크루가 불의의 사고 또는 질병으로 사망 시, 크루 가족이 안정적으로<br>생활계획을 세울 수 있도록 보험금(2억원)을 일시금으로 지원합니다.</p>
            </div>
            <div>
                <strong class="cont__title title6">명절선물</strong>
                <p class="cont__desc">풍요로운 명절. 감사의 마음을 전하기 위해<br>설과 추석에 각각 30만원씩 카카오페이머니(현금)를 지급합니다.</p>
            </div>
        </div>
        <div v-show="currentId === 1" class="tab__contents">bb</div>
        <div v-show="currentId === 2" class="tab__contents">cc</div>
      </transition>
    </div>
  </div>
</template>

<script>
import tabMenu from './tab-menu'
export default {
  components: { tabMenu },
   props: {
        tabTitle:{
            type: String,
            default: ""
        }
    },
  data() {
    return {
      currentId: 0,
      list: [
        { id: 0, label: '생활 속 지원' },
        { id: 1, label: '업무 몰입 지원' },
        { id: 2, label: '휴식 지원' }
      ]
    }
  },
  computed: {
    current() {
      return this.list.find(el => el.id === this.currentId) || {}
    }
  }
}
</script>

<style lang="scss" scoped>
.title{
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
.tabs{
    display: flex;
}
.contents {
    padding-bottom: 36px;
    position: relative;
    overflow: hidden;
  .tab__contents{
    display: flex;
    flex-wrap: wrap;
    div{
        width: 594px;
        margin-top: 72px;
        padding-top: 48px;
        border-top: 1px solid #eee;
        &:first-child,
        &:nth-child(2){
            margin-top: 0;
            border-top: none;
        }
        &:nth-child(2n){
            margin-left: 108px;
        }
        .cont__title{
            display: block;
            font-size: 26px;
            font-weight: 700;
            line-height: 36px;
            letter-spacing: -0.6px;
            &::before{
                display: block;
                overflow: hidden;
                width: 46px;
                height: 46px;
                margin-bottom: 24px;
                font-size: 0px;
                line-height: 0;
                text-indent: -9999px;
                background: url('../assets/img/ico_benefit.png') 0 0 no-repeat;
                background-size: 556px 97px;
                content: '';
            }
        }
        .title2{
            &::before{
                background-position-x: -51px;
            }
        }
        .title3{
            &::before{
                background-position-x: -102px;
            }
        }
        .title4{
            &::before{
                background-position-x: -153px;
            }
        }
        .title5{
            &::before{
                background-position-x: -204px;
            }
        }
        .title6{
            &::before{
                background-position-x: -255px;
            }
        }
        .cont__desc{
            margin: 24px 39px 0 0;
            font-size: 18px;
            line-height: 28px;
            letter-spacing: -0.5px;
            word-break: keep-all;
        }
    }
    }
}
.item {
  box-sizing: border-box;
  padding: 10px;
  width: 100%;
  transition: all 0.8s ease;
}
/* 트랜지션 스타일 */
.v-leave-active {
  position: absolute;
}
.v-enter {
  transform: translateX(-100%);
}
.v-leave-to {
  transform: translateX(100%);
}
</style>