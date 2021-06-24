<template>
  <div class="container">
    <ProductCard
      v-for="product in products"
      :key="product.id"
      :product="product"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      products: [],
    }
  },
  async fetch() {
    this.products = await fetch('https://fakestoreapi.com/products').then(
      (res) => res.json()
    )
  },
}
</script>

<style scoped>
.container {
  display: grid;
  grid-template-columns: 1fr;
  gap: 30px;
}

@media only screen and (min-width: 576px) {
  .container {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media only screen and (min-width: 992px) {
  .container {
    grid-template-columns: repeat(3, 1fr);
  }
}
</style>
