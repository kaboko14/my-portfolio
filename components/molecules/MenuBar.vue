<template>
  <div class="menu-bar__wrapper" :class="{ 'is-view': isView }">
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
          @click-menu-tag="menuOpen()"
        />
      </ul>
    </nav>
    <div
      class="menu-bar__open-button"
      :class="{ close: isView }"
      @click.stop="menuOpen()"
    ></div>
  </div>
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

  isView = false

  menuOpen() {
    this.isView = !this.isView
  }
}
</script>
<style lang="scss" scoped>
.menu-bar {
  &__wrapper {
    position: fixed;
    top: 0;
    left: 0;
    @include tablet {
      height: 0;
    }
    &.is-view {
      @include tablet {
        width: 100vw;
        height: 100vh;
        background-color: rgba($black, 0.8);
        transition: 0.3s;
      }
    }
  }
  &__container {
    text-align: center;
    width: $menuBar-width;
    height: 100vh;
    padding: 60px 0px;
    background-color: $main-color;
    pointer-events: auto;
    @include tablet {
      width: 100vw;
      height: 400px;
      padding: 60px 30px 40px 30px;
      transform: translateY(-100%);
      transition: 0.3s;
    }
    &.is-view {
      @include tablet {
        transform: translateY(0);
      }
    }
  }
  &__home-link {
    display: inline-block;
    font-size: 20px;
    font-weight: bold;
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
  &__up-wrapper {
    margin-bottom: 40px;
    @include tablet {
      margin-bottom: 20px;
    }
  }
  &__under-wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  &__open-button {
    display: none;
    @include tablet {
      display: block;
      position: fixed;
      top: 10px;
      right: 10px;
      width: 40px;
      height: 40px;
      border-radius: 50%;
      background: $main-color url(~@/assets/image/hamburger.svg) center center
        no-repeat;
      background-size: 70%;
      cursor: pointer;
    }
    &.close {
      background-image: url(~@/assets/image/close.svg);
    }
  }
}
</style>
