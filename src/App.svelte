<script>
	import { Col, Container, Row, Button } from "sveltestrap";
	import NavBar from './components/nav/NavBar.svelte';
	import ExpensesList from './components/expenses-list/ExpensesList.svelte';
	import ExpenseData from "./expenses";

	let expenseData = [...ExpenseData];
</script>

<NavBar />
<Container>
	<Row>
		<Col>
			<ExpensesList expenses={expenseData} />
			<!-- <Button color="success">
				Button
			</Button> -->
		</Col>
	</Row>
</Container>