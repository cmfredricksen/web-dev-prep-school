<script context="module">
    export const load = async({fetch}) => {
        const res = await fetch("https://jsonplaceholder.typicode.com/posts/1");
        const post = await res.json();

        return {
            props: {
                post
            }
        }
    }
</script>
<script>
    export let post;
    export let {title, body} = {...post};
    // export let title = singlePost.title;
    // export let body = singlePost.body;
</script>

<h1>{title}</h1>
<p>{body}</p>