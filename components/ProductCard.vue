<template>
  <div class="card shadow">
    <img :src="product.image" class="card-img-top" :alt="product.imagetext" />
    <div class="card-body">
      <small class="text-muted">{{ product.category }}</small>
      <h5 class="card-title">{{ product.title }}</h5>
      <h6 class="card-subtitle mb-2 text-primary">$ {{ product.price }}</h6>
    </div>
    <div class="card-footer">
      <a href="#" class="btn btn-dark">Add to cart</a>
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

.text-muted {
  text-transform: capitalize;
}

img {
  padding: 20px;
  object-fit: contain;
  height: 250px;
}

.card-footer {
  display: grid;
}

.card-footer a {
  width: 40%;
  justify-self: end;
}
</style>
