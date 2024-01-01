<script>
	import { onMount } from "svelte";
	import { fade } from "svelte/transition";
	import "../app.css";

	import Navbar from "./Navbar.svelte";

	onMount(() => {
		const words = [
			"Hello, World!",
			"Welcome to my website!",
			"This is a typewriter effect.",
		];
		let i = 0;
		let j = 0;
		let currentWord = "";
		let isDeleting = false;

		function type() {
			currentWord = words[i];
			if (isDeleting) {
				document.getElementById("typewriter").textContent =
					currentWord.substring(0, j - 1);
				j--;
				if (j == 0) {
					isDeleting = false;
					i++;
					if (i == words.length) {
						i = 0;
					}
				}
			} else {
				document.getElementById("typewriter").textContent =
					currentWord.substring(0, j + 1);
				j++;
				if (j == currentWord.length) {
					isDeleting = true;
				}
			}
			setTimeout(type, 100);
		}

		type();
	});
</script>

<div class="" in:fade out:fade>
	<Navbar />

	<div class="h-screen flex items-center justify-center">
		<div class="select-none text-center text-white font-minecraft_bold flex flex-col h-full justify-around">
			<div class="">
				<p class="text-3xl">The BASEMENT</p>
			</div>

<div class="">			<p
	class="transition duration-500 hover:underline cursor-pointer hover:bg-black rounded-lg mt-8"
>
	Book a Session
</p>

<p
	class="transition duration-500 hover:underline cursor-pointer hover:bg-black rounded-lg mt-2"
>
	Hip Hop / Trap Beats
</p>

<p
	class="transition duration-500 hover:underline cursor-pointer hover:bg-black rounded-lg mt-2"
>
	About
</p></div>


		</div>
	</div>
</div>

<style>
</style>
