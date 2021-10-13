<script>
	import { ApolloClient, InMemoryCache } from '@apollo/client';
	import { setClient } from 'svelte-apollo';

	const cache = new InMemoryCache();
	const client = new ApolloClient({
		uri: 'https://rickandmortyapi.com/graphql',
		cache
	});
	setClient(client);
</script>

<slot />
