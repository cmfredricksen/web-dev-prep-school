<script context="module">
    export const load = async({fetch}) => {
        const res = await fetch("https://jsonplaceholder.typicode.com/posts")
        const posts = await res.json();

        return {
            props: {
                posts
            }
        }
    }
</script>
<script>
    export let posts;
    export let {id, title, body} = {...posts}
    
</script>

{#each posts as { id, title, body} }
    {#if id <= 6}
        <h2>{title}</h2>
        <p>{body}</p>
    {/if}
{/each}