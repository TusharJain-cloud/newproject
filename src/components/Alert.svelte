<script>
    import {fly, fade} from 'svelte/transition'
    import globalStores from '../stores/globalStores'
    import {onMount, onDestroy} from 'svelte'

    const handleClose = () => {
        globalStores.toggleItem('alert', false);
    };
    let timeout;
    onMount(() => {
        timeout = setTimeout(() => {
            globalStores.toggleItem('alert', false);
        }, 3000);
    });
    onDestroy(() => {
        clearTimeout(timeout);
    })
</script>

<div class="alert-container" in:fly={{y: -200, duration: 1000}} out:fade={{duration: 0}} class:alert-danger={$globalStores.alertDanger}>
    <div class="alert">
        <p>{$globalStores.alertText}</p>
        <button on:click={handleClose} class="alert-close">
            <i class="fas fa-window-close" />
        </button>
    </div>
</div>