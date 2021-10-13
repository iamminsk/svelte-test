<script>
	import ApolloClient from '../components/ApolloClient/index.svelte';
	import Characters from '../components/Characters/index.svelte';
	import Billboard from '../components/Billboard/index.svelte';
	import Footer from '../components/Footer/index.svelte';
	import Head from '../components/Head/index.svelte';
</script>

<ApolloClient>
	<Head />
	<Billboard />
	<Characters />
	<Footer />
</ApolloClient>

<style>
	:global(body) {
		margin: 0;
		font-family: 'Raleway', sans-serif;
	}
</style>
