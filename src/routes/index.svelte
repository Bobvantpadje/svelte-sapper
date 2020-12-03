<script lang="ts">
  const maxBookings = 20;
  type User = {
    id: string;
    name: string;
    password: string;
    stack: string;
  };

  let name = "";
  let stack = "";
  $: bookings = [createUser("pieter", "react"), createUser("jantje", "svelte")];
  $: addState = "";

  const createUser = (name: string, stack: string): User => ({
    id: "random",
    password: "password",
    name,
    stack,
  });

  const addBooking = (curName: string, curStack: string) => {
    if (bookings.length === maxBookings) {
      addState = "maxBookings exceeded";
      return;
    }
    bookings = [...bookings, createUser(curName, curStack)];
    addState = "";
    name = "";
    stack = "";
  };

//   const calculateRelativeSkills = (skills: Array<{name: string, count: number}>, user: User) => {
  const calculateRelativeSkills = (skills, user) => {
	  const userStack = user.stack;
	  if (!skills[userStack]) {
		  return {...skills, [userStack]: 1};
	  }
	  return {...skills, [userStack]: skills[userStack] + 1}
  }
  $: stackObject = bookings.reduce(calculateRelativeSkills, {})

  const removeBooking = (name: string) => {
    bookings = bookings.filter((booking) => booking.name !== name);
  };
</script>

<svelte:head>
  <title>Sapper project template</title>
</svelte:head>

<h1 class="text-blue-500">Lets get started!</h1>

<span>
  total spots: {maxBookings} - open spots = {maxBookings - bookings.length}
</span>
<br />
<label>
  <span>name</span>
  <input type="text" bind:value="{name}" />
</label>
<label>
  <span>stack</span>
  <input type="text" bind:value="{stack}" />
</label>
<button on:click="{() => addBooking(name, stack)}">add item</button>
{#if addState}
  <br />
  <span>{addState}</span>
{/if}
<ul>
  {#each bookings as booking}
    <li>
      {booking.name} - {booking.stack}
      <button on:click="{() => removeBooking(booking.name)}">delete</button>
    </li>
  {/each}
</ul>
<ul>
  {#each Object.entries(stackObject) as [key, value]}
    <li>
      {key} - {value}
    </li>
  {/each}
</ul>

<p>
  <strong>
    Try editing this file (src/routes/index.svelte) to test live reloading.
  </strong>
</p>
