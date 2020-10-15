<template>
  <div class="container">
    <content-container :title="'world'">
      <div>hello</div>
    </content-container>
    <my-card>
      <p>hello</p>
    </my-card>
    <LanguageIconContainer :language-list="['HTML', 'css', 'Java']" />
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'
import ContentContainer from '~/components/atoms/ContentContainer.vue'
import myCard from '~/components/atoms/myCard.vue'
import LanguageIconContainer from '~/components/molecules/LanguageIconContainer.vue'

@Component({
  components: {
    ContentContainer,
    LanguageIconContainer,
    myCard,
  },
})
export default class index extends Vue {}
</script>

<style></style>
