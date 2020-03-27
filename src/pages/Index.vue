<template>
  <q-page class="q-pa-sm">
    <portal to="header">
      <q-header elevated>
          <q-toolbar>
            <q-btn flat dense icon="menu" @click="$root.$emit('toggleDrawer')" />
            <q-toolbar-title>類別</q-toolbar-title>
          </q-toolbar>
      </q-header>
    </portal>

    <q-list bordered separator>
      <q-item v-for="item in lists" :key="item.id" to="/style" clickable v-ripple>
        <q-item-section>{{ item.title }}</q-item-section>
      </q-item>
    </q-list>
  </q-page>
</template>

<script>
export default {
  name: 'PageIndex',
  data() {
    return {
      lists: [{
        id: 1,
        title: 'category 1'
      },{
        id: 2,
        title: 'category 2'
      }]
    }
  }

}
</script>
