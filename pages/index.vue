<template>
  <div class="container">
    <content-container :title="'world'">
      <div>hello</div>
      <div>a</div>
      <div>s</div>
      <my-card>
        <p>hello</p>
        <skill-icon-container :skill-list="['HTML', 'css', 'Java']" />
      </my-card>
      <div>aa</div>
    </content-container>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'
import MyCard from '~/components/atoms/MyCard.vue'
import ContentContainer from '~/components/atoms/ContentContainer.vue'
import SkillIconContainer from '~/components/molecules/SkillIconContainer.vue'
import WorkCard from '~/components/molecules/WorkCard.vue'

@Component({
  components: {
    ContentContainer,
    SkillIconContainer,
    MyCard,
    WorkCard,
  },
})
export default class index extends Vue {}
</script>
<style lang="scss" scoped>
img {
  width: 100%;
}
</style>
