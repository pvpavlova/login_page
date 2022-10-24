<template>
  <div class="header1">
    <div class="header1">
      <div class="header">
        <img class="logo" src="..//assets/img/logo.png" />
      </div>
    </div>
  </div>
  <div class="main">
    <form @submit.prevent="handleSubmit" class="login">
      <h1>Авторизация</h1>
      <div class="form-group">
        <label class="form"
          >Логин <input type="email" class="form-control"
        /></label>
      </div>

      <div class="form-group">
        <label>Пароль <input type="password" class="form-control" /></label>
      </div>
      <div class="checkbox">
        <label class="checkbox">
          <input
            type="checkbox"
            name="LDAP"
            value="no"
            class="checkbox1"
          />LDAP</label
        >
      </div>
      <button class="btn">Войти</button>
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
  background-image: url("../../src/assets/img/background.png");
  background-size: 100% auto;
  padding: 0;
  margin: 0;
}
h1 {
  position: absolute;
  width: 144px;
  height: 28px;
  left: 50%;
  top: calc(50% - 28px / 2 - 202.5px);
  font-family: "Arial";
  font-style: normal;
  font-weight: 400;
  font-size: 24px;
  line-height: 28px;
  display: flex;
  align-items: center;

  color: #272727;
}
.main {
  width: 300px;
  height: 250px;
  padding: 35px;
  position: fixed;
  top: 50%;
  left: 48%;
  -webkit-transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
}
img {
  position: relative;
  top: 50%;
  width: 100%;
}
.form-control {
  left: 504px;
  top: 403px;
  font-family: Arial;
  background: rgb(251, 251, 251);
  width: 432px;
  height: 48px;

  margin: 20px 0;
  padding: 14px 12px;
  gap: 10px;
  box-sizing: border-box;
  font-size: 14px;
  border: 1px solid #d5d5d5;
  border-radius: 1px;
}

.checkbox {
  color: #002c5f;
}
.btn {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  padding: 7px 40px;
  gap: 6px;
  margin: 20px 0;
  width: 432px;
  height: 48px;

  color: #ffffff;

  font-family: "Arial";
  font-style: normal;
  font-weight: 700;
  font-size: 16px;
  line-height: 18px;
  background: #002c5f;
  border-radius: 1px;
}
.header {
  height: 90px;
  background: #ffffff;
  padding: 0;
  margin: 0;
}
.logo {
  width: 315px;
  height: 53.11px;
  left: 35px;
  top: 18px;
}
label {
  font-family: "Arial";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 140%;
  letter-spacing: -0.01em;
  color: #707070;
  margin-bottom: 13px;
  padding-bottom: 15px;
  text-align: left;
}
</style>
