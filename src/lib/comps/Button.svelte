<script lang="ts">
    import { createEventDispatcher } from "svelte";
    import Colors from "./Colors.svelte";
    import Spinner from "./Spinner.svelte";
    import BeatLoader from "./BeatLoader.svelte";

    let button: HTMLButtonElement;
    export let variant = "regular";
    export let color = "orange";
    export let size = "md";
    export let loading = false;

    let className: string = "relative text-center";

    function padding(): string {
        switch (size) {
            case "sm":
                return "px-3 py-1";
            case "md":
                return "px-4 py-1.5";
            case "lg":
                return "px-5 py-2";
            case "wide":
                return "px-6 py-1.5";
            default:
                return "px-6 py-2";
        }
    }

    function textSize(): string {
        switch (size) {
            case "lg":
                return "text-lg";
            case "md":
                return "text-md";
            case "lg":
                return "text-lg";
            case "fill":
                return "text-xl";
            default:
                return "text-md";
        }
    }

    function width() {
        switch (size) {
            case "fill":
                return "w-full";
            default:
                return "w-fit";
        }
    }

    const dispatch = createEventDispatcher();
    function tap() {
        button.animate([{ scale: "0.95" }], { duration: 50 });
        dispatch("click");
    }

    switch (variant) {
        case "regular":
            className += `${textSize()} ${padding()} ${width()} rounded-md bg-${color}-600 text-${color == "white" ? "black" : "white"}`;
            break;
        case "ghost":
            className += `${textSize()} ${padding()} ${width()} rounded-md bg-transparent text-${color}`;
            break;
        case "outlined":
            className += `${textSize()} ${padding()} ${width()} rounded-md bg-transparent border border-${color}-600 text-${color}-600`;
            break;
    }
    $: hidden = loading ? 'opacity-0' : ''
</script>

<Colors/>
<button bind:this={button} class={className} on:click={tap}>
    {#if loading}
        <div class="absolute inset-0 flex items-center justify-center"> 
            <!-- <Spinner {size} {color}/> -->
            <BeatLoader {color}/>
        </div>
    {/if}
    <span class={hidden}>
        <slot/>
    </span>

    <!-- <span class="absolute">
        loading...
    </span> -->
</button>
