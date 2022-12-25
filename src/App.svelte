<script>
    import Loader1 from "./lib/Loader1.svelte";
    import Loader2 from "./lib/Loader2.svelte";
</script>

<main>
    <h1>CSS Loaders</h1>
    <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Ipsa impedit
        debitis hic magnam totam nobis placeat quod ex illo assumenda.
    </p>
    <div class="loader-container">
        <Loader1 />
        <Loader2 />
    </div>
</main>

<style>
    .loader-container {
        display: flex;
        flex-wrap: wrap;
        gap: 5rem;
    }
</style>
