<template>
  <div class="home__container">
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
export default class extends Vue {}
</script>
<style lang="scss">
.home {
  &__container {
    min-width: 100vw;
    min-height: 100vh;
  }
}
</style>
