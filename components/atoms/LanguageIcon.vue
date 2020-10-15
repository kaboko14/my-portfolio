<template>
  <img :src="loadImage()" :alt="language" class="language-icon_image" />
</template>
<script lang="ts">
import { Vue, Component, Prop } from 'nuxt-property-decorator'

@Component
export default class LanguageIcon extends Vue {
  @Prop({ type: String, required: true })
  language!: string

  public loadImage() {
    const name = this.language.toLowerCase()
    return require(`~/assets/image/${name}.svg`)
  }
}
</script>

<style lang="scss" scoped>
laguage-icon {
  &__image {
    width: 100px;
    max-width: 100%;
  }
}
</style>
