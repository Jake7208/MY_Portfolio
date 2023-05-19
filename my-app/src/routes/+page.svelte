<script>
	import Typed from 'typed.js';
	import { onMount } from 'svelte';
	import LongCard from '../components/longCard.svelte';
	import Paralax from '../components/paralax.svelte';
	import Nav from '../components/nav.svelte';

	let typedElement;
	let typedInstance;
	let isStringComplete = false;
	let resetTimeout;

	const options = {
		strings: [
			"Hello I'm" + ' <span class="text-[#FC7823]">Jacob</span>',
			"I'm A " + '<span class="text-[#FC7823]">Full Stack Developer</span>.',
			'Want to learn more' + ' <span class="text-[#FC7823]">about me?</span>'
		],
		typeSpeed: 50,
		backSpeed: 50,
		loop: false,
		onComplete: () => {
			isStringComplete = true;
			resetTyped();
		}
	};

	function startTyped() {
		typedInstance = new Typed(typedElement, options);
	}

	onMount(() => {
		startTyped();
	});

	function resetTyped() {
		if (typedInstance && isStringComplete) {
			typedElement.style.transition = 'opacity 3s ease-out';
			typedElement.style.opacity = '0';

			setTimeout(() => {
				typedInstance.destroy();
				isStringComplete = false;

				clearTimeout(resetTimeout);
				resetTimeout = setTimeout(() => {
					typedElement.style.transition = 'opacity 3s ease-in';
					typedElement.style.opacity = '1';
					startTyped();
				}, 3000);
			}, 3000);
		}
	}
	function scrolling() {
		let left = document.querySelector('#scroll-stuff');
		left.scrollBy(-500, 0);
	}
	function scrollingL() {
		let left = document.querySelector('#snapContainer');
		left.scrollBy(-500, 0);
	}

	function scrollingR() {
		let right = document.querySelector('#snapContainer');
		right.scrollBy(500, 0);
	}
	onMount(() => {
		const snapContainer = document.getElementById('snapContainer');
		snapContainer.scrollLeft = snapContainer.offsetWidth / 2;
	});

	let scroll;
	let height;
</script>

<svelte:window bind:scrollY={scroll} bind:innerHeight={height} />

<Nav />
<div class="flex-shrink-0 h-screen flex items-center justify-center">
	<div class="text-8xl lg:text-8xl md:text-6xl">
		<span bind:this={typedElement} />
	</div>
</div>
<!-- <ScrollFun />
		<BackendScroll />
		<Databases />
		<Social /> -->
<div
	class="fixed h-[100vh] w-screen z-10 bottom-0 flex justify-center items-center text-6xl bg-white text-white"
	style:transform={`translateY(${height - scroll * 2}px)`}
/>
<div
	id="scroll-stuff"
	class="snap-x mx-none snap-mandatory h-screen flex w-full overflow-x-scroll overflow-y-hidden scroll-smooth no-scrollbar"
>
	<div
		class="snap-start bg-gray-950 w-full flex-shrink-0 h-screen flex items-center justify-center text-8xl"
	>
		<div class="h-screen flex justify-center items-center text-6xl bg-black text-white">
			<Paralax />
		</div>
	</div>
	<div class="snap-start bg-black w-full flex-shrink-0 h-screen flex items-center text-8xl">
		<button
			class="text-white hover:bg-orange-800 focus:ring-4 focus:outline-none focus:ring-orange-300 font-medium rounded-lg text-sm px-4 py-2 text-center ml-3 md:mr-0 dark:bg-orange-600 dark:hover:bg-orange-700 dark:focus:ring-orange-800 cursor-pointer transition-all hover:-translate-y-[.15rem] delay-150 duration-500 hover:animate-pulse"
			on:click={scrolling}>Back</button
		>
	</div>
</div>
<div
	class="snap-x mx-auto snap-mandatory h-screen flex w-full overflow-scroll scroll-smooth no-scrollbar"
	id="snapContainer"
>
	<div
		class="snap-start bg-black w-1/2 flex-shrink-0 h-screen flex text-4xl max-md:text-2xl max-sm:text-xl"
	>
		<div
			class="snap-start bg-white w-full flex-shrink-0 h-screen flex text-4xl max-md:text-2xl max-sm:text-xl"
		>
			<div class="snap-y snap-mandatory h-screen w-full overflow-scroll">
				<div
					class="snap-start bg-amber-200 w-full h-screen flex items-center justify-center text-8xl"
				>
					1
				</div>
				<div
					class="snap-start bg-teal-200 w-full h-screen flex items-center justify-center text-8xl"
				>
					2
				</div>
				<div
					class="snap-start bg-cyan-200 w-full h-screen flex items-center justify-center text-8xl"
				>
					3
				</div>
				<div class="snap-start bg-fuchsia-200 w-full h-screen flex justify-center text-8xl">
					<button
						class=" items-end text-white hover:bg-gray-800 focus:ring-4 focus:outline-none focus:ring-gray-500 font-medium rounded-lg text-sm px-4 py-2 text-center ml-3 md:mr-0 dark:bg-black dark:hover:bg-gray-700 dark:focus:ring-gray-800 cursor-pointer transition-all hover:-translate-y-[.15rem] delay-150 duration-500 hover:animate-pulse h-10 w-20 mt-5"
						on:click={scrollingR}>Back</button
					>
				</div>
			</div>
		</div>
	</div>
	<button
		class="snap-start bg-gray-300 hover:bg-orange-300 w-1/2 flex-shrink-0 h-screen flex items-center justify-center text-4xl max-md:text-2xl max-sm:text-xl text-black dark:focus:ring-orange-800 cursor-pointer transition-all hover:-translate-y-[.15rem] delay-150 duration-500 hover:animate-pulse"
		on:click={scrollingL}
	>
		FrontEnd
	</button>
	<button
		class="snap-start bg-black hover:bg-orange-900 w-1/2 flex-shrink-0 h-screen flex items-center justify-center text-4xl max-md:text-2xl max-sm:text-xl text-white scroll-smooth dark:focus:ring-orange-800 cursor-pointer transition-all hover:-translate-y-[.15rem] delay-150 duration-500 hover:animate-pulse"
		on:click={scrollingR}
	>
		BackEnd
	</button>
	<div
		class="snap-start bg-white w-1/2 flex-shrink-0 h-screen flex text-4xl max-md:text-2xl max-sm:text-xl"
	>
		<div class="snap-y snap-mandatory h-screen w-full overflow-scroll">
			<div
				class="snap-start bg-amber-200 w-full h-screen flex items-center justify-center text-8xl"
			>
				1
			</div>
			<div class="snap-start bg-teal-200 w-full h-screen flex items-center justify-center text-8xl">
				2
			</div>
			<div class="snap-start bg-cyan-200 w-full h-screen flex items-center justify-center text-8xl">
				3
			</div>
			<div class="snap-start bg-fuchsia-200 w-full h-screen flex justify-center text-8xl">
				<button
					class=" items-end text-white hover:bg-gray-800 focus:ring-4 focus:outline-none focus:ring-gray-500 font-medium rounded-lg text-sm px-4 py-2 text-center ml-3 md:mr-0 dark:bg-black dark:hover:bg-gray-700 dark:focus:ring-gray-800 cursor-pointer transition-all hover:-translate-y-[.15rem] delay-150 duration-500 hover:animate-pulse h-10 w-20 mt-5"
					on:click={scrollingL}>Back</button
				>
			</div>
		</div>
	</div>
</div>

<div class="snap-y snap-mandatory h-1/4" />

<!-- <svelte:window bind:scrollY={scroll} bind:innerHeight={height} /> !-->
