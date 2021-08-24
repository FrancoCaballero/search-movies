<script>
	import Counter from './Counter.svelte'
	import Input from './Input.svelte'

	const commonProps = { maxCounter: 15 }
</script>

<section>
	<h1>Buscar Peliculas 🍿</h1>
	<Input />
</section>

<style>
	h1 {
		font-size: 32px;
	}

	section {
		display: flex;
		align-items: center;
		flex-direction: column;
	}
</style>