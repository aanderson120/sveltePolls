<script>
  export let type = "primary";
  export let flat = false;
  export let inverse = false;
</script>

<button class={type} class:flat={flat} class:inverse={inverse}>
  <slot />
</button>

<style>
  button {
    border: 0;
    cursor: pointer;
    border-radius: 6px;
    padding: 8px 12px;
    font-weight: bold;
    box-shadow: 1px 2px 3pb rgb(0, 0, 0, 0.2);
  }
  .primary {
    background-color: #A81532;
    color: #ffffff;
  }
  .secondary {
    background-color: #006600;
    color: #ffffff;
  }
  .flat {
    box-shadow: none;
  }
  .primary.inverse{
    color: #A81532;
    background-color: #D8CFCF;
    border: 2px solid #A81532;
  }
  .secondary.inverse{
    color: #006600;
    background-color: #D8CFCF;
    border: 2px solid #006600;
  }
</style>
