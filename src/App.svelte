<script>
	import { Router, Route, Link } from "svelte-navigator";
	import Navbar from './components/Navbar.svelte';
	import Home from './pages/Home.svelte';
	import Events from './pages/Events.svelte';
	import Members from './pages/Members.svelte';
	import Alumni from './pages/Alumni.svelte';
	import Learn from './pages/Learn.svelte';
	import Register from './pages/Register.svelte';
	import Footer from './components/Footer.svelte';
	import NotFound from './pages/NotFound.svelte';
</script>

<Router>
	<header>
		<Navbar/>
	</header>
	<main>
		<Route path="/">
			<Home />
		</Route>
		<Route path="events">
			<Events />
		</Route>
		<Route path="members">
			<Members />
		</Route>
		<Route path="alumni">
			<Alumni />
		</Route>
		<Route path="learn">
			<Learn />
		</Route>
		<Route path="register">
			<Register />
		</Route>
		<Route component="{NotFound}" />
	</main>
	<Footer/>
</Router>