<script>
    import SmallNavbar from "./SmallNavbar.svelte";
    import BigNavbar from "./BigNavbar.svelte";
    import globalStores from '../../stores/globalStores';
    let screenWidth;
    $: if (screenWidth > 992){
        globalStores.toggleItem('sidebar',false);
    }
</script>

<svelte:window bind:innerWidth={screenWidth} />

{#if screenWidth > 992}
    <BigNavbar />
{:else}
    <SmallNavbar />
{/if}
