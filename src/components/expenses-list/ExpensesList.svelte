<script>
  import Expense from "../expense/Expense.svelte";
  export let expenses = [];
</script>


{#each expenses as expense }
  <Expense name={expense.name} />
{/each}


