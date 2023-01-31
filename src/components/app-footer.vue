<template>
  <footer class="footer">
    <h3>카카오의 다양한 소식을 확인하세요</h3>
    <ul class="footer__sns">
        <li>
            <a href="javascript:;" class="icon kakao">카카오톡</a>
        </li>
        <li>
            <a href="javascript:;" class="icon insta">인스타그램</a>
        </li>
        <li>
            <a href="javascript:;" class="icon youtube">유튜브</a>
        </li>
        <li>
            <a href="javascript:;" class="icon linkin">링크드인</a>
        </li>
         <li>
            <a href="javascript:;" class="icon facebook">페이스북</a>
        </li>
    </ul>
    <div class="footer__info">
        <div class="info__left">
            <a href="javascript:;" class="privacy">개인정보처리방침</a>
            <a href="javascript:;" class="use">이용약관</a>
            <div class="lang" :class="{active:hasActive}">
                <button class="lang__btn"
                @click="hasActive = !hasActive"
                >한국어</button>
                <div class="lang__option">
                    <a href="javascript:;" class="lang__item ko">한국어</a>
                    <a href="javascript:;" class="lang__item en">English</a>
                </div>
            </div>
            <div class="info__copyright">© Kakao Corp. All rights reserved.</div>
        </div>
        <div class="info__right" :class="{open:hasOpen}">
            <button class="site__btn"
            @click="hasOpen = !hasOpen">관련사이트</button>
            <div class="site__option">
                <a href="javascript:;" class="site__item kakao">카카오</a>
                <a href="javascript:;" class="site__item daum">다음</a>
            </div>
        </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'appFooter',
  data(){
    return {
      hasActive: false,
      hasOpen: false
    };
  },
}
</script>
<style scoped lang="scss">
.footer{
    min-width: 1296px;
    border-top: 1px solid #ebebeb;
    width: 1296px;
    padding: 59px 0 36px;
    margin: 0 auto;
    button{
        border: 0 none;
        background-color: transparent;
        cursor: pointer;
        line-height: 1.5;
    }
    h3{
        display: block;
        font-size: 32px;
        font-weight: 700;
        line-height: 47px;
        letter-spacing: -0.8px;
        text-align: center;
    }
    &__sns{
            display: flex;
            justify-content: center;
            padding: 24px 0 48px;
        a{
            width: 60px;
            height: 60px;
            margin: 0 12px;
        }
        a:hover{
            background-position-x: -200px;
        }
        .icon{
            display: block;
            overflow: hidden;
            font-size: 0px;
            line-height: 0;
            text-indent: -9999px;
            background: url('../assets/img/ico_jobs.png') 0 0 no-repeat;
            background-size: 260px 251px;
        }
        .kakao{
            background-position-x: -140px;
        }
        .insta{
            background-position: -140px -60px;
        }
        .youtube{
            background-position: -140px -120px;
        }
        .linkin{
            background-position: -140px -180px;
        }
        .facebook{
            background-position-y: -191px;
        }
        .facebook:hover{
            background-position-x: -60px;
        }
    }
    &__info{
        display: flex;
        justify-content: space-between;
        .info__left{
            font-size: 0;
            a{
                display: inline-flex;
                padding: 12px 0 10px;
                font-size: 14px;
                color: #888;
                line-height: 20px;
                letter-spacing: -0.4px;
                vertical-align: bottom;
            }
            a:nth-of-type(1){
                font-weight: 700;
                color: #333;
            }
            .privacy{
                margin-right: 24px;
            }
            .lang{
                display: inline-block;
                position: relative;
                height: 42px;
                padding: 0 14px;
                &.active{
                    .lang__btn{
                        color: #333;    
                        font-weight: 700;
                    }
                    .lang__option{
                        display: block;
                    }
                    .lang__btn{
                        &::after{
                            background-position-y: -60px;
                        }
                    }
                }
                &__btn{
                    padding: 12px 10px 10px;
                    font-size: 14px;
                    color: #777;
                    line-height: 20px;
                    letter-spacing: -0.2px;
                    vertical-align: top;
                    &::after{
                        display: inline-block;
                        overflow: hidden;
                        font-size: 0px;
                        line-height: 0;
                        text-indent: -9999px;
                        background: url('../assets/img/ico_jobs.png') 0 0 no-repeat;
                        background-size: 260px 251px;
                        vertical-align: top;
                        content: '';
                        width: 9px;
                        height: 9px;
                        margin: 6px 4px 0;
                        background-position: -120px -40px;
                        }
                    }
                    &__option{
                        display: none;
                        position: absolute;
                        bottom: 42px;
                        left: 0;
                        z-index: 1;
                        padding: 16px 24px;
                        border-radius: 18px;
                        background: #eee;
                    }
             
                }
        }
        .info__copyright{
            display: block;
            font-size: 14px;
            color: #888;
            line-height: 20px;
        } 
        .info__right{
            position: relative;
            margin: 12px 0 5px;
            a:nth-of-type(1){
                font-weight: 700;
                color: #333;
            }
            &.open{
                .site__option{
                    display: block;
                }
                .site__btn{
                    color: #333;
                    font-weight: 700;
                    &::after{
                        background-position-x: -20px;
                    }
                }
            }
            .site__btn{
                overflow: hidden;
                width: 222px;
                padding: 10px 24px 11px;
                border-radius: 24px;
                font-size: 13px;
                color: #888;
                letter-spacing: -0.2px;
                background: #eee;
                text-align: left;
                &::after{
                    overflow: hidden;
                    font-size: 0px;
                    line-height: 0;
                    text-indent: -9999px;
                    background: url('../assets/img/ico_jobs.png') 0 0 no-repeat;
                    background-size: 260px 251px;
                    vertical-align: top;
                    content: '';
                    float: right;
                    width: 12px;
                    height: 12px;
                    margin-top: 5px;
                    background-position-y: -160px;
                }
            }
            .site__option{
                display: none;
                position: absolute;
                bottom: 42px;
                left: 0;
                z-index: 1;
                padding: 16px 24px;
                border-radius: 18px;
                background: #eee;
                width: 222px;
                bottom: 52px;
                box-sizing: border-box;
            }
            .site__item{
                width: fit-content;
                line-height: 19px;
                display: block;
                font-size: 14px;
                color: #888;
                line-height: 20px;
                letter-spacing: -0.2px;
            }
        }   
    }
}

</style>
