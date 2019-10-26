<script>
	import { Router, Route } from 'svelte-routing';
	import NavBar from './components/NavBar.svelte';
	import Politicians from './pages/Politicians.svelte';
	import Sidebar from "./components/Sidebar.svelte";

	export let url = 'politicians';
</script>

<style>
	:global(html, body) {
		height: 100%;
		width: 100%;
	}

	:global(body) {
		padding: 0;
		margin: 0;

		--text-black: #313131;
		--text-grey: #A9A9A9;
		--text-header-size: 16px;
	}

	:global(body *) {
		box-sizing: border-box;
	}
	.app {
		width: 100%;
		height: 100%;
		display: grid;
		grid-template-columns: 200px 1fr;
		grid-template-rows: 64px 1fr;
		grid-template-areas:
			"sidebar header"
			"sidebar content"
			"sidebar content";
	}
	.header {
		grid-area: header;
		border-bottom: 1px solid var(--text-grey);
	}
	.sidebar {
		grid-area: sidebar;
		box-shadow: 0 0 17px rgba(100, 100, 100, 0.12)
	}
	.content {
		grid-area: content;
	}


</style>
<div class="app">
	<Router {url} >
		<header class="header">
			<NavBar />
		</header>
		<div class="sidebar">
			<Sidebar />
		</div>
		<div class="content">
			<Route path="politicians" component={Politicians} />
			<Route path="*" component={Politicians} />
		</div>
	</Router>
</div>


