<script>
    import "../global.css"
    import Footer from "$lib/footer.svelte"
    import Header from "$lib/header.svelte";
    
</script>

<Header />

<div class="wrapper">
    <slot></slot>
</div>

<Footer />

<style>
    .wrapper {
        padding: 3rem;
        width: 70vw;
        margin: 0 auto;
        border-left: 2px solid var(--clr-white-fade);
        border-right: 2px solid var(--clr-white-fade);
    }
</style>