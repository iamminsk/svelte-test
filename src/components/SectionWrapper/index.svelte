<script>
    export let variant = "primary"
</script>

<section class={variant}>
	<div>
		<slot />
	</div>
</section>

<style>
	section {
        padding: 0 20px;
        max-width: 100vw;
    }

    section.primary {
        background-color: transparent;
    }

    section.secondary {
        background-color: #a2dd5d;
    }

    div {
        max-width: 750px;
        margin: 0 auto;
    }
</style>
