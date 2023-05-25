<script>
  export let color;
  export let value = 0;
</script>

<p>{color}({value})</p>
<input type="range"  max="255" bind:value />

<style>
  * {
    margin: 0;
    padding: 0;
  }

  input {
    min-width: 70%;
    max-width: 80%;
    padding: 10px 0;
  }
</style>
