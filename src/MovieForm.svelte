<script>
    import { movies } from './store';
    import { createEventDispatcher } from 'svelte';
    let movieName = '';
    let rating = 1;
    $: counter = 0;
    export let placeholder;

    const dispatch = createEventDispatcher();

    const addMovie = () => {
        $movies = [...$movies, {movieName, rating}];
        movieName = '';
        rating = 1;
        counter++;
        dispatch('formSubmit', {
            count: counter
        });
    };
</script>
<form on:submit|preventDefault={addMovie}>
    {counter}
    <input type="text" bind:value={movieName} {placeholder}/>
    <select bind:value={rating}>
        <option value={1}>1</option>
        <option value={2}>2</option>
        <option value={3}>3</option>
        <option value={4}>4</option>
        <option value={5}>5</option>
    </select>
    <button type="submit">Submit</button>
</form>
