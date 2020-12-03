<script lang="ts">
  import Calendar from "../components/Calendar.svelte";

  const createUser = () => ({ name: "piet", stack: "react" });
  let days: Day[] = [
    { date: "05-12-2020", maxOccupation: 5, users: [] },
    { date: "06-12-2020", maxOccupation: 5, users: [] },
    { date: "07-12-2020", maxOccupation: 5, users: [] },
    { date: "08-12-2020", maxOccupation: 5, users: [] },
  ];
</script>

<svelte:head>
  <title>Reserve a spot</title>
</svelte:head>

<h1>About this site</h1>

<p>This is the 'about' page. There's not much here.</p>

<Calendar days={days} />
