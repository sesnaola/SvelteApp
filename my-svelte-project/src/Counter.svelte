<script>
    export let initialCounter = 0;
    let count = initialCounter;

    function handleCount() {
        count++;
    }
</script>

<main>
    <p>Counter: {count}</p>
</main>

<button on:click={handleCount}>Add count</button>
