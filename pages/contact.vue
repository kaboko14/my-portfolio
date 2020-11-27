<template>
  <div class="contact__container">
    <page-title>Contact</page-title>
    <contact-forms class="fade-in-2"></contact-forms>
  </div>
</template>
<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator'
import PageTitle from '~/components/atoms/PageTitle.vue'
import ContactForms from '~/components/organisms/ContactForms.vue'

@Component({
  components: {
    PageTitle,
    ContactForms,
  },
})
export default class ContactForm extends Vue {}
</script>
