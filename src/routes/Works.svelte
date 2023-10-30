<script>
    import { onMount } from "svelte";
    import WorkLeft from "../components/WorkLeft.svelte";
    import WorkRight from "../components/WorkRight.svelte";

    async function getWorks() {
        const res = await fetch("./works.json");
        const works = await res.json();
        if (res.ok) {
            return works;
        } else {
            throw new Error(works);
        }
    }
</script>

<section class="text-gray-400 bg-gray-900 body-font overflow-hidden">
    <div class="container px-5 py-24 m-auto">
        <div class="flex flex-col text-center w-full mb-10">
            <h1 class="md:text-6xl sm:text-5xl text-3xl font-medium title-font text-white">WORKS</h1>
        </div>
        {#await getWorks() then works}
            {#each works as work (work.id)}
                {#if work.id % 2 == 0}
                    <WorkLeft {...work} />
                {:else}
                    <WorkRight {...work} />
                {/if}
            {/each}
        {/await}
    </div>
</section>
