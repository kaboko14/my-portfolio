<template>
  <div class="content-container__container">
    <slot />
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'

@Component
export default class ContentContainer extends Vue {}
</script>

<style lang="scss" scoped>
.content-container {
  &__container {
    max-width: 1080px;
    min-height: 100vh;
    padding: 60px 40px;
    background-color: $base-color;
    @include tablet {
      margin: 0 auto;
    }
  }
}
</style>
