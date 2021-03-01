<script>
  import { text } from "svelte/internal";
  import Button from "./Button.svelte";

  let someText = `Backend developer at KS`;
  let count = 0;
  let styles = { darkMode: false };

  function handleClick() {
    count += 1;
  }

  function toggle() {
    styles.darkMode = !styles.darkMode;
    window.document.body.classList.toggle("dark-mode");
  }
</script>

<div class="About">
  {#if !styles.darkMode}
    <p>{someText}</p>
  {:else}
    <p>Hello Dark Mode</p>
  {/if}
  <Button text="Dark Mode" on:click={toggle} />
  <Button text="Click" {count} on:click={handleClick} />
  <button on:click={toggle}>Dark Mode</button>
</div>

<style>
  p {
    color: var(--theme-color);
  }
</style>
