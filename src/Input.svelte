<script>
import Movie from "./Movie.svelte"

    let value = ''
    let response = []

    const handleInput = (event) => value = event.target.value

    $: if (value.length > 2) {
        response = fetch(` https://www.omdbapi.com/?s=${value}&apikey=127f9fb`)
                    .then(res => !res.ok ? new Error('Algo salió mal con el api de películas') : res)
                    .then(res => res.json())
                    .then(apiResponse => apiResponse.Search || [])
    }
</script>

<input 
    placeholder="Buscar películas..." 
    value={value} 
    on:input={handleInput} 
/>

{#await response}
    <strong>Loading ...</strong>
{:then movies}
    {#each movies as {Title, Poster, Year}}
        <Movie
            title={Title}
            poster={Poster}
            year={Year}
        />
    {:else}
    <strong>No tenemos películas</strong>
    {/each}
{:catch error}
    <p>❌ Ha ocurrido un error</p>
{/await}