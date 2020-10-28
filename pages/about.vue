<template>
  <section>
    <page-title>About</page-title>
    <div class="about__profile-wrapper">
      <div class="about__profile-contents">
        <h3>おおた かほり</h3>
        <p>32歳</p>
        <p>大阪市在中</p>
        <a
          href="https://github.com/kaboko14"
          target="_blank"
          rel="noopener noreferrer"
        >
          <img
            src="~/assets/image/github.svg"
            alt="GitHubリンク"
            class="about__link-image"
        /></a>
      </div>
      <img
        src="~/assets/image/profile.JPG"
        alt="プロフィール画像"
        class="about__profile-image"
      />
    </div>
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
    <h3 class="about__skill-title">学習中の言語</h3>
    <skill-icon-container
      :skill-list="skilList"
      class="about__skill-icon-container"
    />
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
export default class about extends Vue {
  skilList = [
    'HTML',
    'CSS',
    'Sass',
    'JavaScript',
    'TypeScript',
    'Vue',
    'Nuxt',
    'Java',
  ]
}
</script>
<style lang="scss" scoped>
.about {
  &__profile-wrapper {
    display: flex;
    flex-wrap: wrap;
    margin-bottom: 30px;
    @include tablet {
      display: block;
    }
  }
  &__profile-contents {
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    margin-left: 30px;
    order: 2;
    @include tablet {
      margin-left: 0px;
    }
    & > * {
      margin-bottom: 10px;
    }
  }
  &__profile-image {
    width: 100%;
    max-width: 280px;
    order: 1;
  }
  &__link-image {
    width: 40px;
    opacity: 1;
    transition: 0.2s;
    &:hover {
      transform: translateY(-5px);
      opacity: 0.8;
    }
  }
  &__text {
    margin-bottom: 60px;
  }
  &__skill-title {
    margin-bottom: 20px;
  }
}
</style>
