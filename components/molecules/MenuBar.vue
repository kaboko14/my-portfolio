<template>
  <div class="menu-bar__container">
    <nav class="menu-bar__menu-container">
      <ul>
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
}
</script>
<style lang="scss" scoped>
.menu-bar {
  &__container {
    padding: 30px;
    position: fixed;
    top: 0;
    left: 0;
    width: $menuBar-width;
    height: 100vh;
    background-color: $main-color;

    @include tablet {
      left: -$menuBar-width;
    }
  }
}
</style>
