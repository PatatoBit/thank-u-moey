<script>
    import { onMount, tick } from "svelte";
    import { fly } from "svelte/transition"
    import Confetti from '../components/confetti.svelte'

    let loaded = false;

    onMount(()=> {
        loadText()
    })

    async function loadText(){
        loaded = false
        // What to do here
        await tick();
        loaded = true
    }
</script>

<svelte:head>
    <title>Home</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=BIZ+UDMincho&display=swap');
        @import url('https://fonts.googleapis.com/css2?family=Quicksand:wght@300&display=swap');
    </style>
</svelte:head>

<main class="w-full h-screen overflow-hidden flex flex-col justify-center items-center bg-gray-900 first">
    <Confetti />
    {#if loaded}
    <h1 class=" text-6xl flex flex-col text-center">
        <span in:fly={{ x: 500, y: 100, duration: 1000, delay: 0 }} class="text-white roboto">Thank you Moey</span>
        <span in:fly={{ x: 500, y: 100, duration: 1000, delay: 1000 }} class="text-5xl m-3 text-white roboto">for the</span>
        <span in:fly={{ x: 500, y: 100, duration: 1000, delay: 2000 }} class="welkin">Blessing of the Welkin moon</span>
    </h1>
    {/if}
</main>

<style>
    .first{
        z-index: 2;
    }
    .welkin {
        color: rgb(112 174 255);
        font-family: 'BIZ UDMincho', serif;
    }

    .roboto {
        font-family: 'Quicksand', sans-serif;
    }
</style>
