<template>
	<div id="app">
		<div>
			<ProductForm :onAddProduct="handleOnAddProduct" />
		</div>
		<div>
			<ProductsList :products="products" />
		</div>
	</div>
</template>

<script>
	import ProductForm from './components/ProductForm';
	import ProductsList from './components/ProductsList';

	export default {
		name: 'App',
		components: { ProductForm, ProductsList },
		data() {
			return {
				products: [
					{
						productName: 'Base Triskle 3x110 completa',
						productPrice: '499,00',
						productCategory: 'Bases',
					},
					{
						productName: 'Mochila Traxart Wild',
						productPrice: '250,00',
						productCategory: 'Mochilas',
					},
					{
						productName: 'Kit de Proteção Traxart DG 300',
						productPrice: '279,00',
						productCategory: 'Proteções',
					},
				],
			};
		},
		methods: {
			handleOnAddProduct(product) {
				// console.log(product);
				this.products = this.products.concat(product);
			},
		},
	};
</script>
