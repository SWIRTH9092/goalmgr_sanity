<template>
    <form @submit.prevent="handleSubmit">

        <h2>Sign up Form</h2>

        <label>Userid:</label>
        <input type="text" v-model="userid" placeholder="userid" required maxlength="12">
        <div v-if="useridError" class="error" > {{ useridError }}</div>

        <label>Password:</label>
        <input type="password" v-model="password" placeholder="password" required >
        <div v-if="passwordError" class="error" > {{ passwordError }}</div>
        
        <label>Email:</label>
        <input type="email" v-model="email" placeholder="email" required maxlength="50">

        <label>First Name:</label>
        <input type="text" v-model="firstname"  placeholder="first name" required maxlenth="50">
 
        <label>Last Name:</label>        
        <input type="text" v-model="lastname" placeholder="last name" required maxlenth="50">

        <label>Cell Phone:</label>
        <input type="tel" v-model="cellphone" required placeholder="1234567890" pattern="[0-9]{10}">

        <div class="submit">
            <button>Create Signon</button>
        </div>
    </form>

</template>
<script>
export default {
    data() {
        return {
            userid: '',
            password: '',
            email: '',
            firstname: '',
            lastname: '',
            cellphone: '',
            useridError: null,
            passwordError: null
        }
    },
    methods: {
        handleSubmit() {     
            //validate userid
            this.useridError = this.userid.length> 7 ?
                    '' : 'userid must be at least 7 characters long'
            // validate password
                this.passwordError = this.password.length > 7 ?
                    '' : 'password must be at least 7 characters long'
            
            // print to console log signup info
            if(!this.useridError ) {
                if(!this.passwordError) {
                    console.log('userid:', this.userid)
                    console.log('password:', this.password)
                    console.log('email:', this.email)
                    console.log('firstname:', this.firstname)
                    console.log('lastname:', this.lastname)
                    console.log('cellphone:', this.cellphone)
                }
            }         
        }
    }
}
</script>
<style>
h2 {
    text-align:center;
    color: #0b6dff;
    
}
form {
    max-width: 420px;
    margin: 30px auto;
    background: white;
    text-align: left;
    padding: 40px;
    border-radius: 10px;
  }
  label {
    color: #aaa;
    display: inline-block;
    margin: 25px 0 15px;
    font-size: 0.6em;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: bold;
  }
  input {
    display: block;
    padding: 10px 6px;
    width: 100%;
    box-sizing: border-box;
    border: none;
    border-bottom: 1px solid #ddd;
    color: #555;
  } 

  button {
    background: #0b6dff;
    border: 0;
    padding: 10px 20px;
    margin-top: 20px;
    color: white;
    border-radius: 20px;
  }
  .submit {
    text-align: center;
  }
  .error {
    color: #ff0062;
    margin-top: 10px;
    font-size: 0.8em;
    font-weight: bold;
  }
</style>