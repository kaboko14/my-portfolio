<template>
  <div class="default__container">
    <header>
      <menu-bar />
    </header>
    <content-container>
      <Nuxt />
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
export default class Default extends Vue {}
</script>
<style lang="scss">
body {
  font-family: 'Helvetica Neue', Arial, 'Hiragino Kaku Gothic ProN',
    'Hiragino Sans', Meiryo, sans-serif;
  color: $font-color-bk;
  letter-spacing: 0.03rem;
}
.default {
  &__container {
    margin-left: $menuBar-width;
    @include tablet {
      margin-left: 0px;
    }
  }
}
</style>
