<template>
  <nuxt-link :to="pageLink" class="work-card__link">
    <my-card class="work-card__card">
      <article
        class="work-card__container"
        :class="{
          'large-card': cardSize === 'large',
          'small-card': cardSize === 'small',
        }"
      >
        <h4 class="work-card__title">{{ title }}</h4>
        <div class="work-card__inner-container">
          <div class="work-card__image-wrapper">
            <img :src="image" :alt="title" />
          </div>
          <div class="work-card__text-wrapper">
            <p class="work-card__text">{{ text }}</p>
            <skill-icon-container
              :skill-list="skillList"
              class="work-card__skill-icon-container"
            />
          </div>
        </div>
      </article>
    </my-card>
  </nuxt-link>
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

  @Prop({ type: String, required: true })
  pageLink!: string

  @Prop({ type: String, required: false, default: 'large' })
  cardSize!: string
}
</script>
<style lang="scss" scoped>
.work-card {
  &__link {
    display: block;
  }
  &__card {
    height: 100%;
  }
  &__title {
    font-size: 18px;
    margin-bottom: 10px;
  }
  &__container {
    height: 100%;
    display: flex;
    flex-direction: column;
  }
  &__inner-container {
    flex: 1;
    display: flex;
    flex-direction: column;
  }
  &__image-wrapper {
    margin-bottom: 10px;
    /deep/ img {
      //子コンポーネントのimgのサイズ指定
      width: 100%;
    }
  }
  &__text-wrapper {
    flex: 1;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    /deep/ p {
      font-size: 14px;
      white-space: pre-line;
    }
  }
  &__text {
    margin-bottom: 20px;
  }
}

// 大きいカードのレイアウト
.large-card {
  & .work-card {
    &__inner-container {
      flex-direction: row;
      flex-wrap: wrap;
      @include tablet {
        display: block;
      }
    }
    &__image-wrapper {
      flex: 1;
      margin-bottom: 0px;
      @include tablet {
        margin-bottom: 10px;
      }
    }
    &__text-wrapper {
      flex: 1;
      margin-left: 20px;
      @include tablet {
        margin-left: 0px;
      }
    }
  }
}
</style>
