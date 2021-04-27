<template>
	<form v-on:submit.prevent="handleSearch">
		<input type="text" v-on:keyup="handleSearch" v-model="search" />
		<button type="submit">Search</button>
	</form>
</template>

<script>
	export default {
		name: 'SearchBar',
		props: {
            onSearch: Function,
        },
		data() {
            return {
                search: "",
            };
        },
		methods: {
            handleSearch() {
                this.onSearch(this.search);
            }
        },
	};
</script>
