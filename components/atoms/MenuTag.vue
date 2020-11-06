<template>
  <nuxt-link :to="linkUrl">
    <div>{{ linkName }}</div>
  </nuxt-link>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'nuxt-property-decorator'

@Component
export default class MenuTag extends Vue {
  @Prop({ type: String, required: true })
  linkName!: string

  @Prop({ type: String, required: true })
  linkUrl!: string
}
</script>

<style lang="scss" scoped></style>
