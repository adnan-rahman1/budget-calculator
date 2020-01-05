<script>
	import { Col, Container, Row, Button } from "sveltestrap";
	import NavBar from './components/nav/NavBar.svelte';
	import ExpensesList from './components/expenses-list/ExpensesList.svelte';
	import ExpenseData from "./expenses";
	import TotalExpenses from "./components/total-expenses/TotalExpenses.svelte";

	let expenses = [...ExpenseData];

	$: totalExpenses = expenses.reduce((acc, cur) => ( acc + cur.amount), 0)

	let removeExpense = id => {
		expenses = expenses.filter(expense => expense.id !== id);
	}
</script>

<NavBar />
<Container>
	<Row>
		<Col>
			<TotalExpenses {totalExpenses} />
			<ExpensesList {expenses} {removeExpense} />
			<!-- <Button color="success">
				Button
			</Button> -->
		</Col>
	</Row>
</Container>