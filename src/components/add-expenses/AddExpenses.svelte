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
    <Form>
      <ModalBody>
          <FormGroup>
            <Input
            type="text"
            name="expense"
            bind:value={expense}
            placeholder="Name" />
          </FormGroup>
          <FormGroup>
            <Input
              type="number"
              name="amount"
              bind:value={amount}
              placeholder="Amount" />
          </FormGroup>
      </ModalBody>
      <ModalFooter>
        <Button type="submit" color="primary" on:click={toggle}>Add</Button>
        <Button color="secondary" on:click={toggle}>Cancel</Button>
      </ModalFooter>
    </Form>
  </Modal>
</div>
