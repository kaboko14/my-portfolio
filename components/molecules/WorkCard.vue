<template>
  <my-card>
    <section>
      <h3 class="work-card__title">{{ title }}</h3>
      <div class="work-card__image-wrrapper">
        <slot name="image" />
      </div>
      <div class="work-cord__text-wrapper">
        <slot name="text" />
      </div>
      <skill-icon-container :skill-list="skillList" />
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
