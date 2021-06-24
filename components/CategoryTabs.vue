<template>
  <div class="container category-tabs">
    <div class="d-flex flex-wrap justify-content-center">
      <form class="form-inline my-2 my-lg-0">
        <input
          class="form-control"
          type="search"
          placeholder="Search"
          aria-label="Search"
        />
        <button class="btn btn-outline-dark my-2 my-sm-0" type="submit">
          Search
        </button>
      </form>
    </div>

    <div class="d-flex flex-wrap justify-content-center">
      <button class="btn btn-primary" @click="toggle($event)">
        All Products
      </button>
      <button class="btn btn-dark" @click="toggle($event)">
        Men's clothing
      </button>
      <button class="btn btn-info" @click="toggle($event)">
        Women's clothing
      </button>
      <button class="btn btn-warning" @click="toggle($event)">
        Electronics
      </button>
      <button class="btn btn-secondary" @click="toggle($event)">Jewelry</button>
    </div>
  </div>
</template>

<style scoped>
.category-tabs {
  padding: 50px 0;
}

.btn {
  margin: 10px 10px;
}

form {
  padding-bottom: 10px;
}

.form-control {
  width: 200px;
}

@media only screen and (min-width: 576px) {
  .form-control {
    width: 400px;
  }
}

@media only screen and (min-width: 992px) {
  .form-control {
    width: 600px;
  }
}
</style>
