<script lang="ts">
	import Button from './../lib/comps/Button.svelte';
    import "../app.pcss";
</script>

<div class="flex sticky top-0 start-0 bg-orange-600 shadow-lg w-full z-20 justify-center">
    <div class="flex flex-wrap navbar container z-20 text-white items-center px-2 sm:px-0">
        <h1 class="text-xl font-bold">Tasks</h1 >
        <div class="ms-auto space-x-2">
            <!-- <Button on:click={()=>console.log('hi')} color="gray" variant="ghost">Login</Button>
            <Button color="yellow" variant="outline">logout </Button> -->
            <Button color="blue">Login</Button>
            <Button color="red">logout</Button>
        </div>
    </div>
</div>

<div class="container mx-auto">
    <slot></slot>
</div>


<style>
    .navbar{
        height: 8vh;
    }
</style>
