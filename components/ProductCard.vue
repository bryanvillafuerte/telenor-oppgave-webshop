<template>
  <div class="card shadow">
    <img :src="product.image" class="card-img-top" :alt="product.imagetext" />
    <div class="card-body">
      <h5 class="card-title">{{ product.title }}</h5>
      <h6 class="card-subtitle mb-2 text-primary">$ {{ product.price }}</h6>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    product: {
      type: Object,
      default: () => {},
    },
  },
}
</script>

<style scoped>
.card {
  border: none;
}

img {
  padding: 20px;
  object-fit: contain;
  height: 250px;
}
</style>
