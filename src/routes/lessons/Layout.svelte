<script>
    export let title;
    export let date;
</script>

 <h1>{title}</h1>
 <div class="date-box">
     Last Updated: {new Date(date).toDateString()}
</div>

<div class="content-wrapper">
    <slot />
</div>

<style>
    h1 {
        text-align: center;
    }
    .date-box {
        text-align: center;
        margin: .5rem 0;
        color: var(--clr-lt);
        
    }

    .content-wrapper {
        max-width: 80%;
        margin: 2rem auto;
    }


</style>