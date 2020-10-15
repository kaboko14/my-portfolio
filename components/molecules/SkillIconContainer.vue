<template>
  <div class="skill-icon-container__container">
    <div
      v-for="(skill, index) in skillList"
      :key="index"
      class="skill-icon-container__image"
    >
      <skill-icon :skill="skill" />
    </div>
  </div>
</template>
<script lang="ts">
import { Vue, Component, Prop } from 'nuxt-property-decorator'
import SkillIcon from '~/components/atoms/SkillIcon.vue'

@Component({
  components: {
    SkillIcon,
  },
})
export default class SkillIconContainer extends Vue {
  @Prop({ type: Array, required: true })
  skillList!: Array<string>
}
</script>
<style lang="scss" scoped>
.skill-icon-container {
  &__container {
    display: grid;
    grid-template-columns: repeat(auto-fill, 40px);
    gap: 10px;
  }
}
</style>
