<script lang="ts">
  export let name: string = 'world';
  export let fontSize: number = 64;
  setInterval(() => {
    if (fontSize === 64) {
      fontSize = 16;
    } else {
      fontSize += 1;
    }
  }, 30);
</script>

<div style="font-size: {fontSize}px" class="bg-blue-700 text-white">
  Hello {name}, from Svelte
</div>
