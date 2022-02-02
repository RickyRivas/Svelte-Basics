<script>
	import ContactCard from './ContactCard.svelte';

  let name = "Ricky";
  let description = 'Hardworking, intelligent, and persistent individual who is a servant of God!'
  let jobTitle = 'Entrepreneaurer'
  let age = 1;
  let image = null
  $: uppercaseName = name.toUpperCase()

  $: console.log(name)
  $: if(name === 'Ricky'){
    age = 100
  }

  function addAge() {
    return age++;
  }
  function changeName() {
    name = 'Ricardo'
  }
  function nameInput(e){
    const enteredValue = e.target.value;
    name = enteredValue
  }
</script>

<style>
  h1 {
    color: purple;
  }
</style>

<h1>Hello {uppercaseName}, I am age { age }!</h1>
<button on:click="{addAge}">Change Age</button>
<!-- <button on:click="{changeName}">Change Age</button> -->
<!-- <input type="text" on:input='{nameInput}'> -->
<input type="text" bind:value='{name}'>
<input type="text" bind:value='{description}'>
<input type="text" bind:value='{image}'>
<input type="text" bind:value='{jobTitle}'>

<ContactCard 
userName='{name}'
userDesc='{description}'
userJobTitle='{jobTitle}'
imgSrc='{image}'
/>