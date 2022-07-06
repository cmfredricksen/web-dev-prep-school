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

<h2>{title}</h2>
<p>{body}</p>

<a href="http://localhost:3000/api-samples">Back to List</a>