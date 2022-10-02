<template>
<div class = main>
  <form @submit.prevent="handleSubmit" class="login">
<img src="../assets/img/img1.png">
    <div class="form-group">
      <input type="email" class="form-control" placeholder="Email" />
    </div>

    <div class="form-group">
      <input type="password" class="form-control" placeholder="Password" />
    </div>

    <button class="btn">Отправить</button>
  </form>
  </div>
</template>

<script>
import axios from "axios";
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Login",
  data() {
    return {
      email: "",
      password: "",
    };
  },
  methods: {
    async handleSubmit() {
      const response = await axios.post("Login", {
        email: this.email,
        password: this.password,
      });
      localStorage.setItem("token", response.data.token);
    },
  },
};
</script>

<style>
body {
  background: rgb(241,241,241);

}
.main {
  background: #FFFFFF;
  width: 300px;
  height:250px;
  margin: 0 auto 100px;
  padding: 35px;
  text-align: center;
   border-radius: 4px;
    position: fixed; top: 50%; left: 50%;
  -webkit-transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
   
  }
  img {
  position: relative;
    top: 50%;
    width: 100%;
  }
input {

 font-family:Arial;
  background: rgb(251,251,251);
  width: 90%;
  margin: 0 0 15px;
  padding: 15px;
  box-sizing: border-box;
  font-size: 14px;
  border: 1px solid rgb(220,220,220);
  border-radius: 4px;
  }

.btn {
font-family: Arial;
  background: rgb(241,241,241) ;
  width: 120px;
  height: 30px;
  border: 1px solid rgb(220,220,220);
  padding: 15px;
  color: #111;
  font-size: 14px;
  cursor: pointer;
  margin: 20px;
  border-radius: 4px;
    display: inline-flex;
    justify-content: center;
    align-items: center; 
}

</style>
