<template>
    <v-container>
        <v-toolbar flat color="blue">
          <v-toolbar-title>Pwd Change</v-toolbar-title>
         </v-toolbar>
    
    <v-form>
        <v-row>
            <v-col cols='6'>
                <v-text-field
                    v-model="oldPwd"
                    label="Current Password"
                    :counter="10"
                    required              
                ></v-text-field>
                <v-text-field
                    v-model="newPwd"
                    label="New Password"
                    :counter="10"
                    required              
                ></v-text-field>
                <v-text-field
                    v-model="newPwdAgain"
                    label="New Password Again"
                    :counter="10"
                    required              
                ></v-text-field>
            </v-col>
            <v-col cols='6'>
                <v-alert
                    :type="mType"

                >{{message}} </v-alert>
                
            </v-col>
            <v-btn @click="checkPwd()" color="primary">Submit</v-btn>
        </v-row>
    </v-form>

    </v-container>
</template>

<script>
export default {
    name: 'Pwdchange',

    data(){
        return {
                oldPwd:'',
                newPwd:'',
                newPwdAgain:'',
                mType:undefined,
                message:'',
            }
        },

    methods:{
        checkPwd(){
            if (this.newPwd === this.newPwdAgain){
                this.mType = 'success'
                this.message = 'Password have been changed'  
            }
            else {
                this.mType = 'error'
                this.message = 'Password does not match'
            }
            
        }

    }

}
</script>