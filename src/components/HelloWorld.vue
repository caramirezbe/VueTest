<template>
  <v-container>
    <v-form>

      <v-col cols="4">
        <v-text-field
            v-model="lastName"
            :counter="30"
            label="Last Name"
            required
        ></v-text-field>
      </v-col>

      <v-col cols="4">
        <v-text-field
            v-model="firstName"
            :counter="30"
            label="First Name"
            required
        ></v-text-field>
      </v-col>

      <v-col cols="4">
        <v-text-field
            v-model="email"
            :counter="30"
            label="Email"
            required
        ></v-text-field>
      </v-col>
      <v-col cols="4">
        <v-select
          :items="company"
          label="Company"
          aria-required=""
        ></v-select>
      </v-col>
      <v-col cols="4">
        <v-text-field
          v-model="Pwd"
          :counter="30"
          label="Password"
          required
        ></v-text-field>
      </v-col>
      <v-col cols="4">
        <v-text-field
            v-model="PwdAgain"
            :counter="30"
            label="Password Again"
            required
        ></v-text-field>
      </v-col>  
      <v-btn color="primary" &click="ShowInfo">Create User</v-btn>
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
      firstName: '',
      Email:'',   
      company: ['CompanyA', 'CompanyB', 'CompanyC', 'CompanyD'],
      email:'',
      Pwd:'',
      PwdAgain:'',
    }
  }  
}


  


</script>
