<script>
    export let location;
    import Hero from  "../components/Hero.svelte";
    import { link } from "svelte-routing";
    import Faetured from "../components/Products/Featured.svelte"
    // featured products
</script>

<Hero> 
    <a href="/products" class="btn btn-primary btn-hero" use:link>shop now</a>
</Hero>
<Faetured title="featured products" />
