<template>
  <section id="info" class="about">
    <div class="wrapper">
      <h2 class="text-center">Информация</h2>
      <div class="rows">
        <ul class="row cols justify-between">
          <li class="col">
            <a @click.prevent="rulesShowed = true" class="btn" href="#">Правила акции</a>
            <Dialog v-model="rulesShowed">
              <div>1</div>
            </Dialog>
          </li>
          <li class="col">
            <a @click.prevent="qaShowed = true" class="btn" href="#">Ответы - вопросы</a>
            <Dialog v-model="qaShowed">
              <div>2</div>
            </Dialog>
          </li>
          <li class="col">
            <a class="btn btn--sm" href="#">Согласие на обработку персональных данных</a>
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>
<script>
  import Dialog from './Dialog.vue';

  export default {
    data() {
      return {
        rulesShowed: false,
        qaShowed: false,
      }
    },
    components: {
      Dialog
    }
  }
</script>
<style scoped lang="scss">
  .about {
    padding-top: 27px;
    padding-bottom: 100px;
    background: var(--bej);
    position: relative;

    @include screen($xs) {
      padding-top: 20px;
      padding-bottom: 60px;
    }
  }

  .about::before {
    content: "";
    position: absolute;
    bottom: 0;
    left: 0;
    background: url(@/assets/images/info-decor.png) no-repeat;
    background-size: contain;
    width: 250px;
    height: 296px;

    @include screen($lg) {
      left: -25px;
    }

    @include screen($md) {
      width: 200px;
      height: 235px;
      left: -25px;
    }

    @include screen($sm) {
      width: 180px;
      height: 215px;
      left: -35px;
    }

    @include screen($xs) {
      width: 160px;
      height: 190px;
      left: -20px;
    }

    @include screen(350px) {
      width: 91px;
      height: 108px;
      left: -12px;
    }
  }

  .rows {
    max-width: 900px;
    margin-top: 50px;
    margin-left: auto;
    margin-right: auto;

    @include screen($lg) {
      max-width: 800px;
    }

    @include screen($md) {
      max-width: 750px;
    }

    @include screen($sm) {
      max-width: 600px;
    }

    @include screen($xs) {
      max-width: 240px;
      margin-top: 20px;
    }
  }

  .about ul {
    list-style: none;
  }

  .about li {
    flex-basis: 300px;

    @include screen($lg) {
      flex-basis: 265px;
    }

    @include screen($md) {
      flex-basis: 250px;
    }

    @include screen($sm) {
      flex-basis: 200px;
    }

    @include screen($xs) {
      flex-basis: 100%;
    }
  }

  .about li + li {
    @include screen($xs) {
      margin-top: 18px;
    }
  }

  .btn {
    display: block;
    font-size: 20px;
    font-weight: 600;
    line-height: 24px;
    color: black;
    text-align: center;
    border: 4px dotted #C0A93C;
    border-radius: 10px;
    padding: 28px 4px;
    transition: background 300ms;

    &:hover {
      background: #E6D4B2;
    }

    @include screen($md) {
      padding: 18px 4px;
    }

    @include screen($sm) {
      font-size: 16px;
      line-height: 20px;
    }
  }

  .btn--sm {
    font-size: 16px;
    padding: 20px 4px;
    line-height: 20px;
    @include screen($md) {
      padding: 10px 4px;
    }

    @include screen($sm) {
      font-size: 12px;
      line-height: 18px;
    }

    @include screen($xs) {
      padding: 15px 4px;
      font-size: 12px;
      line-height: 15px;
    }
  }
</style>
