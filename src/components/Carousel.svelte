<script lang="ts">
    import { onMount } from "svelte";

    let slideIndex = 0;
    let carousel: HTMLDivElement;

    function showSlide(n: number) {
        slideIndex = (n + carousel.children.length) % carousel.children.length;
        carousel.style.transform = `translateX(-${slideIndex * 100}%)`;
    }

    onMount(() => {
        showSlide(slideIndex);
    });
</script>

<div class="relative overflow-hidden rounded-lg p-36">
    <div
        bind:this={carousel}
        class="flex gap-3 transition-transform duration-500 ease-in-out"
    >
        <slot />
    </div>

    <button
        class="absolute top-1/2 left-4 transform -translate-y-1/2 bg-gray-800 text-white rounded-full p-2"
        on:click={() => showSlide(slideIndex - 1)}
    >
        <svg
            class="w-6 h-6"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
            xmlns="http://www.w3.org/2000/svg"
            ><path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M15 19l-7-7 7-7"
            ></path></svg
        >
    </button>
    <button
        class="absolute top-1/2 right-4 transform -translate-y-1/2 bg-gray-800 text-white rounded-full p-2"
        on:click={() => showSlide(slideIndex + 1)}
    >
        <svg
            class="w-6 h-6"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
            xmlns="http://www.w3.org/2000/svg"
            ><path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M9 5l7 7-7 7"
            ></path></svg
        >
    </button>
</div>
