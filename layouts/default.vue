<template>
  <v-app dark>
    <v-navigation-drawer
    v-model="drawer"
    :mini-variant="miniVariant"
    :clipped="clipped"
    fixed
    app
    class="drawer"
    >
    <v-list>
    <v-list-item
      v-for="(item, i) in items"
      :key="i"
      :to="item.to"
      router
      exact
    >
      <v-list-item-action>
        <v-icon>{{ item.icon }}</v-icon>
      </v-list-item-action>
        <v-list-item-content class="ml-auto">
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-list>
    </v-navigation-drawer>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
      class="navbar"
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title class="text-right">{{ title }}</v-toolbar-title>
      <v-spacer />
    </v-app-bar>
    <v-main>
      <Nuxt />
    </v-main>
    <v-footer
      :absolute="!fixed"
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: true,
      items: [
        {
          icon: 'mdi-home',
          title: 'Digiit',
          to: '/'
        },
        {
          icon: 'mdi-account-group',
          title: 'Team',
          to: '/team'
        },
        {
          icon: 'mdi-application-parentheses',
          title: 'Screens',
          to: '/functionnalities'
        },
        {
          icon: 'mdi-download-circle',
          title: 'Download',
          to: '/download'
        }
      ],
      title: 'Digiit'
    }
  }
}
</script>

<style>
.navbar{
  background: linear-gradient(to right, #271fa7, #07a1d7);
  color: white;
}

.drawer{
  background: linear-gradient(to right, #0c2fa1, #0752a7);
  color: white;
}
</style>
