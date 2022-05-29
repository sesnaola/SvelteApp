<script>
	import Counter from "./Counter.svelte";
	import Input from "./Input.svelte";
	export let name;

	function handleName() {
		name == "Planet" ? (name = "world") : (name = "Planet");
	}

	const commonProps = { initialCounter: 2, maxCounter: 5 };
</script>

<main>
	<h1>Hello {name}!</h1>
	<button on:click={handleName}>Change name</button>
	<div class="horizontalButtonsLayout">
		<Counter initialCounter="1" maxCounter="12" />
		<Counter {...commonProps} />
		<Counter initialCounter="4" maxCounter="5" /><br /><br />
	</div>
	<Input />
	<!-- <p>
		Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn
		how to build Svelte apps.
	</p> -->
</main>

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

	.horizontalButtonsLayout {
		display: flex;
		justify-content: center;
		align-items: center;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>
