<script>
	import { Col, Container, Row, Button } from "sveltestrap";
	import NavBar from './components/nav/NavBar.svelte';
	import Title from "./components/title/Title.svelte";
	const colors = [
    "primary", "secondary", "success", "danger", "warning", "info", "light", "dark"
  ];
	export let name;
</script>

<div>
	<NavBar />
	<Container>
	<Title />
	<Button color="success">
		Button
	</Button>
	</Container>
</div>
<style>

</style>