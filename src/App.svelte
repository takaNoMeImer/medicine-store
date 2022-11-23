<!--  Svelte port of React example: https://github.com/fireship-io/229-multi-level-dropdown -->
<script>
	import NavBar from './lib/NavBar.svelte';
    import NavItem from './lib/NavItem.svelte';
    import DropdownMenu from './lib/DropdownMenu.svelte';
    import IconButton from './lib/IconButton.svelte';
	
	/* import {mdiPlus, mdiMenuDown, mdiBell} from  */
    /* import {} from '@' */
</script>

<NavBar>
	<NavItem>
		<span class="icon-drop" slot="trigger">
			<!-- <IconButton path={mdiMenuDown} /> -->
            <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/8d/VisualEditor_-_Icon_-_Menu.svg/1200px-VisualEditor_-_Icon_-_Menu.svg.png" alt="">
		</span>
		<DropdownMenu></DropdownMenu>
	</NavItem>
	<NavItem>
		<span class="icon-drop2" slot="trigger">
			<!-- <img src="https://cdn-icons-png.flaticon.com/512/4320/4320337.png" alt=""> -->
			<img src="/light2.png " alt="">
		</span>
	</NavItem>
	
	<NavItem>
		<span class="icon-drop3" slot="trigger">
			<!-- <IconButton path={mdiBell} /> -->
            <p style="margin-left: 5rem;">FarmaClic</p>
		</span>
	</NavItem>
</NavBar>

<main>
	FarmaClic
</main>

<style>
	@font-face{
		font-family: 'Nunito Sans';
		src: url('../fonts/NunitoSans-SemiBold.ttf');
	}
	:root {
		--bg: #242526;
		--bg-accent: #484a4d;
		--text-color: #dadce1;
		--nav-size: 60px;
		--border: 1px solid #474a4d;
		--border-radius: 8px;
		--speed: 200ms; 
	}

	:global(body) {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
		background-image: url('https://www.cien.adexperu.org.pe/wp-content/uploads/2021/07/medicina-humana-800x445.jpg');
		background-repeat: no-repeat;
		background-size: cover;
		font-family: Helvetica;
	}
	.icon-drop img, .icon-drop2 img {
		width: 50px;
	}
	.icon-drop2 {
		margin-left: 2rem;
	}
	main {
		display: grid;
		justify-content: center;
		align-items: center;
		height: calc(100vh - 4rem);
		font-family: 'Nunito Sans';
		font-size: 6rem;
		color: black;
	}
	@media (max-width: 520px) {
		main {
			font-size: 4rem;
		}
	}
</style>