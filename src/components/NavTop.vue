<template>
  <div class="row cols align-center">
    <div class="col logo">
      <a :href="content.home">
        <img width="143" height="37" src="@/assets/images/logo.svg" alt="Лого планеты">
      </a>
    </div>
    <nav class="row align-center grow nav">
      <div class="col">
        <a class="nav-link" href="#terms">Условия участия</a>
      </div>
      <div class="col">
        <a class="nav-link" href="#info">Информация</a>
      </div>
      <div class="grow"></div>
      <div class="col">
        <a class="link-btn" href="https://id.mall.tech">Личный кабинет</a>
      </div>
    </nav>
  </div>
</template>
<script>
  import { inject } from 'vue';

  export default {
    setup() {
      const content = inject('content');

      return {
        content
      }
    }
  }
</script>
<style scoped lang="scss">
.logo {
  flex-basis: 213px;
}

.logo a {
  display: inline-block;
}

nav {
  .link-btn {
    display: inline-block;
    font-size: 18px;
    font-weight: 400;
    line-height: 22px;
    padding: 10px 20px;
    border-radius: 10px;
    background: var(--white);
    color: black;
    transition: all 200ms;

    &:hover {
      background: #D63108;
      color: var(--white);
    }
  }
}

.nav-link {
  font-weight: 600;
  font-size: 18px;
  line-height: 22px;
  color: white;

  &:hover {
    text-decoration: underline;
  }
}
</style>
