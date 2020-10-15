<template>
  <div class="my-card__container">
    <slot />
  </div>
</template>
<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'

@Component
export default class myCard extends Vue {}
</script>
<style lang="scss" scoped>
.my-card {
  &__container {
    padding: 10px 4px;
    background-color: $base-color;
    border-radius: 3px;
    box-shadow: $shadow;
  }
}
</style>
