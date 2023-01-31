<template>
  <div class="tab">
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
        <div class="contents__inner">
            <div v-show="currentId === 0" class="contents__item">
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
            <div v-show="currentId === 1" class="contents__item">
                <div>
                    <strong class="cont__title title7">사내/사외 교육</strong>
                    <p class="cont__desc">크루들의 성장을 위해 각종 MOOC, 사외교육, 해외 컨퍼런스를<br>지원하고 있어요. 특정한 주제에 대해 외부연사를 모시고 북토크/세미나가<br>열리기도 하고, 크루가 직접 진행하는 강연도 진행됩니다. 크루와 크루,<br>크루와 지식을 이어주는 공유의 장을 넘어, 주도적 성장에 필요한 지식과 스킬,<br>콘텐츠를 함께 쌓아나가고 있어요.</p>
                </div>
                <div>
                    <strong class="cont__title title8">전자도서관/크루의 서재</strong>
                    <p class="cont__desc">책을 통해 항상 가까이에서 크루의 성장을 돕습니다.<br>크루들의 주도적인 성장과 역량 향상을 위해 업무 관련 도서를 전자도서관에서 ebook으로 지원합니다. 매월 핫한 주제에 대한 책들를 큐레이션 하고, 업무나<br>관심분야가 비슷한 크루들이 추천하는 책들도 살펴볼 수 있어서 어떤 책을 읽어<br>봐야할지 막막할 때 도움을 받을 수 있어요.</p>
                </div>
                <div>
                    <strong class="cont__title title9">통근버스/순환버스</strong>
                    <p class="cont__desc">장거리 출퇴근 걱정하지 마세요!<br>서울/경기 지역 내의 다양한 셔틀 노선을 제공하고,<br> 판교역 부근을 순환하는 순환버스를 운영하고 있어요.</p>
                </div>
                <div>
                    <strong class="cont__title title10">먹거리/교통비 지원</strong>
                    <p class="cont__desc">상시로 제공되는 음료 및 간식, 그리고 업무에 몰두하느라 시간 가는줄<br>몰랐던 크루들을 위해 야근 시 저녁 식대를 실비 지원하고, 밤 10시 이후엔<br>안전한 귀가를 위해 택시비를 실비 지원하고 있어요.</p>
                </div>
            </div>
            <div v-show="currentId === 2" class="contents__item">
                <div>
                    <strong class="cont__title title11">리프레시 제도</strong>
                    <p class="cont__desc">3년마다 1개월의 휴가가 생긴다고?<br>바쁘게 달려온 크루들의 리프레시를 위해 만 3년 근무마다 1개월 유급휴가와<br>휴가비 200만원을 지급합니다. 낯선 도시에서 한 달 살기, 평일 카페투어 다니기<br>등 직장인이 되고 쉽게 해보지 못한 것들을 하며 리프레시를 할 수 있습니다.</p>
                </div>
                <div>
                    <strong class="cont__title title12">호텔/리조트 제휴</strong>
                    <p class="cont__desc">국내 최상급 호텔/리조트를 기업 할인가로 즐기자!<br>크루의 충분한 휴식을 위해 회사가 보유한 국내 최상급 호텔/리조트를<br>기업 할인가로 제공합니다.</p>
                </div>
                <div>
                    <strong class="cont__title title13">휴식공간</strong>
                    <p class="cont__desc">업무 중 잠깐의 휴식을 통한 충전이 필요할 때!<br>사내 카페에서 다양한 메뉴를 맛볼 수 있고, 휴게공간에서 안마의자, 수면 등을<br>통해 잠깐의 충전 시간을 가질 수 있어요.</p>
                </div>
                <div>
                    <strong class="cont__title title14">동호회 지원</strong>
                    <p class="cont__desc">들어보셨나요? 카카오에는 40개가 넘는 동호회가 있다는 사실!<br>업무를 벗어나 취미가 비슷한 크루들과의 만남의 기회도 만들어보세요.<br>활발한 동호회 활동을 할 수 있도록 매달 지원비를 제공합니다.</p>
                </div>
            </div>
        </div>
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
.tab{
    width: 1296px;
    margin: 0 auto;
    color: #000;
    overflow: hidden;
    display: block;
    min-width: 1296px;
    height: auto;
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
        .contents__item{
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
                .title7{
                    &::before{
                        background-position-x: -408px;
                    }
                }
                .title8{
                    &::before{
                        background-position-x: -510px;
                    }
                }
                .title9{
                    &::before{
                        background-position-y: -51px;
                    }
                }
                .title10{
                    &::before{
                        background-position-x: -408px;
                    }
                }
                .title11{
                    &::before{
                        background-position: -102px -51px;
                        
                    }
                }
                .title12{
                    &::before{
                        background-position: -153px -51px;
                    }
                }
                .title13{
                    &::before{
                        background-position: -204px -51px;
                    }
                }
                .title14{
                    &::before{
                        background-position: -255px -51px;
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
    // .item {
    //   box-sizing: border-box;
    //   padding: 10px;
    //   width: 100%;
    //   transition: all 0.8s ease;
    // }
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