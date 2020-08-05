<script>
    import user from '../stores/user'
    import {link} from "svelte-routing";
    // logout func
    import {logoutUser} from '../stores/user';
    import globalStores from '../stores/globalStores'
</script>

{#if $user.jwt}
    <a href="/" use:link class="logout-btn" on:click="{() => { logoutUser();  globalStores.toggleItem('sidebar',false) }}">logout</a>
{:else}
    <a href="/login" use:link on:click="{() => { globalStores.toggleItem('sidebar',false) }}">login</a>
{/if}