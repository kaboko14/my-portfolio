<template>
  <h2 class="page-title">
    <slot />
  </h2>
</template>
<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator'
@Component
export default class PageTitle extends Vue {}
</script>
<style lang="scss" scoped>
.page-title {
  color: $main-color;
  font-size: 28px;
  margin-bottom: 40px;
}
</style>
