<script>
    export let initialCounter = 0;
    export let maxCounter = 9;
    let count = initialCounter;
    // On count change, isEvenOrOdd is updated
    $: isEvenOrOdd = count % 2 == 0 ? "Is Even" : "Is Odd";
    $: {
        if (count > maxCounter) {
            count = maxCounter;
            console.log("inside");
        }
    }

    function handleCount() {
        count++;
    }
</script>

<div class="centerAndSeparateContents">
    <button on:click={handleCount}>Add count</button>
    <main>
        <p>Counter: {count}</p>
        <p>State: {isEvenOrOdd}</p>
    </main>
</div>

<style>
    .centerAndSeparateContents {
        display: block;
        padding: 20px;
    }
</style>
