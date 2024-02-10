<script lang="ts">
  function handleClick(e: MouseEvent): void {
    alert(`Button was clicked!`);
  }

  interface MyForm {
    text: string;
  }
  function handleSubmit(e: Event): void {
    const form = e.target as HTMLFormElement;
    const formData = new FormData(form);
    const data: MyForm = {
      text: formData.get('my-name') as string,
    };
    console.log(data);
    // or
    // let obj = form.querySelector('input');
    // if (obj) {
    // 	console.log(obj.value);
    // }
  }

  let left = 0;
  let top = 200;
  function handleKeyup(e: KeyboardEvent): void {
    switch (e.key) {
      case 'ArrowUp':
        top -= 1;
        break;
      case 'ArrowDown':
        top += 1;
        break;
      case 'ArrowLeft':
        left -= 1;
        break;
      case 'ArrowRight':
        left += 1;
        break;
      default:
        break;
    }
  }
</script>

<h1>Dom Usage</h1>
<button
  class="bg-blue-500 text-white font-bold py-2 px-4 rounded hover:bg-purple-700"
  on:click={handleClick}>Button</button
>
<svelte:window on:keyup={handleKeyup} />
<form on:submit|stopPropagation|preventDefault={handleSubmit}>
  <input type="text" class="border-2 border-gray-500" name="my-name" />
  <button
    type="submit"
    class="bg-blue-500 text-white font-bold py-2 px-4 rounded hover:bg-purple-700"
    >Submit</button
  >
</form>

<div style="left: {left}px; top: {top}px">press arrow key</div>

<style>
  h1 {
    @apply text-4xl;
  }
  div {
    @apply w-[100px] h-[100px] bg-green-400 absolute;
  }
</style>
