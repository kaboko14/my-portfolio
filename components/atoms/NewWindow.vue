<template>
  <div class="new-window__background">
    <div class="new-window__container">
      <div class="new-window__close-button" @click="closeWindow()">×</div>
      <div class="new-window__contents">
        <slot />
      </div>
    </div>
  </div>
</template>
<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator'

@Component
export default class NewWindow extends Vue {
  closeWindow() {
    this.$emit('click-close-button')
  }
}
</script>
<style lang="scss" scoped>
.new-window {
  &__background {
    display: flex;
    justify-content: center;
    align-items: center;
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    padding: 20px;
    background-color: rgba($black, 0.8);
  }
  &__container {
    display: flex;
    flex-direction: column;
    position: relative;
    width: 100%;
    max-width: 1020px;
    max-height: 100%;
    padding: 50px 30px 30px 30px;
    background-color: $base-color;
    border-radius: 3px;
  }
  &__contents {
    overflow: auto;
  }
  &__close-button {
    position: absolute;
    top: 10px;
    right: 10px;
    border: 1px solid $gray-2;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 30px;
    width: 30px;
    height: 30px;
    cursor: pointer;
  }
}
</style>
