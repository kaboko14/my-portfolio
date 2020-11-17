<template>
  <div class="thanks__container">
    <h2 class="thanks__main-message">お問い合わせを受け付けました</h2>
    <p>お問い合わせいただき、ありがとうございました。</p>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'

@Component
export default class extends Vue {}
</script>
<style lang="scss" scoped>
.thanks {
  &__main-message {
    font-size: 20px;
    color: $accent-color;
    margin-bottom: 20px;
  }
}
</style>
