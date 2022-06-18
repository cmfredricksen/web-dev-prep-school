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
        padding: 0 3rem;
    }
</style>