<template>
  <div class="container">
    <content-container :title="'world'">
      <div>hello</div>
      <div>a</div>
      <work-card :title="'タイトル'" :skill-list="['Java', 'HTML']">
        <template v-slot:image>
          <img
            src="~/assets/image/zakkuri_pre.png"
            alt=""
            width="100%"
            height="auto"
          />
        </template>
        <template v-slot:text>
          <p>
            説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明説明
          </p>
        </template>
      </work-card>
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

<style></style>
