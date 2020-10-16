<template>
  <content-container :title="'Works'" class="works__container">
    <h3 class="works__sub-title">Webアプリ</h3>
    <works-card-container :works-list="worksList"></works-card-container>
    <div>aa</div>
  </content-container>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'
import MyCard from '~/components/atoms/MyCard.vue'
import ContentContainer from '~/components/atoms/ContentContainer.vue'
import SkillIconContainer from '~/components/molecules/SkillIconContainer.vue'
import WorkCard from '~/components/molecules/WorkCard.vue'
import WorksCardContainer from '~/components/molecules/WorksCardContainer.vue'

@Component({
  components: {
    ContentContainer,
    SkillIconContainer,
    MyCard,
    WorkCard,
    WorksCardContainer,
  },
})
export default class index extends Vue {
  worksList = {
    zakkuri: {
      title: 'zakkri',
      image: require('~/assets/image/zakkuri_pre.png'),
      text: 'ざっくりと現金の管理をします。\n説明説明',
      skill: ['Vue', 'Sass', 'Firebase'],
    },
    zakkuri2: {
      title: 'zakkri',
      image: require('~/assets/image/zakkuri_pre.png'),
      text: '説明説明説明',
      skill: ['Vue', 'Sass', 'Firebase'],
    },
  }
}
</script>
<style lang="scss" scoped>
img {
  width: 100%;
}
</style>
