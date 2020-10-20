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
  &__list {
    text-align: center;
    margin-bottom: 10px;
  }
  &__link {
    position: relative;
    font-size: 20px;
    color: $font-color-bk;
    text-decoration: none;
    display: inline-block;
    padding: 10px 20px;
    &::before,
    &::after {
      content: '';
      position: absolute;
      top: 50%;
      transform: translateY(-50%) scale(0);
      width: 6px;
      height: 6px;
      background-color: $white;
      border-radius: 50%;
      z-index: -1;
      transition: 0.3s;
    }
    &::before {
      top: 50%;
      left: 0px;
    }
    &::after {
      top: 50%;
      right: 0px;
    }
    &:hover {
      &::before,
      &::after {
        transform: translateY(-50%) scale(1, 1);
      }
    }

    &.active {
      &:hover {
        opacity: 1;
      }
      &::before,
      &::after {
        top: 50%;
        left: 50%;
        transform: translateY(-50%) translateX(-50%);
        width: 50px;
        height: 50px;
      }
    }
  }
}
</style>
