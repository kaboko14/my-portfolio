<template>
  <div class="index__container">
    <section class="index__content-wrapper">
      <h1 class="index__name fade-in-1">OTA KAHORI</h1>
      <p class="index__text fade-in-2">
        こちらは太田かほりのポートフォリオサイトです。<br />
        会計事務所で勤務していた経験を経て、働く人たちの役に立つツール作りに携わりたいと考えエンジニアを目指して学習しています。<br />
        「物事の効率化」「課題の発見・解決」が実現できるエンジニアを目指しています。
      </p>
    </section>
    <nav class="index__menu-container fade-in-3">
      <ul class="index__menu-wrapper">
        <menu-tag
          v-for="menu in menuList"
          :key="menu.linkName"
          :link-name="menu.linkName"
          :link-url="menu.linkUrl"
        />
      </ul>
    </nav>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'
import MenuTag from '~/components/atoms/MenuTag.vue'

@Component({
  layout: 'home',
  components: {
    MenuTag,
  },
})
export default class extends Vue {
  menuList = {
    about: {
      linkName: 'About',
      linkUrl: 'about',
    },
    works: {
      linkName: 'Works',
      linkUrl: 'works',
    },
    contact: {
      linkName: 'Contact',
      linkUrl: 'contact',
    },
  }
}
</script>
<style lang="scss" scoped>
.index {
  &__container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 100%;
    min-height: 100vh;
    padding: 60px 40px;
    background: url(~@/assets/image/icon-white.png) $main-color no-repeat right
      bottom;
    background-size: contain;
    @include tablet {
      padding: 10vh 40px;
      justify-content: left;
      background-size: 70%;
    }
  }
  &__content-wrapper {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  &__name {
    position: relative;
    font-size: 60px;
    line-height: 1.2;
    margin-bottom: 30px;
    z-index: 1;
    &::before {
      content: '';
      display: block;
      position: absolute;
      top: 50%;
      left: -40px;
      z-index: -1;
      transform: translateY(-50%);
      width: 60px;
      height: 120%;
      background-image: $bg-image-stripe;
    }
    @include tablet {
      font-size: 40px;
    }
  }
  &__text {
    max-width: 560px;
    position: relative;
    z-index: 2;
    margin-bottom: 30px;
  }
  &__menu-container {
    position: relative;
    display: block;
    width: 100%;
    max-width: 300px;
    @include tablet {
      margin-top: auto;
    }
  }
  &__menu-wrapper {
    display: flex;
    justify-content: space-around;
  }
}
</style>
