<template>
  <div class="menu-bar__container"></div>
</template>
<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'

@Component
export default class MenuBar extends Vue {}
</script>
<style lang="scss" scoped>
.menu-bar {
  &__container {
    position: fixed;
    top: 0;
    left: 0;
    width: $menuBar-width;
    height: 100vh;
    background-color: $main-color;

    @include tablet {
      left: -$menuBar-width;
    }
  }
}
</style>
