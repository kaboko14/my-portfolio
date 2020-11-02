<template>
  <work-window :title="'zaKKuri'" :skill-list="['Vue', 'Sass', 'Firebase']">
    <template v-slot:image>
      <img src="~/assets/image/zaKKuri.png" alt="zaKKuriの画面プレビュー" />
    </template>
    <template v-slot:app>
      <p>
        面倒な現金の入出金記録を「ざっくり！」と記録するためのアプリです。<br />
        現金の入出金は自己管理無しで流れを追うことは難しいです。<br />
        家計簿等で収支・損益を管理できれば一番ですが、それが面倒で続かないユーザーのために<br />
        ● 現金の入出金(収支)のみの管理<br />
        ● 金額をざっくりと簡単に入力できる<br />
        ということをテーマに作成しました。<br />
        <a
          href="https://github.com/kaboko14/kakeibo"
          target="_blank"
          rel="noopener noreferrer"
          >GitHubリポジトリ</a
        >
      </p>
    </template>
    <template v-slot:link>
      <p>
        ※Googleアカウントの登録が必要となります。<br />
        ※機能確認用のゲストアカウントがありますが、ゲストログイン中に登録した内容を個人のアカウントに引き継ぐことはできません。<br />
        <a
          href="https://zakkuri-463ac.web.app/login"
          target="_blank"
          rel="noopener noreferrer"
          ><img
            src="~/assets/image/zaKKuri_logo.svg"
            alt="zaKKuriリンク"
            class="zakkuri__link-image"
        /></a>
      </p>
    </template>
    <template v-slot:skill>
      <p>
        Vue-CLI / Vue-router / Vuex / Scss / Firebase(Cloud Firestore /
        Authentication / Hosting)
      </p>
    </template>
  </work-window>
</template>
<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'
import WorkWindow from '~/components/molecules/WorkWindow.vue'

@Component({
  components: {
    WorkWindow,
  },
})
export default class extends Vue {}
</script>
<style lang="scss" scoped>
.zakkuri {
  &__link-image {
    width: 100%;
    max-width: 200px;
    padding: 20px;
    border: 1px solid $gray-2;
    border-radius: 20px;
    transition: 0.3s;
    &:hover {
      transform: translateY(-5px);
    }
  }
}
</style>
