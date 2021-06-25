<template>
  <div>
    <Navbar />
    <div class="container">
      <div class="row">
        <div class="col-md-6">
          <h1 class="heading">Welcome to the WebShop</h1>
          <p class="lead">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Etiam
            ornare turpis sed mi iaculis congue. Sed vel vestibulum metus. Sed
            auctor non odio id ultricies. Pellentesque lobortis consequat eros
            vitae finibus.
          </p>
        </div>
        <div class="col-md-6"></div>
      </div>
      <div class="row product-grid">
        <ProductGrid />
      </div>
    </div>
  </div>
</template>

<style>
.container {
  margin: 0 auto;
}

.heading {
  padding-top: 50px;
}

.product-grid {
  padding-bottom: 50px;
  display: grid;
}
</style>
