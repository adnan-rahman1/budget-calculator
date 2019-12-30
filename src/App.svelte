<script>
	import { Col, Container, Row, Button } from "sveltestrap";
	import NavBar from './components/nav/NavBar.svelte';
	const colors = [
    "primary", "secondary", "success", "danger", "warning", "info", "light", "dark"
  ];
	export let name;
</script>

<main>
	<NavBar />
	<Container>
	<h1>Hello {name}!</h1>
	<Button color="success">
		Button
	</Button>
	</Container>
</main>
<style>

</style>