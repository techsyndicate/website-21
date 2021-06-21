<script>
	import { Router, Route, Link } from "svelte-navigator";
	import Navbar from './components/Navbar.svelte';
	import Home from './components/Home.svelte';
	import Events from './components/Events.svelte';
	import Members from './components/Members.svelte';
	import Alumni from './components/Alumni.svelte';
	import Learn from './components/Learn.svelte';
	import Register from './components/Register.svelte';
	import Footer from './components/Footer.svelte';
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
	</main>
	<footer>
		<Footer/>
	</footer>
</Router>