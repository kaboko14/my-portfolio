<template>
  <nav class="menu-bar__container" :class="{ 'is-view': isView }">
    <div class="menu-bar__up-wrapper">
      <nuxt-link to="/" class="menu-bar__home-link">
        <img
          src="~/assets/image/icon.png"
          alt="ホームへのリンク"
          class="menu-bar__icon"
        /><br />
        OTA KAHORI</nuxt-link
      >
    </div>
    <ul class="menu-bar__under-wrapper">
      <menu-tag
        v-for="menu in menuList"
        :key="menu.linkName"
        :link-name="menu.linkName"
        :link-url="menu.linkUrl"
      />
    </ul>
    <div class="menu-bar__open-button" @click="menuOpen()">maru</div>
  </nav>
</template>
<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'
import MenuTag from '~/components/atoms/MenuTag.vue'

@Component({
  components: { MenuTag },
})
export default class MenuBar extends Vue {
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

  isView = true

  menuOpen() {
    this.isView = !this.isView
  }
}
</script>
<style lang="scss" scoped>
.menu-bar {
  &__container {
    position: fixed;
    top: 0;
    left: 0;
    display: flex;
    flex-direction: column;
    text-align: center;
    width: $menuBar-width;
    height: 100vh;
    padding: 60px 30px;
    background-color: $main-color;
    @include tablet {
      top: -100%;
      width: 100vw;
      height: 400px;
      padding: 60px 30px 40px 30px;
      transition: 0.3s;
    }

    &.is-view {
      @include tablet {
        top: 0;
      }
    }
  }
  &__up-wrapper {
    flex: 1;
  }
  &__home-link {
    display: block;
    font-size: 20px;
    font-weight: bold;
    flex: 1;
    transition: 0.2s;
    &:hover {
      transform: scale(1.1, 1.1);
    }
  }
  &__icon {
    display: inline-block;
    width: 100px;
    height: 100px;
    object-fit: cover;
    border-radius: 50%;
  }
  &__under-wrapper {
    flex: 1;
    @include tablet {
      flex: 0;
      margin-top: auto;
    }
  }
  &__open-button {
    display: none;
    @include tablet {
      display: block;
      position: fixed;
      top: 10px;
      right: 10px;
    }
  }
}
</style>
