<template>
  <div>
    <div class="category-tabs">
      <div class="d-flex flex-wrap justify-content-center">
        <form class="form-inline my-2 my-lg-0">
          <input
            v-model="search"
            type="text"
            class="form-control"
            placeholder="Search for products"
            aria-label="Search"
          />
        </form>
      </div>

      <div class="d-flex flex-wrap justify-content-center">
        <button class="btn btn-secondary" @click="toggle($event)">
          All products
        </button>
        <button class="btn btn-secondary" @click="toggle($event)">
          Men's clothing
        </button>
        <button class="btn btn-secondary" @click="toggle($event)">
          Women's clothing
        </button>
        <button class="btn btn-secondary" @click="toggle($event)">
          Electronics
        </button>
        <button class="btn btn-secondary" @click="toggle($event)">
          Jewelry
        </button>
      </div>
    </div>
    <div class="container">
      <ProductCard
        v-for="product in filteredProducts"
        :key="product.id"
        :product="product"
      />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      products: [],
      search: '',
      selected: [
        'All products',
        "Men's clothing",
        "Women's clothing",
        'Electronics',
        'Jewelry',
      ],
      compKey: 0,
    }
  },
  async fetch() {
    this.products = await fetch('https://fakestoreapi.com/products').then(
      (res) => res.json()
    )
  },
  computed: {
    filteredProducts: function () {
      return this.products.filter((product) => {
        return product.title.toLowerCase().includes(this.search.toLowerCase())
      })
    },

    filtered() {
      if (this.selected.lenght === 0) {
        return <div></div>
      } else {
        return this.products.filtered((product) =>
          this.selected.includes(product.category)
        )
      }
    },
  },
  methods: {
    toggle(event) {
      this.compKey++
      const element = event.target
      const tab = element.textContent.trim()

      if (this.selected.includes(tab)) {
        element.classList.remove('btn-secondary')
        this.selected.splice(this.selected.indexOf(tab), 1)
      } else {
        element.classList.add('btn-secondary')
        this.selected.push(tab)
      }
    },
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
