<script lang="ts">
  import CalendarItem from "./CalendarItem.svelte";
  export let days: Day[];
</script>

<p>This will be the calendar {days}</p>

<div class="border-2 rounded-md border-grey-500 flex flex-row space-x-4">
  {#each days as day}
    <CalendarItem day={day} />
  {/each}
</div>
