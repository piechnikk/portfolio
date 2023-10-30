<script>
    export let title;
    export let description;
    export let live;
    export let image;
    export let readme;
</script>

<section class="text-gray-400 bg-gray-900 body-font">
    <div class="container mx-auto flex px-5 sm:pt-24 py-12 md:flex-row flex-col items-center">
        <div class="lg:max-w-lg lg:w-full md:w-1/2 w-5/6 md:mb-0 mb-10 md:block hidden">
            <img class="object-cover object-center rounded border-2 border-gray-700" alt={description} src={image} />
        </div>
        <div class="lg:flex-grow md:w-1/2 lg:pl-24 md:pl-16 flex flex-col md:items-start md:text-left items-center text-center">
            <h1 class="title-font sm:text-4xl text-3xl mb-4 font-medium text-white">
                {title}
            </h1>
            <p class="mb-8 leading-relaxed">{description}</p>
            <div class="flex justify-center">
                <a href={readme} target="_blank" class="inline-flex text-white bg-blue-500 border-0 py-2 px-6 focus:outline-none hover:bg-blue-600 rounded text-lg">Docs</a>
                <a href={live} target="_blank" class="ml-4 inline-flex text-gray-400 bg-gray-800 border-0 py-2 px-6 focus:outline-none hover:bg-gray-700 hover:text-white rounded text-lg">Live</a>
            </div>
        </div>

        <div class="lg:max-w-lg lg:w-full md:w-1/2 w-5/6 md:hidden mt-10">
            <img class="object-cover object-center rounded border-2 border-gray-700" alt={description} src={image} />
        </div>
    </div>
</section>
