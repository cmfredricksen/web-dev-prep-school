<script context="module">
    const allLessons = import.meta.glob("./*.md")

    let body = [];
    for (let path in allLessons) {
        body.push(allLessons[path]().then(({metadata}) => {
            return {path, metadata}
        })
    )}

    export const load = async () => {
        const lessons = await Promise.all(body)

        return {
            props: {
                lessons
            }
        }
    }
</script>

<script>
    export let lessons;
</script>



<div class="list-box">
    {#each lessons as {path, metadata: {title, date}}} 
        <a href={`lessons/${path.replace(".md", "")}`}>{title}</a>
    {/each}
</div>

<style>
    .list-box {
        display: flex;
        flex-direction: column;
    }

    a {
        padding: 1rem;
    }
</style>