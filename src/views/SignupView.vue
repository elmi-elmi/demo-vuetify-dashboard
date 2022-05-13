<template>
  <v-container>
    <v-row>
      <v-col>
        <h1>Signup</h1>
        <v-form>
          <v-text-field
              type="email"
              label="Email"
          ></v-text-field>
          <v-autocomplete
              label="Which browser do you use?"
              :items="browser"
          ></v-autocomplete>

          <v-file-input
              label="Attach your profile picture"
          ></v-file-input>

          <v-text-field
            v-model="birthday"
            label="Your birthday"
          ></v-text-field>

          <v-date-picker
              v-model="birthday"
          ></v-date-picker>
          <v-checkbox
          label="Agree to terms & conditions "
          ></v-checkbox>

          <v-btn
          type="submit"
          color="primary"
          >Submit</v-btn>

        </v-form>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "SignupView",
  data: () => ({
    browser: [
      'Chrome',
      'Firefox',
      'Opera'
    ],
    birthday:''
  })
}
</script>

<style scoped>

</style>