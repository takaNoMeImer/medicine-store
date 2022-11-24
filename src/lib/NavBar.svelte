<nav class="mynavbar" style={$$props.style}>
	<ul class="mynavbar-nav">
		<slot />
	</ul>
</nav>

<style>
	.mynavbar {
		height: var(--nav-size);
		background-color: var(--bg);
		padding: 0 1rem;
		border-bottom: var(--border);
	}
	
	ul {
		list-style: none;
		margin: 0;
		padding: 0;
	}

	.mynavbar-nav {
		max-width: 100%;
		height: 100%;

		display: flex;
		justify-content: flex-start;
	}
</style>