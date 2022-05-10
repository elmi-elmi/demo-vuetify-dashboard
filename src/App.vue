<template>
  <v-app>
    <v-card width="400px" class="mx-auto mt-10">
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
  </v-app>
</template>

<script>


export default {
  name: 'App',

  components: {},

  data: () => ({
    showPassword: false,
    //
  }),
  computed: {}
};
</script>
