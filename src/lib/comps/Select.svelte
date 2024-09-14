<script lang="ts">  
    export let options = ['option 1','option 2']
    let selected = options[0];
    $: console.log(selected)
</script>

<select bind:value={selected} class="p-2 rounded border border-orange-700 bg-transparent" placeholder="Select">
    {#each options as option}
        <option>{option}</option>
    {/each}
</select>

