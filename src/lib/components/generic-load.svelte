<script context="module">
    export const load =async ({fetch}) => {
        const res = await fetch("api-url");
        const data = await res.json();

        return {
            props: {
                data
            }
        }

    }
</script>
<script>
    export let data = "Hope";
</script>

<h1>{data}</h1>

<p>Below is a copy of the code I used to make hope above! Actually it is just a generic load function that doesn't do anything because it is not fetching an api. It is a component that I am importing into my pages. This is just to see an example of how the function works.</p>

<p>For more see my <a href="/api-samples/weather">weather API</a>, where I go into more detail as I call an actual API.</p>

<img src="../../../static/images/generic-load.png" alt="code-snapshots">

<style>
    h1 {
        text-align: center;
        font-size: 3rem;
    }

    img {
        width: 50%;
    }
</style>