<template>
  <div>
    <div class="login">
      <input 
        type="text" 
        placeholder="Username" 
        id="username" 
        v-model.trim="credentials.username"
      >
      <input 
        type="password"
        id="password"
        placeholder="Password" 
        v-model.trim="credentials.password"
        @keypress.enter="login(credentials)"
        >
      <button @click="login(credentials)">Login</button>
      <router-link :to="{ name : 'Signup' }"><button class="signup">Signup</button></router-link>
    </div>
  </div>
<!-- <div>
    <h2>LogIn</h2>
    <div>
      <label for="username"><b>Username: </b></label>
      <input 
        type="text" 
        placeholder="Enter Username" 
        id="username" 
        v-model.trim="credentials.username"
      >
    </div>
    <div>
      <label for="password"><b>Password: </b></label>
      <input 
        type="password" 
        id="password"
        placeholder="Enter Password" 
        v-model.trim="credentials.password"
        @keypress.enter="login(credentials)"
      >
    </div>
    <button @click="login(credentials)">로그인</button>
  </div> -->
</template>



  

<script>
// import axios from 'axios'
import { mapActions } from 'vuex'

export default {
  name: 'Login',
  data: function() {
    return {
      credentials: {
        username: '',
        password: '',
      }
    }
  },
  methods: {
    ...mapActions([
      'login',
    ]),
    // login: function () {
    //   axios({
    //     method: 'post',
    //     url: 'http://127.0.0.1:8000/accounts/api-token-auth/',
    //     data: this.credentials
    //   })
    //     .then((res) => {
    //       console.log(res)
    //       localStorage.setItem('jwt', res.data.token)
    //       this.$emit('login')
    //       this.$router.push({ name: 'Spring' })
    //     })
    //     .catch(err => {
    //       console.log(err)
    //     })
    // }
  }
}
</script>

<style scoped>
  body {
  /* background-image: url(../../assets/login1.jpg);
  background-color: #FF9292; */
  font-family: DX시인과나;
}
.login {
  overflow: hidden;
  background-color: white;
  padding: 40px 30px 30px 30px;
  border-radius: 10px;
  position: absolute;
  top: 50%;
  left: 50%;
  width: 400px;
  -webkit-transform: translate(-50%, -50%);
  -moz-transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  -o-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  -webkit-transition: -webkit-transform 300ms, box-shadow 300ms;
  -moz-transition: -moz-transform 300ms, box-shadow 300ms;
  transition: transform 300ms, box-shadow 300ms;
  box-shadow: 5px 10px 10px rgba(2, 128, 144, 0.2);
}
.login::before, .login::after {
  content: "";
  position: absolute;
  width: 600px;
  height: 600px;
  border-top-left-radius: 40%;
  border-top-right-radius: 45%;
  border-bottom-left-radius: 35%;
  border-bottom-right-radius: 40%;
  z-index: -1;
}
.login::before {
  left: 40%;
  bottom: -130%;
  background-color: rgba(69, 105, 144, 0.15);
  -webkit-animation: wawes 6s infinite linear;
  -moz-animation: wawes 6s infinite linear;
  animation: wawes 6s infinite linear;
}
.login::after {
  left: 35%;
  bottom: -125%;
  background-color: rgba(2, 128, 144, 0.2);
  -webkit-animation: wawes 7s infinite;
  -moz-animation: wawes 7s infinite;
  animation: wawes 7s infinite;
}
.login > input {
  font-family: "Asap", sans-serif;
  display: block;
  border-radius: 5px;
  font-size: 16px;
  background: white;
  width: 100%;
  border: 0;
  padding: 10px 10px;
  margin: 15px -10px;
}
.login > button {
  font-family: "Asap", sans-serif;
  cursor: pointer;
  color: #fff;
  font-size: 16px;
  text-transform: uppercase;
  width: 80px;
  border: 0;
  padding: 10px 0;
  margin-top: 10px;
  margin-left: -5px;
  border-radius: 5px;
  background-color: #f45b69;
  -webkit-transition: background-color 300ms;
  -moz-transition: background-color 300ms;
  transition: background-color 300ms;
}
.login > button:hover {
  background-color: #f24353;
}
.signup {
  font-family: "Asap", sans-serif;
  cursor: pointer;
  color: #fff;
  font-size: 16px;
  text-transform: uppercase;
  width: 80px;
  border: 0;
  padding: 10px 0;
  margin-bottom: 20px;
  margin-left: -250px;
  border-radius: 5px;
  background-color: #6886c5;
  -webkit-transition: background-color 300ms;
  -moz-transition: background-color 300ms;
  transition: background-color 300ms;
}
.signup > button:hover {
  background-color: #f24353;
}
@-webkit-keyframes wawes {
  from {
    -webkit-transform: rotate(0);
  }
  to {
    -webkit-transform: rotate(360deg);
  }
}
@-moz-keyframes wawes {
  from {
    -moz-transform: rotate(0);
  }
  to {
    -moz-transform: rotate(360deg);
  }
}
@keyframes wawes {
  from {
    -webkit-transform: rotate(0);
    -moz-transform: rotate(0);
    -ms-transform: rotate(0);
    -o-transform: rotate(0);
    transform: rotate(0);
  }
  to {
    -webkit-transform: rotate(360deg);
    -moz-transform: rotate(360deg);
    -ms-transform: rotate(360deg);
    -o-transform: rotate(360deg);
    transform: rotate(360deg);
  }
}
a {
  text-decoration: none;
  color: rgba(255, 255, 255, 0.6);
  position: absolute;
  right: 10px;
  bottom: 10px;
  font-size: 12px;
}
</style>
