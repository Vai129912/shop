<template>
  <div>
    <div>
      <nav class="navbar navbar-expand-lg navbar-dark fixed-top">
        <router-link class="navbar-brand" to="/">Shopping-Cart</router-link>
        <div class="ml-auto">
          <div v-if="user.photoURL">
            <img :src="user.photoURL" class="img-thumbnail profile-image" alt />
            <router-link class=" btn-2 " to="/cart">
              <img src="https://pngimg.com/uploads/shopping_cart/shopping_cart_PNG38.png" width="50" alt />
              <span class="badge badge-danger badge-pill">{{ cart.length }}</span>
            </router-link>
          </div>
          <router-link v-else class="btn btn-primary my-2 my-sm-0" to="/login">Login</router-link>
        </div>
      </nav>
    </div>
    <div class="page-container">
      <router-view />
    </div>
  </div>
</template>

<script>
  import { mapGetters } from "vuex";
  export default {
    name: "Base",
    computed: {
      ...mapGetters("account", ["user"]),
      ...mapGetters("product", ["cart"])
    }
  };
</script>

<style>
  nav {
    background-color: #f0fa9a;
  }

  .navbar-brand {
    font-weight: bold;
    font-weight:700;
    font-size: 30px;
    /* font-family: Comic; */
    color: #080808 !important;
    margin: auto;
    width: 70%;
  }

  .profile-image {
    width: 40px;
    border-radius: 100% !important;
    border: solid black 1px;
    margin: auto;
  }

  .page-container {
    padding-top: 100px;
    
  }

  .btn {
    border-radius: 20px;
    font-weight: bold;
    background-color: black;
    border: rgb(10, 10, 10);
    margin: auto;
  }

  .btn:hover {
    background: #00b4b4;
  }

  input {
    border-radius: 0%;
  }

  .btn:focus {
    background: teal;
  }
  .btn-2
  {
    background-color: none;
  }
</style>