<script>
    const links = [
        {
            title: "Home",
            path: "/"
        },
        {
            title: "Lessons",
            path: "/lessons"
        },
        {
            title: "Api Samples",
            path: "/api-samples"
        },
        {
            title: "About",
            path: "/about"
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