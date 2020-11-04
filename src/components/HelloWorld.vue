<template>
  <v-container>
    <v-form>
      <v-text-field
          v-model="lastName"
          :counter="50"
          label="Last Name"
          required
      ></v-text-field>

      <v-btn color="primary">Create User</v-btn>
    </v-form>

    {{ lastName }}
  </v-container>
</template>

<script>
export default {
  // LastName, FirstName, Email, Company, Pwd, PwdAgain
  name: 'HelloWorld',

  data() {
    return {
      lastName: '',
    }
  }
}
</script>
