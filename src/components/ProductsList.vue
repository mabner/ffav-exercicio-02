<template>
	<div>
		<div>
			<ul>
				<li v-for="product in products" :key="product.productName">
					<!-- {{ product.name }} | {{ product.price }} | {{ product.category }} -->
					<ProductItem :product="product" />
				</li>
			</ul>
		</div>
	</div>
</template>

<script>
	import ProductItem from './ProductItem';

	export default {
		name: 'ProductsList',
		props: {
			products: Array,
		},
		components: {
			ProductItem,
		},
	};
</script>
