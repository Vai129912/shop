<template>
  <div class="container" style="padding: 30px">
    <div class="row d-flex justify-content-center">
      <div class="list-group col-8">
        <a
          v-for="item in cart"
          :key="item.id"
          href="#"
          class="list-group-item list-group-item-action d-flex justify-content-between align-items-center"
        >
          <img :src="item.image" alt height="60" width="60" />
          <p class="head-1">{{ item.title }}</p>

          <div class="row">
            <div class="mr-2">
              <p class="head-1">Price(Quantity)</p>
              <p> Rs. {{ item.price }} ({{ item.quantity }}) </p>
            </div>
            
          </div>
         
          <div class="ml-auto">
            <p class="head-1">Total Price</p>
            <p>Rs. {{ item.price * item.quantity }}</p>
          </div>
         
        </a>
      
        <div
          class="list-group-item list-group-item-action d-flex justify-content-between align-items-center"
        >
          <p class="head-2">Final Price</p>
          <div>
            <p class="head-2">Rs. {{ totalPrice }}</p>
          </div>
        </div>
        <button
          @click="checkout()"
          type="button"
          class="btn btn-primary btn-lg btn-block mt-4"
        >Checkout</button>
      </div>
    </div>
  </div>
</template>

<script>
import { mapGetters, mapActions } from "vuex";
export default {
  name: "Cart",
  data() {
    return {
      totalPrice: 0,
    };
  },
  computed: {
    ...mapGetters("product", ["cart"]),
    ...mapGetters("account", ["user"]),
  },
  methods: {
    ...mapActions("product", ["removeCart"]),
    calcPrice() {
      this.cart.forEach((element) => {
        this.totalPrice += element.price * element.quantity;
      });
    },
    checkout() {
      const vm = this;
      setTimeout(() => {
        vm.removeCart();
        alert("Purchase successful!");
        vm.$router.push("/");
      }, 2000);
    },
  },
  mounted() {
    this.calcPrice();
  },
};
</script>

<style>
  .container{
    max-width: 100%;
    max-height: 100%;
  }

.head-1{
font-size: 15px;
font-weight: bold;
margin:auto;

}
.head-2{
  text-align: center;
  margin: auto;
  font-weight: bolder;
  font-size: 18px;
  
}
</style>