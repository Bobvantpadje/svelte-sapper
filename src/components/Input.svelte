<script lang="ts">
    export const label: string = null;
    export const inputType: string = 'text';
</script>

{#if label}
<span>{label}</span>
{/if}

<input type={inputType} />