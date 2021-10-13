<script>
  import { writable } from "svelte/store";

  const storedContent = localStorage.content || "";
  const content = writable(storedContent);
  content.subscribe(value => localStorage.content = value);
</script>

<style>
  .container {
    height: 100%;
    width: 100%;
    overflow: hidden;
    font-family: monospace;
  }
  .editor {
    width: 100%;
    height: 100%;
    font-size: 1rem;
    padding: 1rem;
    margin: 0;
    resize: none;
    border: 0;
  }
</style>

<div class="container">
  <textarea class="editor" bind:value={$content}></textarea>
</div>
