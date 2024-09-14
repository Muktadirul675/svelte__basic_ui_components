<script lang="ts">
    export let borderless = false;
</script>

<div class={`rounded-md ${borderless ? '' : 'border'}`}>
    <slot/>
</div>