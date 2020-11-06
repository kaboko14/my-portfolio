<template>
  <img :src="loadImage()" :alt="skill" class="skill-icon__image" />
</template>
<script lang="ts">
import { Vue, Component, Prop } from 'nuxt-property-decorator'

@Component
export default class SkillIcon extends Vue {
  @Prop({ type: String, required: true })
  skill!: string

  public loadImage() {
    const name = this.skill.toLowerCase()
    return require(`~/assets/image/${name}.svg`)
  }
}
</script>
<style lang="scss" scoped>
.skill-icon {
  &__image {
    display: block;
    max-width: 100%;
  }
}
</style>
