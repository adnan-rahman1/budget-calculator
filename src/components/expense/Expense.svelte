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
  <span>{ index }.</span>
  <span>Title: { expense.name }</span>
  <Button color="primary" size="sm" on:click={toggleBudgetAmountVisibility}>
  <i class={"fa fa-caret-" + subClassName} aria-hidden="true"></i>
  </Button><br>

  {#if isBudgetAmountVisible}
    <span>Amount: { expense.amount }</span>
  {/if}
</p>