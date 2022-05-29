<script>
    export let index, movieTitle, poster, year;
</script>

<article class="cards">
    <small>
        #{index + 1}
        {#if new Date().getFullYear() - year < 5}
            <i>🆕</i>
        {/if}
    </small>
    <h3>{movieTitle}</h3>
    <img onerror="this.remove()" alt={movieTitle} src={poster} />
    <p>{year}</p>
</article>

<style>
    .cards {
        max-width: 300px;
        border-radius: 10px;
        overflow: hidden;
        box-shadow: 0 0 10px #222;
        transition: 0.3s;
        margin-top: 15px;
        margin: 10px;
    }
    h3 {
        font-size: 24px;
        margin-bottom: 4px;
    }
</style>
