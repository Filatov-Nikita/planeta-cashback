<template>
  <footer class="footer">
    <div class="wrapper">
      <ol class="texts">
        <li v-for="item in texts">
          <div v-html="item"></div>
        </li>
      </ol>
      <div class="contacts">
        <p class="contacts__name">ТРЦ «Планета», <br> Уфа, Энтузиастов, 20</p>
        <ul class="row social">
          <li v-for="link, icon in social">
            <a :class="['social__icon', `social__${icon}`]" :href="link" target="_blank"></a>
          </li>
        </ul>
      </div>
    </div>
  </footer>
</template>
<script>
export default {
  created() {
    this.texts = [
      `<p>За исключением гипермаркета «О’КЕЙ» и арендаторов на его  , кинотеатра «Киномакс», парка развлечений «Мегалэнд», предприятий общественного питания (рестораны, кафе, киоски, и пр. предприятия общественного питания или оказания услуг), в том числе в зоне фудкорта ТРЦ «Планета», арендаторов Дома быта, салона красоты  «Чио-чио», Q-store, Churchill, Corsar, детских развлекательных аттракционов, а также, туристических агентств и магазинов островной торговли ТРЦ (Coffee Like, NicePriceCoffee, NiceCream, Праздничная лавка, BRONOSKINS, O:space, Yota, FOR SMOKE, JoyeShop, Город тачек).</p>`,
      `<p>В Акции не принимают участие корпоративные подарочные карты ТРЦ «Планета», приобретенные по безналичному расчету. Чеки из одной или нескольких торговых точек между собой не суммируются. Чеки от приобретения подарочных сертификатов в любой торговой точке ТРЦ «Планета» не дают право участвовать в Акции (кроме чеков от приобретения подарочных карт ТРЦ «Планета»).</p>`,
      `
        <p>Участник Акции может зарегистрировать не более 1 чека за весь период акции. Чек считается зарегистрированным в акции после прохождения проверки организатором акции. Организатор Акции оставляет за собой право отклонить регистрацию чека в случае обнаружения нарушения правил Акции. </p>
        <p>Внешний вид призов, комплектация, цветовое изображение могут отличаться от указанного в настоящем рекламном макете и интернете. Количество призов ограничено. Возможно досрочное прекращение акции при выдаче всех акционных товаров.Подробная информация об организаторе Акции, о правилах и порядке ее проведения, количестве призов, сроках, месте и порядке их получения на сайте <a href="https://ufa.planeta-mall.ru" target="_blank">ufa.planeta-mall.ru</a></p>
      `,
    ];
  },
  data() {
    return {
      social: {
        vk: 'https://vk.com/trc_planeta_ufa',
        tg: 'https://t.me/trc_planeta_ufa',
        rutube: 'https://rutube.ru/channel/24694861',
        youtube: 'https://www.youtube.com/channel/UCwQ9kwTOFChkJKrMOMqJ-pg',
        ok: 'https://ok.ru/group/57048741838907',
      }
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
    max-width: 158px;
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
