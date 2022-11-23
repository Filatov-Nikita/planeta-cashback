<template>
  <main>
    <ScreenMain />
    <ScreenTerms />
    <ScreenAbout />
    <ScreenFooter />
  </main>
</template>

<script>
import ScreenMain from './ScreenMain.vue';
import ScreenTerms from './ScreenTerms.vue';
import ScreenAbout from './ScreenAbout.vue';
import ScreenFooter from './ScreenFooter.vue';

export default {
  components: {
    ScreenMain,
    ScreenTerms,
    ScreenAbout,
    ScreenFooter
  }
}
</script>

<style>

</style>
