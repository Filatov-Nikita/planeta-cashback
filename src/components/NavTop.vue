<template>
  <div class="row cols align-center">
    <div class="col logo">
      <a href="https://ufa.planeta-mall.ru">
        <img width="143" height="37" src="@/assets/images/logo.svg" alt="Лого планеты">
      </a>
    </div>
    <nav class="row align-center grow nav">
      <div class="col">
        <a href="#terms">Условия участия</a>
      </div>
      <div class="col">
        <a href="#info">Информация</a>
      </div>
      <div class="grow"></div>
      <div class="col">
        <a class="link-btn" href="https://id.mall.tech">Личный кабинет</a>
      </div>
    </nav>
  </div>
</template>
<script>
  export default {

  }
</script>
<style scoped>
.logo {
  flex-basis: 213px;
}

.logo a {
  display: inline-block;
}

.nav a {
  font-weight: 600;
  font-size: 18px;
  line-height: 22px;
  color: white;
}

nav .link-btn {
  display: inline-block;
  font-size: 18px;
  font-weight: 400;
  line-height: 22px;
  padding: 10px 20px;
  border-radius: 10px;
  background: var(--white);
  color: black;
}
</style>
