<template>
  <work-window :title="'Word Counter'" :skill-list="['HTML', 'CSS', 'Vue']">
    <template v-slot:image>
      <img
        src="~/assets/image/wordCounter.png"
        alt="WordCounterの画面プレビュー"
      />
    </template>
    <template v-slot:app>
      <p>
        学習の際に読んだ記事に書かれていた<br />
        「英語で書かれた文字列中に含まれる英単語の個数を単語ごとにカウントする」<br />
        というプログラムを自分ならどうやって実装するだろうかと考えて作成したものです(<a
          href="https://kuranuki.sonicgarden.jp/2017/02/programming-brain.html"
          target="_blank"
          rel="noopener noreferrer"
          >参考</a
        >）。<br />
        <a
          href="https://github.com/kaboko14/Word-Count"
          target="_blank"
          rel="noopener noreferrer"
          >GitHubリポジトリ</a
        >
      </p>
    </template>
    <template v-slot:link>
      <p>
        ※GitHub Pagesにて公開<br />
        <a
          href="https://kaboko14.github.io/Word-Count/"
          target="_blank"
          rel="noopener noreferrer"
          >Word Counter デモページ</a
        >
      </p>
    </template>
    <template v-slot:skill>
      <p>HTML / CSS / Vue.js</p>
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
