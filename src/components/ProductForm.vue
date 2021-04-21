<template>
  <div>
    <form @submit.prevent="onFormSubmit">
      <p>
        <label>Nome: </label>
        <input type="text" v-model="productName" />
      </p>
      <p>
        <label>Preço: </label>
        <input type="text" v-model="productPrice" />
      </p>
      <p>
        <label>Categoria: </label>
        <input type="text" v-model="productCategory" />
      </p>
      <button type="submit">Enviar</button>
    </form>
    <p>{{ productName }} {{ productPrice }} | {{ productCategory }}</p>
  </div>
</template>

<script>
export default {
  name: "ProductForm",
  data() {
    return {
      productName: "",
      productPrice: "",
      productCategory: "",
    };
  },
  props: {
    onAddProduct: Function,
  },
  methods: {
    onFormSubmit() {
      const product = {
        name: `${this.productName}`,
        price: `${this.productPrice}`,
        category: this.productCategory,
      };

      this.onAddProduct(product);
    },
  },
};
</script>
