<script>
  export let goal;

  $: shouldRed = goal.includes('!');
</script>

<style>
  .red{
    color: red;
  }
</style>

<h1 class:red={shouldRed}>{goal}</h1>