<script>
    export let title, poster, year
    if (poster === 'N/A') {
        poster = 'img/Imagen_no_disponible.png'
    }
    console.log(poster)
</script>

<article>
    <img src={poster} alt={title}>
    <h3>{title}</h3>
    <span>{year}</span>
    {#if 2020 - year < 5}
        <i>🆕</i>
    {/if}
</article>

<style>
    article {
        border: 1px solid #eee;
        border-radius: 4px;
        padding: 16px;
        max-width: 300px;
    }

    h3 {
        font-size: 24px;
        margin-bottom: 4px;
    }

    img {
        max-width: 300px;
    }
</style>