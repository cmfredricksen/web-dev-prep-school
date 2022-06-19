<script context="module">
    export const load = async({fetch}) => {
        const res = await fetch('https://jsonplaceholder.typicode.com/todos');
        const todos = await res.json();


        return {
            props: {
                todos
            }
        }
    }

</script>

<script>
    export let todos;
    export let {id, title, completed} = {...todos}
</script>


{#each todos as {id, title, completed}}
{#if completed}
    <h3>{id}: {title} &checkmark;</h3>
{:else}
    <p>{id}: {title}</p>
{/if}
{/each}



