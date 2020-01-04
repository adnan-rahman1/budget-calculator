<script>
  import Expense from "../expense/Expense.svelte";
  import Title from "../title/Title.svelte";
  export let expenses = [];
</script>

<div>
  <br>
  <strong>
    <Title title="Expense List" />
  </strong>
  {#each expenses as expense, index }
    <Expense index={index+1} {expense} />
    {:else}
    <p>No expenses are available right now.</p>
  {/each}
</div>


<style>
  strong {
    color: royalblue;
  }
</style>