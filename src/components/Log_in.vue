<template>
<div>
  <h1>{{msg}}</h1>
</div> 
<h1>Login</h1>
 <div>
    <input type="text" v-model="form.username" placeholder="Username"/>
    <input type="password" v-model="form.password" placeholder="Password"/>
    <button v-on:click = "login()">Login</button>
 </div>
</template>




<script>
import axios from 'axios'
export default {
  // name:'Log_in',
  // props:{
  //       msg: String
  //     }
  data() {
    return {
      form:{
        username: '',
        password:'',
      }
    }
  },
  methods: {
    login() {
       axios.post("https://usermanagementsyt.herokuapp.com/api/login-user",this.form)
       .then(function(response){
            if(response == 201){
                this.$router.push({name:'Home'})
            }
       }.bind(this));
    }
  }
}
</script>

