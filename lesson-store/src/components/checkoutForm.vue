<template>
<main>

<h2>Checkout</h2>
    <h3> Cart</h3>
  <div style="display: flex; flex-wrap: wrap;" >
    
    <div v-for='product in cart' :key="product.id">
        <div class="img-box">
      <figure>
        <img style="height: 100px;" v-bind:src="product.image" />
      </figure>
      </div>
      <p v-html="product.title"></p>
      <p>Price: ${{ product.price }}</p>
        <button @click='remove(product)'>remove</button>    </div>
 </div>

     <p>
      <strong> Name </strong> 
      <input v-model="name" />
      <strong> phone </strong>
       <input v-model="phone" />
      <button @click='submit()' > Submit </button>
</p>
 </main>
 
</template>

<script>
export default {
  name: "checkout",
  props: ['cart'],
  data() {
    return {
      name: "",
      phone: "",
}; },
methods: {
     remove(product) {
        this.$emit('removeProduct', product)
     }},

}
</script>