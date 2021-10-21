<template>
  <div class="container-fluid">
    <div class="row d-flex justify-content-center">
      <div class="col-6">
        <div class="card text-left shadow-md">
          <img class="card-img-top" :src="product.image" alt />
        </div>
      </div>
      <div class="col-6 text-left text-justify">
        <div class=" head-name lead text-justify">{{ product.title }}</div>
        <br>
        <div class="heading">Description</div>
        <p class="display-6">{{ product.description }}</p>
        <div>
          <p class="rupee"> Rs. {{ product.price }}</p>
        </div>
        <AddToCart :product="product" v-if="user.uid" />
      </div>
    </div>
  </div>
</template>

<script>
  import { mapGetters, mapActions } from "vuex";
  import AddToCart from "../../components/details/AddToCart"
  export default {
    data() {
      return {
        isInCardProp: false,
      }
    },
    computed: {
      ...mapGetters("account", ["user"]),
      ...mapGetters("product", ["product"])
    },
    components: { AddToCart },
    methods: {
      ...mapActions("product", ["productDetails"]),
    },
    mounted() {
      this.productDetails(this.$route.params.idProduct);
    }
  };
</script>

<style>
  .container-fluid {
    padding: 0px;
  }

  .image-product {
    width: 50%;
    height: 100%;

  }

  .card * {
    max-height: 60vh;
    max-width: 50vh;
    margin: auto;
  }

  .head-name {
    font-weight: bolder;
  }

  .heading {
    font-weight: bold;
    font-size: 15px;
    font-family: monospace;
  }

  .rupee {
    font-weight: 900;
    font-family: monospace;
    font-size: 25px;
  }
</style>