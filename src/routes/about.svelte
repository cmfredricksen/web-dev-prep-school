<script>
    import Props from "$lib/props.svelte";
    import Slots from "$lib/slots.svelte";
    import Generic from "$lib/components/generic-load.svelte"
    let count = 1;

    const doubleCount = () => count += 2;
    const resetCount = () => count = 1;

    $: doubled = count * 2;
    $: quadrupled = doubled * 2;

    $: if (count >= 10) {
        alert("Count is dangerously high!")
        count = 2;
    }

    // Updates the console every time you use the reactive variable
    $: {
        console.log(doubled)
        console.log(quadrupled)
    }

    
</script>

<a href="https://github.com/cmfredricksen/web-dev-prep-school">GitHub repository for this project</a>

<h2>About Dev Prep School</h2>

<p>This website is a place for me to learn, experiment and practice several skills. It is here where I will learn how to make a blog or a school website using MarkDown and SvelteKit. I will also review using the terminal and VSCode. I am currently practising fetching data with APIs, using asynchronous JavaScript. I have just started learning how to use a writable in SvelteKit to show state across components.</p>

<p>There is so much more I want to learn and try, and here is where I will do it. You will find pages that make little sense, those are experiments in action. As I begin to understand how things work I will add instructions and explanations.</p>

<h4>The CSS is an ongoing art project.</h4>

<h3>Enjoy!</h3>

<h1>Click the button to Double the Count</h1>

<h2>{count}</h2>

<h3>{count} * 2 = {doubled}</h3>
<h3>{count} * 4 = {quadrupled}</h3>

<button on:click={doubleCount}>Count +</button>
<button on:click={resetCount}>Reset</button>

<h3>Props in Action</h3>
<h4>First with default values:</h4>

<Props /> 

<h4>Now with added values:</h4>
<Props props=13 greeting="Hello!" />

<h3>Slots</h3>
<p>The use I have found for custom slots is customizing CSS</p>

<Slots>
    <h1 slot="header">Title</h1>
    <p slot="content">This is the section</p>
</Slots>

<Slots>
    <p slot="header">Another Slot</p>
</Slots>

<h3>Generic API</h3>
<p>for more api information and some examples see: <a href="/api-samples">API Samples</a></p>

<Generic />


<style>
    h2, h3, h4 {
        color: white;
        font-family: "Inconsolata";
    }
    h4 {
        text-align: center;
    }
    button {
        background-color: var(--clr-lt);
        color: white;
        padding: 1rem;
    }
    p {
        text-align: center;
    }
</style>