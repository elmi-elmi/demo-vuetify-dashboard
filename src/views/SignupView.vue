<template>
  <v-container
  >
    <v-row
        justify="center"
    >
      <v-col
          cols="6"
      >

        <h1>Signup</h1>
        <v-form
            ref="form"
            v-model="valid"
            lazy-validation
        >
          <v-text-field
              type="email"
              label="Email"
              :rules="emailRules"

          ></v-text-field>
          <v-autocomplete
              label="Which browser do you use?"
              :items="browser"
              :rules="[v=>!!v || 'please select a browser']"
          ></v-autocomplete>

          <v-file-input
              label="Attach your profile picture"
              :rules="[v=>!!v || 'please select you file']"

          ></v-file-input>

          <v-text-field
              v-model="birthday"
              label="Your birthday"
              :rules="[v=>!!v || 'please select your birthday']"

          ></v-text-field>

          <v-date-picker
              v-model="birthday"
          ></v-date-picker>
          <v-checkbox
              label="Agree to terms & conditions "
              v-model="checkbox"
          ></v-checkbox>

          <v-btn
              @click="validate"
              type="submit"
              color="primary"
              :disabled="!valid"
          >Submit
          </v-btn>

          <v-btn
              color="error"
              class="ml-3"
              @click="reset"


          >
            Reset form
          </v-btn>

          <v-btn
              color="warning"
              class="ml-3"
              @click="resetValidation"
          >
            Reset Validation
          </v-btn>

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
    birthday: '',
    emailRules: [
      v => !!v || 'E-mail is required',
      v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
    ],
    checkbox: false,
    valid:true
  }),
  methods: {
    reset() {
      this.$refs.form.reset()
    },
    resetValidation() {
      this.$refs.form.resetValidation()
    },
    validate(){
      this.$refs.form.validate()
    }


  }
}
</script>

<style scoped>

</style>