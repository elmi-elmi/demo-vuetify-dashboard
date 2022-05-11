<template>
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
      <v-btn color="success" >Register</v-btn>
      <v-spacer></v-spacer>
      <v-btn color="info" >Login</v-btn>
    </v-card-actions>

  </v-card>
</template>

<script>
export default {
  name: "LoginUser",
  data: () => ({
    showPassword: false,
  }),
}
</script>

<style scoped>

</style>