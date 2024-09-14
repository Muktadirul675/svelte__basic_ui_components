<script lang="ts">
    import { onMount } from "svelte";
    import Colors from "./Colors.svelte";

    export let color = 'gray';
    export let animate = false;
    export let delay = 0;
    let dot: HTMLElement;

    onMount(()=>{
        if(animate){
            let keyframes = [{scale:0.5,opacity:0.5},{scale:0.75,opacity:0.75},{scale:1,opacity:1},{scale:0.75,opacity:0.75},{scale:0.5,opacity:0.5}]
            dot.animate(keyframes,{
                duration: 700,
                iterations: Infinity,
                delay: delay
            })
        }
    })

</script>

<Colors/>
<div bind:this={dot} class={`inline-block rounded-full h-2 w-2 bg-${color}-700`}></div>
        