<template>
  <nuxt-link :to="pageLink">
    <my-card>
      <section
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
            <p>{{ text }}</p>
            <skill-icon-container
              :skill-list="skillList"
              class="work-card__skill-icon-container"
            />
          </div>
        </div>
      </section>
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
  &__title {
    font-size: 18px;
    margin-bottom: 10px;
  }
  &__image-wrapper {
    margin-bottom: 10px;
    /deep/ img {
      //子コンポーネントのimgのサイズ指定
      width: 100%;
    }
  }
  &__text-wrapper {
    /deep/ p {
      font-size: 14px;
      white-space: pre-line;
    }
  }
  &__skill-icon-container {
    margin-top: 10px;
  }
}

// 大きいカードのレイアウト
.large-card {
  & .work-card {
    &__inner-container {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
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
