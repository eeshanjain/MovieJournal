<script>
	import MovieForm from './MovieForm.svelte';
	import MovieList from './MovieList.svelte';
	export let name;

	const onMovieAdd = (event) => console.log('Movie was added. Count: ', event.detail.count);
</script>

<main>
	<h1>Movie Journal</h1>
	<MovieForm placeholder={"Movie Name"} on:formSubmit={onMovieAdd}/>
	<MovieList />
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