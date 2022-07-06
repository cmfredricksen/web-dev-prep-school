<script>
     let post = {};
    const getPost = async() => 
    {
        const res = await fetch("https:jsonplaceholder.typicode.com/posts/1")
        const singlePost = await res.json()
        
        return singlePost;
        
    }

    $: getPost().then((val) => (post = val));

    $: console.log(post);
</script>


<h2>{post.title}</h2>
<p>{post.body}</p>
<a href="http://localhost:3000/api-samples">Back to List</a>

