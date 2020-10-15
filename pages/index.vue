<template>
  <div class="container">
    <content-container :title="'world'">
      <div>hello</div>
    </content-container>
    <my-card>
      <p>hello</p>
      <skill-icon-container :skill-list="['HTML', 'css', 'Java']" />
    </my-card>
    <div>aa</div>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'
import MyCard from '~/components/atoms/MyCard.vue'
import ContentContainer from '~/components/atoms/ContentContainer.vue'
import SkillIconContainer from '~/components/molecules/SkillIconContainer.vue'

@Component({
  components: {
    ContentContainer,
    SkillIconContainer,
    MyCard,
  },
})
export default class index extends Vue {}
</script>

<style></style>
