<script lang="ts">
    import { onMount } from "svelte";

    export let src;
    export let alt = 'Avatar';
    export let size = 'md'
    export let name = 'Avatar'

    let firstLetter = ''
    let secondtLetter = ''
    let words = name.split(' ')
    if(words.length == 1){
        firstLetter = words[0][0].toUpperCase()
        secondtLetter = words[0][1].toUpperCase()
    }else{
        firstLetter = words[0][0].toUpperCase()
        secondtLetter = words[1][0].toUpperCase()
    }

    let imageExists = true;
    onMount(()=>{
        let image = new Image()
        image.onload = function(){
            imageExists = true
        }
        image.onerror = function(){
            imageExists = false
        }
        image.src = src
    })

    function hw(){
        switch(size){
            case 'xs':
                return 'w-12 h-12'
            case 'sm':
                return 'w-14 h-14'
            case 'md':
                return 'w-16 h-16'
            case 'lg':
                return 'w-[72px] h-[72px]'
            case 'xl':
                return 'w-[80px] h-[80px]'
            case '2xl':
                return 'w-[88px] h-[88px]'
            case 'sxl':
                return 'w-[100px] h-[100px]'
        }
    }
</script>
{#if false}
<div class="w-12 w-14 w-16 h-12 h-14 h-16 rounded-full"></div>
{/if}
{#if imageExists}
    <img {src} {alt} class={`${hw()} rounded-full`}/>
{:else}
    <span class={`bg-green-700 ${hw()} text-white flex rounded-full justify-center items-center`}>
        {firstLetter}{secondtLetter}
    </span>
{/if}