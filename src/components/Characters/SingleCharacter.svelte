<script>
	export let name;
	export let image;
	export let status;
	export let species;
	export let gender;

	let isActive = false;
</script>

<li on:click={() => (isActive = !isActive)}>
	<div class="front" class:isActive>
		<img src={image} alt={name} />
		<p>{name}</p>
	</div>
	<div class="back" class:isActive>
		<p class="paragraph">{status}<span>is my status</span></p>
		<p class="paragraph">{species}<span>is my species</span></p>
		<p class="paragraph">{gender}<span>is my gender</span></p>
	</div>
</li>

<style>
	li {
		background-color: rgba(255, 255, 255, 0.6);
		border-radius: 10px;
		padding: 20px;
		box-shadow: 0px 40px 20px 0px rgba(0, 0, 0, 0.2);
		cursor: pointer;
	}

	li:not(:last-child) {
		margin-bottom: 25px;
	}

	img {
		max-width: 200px;
		border-radius: 10px;
		margin-right: 15px;
	}

	p {
		margin: 0;
		font-size: 50px;
	}

	div {
		display: flex;
	}

	.front {
		height: auto;
		visibility: visible;
	}

	.front.isActive {
		height: 0;
		visibility: hidden;
	}

	.back {
		height: 0;
		visibility: hidden;
		flex-direction: column;
	}

	.back.isActive {
		height: auto;
		visibility: visible;
	}

	.paragraph {
		font-size: 40px;
	}

	.paragraph span {
		font-size: 20px;
	}

	.paragraph:not(:last-child) {
		margin-bottom: 5px;
	}
</style>
