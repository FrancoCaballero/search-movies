<script>
	export let initialCounter = 0
    export let maxCounter = 9
	
    let contador = initialCounter
    

	const handleClick = () => {
		contador++
	}

    $: isEvenOrOdd = contador % 2 === 0 ? 'Is Even' : 'Is Odd'
    $: if (contador > maxCounter) {
        console.log('limit contador')
        contador = maxCounter
    }
</script>

<main>
	<button on:click={handleClick}>Incrementar</button>
	<span>{contador}</span>
    <span>{isEvenOrOdd}</span>
</main>

<style>
	span {
		color: red;
	}
</style>