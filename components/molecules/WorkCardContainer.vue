<template>
  <div class="work-card-container__container">
    <work-card
      v-for="(work, index) in worksList"
      :key="index"
      :title="work.title"
      :image="work.image"
      :text="work.text"
      :skill-list="work.skill"
      :page-link="work.pageLink"
      :card-size="work.cardSize"
      :class="{ 'large-card-container': work.cardSize === 'large' }"
      class="work-card-container__work-card"
    />
  </div>
</template>
<script lang="ts">
import { Vue, Component, Prop } from 'nuxt-property-decorator'
import WorkCard from '~/components/molecules/WorkCard.vue'

@Component({
  components: {
    WorkCard,
  },
})
export default class WorkCardContainer extends Vue {
  @Prop({ type: Object, required: true })
  worksList!: Object
}
</script>
<style lang="scss" scoped>
.work-card-container {
  &__container {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    @include tablet {
      display: inline;
    }
  }
  &__work-card {
    width: 48%;
    margin-bottom: 30px;
    @include tablet {
      width: 100%;
    }
    &.large-card-container {
      width: 100%;
    }
  }
}
</style>
