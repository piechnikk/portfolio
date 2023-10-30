<script>
    function displayMessage(err, data, root = null) {
        if (root == null) root = document.getElementsByTagName("main")[0];
        let msg_div = document.createElement("div");
        msg_div.className = "fixed m-auto w-full mt-2 transition-opacity duration-500 opacity-0 top-0 z-1";
        let msg = document.createElement("p");
        msg.className = "text-white block pt-2 pb-2 text-center text-lg font-bold w-full rounded m-auto";
        msg.classList.add(err ? "bg-red-600" : "bg-green-500");
        msg.innerText = data;
        msg_div.appendChild(msg);
        root.append(msg_div);
        setTimeout(() => {
            msg_div.classList.add("opacity-90");
            msg_div.classList.remove("opacity-0");
            setTimeout(() => {
                msg_div.classList.remove("opacity-90");
                msg_div.classList.add("opacity-0");
                setTimeout(() => {
                    root.removeChild(msg_div);
                }, 500);
            }, 4000);
        }, 10);
    }

    function sendMessage(e) {
        if (e.target[1].value.length == 0) {
            displayMessage(true, "The message cannot be empty");
        } else {
            displayMessage(false, "The message has been sent");
            console.log("email: ", e.target[0].value);
            console.log("message: ", e.target[1].value);
            e.target[0].value = "";
            e.target[1].value = "";
        }
    }
</script>

<section class="text-gray-400 bg-gray-900 body-font relative">
    <div class="container px-5 sm:py-24 pt-12 m-auto">
        <div class="flex flex-col text-center w-full mb-10">
            <h1 class="md:text-6xl sm:text-5xl text-3xl font-medium title-font text-white">CONTACT</h1>
        </div>
    </div>
    <form on:submit|preventDefault={sendMessage} class="lg:w-1/2 container px-5 pb-12 mx-auto flex">
        <div class="bg-gray-900 shadow-md rounded-lg p-8 flex flex-col md:ml-auto w-full mt-10 md:mt-0 relative z-10">
            <h2 class="text-white text-lg mb-1 font-medium title-font">Message me</h2>
            <div class="relative mb-4">
                <label for="email" class="leading-7 text-sm text-gray-400">Email</label>
                <input
                    on:invalid|preventDefault={() => displayMessage(true, "Enter valid email address")}
                    type="email"
                    id="email"
                    name="email"
                    class="w-full bg-gray-800 rounded border border-gray-700 focus:border-indigo-500 focus:ring-2
                focus:ring-indigo-900 text-base outline-none text-gray-100 py-1 px-3 leading-8 transition-colors duration-200 ease-in-out"
                    required
                />
            </div>
            <div class="relative mb-4">
                <label for="message" class="leading-7 text-sm text-gray-400">Message</label>
                <textarea id="message" name="message" class="w-full bg-gray-800 rounded border border-gray-700 focus:border-indigo-500 focus:ring-2 focus:ring-indigo-900 h-32 text-base outline-none text-gray-100 py-1 px-3 resize-none leading-6 transition-colors duration-200 ease-in-out" />
            </div>
            <input type="submit" class="text-white bg-indigo-500 border-0 py-2 px-6 focus:outline-none hover:bg-indigo-600 rounded text-lg" />
        </div>
    </form>
</section>
