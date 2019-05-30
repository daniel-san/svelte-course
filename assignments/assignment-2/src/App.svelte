<script>
  let password = '';
  let passwords = [];

  $: passSize = password.trim().length;

  function addPassword() {
    if (passSize < 5 || passSize > 10)
      return;

    passwords = [
      ...passwords,
      password
    ];
    password = '';
  }

  function removePassword(password){
    passwords = passwords.filter(pass => pass !== password)
  }
</script>

<h1>Assignment</h1>

<p>Solve these tasks.</p>

<ol>
	<li>Add a password input field and save the user input in a variable.</li>
	<li>Output "Too short" if the password is shorter than 5 characters and "Too long" if it's longer than 10.</li>
	<li>Output the password in a paragraph tag if it's between these boundaries.</li>
	<li>Add a button and let the user add the passwords to an array.</li>
	<li>Output the array values (= passwords) in a unordered list (ul tag).</li>
	<li>Bonus: If a password is clicked, remove it from the list.</li>
</ol>

<input type="password" bind:value={password}>
<button on:click={addPassword}>Add Password</button>
{#if passSize < 5}
  <p>Too short</p>
{:else if passSize > 10}
  <p>Too long</p>
{:else}
  <p>Password: {password}</p>
{/if}
<ul>
  {#each passwords as pass, i}
    <li on:click={() => removePassword(pass)}>{pass}</li>
  {/each}
</ul>