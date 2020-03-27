<template>
  <q-page class="flex q-pa-sm">
    <portal to="header">
      <q-header elevated>
        <q-toolbar>
          <q-btn flat dense icon="menu" @click="$root.$emit('toggleDrawer')" />
          <q-toolbar-title>登錄</q-toolbar-title>
        </q-toolbar>
      </q-header>
    </portal>

    <q-card class="full-width">
      <q-tabs
        v-model="tab"
        dense
        class="text-grey"
        active-color="primary"
        indicator-color="primary"
        align="justify"
        narrow-indicator
      >
        <q-tab name="login" label="Login" />
        <q-tab name="register" label="Register" />
      </q-tabs>

      <q-separator />

      <q-tab-panels v-model="tab" animated>
        <q-tab-panel name="login">
          <login-register :tab="tab" />
        </q-tab-panel>

        <q-tab-panel name="register">
          <login-register :tab="tab" />
        </q-tab-panel>
      </q-tab-panels>
    </q-card>
  </q-page>
</template>

<script>
export default {
  name: 'PageAuth',
  data(){
    return {
      tab: 'login'
    }
  },
  components: {
    'login-register': require('components/LoginRegister.vue').default
  }
}
</script>
