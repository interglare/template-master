<script>
	import Nested from './Nested.svelte';
	let name=0;

	$: y = name *2; 
	$: console.log("LL", name);
	const add = () => {
		name++;
	}
</script>

<main>
	<h1>Hello {name}!</h1>
	<h2>{y}</h2>
	<button on:click="{add}">PLUS ONE</button>
	<Nested answer={name}/>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
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