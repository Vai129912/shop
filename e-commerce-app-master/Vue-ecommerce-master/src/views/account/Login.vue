
<template>
<div>
  <div class="container" style="padding-top: 10%">
    <div class="row d-flex justify-content-center">
      <div class="col-5 text-left login-form-container">
        <div class="d-flex justify-content-center">
          <img src="https://cdn0.iconfinder.com/data/icons/set-ui-app-android/32/8-512.png" width="100" height="100" alt="">
        </div>
        <div>
          <div class="form-group">
            <label for="exampleInputEmail1">Enter Email address</label>
            <input
              type="email"
              class="form-control"
              id="exampleInputEmail1"
              aria-describedby="emailHelp"
            />
            
          </div>
          <div class="form-group">
            <label for="exampleInputPassword1">Password</label>
            <input type="password" class="form-control" id="exampleInputPassword1" />
            <small
              id="emailHelp"
              class="form-text text-muted head-3 "
            >By continuing, you agree to Shopping-Cart's Terms of Use and Privacy Policy.</small>
          </div>
          <div class="form-group form-check">
            <input type="checkbox" class="form-check-input" id="exampleCheck1" />
            <label class="form-check-label" for="exampleCheck1">Remember</label>
          </div>
          <button @click="login()" type="submit" class="btn btn-primary btn-block">Login</button>
        </div>
      </div>
    </div>
  </div>
</div>
</template>

<script>
import { mapActions } from "vuex";
export default {
name: "Login",
methods: {
  ...mapActions("account", ["login"]),
},
};
</script>

<style>
.form-control {
border-radius: 0%;
height: 50px;
}
.login-form-container {
padding: 20px;
box-shadow: 0px 2px 5px 2px #888888;
background-color: #d9fd94 ;
}
.btn {
border-radius: 20px;
font-weight: bold;
background: rgb(8, 8, 8);
border: teal;
width: fit-content;
margin: auto;
}
.btn:hover {
background: #00b4b4;
}
.btn:focus {
background: teal;
}

</style>