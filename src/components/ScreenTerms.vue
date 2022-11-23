<template>
  <section id="terms" class="terms">
    <div class="wrapper">
      <h2 class="text-center">Условия Участия</h2>
      <ul class="terms-list">
        <li v-for="item, index in list">
          <span class="index">{{ index + 1 }}</span>
          <p v-html="item"></p>
        </li>
      </ul>
      <div class="btn">
        <a class="round-btn" href="https://id.mall.tech">Участвовать в акции</a>
      </div>
    </div>
  </section>
</template>
<script>
  export default {
    created() {
      this.list = [
        'Совершайте покупку с 10:00 <span>5 декабря</span> по 22:00 <span>25 декабря 2022 г.</span> на сумму от 5 000 рублей в одном чеке в ТРЦ «Планета»¹ или приобретайте подарочную карту ТРЦ «Планета» на сумму от 5 000 рублей на стойке информации или на сайте <a class="link-thin" href="https://ufa.planeta-mall.ru/gift-card" target="_blank">ufa.planeta-mall.ru/gift-card²</a>;',
        'Регистрируйте чек³ в Личном кабинете <a href="https://id.mall.tech" target="_blank">id.mall.tech</a> и гарантированно получайте 500 рублей кэшбэк⁴;',
        'Приз можно получить на стойке информации в период <span>с 5 по 30 декабря</span> в часы работы ТРЦ. Для получения приза требуется иметь при себе номер телефона, с которого производилась регистрация в акции.'
      ]
    }
  }
</script>
<style>
  .terms-list span {
    font-weight: 700;
  }

  .terms-list a {
    color: black;
    text-decoration: underline;
    font-weight: 700;
  }

  .terms-list .link-thin {
    font-weight: 400;
  }
</style>
<style scoped lang="scss">
.terms {
  background: var(--bej);
  min-height: 500px;
  padding-top: 47px;
  padding-bottom: 120px;
  position: relative;
  overflow: hidden;

  @include screen($xs) {
    padding-bottom: 30px;
  }
}

.terms::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  background: url(@/assets/images/terms-decor-1.png) no-repeat;
  background-size: contain;
  width: 250px;
  height: 470px;

  @include screen($sm) {
    left: -20px;
    width: 180px;
    height: 400px;
    top: 60px;
  }

  @include screen($xs) {
    display: none;
  }
}

.terms::after {
  content: "";
  position: absolute;
  top: 115px;
  right: -8px;
  background: url(@/assets/images/terms-decor-2.png) no-repeat;
  background-size: contain;
  width: 250px;
  height: 550px;

  @include screen($md) {
    right: -50px;
    width: 200px;
    height: 500px;
  }

  @include screen($xs) {
    display: none;
  }
}

.index {
  position: absolute;
  top: -50px;
  left: 0;
  font-family: 'Playfair Display', serif;
  font-size: 100px;
  font-weight: 900;
  background-clip: text;
  color: transparent;
	background-image: url(@/assets/images/gold-bg.jpg);
  background-position: center;
  align-self: flex-start;

  @include screen($md) {
    font-size: 80px;
  }

  @include screen($xs) {
    font-size: 70px;
    padding-top: 20px;
  }
}

.terms li p {
  color: black;
  padding-left: 95px;
  font-size: 22px;
  line-height: 140%;

  @include screen($lg) {
    font-size: 16px;
  }

  @include screen($md) {
    padding-left: 60px;
  }

  @include screen($xs) {
    font-size: 14px;
    padding-left: 50px;
  }
}

.terms li {
  position: relative;
  min-height: 80px;
}

.terms li + li {
  margin-top: 45px;

  @include screen($xs) {
    margin-top: 35px;
  }
}

.terms ul {
  list-style: none;
  max-width: 975px;
  margin-left: auto;
  margin-right: auto;
  margin-top: 56px;

  @include screen($lg) {
    max-width: 675px;
  }

  @include screen($md) {
    max-width: 500px;
  }

  @include screen($sm) {
    max-width: 500px;
    margin-top: 25px;
  }
}

.btn {
  padding-top: 50px;
  text-align: center;
}
</style>
