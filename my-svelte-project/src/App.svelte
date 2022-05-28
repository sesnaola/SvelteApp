<script>
	import Counter from "./Counter.svelte";

	export let name;

	function handleName() {
		name == "Planet" ? (name = "world") : (name = "Planet");
	}
</script>

<main>
	<h1>Hello {name}!</h1>
	<Counter initialCounter="1" />
	<Counter />
	<Counter initialCounter="4" />
	<p>
		Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn
		how to build Svelte apps.
	</p>
</main>

<button on:click={handleName}>Change name</button>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: rgb(0, 255, 191);
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>
