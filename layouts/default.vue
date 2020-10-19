<template>
  <div class="default__container">
    <header>
      <menu-bar />
    </header>
    <Nuxt />
  </div>
</template>
<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'
import MenuBar from '~/components/molecules/MenuBar.vue'

@Component({
  components: {
    MenuBar,
  },
})
export default class Default extends Vue {}
</script>
<style lang="scss">
.default {
  &__container {
    margin-left: $menuBar-width;
    @include tablet {
      margin-left: 0px;
    }
  }
}
</style>
