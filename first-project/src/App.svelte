<script>
  let name = 'Daniel';
  let age = 25;

  $: uppercaseName = name.toUpperCase();

  $: console.log(name);

  $: if(name === 'Lucas') {
    console.log('It runs!');
    age = 25;
  }

  function incrementAge() {
    age += 1;
  }

  function changeName() {
    name = 'Lucas';
  }
</script>

<style>
	h1 {
		color: purple;
	}
</style>

<h1>Hello {uppercaseName}, my age is {age}!</h1>
<button on:click="{incrementAge}">Change Age</button>
<button on:click="{changeName}">Change Name</button>