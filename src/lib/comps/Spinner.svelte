<script lang="ts">
    import Colors from "./Colors.svelte";
    export let color = 'blue'
    export let bg = 'gray';
    export let size = 'md';

    function hw(){
        switch(size){
            case 'xs':
                return 'h-4 w-4'
            case 'sm':
                return 'h-5 w-5'
            case 'md':
                return 'h-6 w-6'
            case 'lg':
                return 'h-7 w-7'
        }
    }
</script>

<Colors/>
<div class={`inline-block border-${bg}-200 ${hw()} animate-spin rounded-full border-[1px] border-t-${color}-600`} />

