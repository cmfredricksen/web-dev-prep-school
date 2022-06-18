<script>
    import Props from "$lib/props.svelte";
    import Slots from "$lib/slots.svelte"
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