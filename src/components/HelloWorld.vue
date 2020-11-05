<template>
  <v-container>
    <v-toolbar flat color="blue">
      <v-toolbar-title>My Document</v-toolbar-title>
    </v-toolbar>
    <v-form>
      <v-col cols="4">
        <v-text-field
            v-model="lastName"
            :rules="[rules.required]"
            :counter="30"
            label="Last Name"
            required
        ></v-text-field>
      </v-col>

      <v-col cols="4">
        <v-text-field
            v-model="firstName"
            :rules="[rules.required]"
            :counter="30"
            label="First Name"
            required
        ></v-text-field>
      </v-col>

      <v-col cols="4">
        <v-text-field
            v-model="email"
            :rules="[rules.required]"
            :counter="30"
            label="Email"
            required
        ></v-text-field>
      </v-col>
      <v-col cols="4">
        <v-select
          :items="company"
          label="Company"
          :rules="[rules.required]"
        ></v-select>
      </v-col>
      <v-col cols="4">
        <v-text-field
          v-model="Pwd"
          :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
          :rules="[rules.required, rules.mine]"
          :type="show1 ? 'text' : 'password'"
          @click:append="show1 = !show1" 
          hint="At least 8 characters"
          counter
          label="Password"
        ></v-text-field>
      </v-col>
      <v-col cols="4">
        <v-text-field
          v-model="PwdAgain"
          :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
          :rules="[rules.required]"
          :type="show1 ? 'text' : 'password'"
          @click:append="show1 = !show1" 
          hint="At least 8 characters"
          counter
          label="Password Again"
          required
        ></v-text-field>
      </v-col>  
    <v-btn @click="showInfo()" color="primary">Create User</v-btn>
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
      show1: false,
      password: 'Password',
        
        rules: {
          required: value => !!value || 'Required.',
          min: v => v.length >= 8 || 'Min 8 characters',
        },  


    } 
  },
  
  methods: {
    showInfo(){
      alert('User ' + this.lastName + ' ' + this.firstName + ' have created')
    }
  },  
}

</script>
