<!--  Svelte port of React example: https://github.com/fireship-io/229-multi-level-dropdown -->
<script>
	import NavBar from "./lib/NavBar.svelte";
	import NavItem from "./lib/NavItem.svelte";
	import DropdownMenu from "./lib/DropdownMenu.svelte";

	import Contacto from "./lib/Contacto.svelte";
    import Nosotros from "./lib/Nosotros.svelte";
    import ModalInfo from "./lib/ModalInfo.svelte";

</script>

<NavBar>
	<NavItem>
		<span class="myicon-drop" slot="trigger">
			<!-- <IconButton path={mdiMenuDown} /> -->
			<img
				src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/8d/VisualEditor_-_Icon_-_Menu.svg/1200px-VisualEditor_-_Icon_-_Menu.svg.png"
				alt=""
			/>
		</span>
		<DropdownMenu />
	</NavItem>
	<NavItem>
		<span class="myicon-drop2" slot="trigger">
			<!-- <img src="https://cdn-icons-png.flaticon.com/512/4320/4320337.png" alt=""> -->
			<img src="/light2.png " alt="" />
		</span>
	</NavItem>
</NavBar>

<div class="myaction">
	<a href="#nosotros">Nosotros</a>
	<a href="#contacto">Contacto</a>
</div>

<main>
	<p>FarmaClic</p>
</main>
<ModalInfo />
<Nosotros />
<Contacto />

<style>
	.myaction {
		position: absolute;
		color: white;

		right: 20px;
		top: 20px;
	}
	.myaction a {
		font-size: 1.2rem;
		color: white;
		margin-right: 30px;
		text-decoration: none;
		padding: 5px;
		transition: all 2s ease;
	}
	.myaction a:hover {
		border-bottom: 1px solid white;
	}
	@font-face {
		font-family: "Nunito Sans";
		src: url("../fonts/NunitoSans-SemiBold.ttf");
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
		height: calc(100vh - 4rem);
		margin: 0;
		padding: 0;
		box-sizing: border-box;

		font-family: Helvetica;
	}
	.myicon-drop img,
	.myicon-drop2 img {
		width: 50px;
	}
	.myicon-drop2 {
		margin-left: 2rem;
	}
	main {
		display: grid;
		justify-content: center;
		align-items: center;
		height: calc(100vh - 4rem);
		font-family: "Nunito Sans";
		font-size: 6rem;
		color: black;

		background-image: url("/BG.jpg");
		background-repeat: no-repeat;
		background-size: cover;
		background-position: center;
	}
	main p {
		-webkit-text-stroke: 2px white;
		text-transform: uppercase;
	}
	@media (max-width: 520px) {
		main {
			font-size: 3rem;
		}
		.myaction {
			right: 10px;
		}
		.myaction a {
			font-size: 1rem;
			margin-right: 10px;
			padding: 3px;
		}
	}
</style>
