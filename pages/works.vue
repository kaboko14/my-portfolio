<template>
  <div>
    <section>
      <page-title>Works</page-title>
      <h3 class="works__sub-title">Webアプリ</h3>
      <work-card-container :works-list="worksList"></work-card-container>
      <nuxt-child />
    </section>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'
import PageTitle from '~/components/atoms/PageTitle.vue'
import MyCard from '~/components/atoms/MyCard.vue'

import SkillIconContainer from '~/components/molecules/SkillIconContainer.vue'
import WorkCard from '~/components/molecules/WorkCard.vue'
import WorkCardContainer from '~/components/molecules/WorkCardContainer.vue'

@Component({
  components: {
    PageTitle,
    SkillIconContainer,
    MyCard,
    WorkCard,
    WorkCardContainer,
  },
})
export default class works extends Vue {
  worksList = {
    zakkuri: {
      title: 'zaKKuri',
      image: require('~/assets/image/zaKKuri.png'),
      text: 'ざっくりと現金の管理をします。\n説明説明',
      skill: ['Vue', 'Sass', 'Firebase'],
      pageLink: 'works/zakkuri',
      cardSize: 'large',
    },
    zakkuri2: {
      title: 'To Do List',
      image: require('~/assets/image/toDoList.png'),
      text: '説明説明説明',
      skill: ['HTML', 'CSS', 'JavaScript'],
      pageLink: 'works/todolist',
      cardSize: 'small',
    },
    zakkuri3: {
      title: 'Word Counter',
      image: require('~/assets/image/wordCounter.png'),
      text: '説明説明説明',
      skill: ['HTML', 'CSS', 'Vue'],
      pageLink: 'works/wordcounter',
      cardSize: 'small',
    },
    zakkuri4: {
      title: 'zakkri',
      image: require('~/assets/image/zaKKuri.png'),
      text: '説明説明説明',
      skill: ['Vue', 'Sass', 'Firebase'],
      pageLink: 'works/zakkuri',
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
