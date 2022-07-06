<script>
    import { page } from "$app/stores"

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
        <a class:active={$page.url.pathname === path} href={path}>{title}</a>
    {/each}
</nav>

<style>
    nav {
        display: flex;
    }
    a {
        margin: 0 1rem;
        color: var(--clr-white);
        text-decoration: none;
    }
    
    a:hover {
        color: var(--clr-lt);
    }

    .active {
        color: var(--clr-lt);
        text-decoration: var(--clr-lt) wavy underline;
    }
</style>