<template>
  <q-layout view="lHh Lpr lFf">
    <portal-target name="header"></portal-target>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-grey-1"
    >
      <q-list>
        <q-item-label
          header
          class="text-grey-8"
        >
          菜單
        </q-item-label>
        <Menu
          v-for="link in menus"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import Menu from 'components/Menu'

export default {
  name: 'MainLayout',
  components: {
    Menu
  },
  data () {
    return {
      leftDrawerOpen: false,
      menus: [
        {
          title: '首頁',
          icon: 'home',
          link: '/'
        },
        {
          title: '登錄',
          icon: 'input',
          link: '/login'
        },
        {
          title: '註冊',
          icon: 'open_in_new',
          link: '/signup'
        },
        {
          title: '用戶信息',
          icon: 'person',
          link: '/user'
        },
        {
          title: '尺寸估算',
          icon: 'camera',
          link: '/faceplus'
        },
        {
          title: '訂單信息',
          icon: 'assignment',
          link: '/user-order'
        },
        {
          title: '購物車',
          icon: 'shopping_cart',
          link: '/cart'
        }
      ]
    }
  },
  computed: {
    title() {
      return this.$route.meta.title
    }
  },
  created() {
    this.$root.$on('toggleDrawer', ()=>{
      this.leftDrawerOpen = !this.leftDrawerOpen
    })
  }
}
</script>
