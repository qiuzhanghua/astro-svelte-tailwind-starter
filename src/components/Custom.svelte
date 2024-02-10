<script lang="ts">
  import Form from './Form.svelte';

  function onFormSubmit(e: CustomEvent) {
    const { name, age } = e.detail;
    console.log(name, age);
  }
</script>

<Form
  on:form_submit={onFormSubmit}
  on:click={() => {
    console.log('Button was clicked!');
  }}
/>
