<script>
    function close() {
        const readme = document.getElementById("readme");
        readme.classList.add("hidden");
    }
</script>

<section id="readme" class="fixed bg-gray-800 text-gray-400 m-auto w-2/3 h-2/3 rounded-lg left-0 right-0 top-0 bottom-0 body-font hidden">
    <button on:click={close} class="absolute right-0 top-0 w-6 h-6 flex justify-center items-center cursor-pointer text-xl border-0 rounded-lg">&times;</button>
    <div class="container p-5 flex justify-center h-full">
        <div class="overflow-auto w-full h-full">
            <div id="readmeContent" class="min-w-full min-h-full">lol</div>
        </div>
    </div>
</section>

<style>
</style>
