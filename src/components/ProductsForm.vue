<template>
	<div>
		<form @submit.prevent="onFormSubmit">
			<p>
				<label>Nome:</label>
				<input type="text" v-model="productName" />
			</p>
			<p>
				<label>Preço:</label>
				<input type="text" v-model="productPrice" />
			</p>
			<p>
				<label>Categoria:</label>
				<input type="text" v-model="productCategory" />
			</p>
			<button type="submit">Enviar</button>
		</form>
		<div>
			<p>{{ productName }}</p>
			<p>{{ productPrice }}</p>
			<p>{{ productCategory }}</p>
		</div>
	</div>
</template>

<script>
	export default {
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
					name: this.productName,
					price: this.productPrice,
					category: this.productCategory,
				};
				this.onAddProduct(product);
			},
		},
	};
</script>
