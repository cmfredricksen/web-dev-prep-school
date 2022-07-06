<script>
    import Nav from "./nav.svelte"
</script>

<header>
    <a href="/">
        <h1>
            Web Dev Prep School
        </h1>
        </a>
    <Nav />
</header>

<style>
    header {
        display: flex;
        justify-content: space-between;
        padding: 2rem 1rem;
        align-items: baseline;
        border-bottom: 1px solid var(--clr-white-fade);
    }

    h1:hover {
        color: var(--clr-white-fade);
    }
</style>