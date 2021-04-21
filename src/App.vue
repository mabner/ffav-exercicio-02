<template>
  <div>
    <ProductForm :onAddProduct="handleOnAddProduct"/>

    <div>
      <ul>
        <li v-for="product in products" :key="product.name">
          {{ product.name }} | {{ product.price }} | {{ product.category }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import ProductForm from './components/ProductForm';

export default {
  components: { ProductForm },
  data() {
    return {
      products: [
        {
          name: "Base Triskle 3x110",
          price: "299.00",
          category: "Bases",
        },
      ],
    };
  },
  methods: {
    handleOnAddProduct(product) {
      console.log(product);
      this.products = this.products.concat(product);
    },
  },
};
</script>
