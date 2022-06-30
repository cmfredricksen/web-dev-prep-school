<script context="module">
    export const load = async({fetch}) => {
        const res = await fetch("https://jsonplaceholder.typicode.com/photos");
        const photos = await res.json();

        return {
            props: {
                photos
            }
        }
    }
</script>

<script>
    export let photos;
    export let {id, title, thumbnailUrl} = {...photos}
</script>

<div class="album">

    {#each photos as {id, title, thumbnailUrl}}
    {#if id <=6}
    <img src={thumbnailUrl} alt={title}>
    {/if}
    {/each}
</div>

<style>
    .album {
        display: flex;
        flex-wrap: wrap;
    }
    img {
        margin: 1rem;
    }
</style>