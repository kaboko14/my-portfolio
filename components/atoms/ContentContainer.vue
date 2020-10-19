<template>
  <div class="content-container__container">
    <h2 v-if="title" class="content-container__title">
      {{ title }}
    </h2>
    <slot />
  </div>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'nuxt-property-decorator'

@Component
export default class ContentContainer extends Vue {
  @Prop({ type: String, default: null, required: false })
  title!: string
}
</script>

<style lang="scss" scoped>
.content-container {
  &__container {
    max-width: 1080px;
    margin: 0 auto;
    padding: 60px 40px;
    background-color: $base-color;
    @include tablet {
      margin: 0 auto;
    }
  }
  &__title {
    margin-bottom: 30px;
  }
}
</style>
