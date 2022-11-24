<template>
  <footer class="footer">
    <div class="wrapper">
      <ol class="texts">
        <li v-for="item in content.footer">
          <div v-html="item"></div>
        </li>
      </ol>
      <div class="contacts">
        <p class="contacts__name" v-html="content.address"></p>
        <ul class="row social">
          <li v-for="link, icon in content.social">
            <a :class="['social__icon', `social__${icon}`]" :href="link" target="_blank"></a>
          </li>
        </ul>
      </div>
    </div>
  </footer>
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
<style>
  .texts p + p {
    margin-top: 30px;
  }

  .texts p a {
    font-weight: 600;
    text-decoration: underline;
    color: var(--white);
  }
</style>
<style scoped lang="scss">
.footer {
  padding-top: 67px;
  padding-bottom: 45px;
  background: var(--primary);
  background-image: url(@/assets/images/footer-decor.svg);
  background-repeat: repeat-x;

  @include screen($xs) {
    padding-top: 40px;
    padding-bottom: 30px;
  }
}

.texts {
  list-style-type: decimal;
  padding: 0 15px;
}

.texts li {
  font-weight: 400;
  font-size: 13px;
  line-height: 142%;

  @include screen($xs) {
    font-size: 11px;
  }
}

.texts li + li {
  margin-top: 30px;
}

.contacts {
  margin-top: 70px;

  &__name {
    font-weight: 700;
    font-size: 14px;
    line-height: 142%;
    max-width: 200px;
    margin-bottom: 20px;
  }

  @include screen($xs) {
    margin-top: 30px;
  }
}

.social {
  li + li {
    margin-left: 15px;
  }

  &__icon {
    display: block;
    width: 32px;
    height: 32px;
  }

  &__ok {
    background: url(@/assets/images/ok.svg) no-repeat;
  }

  &__youtube {
    background: url(@/assets/images/youtube.svg) no-repeat;
  }

  &__vk {
    background: url(@/assets/images/vk.svg) no-repeat;
  }

  &__tg {
    background: url(@/assets/images/tg.svg) no-repeat;
  }

  &__rutube {
    background: url(@/assets/images/rutube.svg) no-repeat;
  }
}
</style>
