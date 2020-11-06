<template>
  <div class="default__container">
    <header>
      <menu-bar class="default__menu-bar" />
    </header>
    <content-container class="default__content-container">
      <Nuxt :nuxt-child-key="$route.fullPath" />
    </content-container>
  </div>
</template>
<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'
import ContentContainer from '~/components/atoms/ContentContainer.vue'
import MenuBar from '~/components/molecules/MenuBar.vue'

@Component({
  components: {
    MenuBar,
    ContentContainer,
  },
})
export default class extends Vue {}
</script>
<style lang="scss">
@import '~/assets/sass/style';

.default {
  &__container {
    position: relative;
    min-height: 100vh;
    margin-left: $menuBar-width;
    z-index: 0;

    @include tablet {
      margin-left: 0px;
    }
  }
  &__menu-bar {
    z-index: 1;
  }
  &__content-container {
    margin: 0 auto;
    z-index: 1;
  }
}
</style>
