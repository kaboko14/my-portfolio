<template>
  <div class="works-card-container__container">
    <work-card
      v-for="(work, index) in worksList"
      :key="index"
      :title="work.title"
      :image="work.image"
      :text="work.text"
      :skill-list="work.skill"
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
export default class WorksCardContainer extends Vue {
  @Prop({ type: Object, required: true })
  worksList!: Object
}
</script>
