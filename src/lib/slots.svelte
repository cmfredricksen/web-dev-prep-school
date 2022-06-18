<article>
    <header>
        <slot name="header" />
    </header>

    <section>
        <slot name="content" />
    </section>
</article>

<style>
    header {
        font-size: 5rem;
    }

    section {
        color: var(--clr-lt);
    }
</style>