<script lang="ts">
    import { onMount } from "svelte";
    import Colors from "./Colors.svelte";

    export let variant = "solid";
    export let color = "blue";

    let badge: HTMLElement;
    onMount(() => {
        badge.innerText = badge.innerText.toUpperCase();
    });

    function bg() {
        switch (variant) {
            case "solid":
                return `bg-${color}-300`;
            case 'outline':
                return 'bg-transparent'
        }
    }
    function text(){
        switch(variant){
            case 'solid':
                return `text-${color}-700`
            case 'outline':
                return `text-${color}-500`
        }
    }

    function border(){
        switch(variant){
            case 'outline':
                return `border border-${color}-700`
            default:
                return `border border-${color}-300`
        }
    }

</script>

<Colors/>
<span bind:this={badge} class={`font-bold ${bg()} ${text()} ${border()} p-1 text-xs rounded border-${color}-300`}>
    <slot />
</span>
