<script>
	import data from '../data.json'
    import Navbar from './Navbar.svelte';
	export let status;
</script>

<div>
	{#if status}
		<input type="checkbox" id="btn-menu" />
		<div class="container-menu">
			<div class="cont-menu">
				<nav>
					{#each data as item}
						<a class="item-farm" href="test">
							<span>{item.name}</span>
							<span class="siguiente"> <img src="https://cdn-icons-png.flaticon.com/512/2883/2883482.png" alt=""> </span>
						</a>
					{/each}
				</nav>
				<label for="btn-menu">✖️</label>
			</div>
		</div>
	{/if}
	
</div>

<style>
	.item-farm {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}
	.item-farm img {
		height: 25px;
	}
</style>
