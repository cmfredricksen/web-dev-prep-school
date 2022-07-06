<script>
    
    import Generic from "$lib/components/generic-load.svelte";
    const links = [
        {
            title: "API try",
            path: "/api-samples/api-try",
            description: "Fetching from external API"
        },
        {
            title: "API try using SSR",
            path: "/api-samples/api-try-ssr",
            description: "Fetching from API using SSR"
        },
        {
            title: "Photos API",
            path: "/api-samples/photos",
            description: "Fetching Images using an API"
        },
        {
            title: "Posts API",
            path: "/api-samples/posts",
            description: "Fetching blog posts from an external server using API"
        },
        {
            title: "Using Typicode",
            path: "/api-samples/typicode",
            description: "Learning how to use APIs with Typicode"
        },
        {
            title: "Local Weather",
            path: "/api-samples/weather",
            description: "Fetching the local weather using the National Weather Service's API"
        }
    ]
</script>

<section class="intro">
    <h2>API Samples</h2>
    <p>
        On this page are links to pages I made using data I retrieved from the web. In SvelteKit it is pretty straightforward to grab information and then iterate through it and finally display it on the page. At this time the <a href="/api-samples/weather">weather API</a> has an example of how I used the load function to get the weather forecast for where I live. More to come!
    </p>
</section>

<nav>
    {#each links as {title, path, description} }
        <li>
            <a href={path}>{title}</a>
            <p>{description}</p>
        </li>
    {/each}
</nav>

<div class="code-block">
    <h2>Generic Load Function as used in SvelteKit:</h2>

    <Generic />
</div>
<a href="http://localhost:3000/api-samples">Back to List</a>

<style>
    nav {
        display: flex;
        /* flex-direction: column; */
        margin: 1rem 0 4rem;
    }
    li {
        padding: .5rem 0;
        box-shadow: -2px 2px 3px 0px var(--clr-white-fade);
        list-style: none;
        padding: 7px;
        border: 1px solid var(--clr-lt);

    }
</style>