<template>
  <div class="my-card__container">
    <slot />
  </div>
</template>
<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'

@Component
export default class MyCard extends Vue {}
</script>
<style lang="scss" scoped>
.my-card {
  &__container {
    padding: 20px 36px 30px;
    background-color: $base-color;
    border-radius: 3px;
    box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.4);
    transition: 0.3s;
    &:hover {
      transform: translateY(-5px);
      box-shadow: 0px 10px 18px rgba(0, 0, 0, 0.4);
    }
  }
}
</style>
