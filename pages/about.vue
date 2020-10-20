<template>
  <section>
    <page-title>About</page-title>
    <p class="about__text">
      はじめまして。<br />
      サイトにお越しくださりありがとうございます。<br /><br />
      私は会計事務所に6年ほど勤務しておりました。<br />
      業務をこなしていく中で特に興味があったことは、<br /><br />
      「業務の効率化にはどういったツールが必要か？」<br />
      「どういったツールを用意すれば従業員は仕事がしやすくなるのか？」<br /><br />
      といった社内の業務改善や、顧客である中小企業様の<br /><br />
      「経理の従業員がほかの業務も兼任しているため自計化がむずかしい」<br />
      「家族経営で経理に詳しくないけど経理をしなくてはいけない」<br /><br />
      などといった問題をいかに解決するかということでした。<br />
      「誰かの役に立つツール開発に携わりたい」という気持ちから2020年5月に前職を退職し、プログラミングの勉強を継続しています。<br />
      Vue.js/Firebaseを使用して現金の入出金をざっくり記録できる「Zakkuri」というアプリを製作いたしました。<br />
      また、学習のため、こちらのポートフォリオサイトはNuxt.js/TypeScriptを使用しています。<br />
      現在は職業訓練にてJavaを学習しています。<br />
      積極的に学習することを常に心掛けています。<br />
    </p>
  </section>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'
import PageTitle from '~/components/atoms/PageTitle.vue'
import ContentContainer from '~/components/atoms/ContentContainer.vue'
import SkillIconContainer from '~/components/molecules/SkillIconContainer.vue'

@Component({
  components: {
    PageTitle,
    ContentContainer,
    SkillIconContainer,
  },
})
export default class index extends Vue {}
</script>
<style lang="scss" scoped>
.works {
  &__sub-title {
    font-weight: normal;
    margin-bottom: 20px;
  }
}
</style>
