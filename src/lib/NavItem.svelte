<script>
    let open = false;
</script>

<li class="mynav-item">
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <div on:click|preventDefault={() => (open = !open)}>
        <slot name="trigger" />
    </div>

    {#if open}
        <slot />
    {/if}
</li>

<style>
    .mynav-item {
        width: calc(var(--nav-size) * 0.8);
        display: flex;
        align-items: center;
        justify-content: center;
    }
</style>
