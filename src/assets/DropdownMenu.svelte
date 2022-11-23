<script>
	import { slide, fly } from 'svelte/transition';
	import data from '../data.json'
	
	import MenuItem from './MenuItem.svelte';
	import { mdiArrowLeft, mdiChevronRight, mdiCog, mdiAccount, mdiAccountBox, mdiSecurity } from '@mdi/js';
	
	let activeMenu = 'main';
	let menuHeight = 0;
	let menuEl = null;
	
	$: menuHeight = menuEl?.offsetHeight ?? 0;
</script>

<div class="dropdown stack" style="height: {menuHeight}px">
	{#if activeMenu === 'main'}
		<div class="menu" in:fly={{ x: -300 }} out:fly={{ x: -300 }} bind:this={menuEl}>
			<MenuItem on:click={() => activeMenu = "farmacia"} leftIcon={mdiCog} rightIcon={mdiChevronRight}>Farmacia 1</MenuItem>
			<MenuItem on:click={() => activeMenu = "farmacia"} leftIcon={mdiCog} rightIcon={mdiChevronRight}>Farmacia 2</MenuItem>
			<MenuItem on:click={() => activeMenu = "farmacia"} leftIcon={mdiCog} rightIcon={mdiChevronRight}>Farmacia 3</MenuItem>
			<MenuItem on:click={() => activeMenu = "farmacia"} leftIcon={mdiCog} rightIcon={mdiChevronRight}>Farmacia 4</MenuItem>
		</div>
	{/if}
	
	<!-- {#if activeMenu === 'profile'}
		<div class="menu" in:fly={{ x: 300 }} out:fly={{ x: 300 }} bind:this={menuEl}>
			 <MenuItem on:click={() => activeMenu = "main"} leftIcon={mdiArrowLeft}>
				 Regresar
			</MenuItem>
			
			<MenuItem leftIcon={mdiAccountBox}>Change Picture</MenuItem>
			<MenuItem leftIcon={mdiSecurity}>Permissions</MenuItem>
		</div>
	{/if} -->
	
	{#if activeMenu === 'farmacia'}
		<div class="menu" in:fly={{ x: 300 }} out:fly={{ x: 300 }} bind:this={menuEl}>
			 <MenuItem on:click={() => activeMenu = "main"} leftIcon={mdiArrowLeft}>
				 Back
			</MenuItem>
			
			{#each data[0].categorias as d,index}
				<MenuItem leftIcon={mdiCog}>{d.name}</MenuItem>
			{/each}
		</div>
	{/if}
	
</div>

<style>
	.dropdown {
		position: absolute;
		top: 58px;
		left: 7.4rem;
		width: 300px;
		transform: translateX(-45%);
		background-color: var(--bg);
		border: var(--border);
		border-radius: var(--border-radius);
		padding: 1rem;
		overflow: hidden;
		transition: height var(--speed) ease;
	}
	
	.stack {
		display: grid;
		align-items: start; /* allow to shrink */
	}
	
	.stack > :global(*) {
		grid-area: 1 / 1;
  }
	
	.menu {
		width: 100%;
	}
</style>