<template>
  <header class="header">
    <div class="header__inner">
      <h1 class="logo">
        <a href="/" class="logo__link">
          <img src="../assets/img/img_logo.png" alt="" class="logo__img">
        </a>
      </h1>
      <nav class="nav">
        <ul class="nav__list">    
          <li class="nav__item"><a href="javascript:;" class="nav__link">카카오 생활</a></li>
          <li class="nav__item"><a href="javascript:;" class="nav__link">크루이야기</a></li>
          <li class="nav__item"><a href="javascript:;" class="nav__link">진행중공고</a></li>
          <li class="nav__item"><a href="javascript:;" class="nav__link">지원안내</a></li>
          <li class="nav__item"><a href="javascript:;" class="nav__link">나의지원서</a></li>
        </ul>
      </nav>
      <div class="header__login">
        <a href="javascript:;">로그인</a>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'appHeader',
}
</script>
<style scoped lang="scss">
.header {
  position: sticky;
  width: 100%;
  z-index: 50;
  top: 0;
  left: 0;
  right: 0;
  background: #fff;
  &__inner {
    position: relative;
    width: 1296px;
    height: 72px;
    padding: 19px 0;
    margin: 0 auto;
    background: #fff;
    text-align: center;
    box-sizing: border-box;
    .logo{
      float: left;
      &__link{
        display: block;
        padding: 5px 0;
      }
      &__img{
          display: block;
          width: 107px;
      }
    }
    .nav{
      display: inline-block;
      &__list{
        display: flex;
        margin-right: 14px;
        &:hover a{
          opacity: 0.4;
        }
        a:hover{
          opacity: 1;
        }
      }
      li+li {
        padding-left: 40px;
      }
      &__link{
        display: block;
        padding: 5px 10px;
        font-size: 16px;
        font-weight: 700;
        letter-spacing: -0.5px;
        color: #000;
      }
    }
  }
  &__login{
    float: right;
    padding: 7px 0;
    a{
      font-size: 14px;
      font-weight: 700;
      letter-spacing: -0.2px;
      color: #000;
      &::after{
        content: '';
        background: url(../assets/img/ico_jobs.png) no-repeat;
        width: 14px;
        height: 14px;
        margin: 3px 0 0 5px;
        background-size: 260px 251px;
        background-position: -120px -219px;
        display: inline-block;
        overflow: hidden;
        vertical-align: top;
      }
    }
  }
}
</style>
