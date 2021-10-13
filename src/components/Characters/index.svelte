<script>
	// @ts-nocheck
	import { query } from 'svelte-apollo';
	import { gql } from '@apollo/client/core';
	import SectionWrapper from '../SectionWrapper/index.svelte';
	import SingleCharacter from '../Characters/SingleCharacter.svelte';

	const GET_CHARACTERS = gql`
		query {
			characters(page: 1) {
				info {
					count
				}
				results {
					id
					name
					image
					status
					species
					gender
				}
			}
		}
	`;
	const characters = query(GET_CHARACTERS);
</script>

<SectionWrapper variant="secondary">
	<p class="info">click on the character to check more detailed data</p>

	{#if $characters.loading}
		<p class="loading">Loading...</p>
	{:else if $characters.error}
		<p class="error">Error:</p>
	{:else}
		<ul>
			{#each $characters.data.characters.results as char (char.id)}
				<SingleCharacter
					name={char.name}
					image={char.image}
					status={char.status}
					species={char.species}
					gender={char.gender}
				/>
			{/each}
		</ul>
	{/if}
</SectionWrapper>

<style>
	ul {
		list-style: none;
		padding: 0;
		margin: 0;
		padding-bottom: 80px;
	}

	.info {
		margin: 0;
		font-size: 36px;
		padding: 10px 0 60px 0;
	}

	.loading {
		margin: 0;
		font-size: 36px;
		padding: 40px 0;
	}

	.error {
		margin: 0;
		font-size: 36px;
		color: red;
		padding: 40px 0;
	}
</style>
