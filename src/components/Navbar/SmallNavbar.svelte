<script>
    // cart button
    import CartButton from '../Cart/CartButton.svelte';
    // global store
    import globalStores from '../../stores/globalStores';
    import { link } from 'svelte-routing'
    let openSidebar = globalStores.toggleItem
</script>

<nav class="navbar">
    <div class="nav-center">
        <!-- sidebar toggle -->
        <button class="btn-sidebar-toggle" on:click={()=> {
            openSidebar('sidebar',true);
        }}>
            <i class="fas fa-bars" />
        </button>
        <!-- logo -->
        <a href="/" use:link class="nav-logo" >
            <img src="/assets/images/logo.svg" class="logo" alt="razers logo" />
        </a>
        <!-- cart button -->
        <CartButton />
    </div>
</nav>