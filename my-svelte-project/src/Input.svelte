<script>
    import App from "./App.svelte";
    import Movie from "./Movie.svelte";

    let value = "";
    const handleInput = (event) => (value = event.target.value);
    let response = [];
    let loading;
    $: {
        if (value.length > 2) {
            loading = true;
            fetch(`https://www.omdbapi.com/?s=${value.trim()}&apikey=422350ff`)
                .then((res) => res.json())
                .then((apiResponse) => {
                    response = apiResponse.Search || [];
                    console.log(apiResponse);
                    loading = false;
                });
        }
    }
</script>

<input placeholder="Search movies..." {value} on:input={handleInput} /><br />

{#if loading}
    <strong> Loading...</strong>
{:else}
    <!-- <strong> {response.length} movies found </strong> -->
    <div class="cardsGrid">
        {#each response as { Title: movieTitle, Poster, Year }, index}
            <Movie {index} {movieTitle} poster={Poster} year={Year} />
        {:else}
            <strong> No results </strong>
        {/each}
    </div>
{/if}

<style>
    .cardsGrid {
        display: flex;
        align-content: stretch;
        justify-content: center;
        flex-grow: 4;
        flex-wrap: wrap;
        align-self: auto;
    }
</style>
