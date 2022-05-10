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
      <v-btn text rounded>home</v-btn>
      <v-btn text rounded>login</v-btn>
    </v-app-bar>

<!--    login -->
    <v-content>
    <v-card width="400px" class="mx-auto mt-5">
      <v-card-title>
        <h1 class="display-1">Login</h1>
      </v-card-title>

      <v-card-text>
        <v-form>
          <v-text-field
              label="Username"
              type="text"
              prepend-icon="mdi-account-circle">
            User
          </v-text-field>
          <v-text-field
              label="Password"
              :type="showPassword
              ?'text':'password'"
              prepend-icon="mdi-lock"
              :append-icon="showPassword
              ?'mdi-eye'
              : 'mdi-eye-off'"
              @click:append="showPassword=!showPassword">
            Password
          </v-text-field>
        </v-form>
      </v-card-text>

      <v-divider></v-divider>

      <v-card-actions>
        <v-btn color="success" @click="login">Register</v-btn>
        <v-spacer></v-spacer>
        <v-btn color="info" @click="register">Login</v-btn>
      </v-card-actions>

    </v-card>
    </v-content>
    <v-footer
        padless
        color="green"
        app
        v-bind="localAttrs"

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
      </v-card>
    </v-footer>

  </v-app>
</template>

<script>


export default {
  name: 'App',

  components: {},

  data: () => ({
    showPassword: false,
    icons: [
      'mdi-facebook',
        'mdi-twitter']
    //
  }),
  computed: {}
};
</script>
