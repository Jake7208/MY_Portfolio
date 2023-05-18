<script>
	import Typed from 'typed.js';
	import { onMount } from 'svelte';
	import LongCard from '../components/longCard.svelte';
	import Paralax from '../components/paralax.svelte';
	import Nav from '../components/nav.svelte';
	import ScrollFun from '../components/scrollFun.svelte';
	import BackendScroll from '../components/backendScroll.svelte';
	import Databases from '../components/databases.svelte';
	import Social from '../components/social.svelte';

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

	function scrollingR() {
		let right = document.querySelector('#scroll-stuff');
		right.scrollBy(500, 0);
	}
</script>

<main class="max-h-screen overflow-y-scroll snap snap-y snap-mandatory no-scrollbar">
	<section class="w-full h-screen bg-black- snap-start">
		<Nav />
		<div class="flex-shrink-0 h-screen flex items-center justify-center">
			<div class="text-8xl lg:text-8xl md:text-6xl">
				<span bind:this={typedElement} />
			</div>
		</div>
	</section>

	<section class=" h-screen bg-black snap-start scroll-smooth">
		<div
			id="scroll-stuff"
			class="snap-x mx-none snap-mandatory h-screen flex w-full overflow-x-scroll overflow-y-hidden scroll-smooth no-scrollbar"
		>
			<div
				class="snap-start bg-black w-full flex-shrink-0 h-screen flex items-center justify-center text-8xl"
			>
				<div class="h-screen flex justify-center items-center text-6xl bg-black text-white">
					<Paralax />
				</div>
			</div>
			<div class="snap-start bg-black w-full flex-shrink-0 h-screen flex items-center text-8xl">
				<button
					class="text-white bg-black hover:bg-orange-800 focus:ring-4 focus:outline-none focus:ring-orange-300 font-medium rounded-lg text-sm px-4 py-2 text-center ml-3 md:mr-0 dark:bg-orange-600 dark:hover:bg-orange-700 dark:focus:ring-orange-800 cursor-pointer transition-all hover:-translate-y-[.15rem] delay-150 duration-500 hover:animate-pulse"
					on:click={scrolling}>prev</button
				>
			</div>
		</div>
	</section>
	<section class="flex flex-wrap h-screen snap-start">
		<ScrollFun class="bg-indigo-300" />
		<BackendScroll class="bg-orange-300" />
		<Databases class="bg-green-300" />
		<Social class="bg-pink-300" />
	</section>
	<div class="snap-y snap-mandatory h-1/4" />
</main>

<!-- <div
	class="fixed h-screen w-screen z-10 bottom-0 flex justify-center items-center text-6xl bg-white text-white mix-blend-difference"
	style:transform={`translateY(${height - scroll / 2}px)`}
/> -->
<!-- <svelte:window bind:scrollY={scroll} bind:innerHeight={height} />
 -->
