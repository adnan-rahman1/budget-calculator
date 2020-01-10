<script>
  import Title from "../title/Title.svelte";
  import {
    Button,
    Modal,
    ModalBody,
    ModalFooter,
    ModalHeader,
    Form,
    FormGroup,
    FormText,
    Input,
    Label
  } from "sveltestrap";

  let open = false;
  const toggle = () => (open = !open);

  let expense = "";
  let amount = 0;

  $: isEmpty = !expense || !amount;

  export let addExpense;

  const handleFormSubmit = () => {
    const newExpense = {
      id: Math.random() * Date.now(),
      name: expense,
      amount
    };
    addExpense(newExpense)
    expense = "";
    amount = 0;
  }

</script>

<style>
  div {
    float: right;
  }
</style>

<div>
  <Button color="light" on:click={toggle}>Add Item</Button>
  <Modal isOpen={open} {toggle}>
    <ModalHeader {toggle}>
      <Title title="Add Expense" />
    </ModalHeader>
    <form on:submit|preventDefault={handleFormSubmit}>
      <ModalBody>
          <FormGroup>
            <Input
            id="name"
            type="text"
            name="expense"
            bind:value={expense}
            placeholder="Name" />
          </FormGroup>
          <FormGroup>
            <Input
              id="amount"
              type="number"
              name="amount"
              bind:value={amount}
              placeholder="Amount" />
          </FormGroup>
          {#if (isEmpty)}
            <p class="text-center text-danger">Please fill out all the input.</p>
          {/if}
      </ModalBody>
      <ModalFooter>
        <Button id="submit" disabled={isEmpty} type="submit" color="primary">Add</Button>
        <Button type="button" id="cancel" color="secondary" on:click={toggle}>Cancel</Button>
      </ModalFooter>
    </form>
  </Modal>
</div>
