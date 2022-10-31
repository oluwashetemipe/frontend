<template>
<div>
  <h1>{{msg}}</h1>
</div> 
<h1>Login</h1>
<form className="myform" onSubmit={this.validateLogin()}>
    <div className="myformgroup">
    <input type="text" v-model="form.userName" placeholder="Username"/>
    <input type="password" v-model="form.password" placeholder="Password"/>
    <button v-on:click = "login()">Login</button>
 </div>
</template>




<script>
import axios from 'axios'
// import axios from 'axios'
export default {
  name:'Log_in',
  data() {
    return {
      form:{
        userName: '',
        password:'',
      }
    }
  },
  methods: {
    login() {
    //   let result = await axios.post(
    //     `https://usermanagementsyt.herokuapp.com/api/login-user`
    //   )
    //   if(result.status == 200 && result.data.length>0)
    // {
    //   localStorage.setItem("user-info",JSON.stringify(result.data[0]))
    //   this.$router.push({name: 'Home'})
    // }
       console.warn(this.userName,this.password)
       axios.post("https://usermanagementsyt.herokuapp.com/api/login-user",this.form)
       .then(function(response){
            if(response == 201){
                this.$router.push({name:'Home'})
            }
       }.bind(this));
    }
  },
  mounted(){
    let user = localStorage.getItem('user-info');
    if(user){
      this.$router.push({name: 'Home'})
    }
  }
}
</script>

