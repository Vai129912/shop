<template>
  <div class="card card-1 mb-4 shadow-sm">
    <img :src="product.image" class="card-img-top product-image" />
    <div class="card-body">
      <h5 class="card-title text-left">{{ product.title }}</h5><br>
      <br><br><div class="row">
        <router-link
          type="button"
          class="btn-1 btn btn-primary btn-lg"
          :to="'/details/' + product.id"
        >Details</router-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    name: "ProductCard",
    props: ["product"]
};
</script>

<style>
.card .product-image {
  height: 300px;
  padding: 50px;
}
.card-title{
 margin: auto;
  text-align:start;
  font-size:20px;

}  
.btn-1{
  
 
}

.card-1{
  width:100%;
  height: 100%;
}
</style>