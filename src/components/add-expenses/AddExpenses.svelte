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
    <ModalBody>
      <Form>
        <FormGroup>
          <Input
          type="text"
          name="expense-name"
          placeholder="Name" />
        </FormGroup>
        <FormGroup>
          <Input
            type="text"
            name="amount"
            placeholder="Amount" />
        </FormGroup>
      </Form>
    </ModalBody>
    <ModalFooter>
      <Button color="primary" on:click={toggle}>Add</Button>
      <Button color="secondary" on:click={toggle}>Cancel</Button>
    </ModalFooter>
  </Modal>
</div>
