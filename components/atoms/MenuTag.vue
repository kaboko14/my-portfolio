<template>
  <li class="menu-tag__list">
    <nuxt-link :to="linkUrl" class="menu-tag__link">
      {{ linkName }}
    </nuxt-link>
  </li>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'nuxt-property-decorator'

@Component
export default class MenuTag extends Vue {
  @Prop({ type: String, required: true })
  linkName!: string

  @Prop({ type: String, required: true })
  linkUrl!: string
}
</script>

<style lang="scss" scoped>
.menu-tag {
  &__link {
    position: relative;
    font-size: 16px;
    font-weight: bold;
    color: $font-color-bk;
    display: inline-block;
    padding: 10px 0px;
    transform: scale(1, 1);
    transition: 0.2s;
    &::after {
      content: '';
      position: absolute;
      bottom: 8px;
      left: 50%;
      transform: translateX(-50%) scale(0);
      width: 120%;
      height: 3px;
      background-image: $bg-image-stripe;
      transition: 0.2s;
    }
    &:hover {
      transform: scale(1.2, 1.2);
      &::after {
        transform: translateX(-50%) scale(0.83, 1);
      }
    }

    &.active {
      color: $accent-color;
      &:hover {
        transform: scale(1, 1);
      }
      &::after {
        transform: scale(0, 0);
      }
    }
  }
}
</style>
