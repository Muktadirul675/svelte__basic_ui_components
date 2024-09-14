<script lang="ts">
    export let color = 'gray';
    import Dot from "./Dot.svelte";
</script>

<div class="inline-block">
    <Dot {color} animate={true}/>
    <Dot {color} animate={true} delay={350}/>
    <Dot {color} animate={true}/>
</div>
