<template>
  <new-window @click-close-button="closeWindow()">
    <section class="work-window__container">
      <h3 class="work-window__title">{{ title }}</h3>
      <div class="work-window__contents-wrapper">
        <div class="work-window__image-wrapper">
          <slot name="image" />
        </div>
        <div class="work-window__text-wrapper">
          <h4 class="work-window__sub-title">■ アプリについて ■</h4>
          <slot name="app" />
          <h4 class="work-window__sub-title">■ リンク ■</h4>
          <slot name="link" />
          <h4 class="work-window__sub-title">■ 使用言語・環境 ■</h4>
          <skill-icon-container
            :skill-list="skillList"
            class="work-window__skil-icon-container"
          />
          <slot name="skill" />
        </div>
      </div>
    </section>
  </new-window>
</template>
<script lang="ts">
import { Vue, Component, Prop } from 'nuxt-property-decorator'
import NewWindow from '~/components/atoms/NewWindow.vue'
import SkillIconContainer from '~/components/molecules/SkillIconContainer.vue'

@Component({
  components: {
    NewWindow,
    SkillIconContainer,
  },
})
export default class WorkCard extends Vue {
  @Prop({ type: String, required: true })
  title!: string

  @Prop({ type: Array, required: true })
  skillList!: Array<string>

  closeWindow() {
    this.$router.push('/works')
  }
}
</script>
<style lang="scss" scoped>
.work-window {
  &__container {
    height: 100%;
  }

  &__title {
    font-size: 22px;
    margin-bottom: 20px;
  }
  &__sub-title {
    font-size: 20px;
    margin-bottom: 6px;
  }
  &__image-wrapper {
    flex: 1;
    margin-bottom: 20px;
    /deep/ img {
      //子コンポーネントのimgのサイズ指定
      width: 100%;
    }
  }
  &__text-wrapper {
    flex: 1;
    /deep/ p {
      font-size: 16px;
      margin-bottom: 16px;
    }
    /deep/ a {
      text-decoration: underline;
      transition: 0.2s;
      &:hover {
        opacity: 0.8;
      }
    }
  }
}
</style>
