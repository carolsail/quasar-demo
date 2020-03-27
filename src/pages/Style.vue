<template>
    <q-page class="q-pa-sm">
      <portal to="header">
          <q-header elevated>
              <q-toolbar>
                  <q-btn v-go-back.single flat dense icon="arrow_back" /> 
                  <q-toolbar-title>款式</q-toolbar-title>
              </q-toolbar>
          </q-header>
      </portal>

      <q-list bordered separator>
        <q-item v-for="item in lists" :key="item.id" to="/diy" clickable v-ripple>
            <q-item-section>{{ item.title }}</q-item-section>
        </q-item>
      </q-list>
    </q-page>
</template>

<script>
export default {
  name: 'PageStyle',
  data() {
    return {
      lists: [{
        id: 1,
        title: 'style 1'
      },{
        id: 2,
        title: 'style 2'
      }]
    }
  }

}
</script>
