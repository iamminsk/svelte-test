<script>
	import { ApolloClient, InMemoryCache } from '@apollo/client/core';
	import { setClient } from 'svelte-apollo';

	const cache = new InMemoryCache();
	const client = new ApolloClient({
		uri: 'https://rickandmortyapi.com/graphql',
		cache
	});
	setClient(client);
</script>

<slot />
