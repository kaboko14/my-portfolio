<template>
  <my-card>
    <section>
      <h3 class="work-card__title">{{ title }}</h3>
      <div class="work-card__inner-container">
        <div class="work-card__image-wrapper">
          <slot name="image" />
        </div>
        <div class="work-card__text-wrapper">
          <slot name="text" />
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
      flex-direction: column;
    }
  }
  &__title {
    margin-bottom: 10px;
  }
  &__image-wrapper {
    // text-align: center;
    display: flex;
    height: 500px;
    flex: 1;
    height: auto;
    @include tablet {
      margin-bottom: 0px;
    }
  }
  &__text-wrapper {
    margin-left: 20px;
    flex: 1;
    @include tablet {
      margin-left: 0px;
    }
  }
  &__skill-icon-container {
    margin-top: 10px;
  }
}
</style>
