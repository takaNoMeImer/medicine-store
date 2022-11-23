<script>
    import Icon from "./Icon.svelte";
    import IconButton from "./IconButton.svelte";

    export let leftIcon = null;
    export let rightIcon = null;
</script>

<!-- svelte-ignore a11y-click-events-have-key-events -->
<div class="menu-item" on:click|preventDefault>
    <IconButton path={leftIcon ?? ""} />

    <slot />

    {#if rightIcon}
        <span class="icon-right">
            <Icon path={rightIcon ?? ""} />
        </span>
    {/if}
</div>

<style>
    .menu-item {
        margin-left: 1rem;
        height: 40px;
        display: grid;
        grid-template-columns: auto 1fr auto;
        gap: 8px;
        align-items: center;
        border-radius: var(--border-radius);
        transition: background var(--speed);
        padding: 0.5rem;
        color: var(--text-color);
    }

    .menu-item:hover {
        background-color: #525357;
    }
</style>
