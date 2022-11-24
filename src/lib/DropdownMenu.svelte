<script>
	import { slide, fly } from 'svelte/transition';
	import data from '../data.json'
	
	import MenuItem from './MenuItem.svelte';
	import { mdiArrowLeft, mdiChevronRight, mdiCog, mdiAccount, mdiAccountBox, mdiSecurity } from '@mdi/js';
	import { writeKeyComponent, writeDataComponent, numero,nombre } from './store.js'
    import MyItem from './MyItem.svelte';
	
	let activeMenu = 'main';
	let menuHeight = 0;
	let menuEl = null;
	let keyComponent;
	let dataComponent;
	
	$: menuHeight = menuEl?.offsetHeight ?? 0;

	function saveData(dataComponent, keyComponent) {
		numero.set(20)
		nombre.set(keyComponent)
	}
</script>

<div class="mydropdown mystack" style="height: {menuHeight}px">
	{#if activeMenu === 'main'}
		<div class="mymenu" in:fly={{ x: -300 }} out:fly={{ x: -300 }} bind:this={menuEl}>
			<MenuItem on:click={() => activeMenu = "farmacia"} leftIcon={mdiCog} rightIcon={mdiChevronRight}>Farmacia 1</MenuItem>
			<MenuItem on:click={() => activeMenu = "farmacia"} leftIcon={mdiCog} rightIcon={mdiChevronRight}>Farmacia 2</MenuItem>
			<MenuItem on:click={() => activeMenu = "farmacia"} leftIcon={mdiCog} rightIcon={mdiChevronRight}>Farmacia 3</MenuItem>
			<MenuItem on:click={() => activeMenu = "farmacia"} leftIcon={mdiCog} rightIcon={mdiChevronRight}>Farmacia 4</MenuItem>
		</div>
	{/if}
	
	{#if activeMenu === 'farmacia'}
		<div class="mymenu" in:fly={{ x: 300 }} out:fly={{ x: 300 }} bind:this={menuEl}>
			 <MenuItem on:click={() => activeMenu = "main"} leftIcon={mdiArrowLeft}>
				 Back
			</MenuItem>
			
			{#each data[0].categorias as d,index}
				<MenuItem on:click={ () => {
					activeMenu = d.name
				} } leftIcon={mdiCog}>{d.name}</MenuItem>
			{/each}
		</div>
	{/if}

	{#if activeMenu === 'ANALGÉSICOS OPIODES'}
		<div class="mymenu" in:fly={{ x: 300 }} out:fly={{ x: 300 }} bind:this={menuEl}>
			 <MenuItem on:click={() => activeMenu = "farmacia"
			 } leftIcon={mdiArrowLeft}>
				 Back
			</MenuItem>
			
			{#each data[0].categorias[0].value as d,index}
				<!-- <MenuItem leftIcon={mdiCog} on:click={() => saveData(data[0].categorias[0],d)}>{d}</MenuItem> -->
				<MyItem leftIcon={mdiCog} on:click={() => saveData(data[0].categorias[0],d)}>{d}</MyItem>
			{/each}
		</div>
	{/if}

	<!-- saveData
					dataComponent = data[0].categorias[0]
					keyComponent = d
					saveData -->

	{#if activeMenu === 'ANALGÉSICOS'}
		<div class="mymenu" in:fly={{ x: 300 }} out:fly={{ x: 300 }} bind:this={menuEl}>
			 <MenuItem on:click={() => activeMenu = "farmacia"} leftIcon={mdiArrowLeft}>
				 Back
			</MenuItem>
			
			{#each data[0].categorias[1].value as d,index}
				<MenuItem leftIcon={mdiCog}>{d}</MenuItem>
			{/each}
		</div>
	{/if}

	<!--  -->
	{#if activeMenu === 'ANTIÁCIDOS'}
		<div class="mymenu" in:fly={{ x: 300 }} out:fly={{ x: 300 }} bind:this={menuEl}>
			 <MenuItem on:click={() => activeMenu = "farmacia"} leftIcon={mdiArrowLeft}>
				 Back
			</MenuItem>
			
			{#each data[0].categorias[2].value as d,index}
				<MenuItem leftIcon={mdiCog}>{d}</MenuItem>
			{/each}
		</div>
	{/if}

	{#if activeMenu === 'ANTIULCEROS / PROTECTOR GASTRICO'}
		<div class="mymenu" in:fly={{ x: 300 }} out:fly={{ x: 300 }} bind:this={menuEl}>
			 <MenuItem on:click={() => activeMenu = "farmacia"} leftIcon={mdiArrowLeft}>
				 Back
			</MenuItem>
			
			{#each data[0].categorias[3].value as d,index}
				<MenuItem leftIcon={mdiCog}>{d}</MenuItem>
			{/each}
		</div>
	{/if}

	{#if activeMenu === 'ANTIBIÓTICOS'}
		<div class="mymenu" in:fly={{ x: 300 }} out:fly={{ x: 300 }} bind:this={menuEl}>
			 <MenuItem on:click={() => activeMenu = "farmacia"} leftIcon={mdiArrowLeft}>
				 Back
			</MenuItem>
			
			{#each data[0].categorias[4].value as d,index}
				<MenuItem leftIcon={mdiCog}>{d}</MenuItem>
			{/each}
		</div>
	{/if}

	{#if activeMenu === 'ANTIDIARRÉICOS'}
		<div class="mymenu" in:fly={{ x: 300 }} out:fly={{ x: 300 }} bind:this={menuEl}>
			 <MenuItem on:click={() => activeMenu = "farmacia"} leftIcon={mdiArrowLeft}>
				 Back
			</MenuItem>
			
			{#each data[0].categorias[5].value as d,index}
				<MenuItem leftIcon={mdiCog}>{d}</MenuItem>
			{/each}
		</div>
	{/if}

	{#if activeMenu === 'LAXANTES'}
		<div class="mymenu" in:fly={{ x: 300 }} out:fly={{ x: 300 }} bind:this={menuEl}>
			 <MenuItem on:click={() => activeMenu = "farmacia"} leftIcon={mdiArrowLeft}>
				 Back
			</MenuItem>
			
			{#each data[0].categorias[5].value as d,index}
				<MenuItem leftIcon={mdiCog}>{d}</MenuItem>
			{/each}
		</div>
	{/if}

	{#if activeMenu === 'ANTIFÚNGICOS'}
		<div class="mymenu" in:fly={{ x: 300 }} out:fly={{ x: 300 }} bind:this={menuEl}>
			 <MenuItem on:click={() => activeMenu = "farmacia"} leftIcon={mdiArrowLeft}>
				 Back
			</MenuItem>
			
			{#each data[0].categorias[5].value as d,index}
				<MenuItem leftIcon={mdiCog}>{d}</MenuItem>
			{/each}
		</div>
	{/if}

	{#if activeMenu === 'ANTIHISTAMÍNICOS'}
		<div class="mymenu" in:fly={{ x: 300 }} out:fly={{ x: 300 }} bind:this={menuEl}>
			 <MenuItem on:click={() => activeMenu = "farmacia"} leftIcon={mdiArrowLeft}>
				 Back
			</MenuItem>
			
			{#each data[0].categorias[5].value as d,index}
				<MenuItem leftIcon={mdiCog}>{d}</MenuItem>
			{/each}
		</div>
	{/if}
	
</div>

<style>
	.mydropdown {
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
	
	.mystack {
		display: grid;
		align-items: start; /* allow to shrink */
	}
	
	.mystack > :global(*) {
		grid-area: 1 / 1;
  }
	
	.mymenu {
		width: 100%;
	}
</style>