<template>
  <work-window :title="'ToDoList'" :skill-list="['HTML', 'CSS', 'JavaScript']">
    <template v-slot:image>
      <img src="~/assets/image/toDoList.png" alt="ToDoListの画面プレビュー" />
    </template>
    <template v-slot:app>
      <p>
        JavaScriptの学習のために作成したToDoListです。<br />
        実装したことは以下の通りです。<br />
        ● タスクの追加 <br />● チェックボックスでタスクの完了の管理<br />
        ● 完了済みタスクのスタイル変更<br />
        ● タスクの削除<br />
        ● タスクの検索・検索解除<br />
        ● 空文字の登録及び検索・重複登録の不可、エラーメッセージ表示<br />
        ● ローカルストレージの保存<br />
        見やすいデザインを心掛け、レスポンシブにも対応しています。<br />
        <a
          href="https://github.com/kaboko14/todo-list"
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
          href="https://kaboko14.github.io/todo-list/"
          target="_blank"
          rel="noopener noreferrer"
          >ToDoList デモページ</a
        >
      </p>
    </template>
    <template v-slot:skill>
      <p>HTML / CSS / JavaScript</p>
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
export default class zakkuri extends Vue {}
</script>
