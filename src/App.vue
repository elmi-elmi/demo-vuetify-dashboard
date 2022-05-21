<template>

  <v-app>
    <v-app-bar
        dense
        flat
        app
        dark
        color="green"
        class="lighten-1"
    >
      <v-app-bar-title>Vue Dahboard</v-app-bar-title>
      <v-spacer></v-spacer>
      <v-btn
          rounded
          text
          v-for="link in links" :key="`${link.label}-link-header`" :to="link.url" >{{link.label}}
      </v-btn>

      <v-btn @click="toggleTheme" text rounded>Toggle theme</v-btn>
    </v-app-bar>

<!--    login -->
    <v-main>
    <router-view></router-view>
    </v-main>
    <v-footer
        padless
        color="green"
        app
    >
      <v-card
          flat
          tile
          width="100%"
          class="green lighten-1 text-center"
      >
        <v-card-text>
          <v-btn
              v-for="icon in icons"
              :key="icon"
              class="mx-4"
              icon
          >
            <v-icon size="24px">
              {{ icon }}
            </v-icon>
          </v-btn>
        </v-card-text>

        <v-divider></v-divider>

        <v-card-text class="white--text">
          {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
        </v-card-text>

        <v-btn
            rounded
            text
            v-for="link in links" :key="`${link.label}-link-footer`" :to="link.url" >{{link.label}}
        </v-btn>

      </v-card>
    </v-footer>

  </v-app>
</template>

<script>

export default {
  name: 'App',

  components: {},

  data: () => ({

    icons: [
      'mdi-facebook',
        'mdi-twitter'],

    links:[{
      label:'home',
      url:'/'
    },
      {
        label:'login',
        url: '/login'
      },
      {
        label: 'signup',
        url:'/signup'
      },
      {
        label:'dashboard',
        url: '/dashboard'
      }]
  }),
  methods:{
    toggleTheme(){
      this.$vuetify.theme.dark = !this.$vuetify.theme.dark
    }
  }
};
</script>
