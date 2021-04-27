<template>
	<div>
		<form v-on:submit.prevent="onFormSubmit">
			<div>
				<p>
					<label for="productName">Nome: </label>
					<input type="text" v-model="productName" />
				</p>
			</div>
			<p>
				<label for="productPrice">Preço: </label>
				<input type="text" v-model="productPrice" />
			</p>
			<p>
				<label for="productCategory">Categoria: </label>
				<input type="text" v-model="productCategory" />
			</p>
			<button type="submit">Enviar</button>
		</form>
		<p>{{ productName }} {{ productPrice }} {{ productCategory }}</p>
	</div>
</template>

<script>
	export default {
		name: 'ProductForm',
		data() {
			return {
				productName: '',
				productPrice: '',
				productCategory: '',
			};
		},
		props: {
			onAddProduct: Function,
		},
		methods: {
			onFormSubmit() {
				const product = {
					productName: this.productName,
					productPrice: this.productPrice,
					productCategory: this.productCategory,
				};

				this.onAddProduct(product);
			},
		},
	};
</script>
