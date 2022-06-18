<script>
    const links = [
        {
            title: "Home",
            path: "/"
        },
        {
            title: "Lessons",
            path: "/lessons"
        }
    ]
</script>

<nav>
    {#each links as {path, title}} 
        <a href={path}>{title}</a>
    {/each}
</nav>

<style>
    nav {
        display: flex;
    }
    a {
        margin: 0 1rem;
    }
</style>