<template>
  <div class="header">
    <div class="wrapper">
      <div class="box relative">
        <NavTop class="desktop" />
        <NavMainSmall class="mobile" />
        <div class="cashback">
          <img width="1268" height="976" src="@/assets/images/accent-pic.png" alt="Новогодний кэшбек: 5-25 декабря">
        </div>
        <div class="info" v-html="infoText"></div>
        <a class="round-btn hide-mobile" href="https://id.mall.tech/">Зарегистрировать чек</a>
      </div>
    </div>
    <div class="bot">
      <DecorBot />
    </div>
    <div class="info-mobile">
      <div class="wrapper">
        <div class="info-mobile__text" v-html="infoText"></div>
        <a class="round-btn" href="https://id.mall.tech/">Зарегистрировать чек</a>
      </div>
    </div>
  </div>
</template>

<script>
import NavTop from './NavTop.vue';
import NavMainSmall from './NavMainSmall.vue';
import DecorBot from './DecorBot.vue';

export default {
  created() {
    this.infoText = 'Совершайте покупку от 5&nbsp;000 рублей и&nbsp;гарантированно получайте кэшбэк 500 рублей подарочной картой «Планета» на&nbsp;стойке информации';
  },
  components: {
    NavTop,
    NavMainSmall,
    DecorBot
  }
}
</script>

<style scoped lang="scss">
.header {
  padding-top: 30px;
  background: var(--primary);
  position: relative;
  z-index: 0;
  overflow: hidden;
}

.box::before {
  content: "";
  width: 1009px;
  height: calc(100% + 174px);
  position: absolute;
  right: -440px;
  top: -30px;
  z-index: -1;
  background: url(@/assets/images/decor.png) no-repeat;
  background-size: cover;

  @include screen($lg) {
    width: 909px;
  }

  @include screen($md) {
    width: 750px;
    right: -400px;
  }

  @include screen($xs) {
    width: 360px;
    right: -80px;
  }
}

.box::after {
  content: "";
  width: 900px;
  height: 890px;
  position: absolute;
  right: -220px;
  bottom: -170px;
  z-index: 1;
  background: url(@/assets/images/accent-pic-2.png) no-repeat;
  background-size: contain;

  @include screen($lg) {
    width: 810px;
    height: 800px;
    bottom: -160px;
    right: -200px;
  }

  @include screen($md) {
    width: 720px;
    height: 710px;
    bottom: -130px;
    right: -170px;
  }

  @include screen($sm) {
    width: 580px;
    height: 570px;
    bottom: -120px;
    right: -150px;
  }

  @include screen($xs) {
    width: 370px;
    height: 343px;
    bottom: -90px;
    right: -90px;
  }

  @include screen(530px) {
    width: 248px;
    height: 231px;
    bottom: -68px;
    right: auto;
    left: 47%;
  }

  @include screen(350px) {
    left: 125px;
    width: 218px;
    height: 201px;
    bottom: -50px;
  }
}

.cashback {
  margin-top: 55px;
  max-width: 634px;

  @include screen($lg) {
    max-width: 550px;
  }

  @include screen($md) {
    max-width: 460px;
  }

  @include screen($sm) {
    max-width: 360px;
    margin-top: 40px;
  }

  @include screen($sm) {
    max-width: 340px;
  }

  @include screen($xs) {
    max-width: 330px;
  }

  @include screen(530px) {
    max-width: 230px;
  }

  @include screen(350px) {
    max-width: 180px;
  }
}

.cashback img {
  height: auto;
  transform: translateX(-20px);

  @include screen($xs) {
    transform: translateX(-10px);
  }
}

.info {
  max-width: 610px;
  font-weight: 500;
  font-size: 26px;
  line-height: 125%;
  margin-bottom: 30px;

  @include screen($lg) {
    max-width: 510px;
    font-size: 22px;
  }

  @include screen($md) {
    max-width: 410px;
    font-size: 20px;
  }

  @include screen($sm) {
    max-width: 340px;
    font-size: 16px;
    margin-bottom: 15px;
  }

  @include screen($xs) {
    display: none;
  }
}

.bot {
  padding-top: 22px;
  position: relative;
  z-index: 3;
}

.desktop {
  @include screen($md) {
    display: none;
  }
}

.mobile {
  display: none;
  @include screen($md) {
    display: block;
  }
}

.hide-mobile {
  @include screen($xs) {
    display: none;
  }
}

.info-mobile {
  display: none;
  background: var(--bej);
  color: #05301A;
  font-size: 16px;
  font-weight: 500;
  line-height: 125%;
  text-align: center;
  padding-bottom: 20px;
  padding-top: 10px;

  &__text {
    max-width: 345px;
    margin-left: auto;
    margin-right: auto;
    margin-bottom: 15px;
  }

  @include screen($xs) {
    display: block;
  }
}
</style>
