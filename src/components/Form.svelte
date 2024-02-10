<script lang="ts">
  let name = 'blue';
  let age = 30;
  import { createEventDispatcher } from 'svelte';
  const dispatch = createEventDispatcher();

  function handleSubmit(e: Event) {
    dispatch('form_submit', { name, age });
  }
</script>

<form on:submit|preventDefault={handleSubmit}>
  <label for="name">Name:</label>
  <input type="text" id="name" bind:value={name} />

  <label for="age">Age:</label>
  <input type="number" id="age" bind:value={age} />

  <button type="submit">Submit</button>
</form>

<button class="border p-2 bg-purple-200 font-bold" on:click|once
  >Click once</button
>
