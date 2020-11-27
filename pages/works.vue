<template>
  <div>
    <section>
      <page-title>Works</page-title>
      <h3 class="works__sub-title fade-in-2">Webアプリ</h3>
      <work-card-container
        :works-list="webAppList"
        class="fade-in-2"
      ></work-card-container>
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
  webAppList = {
    zakkuri: {
      title: 'zaKKuri',
      image: require('~/assets/image/zaKKuri.png'),
      text:
        '面倒な現金の入出金記録を「ざっくり！」と記録するためのアプリです。',
      skill: ['Vue', 'Sass', 'Firebase'],
      pageLink: '/works/zakkuri',
      cardSize: 'large',
    },
    wordCounter: {
      title: 'Word Counter',
      image: require('~/assets/image/wordCounter.png'),
      text:
        '英文中に含まれる英単語の個数を単語ごとにカウントするためのアプリです。Vue.jsの学習のために作成いたしました',
      skill: ['HTML', 'CSS', 'Vue'],
      pageLink: '/works/wordcounter',
      cardSize: 'small',
    },
    toDoList: {
      title: 'To Do List',
      image: require('~/assets/image/toDoList.png'),
      text:
        'ToDoを管理できるアプリです。登録したデータはブラウザのローカルストレージに保存されます。',
      skill: ['HTML', 'CSS', 'JavaScript'],
      pageLink: '/works/todolist',
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
