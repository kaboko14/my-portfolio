<template>
  <div class="language-icon-container__container">
    <div
      v-for="(language, index) in languageList"
      :key="index"
      class="language-icon-container__image"
    >
      <language-icon :language="language" />
    </div>
  </div>
</template>
<script lang="ts">
import { Vue, Component, Prop } from 'nuxt-property-decorator'
import LanguageIcon from '~/components/atoms/LanguageIcon.vue'

@Component({
  components: {
    LanguageIcon,
  },
})
export default class LanguageIconContainer extends Vue {
  @Prop({ type: Array, required: true })
  languageList!: Array<string>
}
</script>
<style lang="scss" scoped>
.language-icon-container {
  &__container {
    display: grid;
  }
  &__image {
    width: 100%;
  }
}
</style>
