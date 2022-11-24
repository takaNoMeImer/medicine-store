<!-- This is a IconButton component -->
<script>
    import Icon from "./Icon.svelte";
    export let path = "";
</script>

<!-- svelte-ignore a11y-click-events-have-key-events -->
<div class="myiconbutton" on:click|preventDefault>
    <Icon {path} />
</div>

<style>
    .myiconbutton {
        --button-size: calc(var(--nav-size) * 0.5);
        width: var(--button-size);
        height: var(--button-size);
        background-color: #484a4d;
        border-radius: 50%;
        padding: 5px;
        margin: 2px;
        display: flex;
        align-items: center;
        justify-content: center;
        transition: filter 300ms;
        color: var(--text-color);
    }

    .myiconbutton:hover {
        filter: brightness(1.2);
    }
</style>
