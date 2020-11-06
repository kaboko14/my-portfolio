<template>
  <div class="contact-form__container">
    <form
      action="https://docs.google.com/forms/u/0/d/e/1FAIpQLScaY4q4dP0PDfH41PtN-rhtf1zJPTIMnYcUzNepXjjgWWIanA/formResponse"
      target="dummy"
      @submit="submit"
    >
      <div class="contact-form__form-wrapper">
        <label for="name" class="contact-form__label"> お名前</label>
        <input
          id="name"
          v-model="name"
          name="entry.1994330948"
          type="text"
          placeholder="お名前"
          required
          class="contact-form__name-form contact-form__form"
        />
        <label for="email" class="contact-form__label">メールアドレス</label>
        <p v-if="!emailBool" class="contact-form__error-text">
          入力内容が正しくありません
        </p>
        <input
          id="email"
          v-model="email"
          name="entry.565826134"
          type="text"
          placeholder="adress@mail.co.jp"
          required
          :class="{ 'is-error': !emailBool }"
          class="contact-form__email-form contact-form__form"
          @blur="validateEmailAdress()"
        />
        <label for="message" class="contact-form__label"
          >お問い合わせ内容</label
        >
        <textarea
          id="message"
          v-model="message"
          name="entry.1620761451"
          placeholder="お問い合わせ内容"
          required
          class="contact-form__message-form contact-form__form"
        />
      </div>
      <button
        type="submit"
        name="submit-button"
        value="送信"
        class="contact-form__submit-button"
      >
        送信する
      </button>
    </form>
    <iframe name="dummy" style="display: none" />
  </div>
</template>
<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator'

@Component
export default class ContactForms extends Vue {
  email = ''
  name = ''
  message = ''
  emailBool = true

  submit(event: Event) {
    // 入力漏れ、emailの不備、送信キャンセルの場合は
    // submitしない
    let check: Boolean = false
    if (this.email && this.name && this.message && this.emailBool) {
      check = true
    }
    if (check && confirm('送信してよろしいですか？')) {
      this.$router.push('thanks')
      return true
    }
    event.preventDefault()
  }

  validateEmailAdress() {
    // メールアドレスをバリデーション
    const emailPattern: RegExp = /[\w\-._]+@[\w\-._]+\.[A-Za-z]+/
    this.emailBool = emailPattern.test(this.email)
  }

  pushThanks() {
    if (this.email && this.name && this.message && this.emailBool) {
      this.$router.push('thanks')
    }
  }
}
</script>
<style lang="scss" scoped>
.contact-form {
  &__container {
    max-width: 400px;
  }
  &__form-wrapper {
    display: flex;
    flex-direction: column;
    margin-bottom: 30px;
  }
  &__label {
    font-size: 12px;
    margin-bottom: 4px;
  }
  &__form {
    padding: 8px 10px;
    margin-bottom: 14px;
    background-color: $main-color;
    border: none;
    outline: none;

    //Chormeのオートコンプリート時の背景色を隠す
    &:-webkit-autofill {
      box-shadow: 0 0 0px 1000px $main-color inset;
    }

    &:focus::placeholder {
      color: $main-color;
    }
    &:last-child {
      margin-bottom: 0px;
    }
    &.is-error {
      border: 1px solid $error-color;
    }
  }
  &__error-text {
    font-size: 12px;
    color: $error-color;
  }
  &__message-form {
    height: 160px;
  }
  &__submit-button {
    border: none;
    background-color: $accent-color;
    color: $font-color-wh;
    padding: 6px 20px;
    border-radius: 30px;
  }
}
</style>
