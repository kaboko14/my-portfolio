<template>
  <content-container :title="'Works'" class="works__container">
    <h3 class="works__sub-title">Webアプリ</h3>
    <work-card-container :works-list="worksList"></work-card-container>
    <div>aa</div>
  </content-container>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'
import MyCard from '~/components/atoms/MyCard.vue'
import ContentContainer from '~/components/atoms/ContentContainer.vue'
import SkillIconContainer from '~/components/molecules/SkillIconContainer.vue'
import WorkCard from '~/components/molecules/WorkCard.vue'
import WorkCardContainer from '~/components/molecules/WorkCardContainer.vue'

@Component({
  components: {
    ContentContainer,
    SkillIconContainer,
    MyCard,
    WorkCard,
    WorkCardContainer,
  },
})
export default class index extends Vue {
  worksList = {
    zakkuri: {
      title: 'zaKKuri',
      image: require('~/assets/image/zakkuri_pre.png'),
      text: 'ざっくりと現金の管理をします。\n説明説明',
      skill: ['Vue', 'Sass', 'Firebase'],
      cardSize: 'large',
    },
    zakkuri2: {
      title: 'zakkri',
      image: require('~/assets/image/zakkuri_pre.png'),
      text: '説明説明説明',
      skill: ['Vue', 'Sass', 'Firebase'],
      cardSize: 'small',
    },
    zakkuri3: {
      title: 'zakkri',
      image: require('~/assets/image/zakkuri_pre.png'),
      text: '説明説明説明',
      skill: ['Vue', 'Sass', 'Firebase'],
      cardSize: 'small',
    },
    zakkuri4: {
      title: 'zakkri',
      image: require('~/assets/image/zakkuri_pre.png'),
      text: '説明説明説明',
      skill: ['Vue', 'Sass', 'Firebase'],
      cardSize: 'small',
    },
  }
}
</script>
<style lang="scss" scoped>
.works {
  &__sub-title {
    font-weight: normal;
    margin-bottom: 20px;
  }
}
</style>
