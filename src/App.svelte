<script>
	import Screen_device from './Components/add.svelte';
	export let name;
	let fill = 'red';
</script>


<main>
	<h1>Hello {name}! sbs   asdasd</h1>
	<Screen_device fill={fill} />
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