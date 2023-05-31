<template>
  <div class="signup-box">
    <h2>SignUp</h2>
    <form>
      <div class="user-box">
        <input type="text" name="" v-model="username" required="">
        <label>Username</label>
      </div>
      <div class="user-box">
        <input type="email" name="" v-model="email" required="">
        <label>Email</label>
      </div>
      <div class="user-box">
        <input type="password" name="" v-model="password" required="">
        <label>Password</label>
      </div>
     
      <a href="#" v-on:click="signUp">
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        SignUp
      </a>
    </form>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'SignUp',
  data() {
   return {
    username: '',
    email: '',
    password: '',
   }
  },
  methods: {
   async signUp() {
      let result = await axios.post("/users/signup", {
        username: this.username,
        email: this.email,
        password: this.password,
      });
      console.warn(result);
      if(result.status ==201) {
         alert("SignUp successfully")
      }
      else {
    alert("SignUp failed")
      }
  }
  
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.logo {
  height: 50px;
  width: 50px;
  border-radius: 50%;

}

.main {
  margin:0;
  padding:0;
  font-family: sans-serif;
  background: linear-gradient(#30142b, #a12727);
}


.signup-box {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 400px;
  padding: 40px;
  transform: translate(-50%, -50%);
  background: rgba(0,0,0,.5);
  box-sizing: border-box;
  box-shadow: 0 15px 25px rgba(0,0,0,.6);
  border-radius: 10px;
}

.signup-box h2 {
  margin: 0 0 30px;
  padding: 0;
  color: #fff;
  text-align: center;
}

.signup-box .user-box {
  position: relative;
}

.signup-box .user-box input {
  width: 100%;
  padding: 7px 0;
  font-size: 16px;
  color: #fff;
  margin-bottom: 30px;
  border: none;
  border-bottom: 1px solid #fff;
  outline: none;
  background: transparent;
}
.signup-box .user-box label {
  position: absolute;
  top:0;
  left: 0;
  padding: 10px 0;
  font-size: 16px;
  color: #fff;
  pointer-events: none;
  transition: .5s;
}

.signup-box .user-box input:focus ~ label,
.signup-box .user-box input:valid ~ label {
  top: -20px;
  left: 0;
  color: #f68e44;
  font-size: 12px;
}

.signup-box form a {
  position: relative;
  display: inline-block;
  padding: 10px 10px;
  color: #ffffff;
  font-size: 16px;
  text-decoration: none;
  text-transform: uppercase;
  overflow: hidden;
  transition: .5s;
  margin-top: 20px;
  letter-spacing: 2px;
  background-color: blue;
  border-radius: 5px;
}

.signup-box a:hover {
  background: #09740b;
  color: #fff;
  border-radius: 5px;
  box-shadow: 0 0 5px #025274,
              0 0 25px #027aad,
              0 0 30px #0290cd,
              0 0 50px #05b4ff;
}

.signup-box a span {
  position: absolute;
  display: block;
}

.signup-box a span:nth-child(1) {
  top: 0;
  left: -100%;
  width: 100%;
  height: 2px;
  background: linear-gradient(90deg, transparent, #f4c003);
  animation: btn-anim1 1s linear infinite;
}

@keyframes btn-anim1 {
  0% {
    left: -100%;
  }
  50%,100% {
    left: 100%;
  }
}

.signup-box a span:nth-child(2) {
  top: -100%;
  right: 0;
  width: 2px;
  height: 100%;
  background: linear-gradient(180deg, transparent, #f4bc03);
  animation: btn-anim2 1s linear infinite;
  animation-delay: .25s
}

@keyframes btn-anim2 {
  0% {
    top: -100%;
  }
  50%,100% {
    top: 100%;
  }
}

.signup-box a span:nth-child(3) {
  bottom: 0;
  right: -100%;
  width: 100%;
  height: 2px;
  background: linear-gradient(270deg, transparent, #f4dc03);
  animation: btn-anim3 1s linear infinite;
  animation-delay: .5s
}

@keyframes btn-anim3 {
  0% {
    right: -100%;
  }
  50%,100% {
    right: 100%;
  }
}

.signup-box a span:nth-child(4) {
  bottom: -100%;
  left: 0;
  width: 2px;
  height: 100%;
  background: linear-gradient(360deg, transparent, #f4b003);
  animation: btn-anim4 1s linear infinite;
  animation-delay: .75s
}

@keyframes btn-anim4 {
  0% {
    bottom: -100%;
  }
  50%,100% {
    bottom: 100%;
  }
}


</style>
