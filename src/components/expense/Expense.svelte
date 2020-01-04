<script>
  import { Button } from "sveltestrap";
  export let index = 0;
  export let expense = {};
  let isBudgetAmountVisible = false;
  let subClassName = "down";

  const toggleBudgetAmountVisibility = () => {
    isBudgetAmountVisible = !isBudgetAmountVisible;
    subClassName = isBudgetAmountVisible ? "up" : "down";
  }
  
</script>


<hr>
<p>
  <!-- <span>{ index }.</span> -->
  <span>Title: { expense.name }</span>
  <span class="all-btn">
  <Button color="light" size="sm" on:click={toggleBudgetAmountVisibility}>
  <i class="text-secondary fa fa-pencil" aria-hidden="true"></i>
  </Button>

  <Button color="light" size="sm" on:click={toggleBudgetAmountVisibility}>
  <i class="text-danger fa fa-trash" aria-hidden="true"></i>
  </Button>

  <Button color="light" size="sm" on:click={toggleBudgetAmountVisibility}>
  <i class={"text-info fa fa-caret-" + subClassName} aria-hidden="true"></i>
  </Button></span><br>

  {#if isBudgetAmountVisible}
    <span>Amount: { expense.amount }</span>
  {/if}
</p>

<style>
  .all-btn {
    float: right;
  }
</style>