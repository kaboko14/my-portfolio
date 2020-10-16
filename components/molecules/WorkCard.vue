<template>
  <my-card>
    <section>
      <h4 class="work-card__title">{{ title }}</h4>
      <div class="work-card__inner-container">
        <div class="work-card__image-wrapper">
          <img :src="image" :alt="title" />
        </div>
        <div class="work-card__text-wrapper">
          <p>{{ text }}</p>
          <skill-icon-container
            :skill-list="skillList"
            class="work-card__skill-icon-container"
          />
        </div>
      </div>
    </section>
  </my-card>
</template>
<script lang="ts">
import { Vue, Component, Prop } from 'nuxt-property-decorator'
import MyCard from '~/components/atoms/MyCard.vue'
import SkillIconContainer from '~/components/molecules/SkillIconContainer.vue'

@Component({
  components: {
    MyCard,
    SkillIconContainer,
  },
})
export default class WorkCard extends Vue {
  @Prop({ type: String, required: true })
  title!: string

  @Prop({ type: String, required: true })
  image!: string

  @Prop({ type: String, required: true })
  text!: string

  @Prop({ type: Array, required: true })
  skillList!: Array<string>
}
</script>
<style lang="scss" scoped>
.work-card {
  &__inner-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    @include tablet {
      display: block;
    }
  }
  &__title {
    margin-bottom: 10px;
  }
  &__image-wrapper {
    flex: 1;
    /deep/ img {
      //子コンポーネントのimgのサイズ指定
      width: 100%;
    }
    @include tablet {
      margin-bottom: 0px;
    }
  }
  &__text-wrapper {
    margin-left: 20px;
    flex: 1;
    /deep/ p {
      white-space: pre-line;
    }
    @include tablet {
      margin-left: 0px;
    }
  }
  &__skill-icon-container {
    margin-top: 10px;
  }
}
</style>
