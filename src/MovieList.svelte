<script>
    import { movies } from './store';
</script>
<div>
    <ul>
        {#each $movies as m}
            <li>
                <h3>{m.movieName}</h3>
                <span>Rating - {m.rating}</span>
            </li>
        {/each}
    </ul>
</div>

<style>
    li {
        list-style: none;
    }
</style>