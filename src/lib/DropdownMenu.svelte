<script>
	import { slide, fly } from 'svelte/transition';
	import data from '../data.json'
	
	import MenuItem from './MenuItem.svelte';
	import { mdiArrowLeft, mdiChevronRight, mdiCog, mdiAccount, mdiAccountBox, mdiSecurity, mdiMortarPestlePlus, mdiPill, mdiPillMultiple, mdiShape } from '@mdi/js';
    import MyItem from './MyItem.svelte';
	import { categoria, descripcion, medicamento, imagen } from './store'
	
	let activeMenu = 'main';
	let menuHeight = 0;
	let menuEl = null;
	let keyComponent;
	let dataComponent;
	
	$: menuHeight = menuEl?.offsetHeight ?? 0;

	function saveData(cat, med, desc, img) {
		medicamento.set(med)
		categoria.set(cat)
		descripcion.set(desc)
		imagen.set(img)
	}
</script>

<div class="mydropdown mystack" style="/*height: {menuHeight}px*/">
	{#if activeMenu === 'main'}
		<div class="mymenu" in:fly={{ x: -300 }} out:fly={{ x: -300 }} bind:this={menuEl}>
			<MenuItem on:click={() => activeMenu = "farmacia"} leftIcon={mdiMortarPestlePlus} rightIcon={mdiChevronRight}>Farmacia 1</MenuItem>
			<MenuItem on:click={() => activeMenu = "farmacia"} leftIcon={mdiMortarPestlePlus} rightIcon={mdiChevronRight}>Farmacia 2</MenuItem>
			<MenuItem on:click={() => activeMenu = "farmacia"} leftIcon={mdiMortarPestlePlus} rightIcon={mdiChevronRight}>Farmacia 3</MenuItem>
			<MenuItem on:click={() => activeMenu = "farmacia"} leftIcon={mdiMortarPestlePlus} rightIcon={mdiChevronRight}>Farmacia 4</MenuItem>
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
				} } leftIcon={mdiShape}>{d.name}</MenuItem>
			{/each}
		</div>
	{/if}

	{#if activeMenu === 'ANALGÉSICOS OPIODES'}
		<div class="mymenu" in:fly={{ x: 300 }} out:fly={{ x: 300 }} bind:this={menuEl}>
			 <MenuItem on:click={() => activeMenu = "farmacia"
			 } leftIcon={mdiArrowLeft}>
				 Back
			</MenuItem>
			<!-- on:click={() => saveData(data[0].categorias[0],d)} -->
			{#each data[0].categorias[0].value as d,index}
				<!-- <MenuItem leftIcon={mdiCog} on:click={() => saveData(data[0].categorias[0],d)}>{d}</MenuItem> -->
				<MyItem leftIcon={mdiPillMultiple} on:click={ () => saveData(
					data[0].categorias[0].name,
					d,
					data[0].categorias[0].description,
					data[0].categorias[0].imagenes[index]
				) }>{d}</MyItem>
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
				<MyItem leftIcon={mdiPillMultiple} on:click={ () => saveData(data[0].categorias[1].name, d,
					data[0].categorias[1].description,
					data[0].categorias[1].imagenes[index]) }>{d}</MyItem>
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
				<MyItem leftIcon={mdiPillMultiple} on:click={ () => saveData(data[0].categorias[2].name, d,
					data[0].categorias[2].description,
					data[0].categorias[2].imagenes[index]) }>{d}</MyItem>
			{/each}
		</div>
	{/if}

	{#if activeMenu === 'ANTIULCEROS / PROTECTOR GASTRICO'}
		<div class="mymenu" in:fly={{ x: 300 }} out:fly={{ x: 300 }} bind:this={menuEl}>
			 <MenuItem on:click={() => activeMenu = "farmacia"} leftIcon={mdiArrowLeft}>
				 Back
			</MenuItem>
			
			{#each data[0].categorias[3].value as d,index}
				<MyItem leftIcon={mdiPillMultiple} on:click={ () => saveData(data[0].categorias[3].name, d,
					data[0].categorias[3].description,
					data[0].categorias[3].imagenes[index]) }>{d}</MyItem>
			{/each}
		</div>
	{/if}

	{#if activeMenu === 'ANTIBIÓTICOS'}
		<div class="mymenu" in:fly={{ x: 300 }} out:fly={{ x: 300 }} bind:this={menuEl}>
			 <MenuItem on:click={() => activeMenu = "farmacia"} leftIcon={mdiArrowLeft}>
				 Back
			</MenuItem>
			
			{#each data[0].categorias[4].value as d,index}
				<MyItem leftIcon={mdiPillMultiple} on:click={ () => saveData(data[0].categorias[4].name, d,
					data[0].categorias[4].description,
					data[0].categorias[4].imagenes[index]) }>{d}</MyItem>
			{/each}
		</div>
	{/if}

	{#if activeMenu === 'ANTIDIARRÉICOS'}
		<div class="mymenu" in:fly={{ x: 300 }} out:fly={{ x: 300 }} bind:this={menuEl}>
			 <MenuItem on:click={() => activeMenu = "farmacia"} leftIcon={mdiArrowLeft}>
				 Back
			</MenuItem>
			
			{#each data[0].categorias[5].value as d,index}
				<MyItem leftIcon={mdiPillMultiple} on:click={ () => saveData(data[0].categorias[5].name, d,
					data[0].categorias[5].description,
					data[0].categorias[5].imagenes[index]) }>{d}</MyItem>
			{/each}
		</div>
	{/if}

	{#if activeMenu === 'LAXANTES'}
		<div class="mymenu" in:fly={{ x: 300 }} out:fly={{ x: 300 }} bind:this={menuEl}>
			 <MenuItem on:click={() => activeMenu = "farmacia"} leftIcon={mdiArrowLeft}>
				 Back
			</MenuItem>
			
			{#each data[0].categorias[6].value as d,index}
				<MyItem leftIcon={mdiPillMultiple} on:click={ () => saveData(data[0].categorias[6].name, d,
					data[0].categorias[6].description,
					data[0].categorias[6].imagenes[index]) }>{d}</MyItem>
			{/each}
		</div>
	{/if}

	{#if activeMenu === 'ANTIFÚNGICOS'}
		<div class="mymenu" in:fly={{ x: 300 }} out:fly={{ x: 300 }} bind:this={menuEl}>
			 <MenuItem on:click={() => activeMenu = "farmacia"} leftIcon={mdiArrowLeft}>
				 Back
			</MenuItem>
			
			{#each data[0].categorias[7].value as d,index}
				<MyItem leftIcon={mdiPillMultiple} on:click={ () => saveData(data[0].categorias[7].name, d,
					data[0].categorias[7].description,
					data[0].categorias[7].imagenes[index]) }>{d}</MyItem>
			{/each}
		</div>
	{/if}

	{#if activeMenu === 'ANTIHISTAMÍNICOS'}
		<div class="mymenu" in:fly={{ x: 300 }} out:fly={{ x: 300 }} bind:this={menuEl}>
			 <MenuItem on:click={() => activeMenu = "farmacia"} leftIcon={mdiArrowLeft}>
				 Back
			</MenuItem>
			
			{#each data[0].categorias[8].value as d,index}
				<MyItem leftIcon={mdiPillMultiple} on:click={ () => saveData(data[0].categorias[8].name, d,
					data[0].categorias[8].description,
					data[0].categorias[8].imagenes[index]) }>{d}</MyItem>
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
		/* transition: height 1s ease; */
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