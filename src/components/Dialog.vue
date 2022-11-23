<template>
  <teleport to="body">
    <div class="dialog" v-if="modelValue">
      <div class="content">
        <div class="inner">
          <div>
            <button class="close-btn" @click="$emit('update:modelValue', false)"></button>
          </div>
          <slot />
        </div>
      </div>
      <div class="overlay"></div>
    </div>
  </teleport>
</template>

<script>
export default {
  props: {
    modelValue: {
      default: false,
      type: Boolean,
    },
  },
  emits: ['update:modelValue'],
};
</script>

<style scoped lang="scss">
.overlay {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background: rgba(37, 32, 32, 0.5);
  backdrop-filter: blur(5px);
  z-index: 90;
}

.dialog {
  position: fixed;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.content {
  position: relative;
  z-index: 100;
  width: 100%;
  max-width: 1200px;
  padding: 15px;
}

.inner {
  background: #ffffff;
  border-radius: 20px;
  padding: 25px 24px;
  overflow: scroll;
  max-height: calc(100vh - 30px);
  color: black;
}

.close-btn {
  width: 32px;
  height: 32px;
  display: block;
  margin-left: auto;
  cursor: pointer;
  background: transparent;
  border: 0;
  padding: 0;

  &::after {
    content: url(@/assets/images/nav-close.svg);
    display: block;
    width: 100%;
    height: 100%;
    position: relative;
    left: 0;
  }
}
</style>
