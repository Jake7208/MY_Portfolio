<script>
	import Typed from 'typed.js';
	import { onMount } from 'svelte';
	import LongCard from '../components/longCard.svelte';
	import Paralax from '../components/paralax.svelte';
	import Nav from '../components/nav.svelte';
	import FrontEndCard from '../components/FrontEndCard.svelte';
	import ContactForm from '../components/contactForm.svelte';
	import Projects from '../components/projects.svelte';
	const imgUrl = new URL('../components/projects/js.png', import.meta.url).href;
	const imgUrl1 = new URL('../components/projects/animated.png', import.meta.url).href;
	const imgUrl2 = new URL('../components/projects/frontend-design.png', import.meta.url).href;
	const imgUrl3 = new URL('../components/projects/resume.png', import.meta.url).href;
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

	let element;
	let lastScrollTop = 0;

	const handleScroll = () => {
		let scrollTop = window.pageYOffset || document.documentElement.scrollTop;
		let scrollDelta = lastScrollTop - scrollTop;

		let transformValue =
			parseInt(window.getComputedStyle(element).getPropertyValue('transform').split(',')[5]) || 0;
		element.style.transform = `translateY(${transformValue - 2 * scrollDelta}px)`;
		lastScrollTop = scrollTop;

		onMount(() => {
			window.addEventListener('scroll', handleScroll);

			return () => {
				window.removeEventListener('scroll', handleScroll);
			};
		});
	};
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
	class="fixed h-[100vh] w-screen z-10 bottom-0 flex justify-center items-center text-6xl bg-black text-white"
	style:transform={`translateY(${height - scroll * 2}px)`}
>
	Who Am I?
</div>
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
	<div
		class="snap-start bg-black w-full flex-shrink-0 h-screen flex justify-center items-center text-8xl"
	>
		<ContactForm />
	</div>
</div>
<div
	bind:this={element}
	class=" h-[100vh] w-auto z-10 bottom-0 flex justify-center items-center text-6xl bg-black text-white overflow-hidden"
	style:transform={`translateY(${500 - scroll / 2}px)`}
>
	Projects
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
			<div class="snap-y snap-mandatory h-screen w-full overflow-scroll no-scrollbar">
				<div class="snap-start bg-black w-full h-screen flex items-center justify-center text-8xl">
					<FrontEndCard />
				</div>
				<div class="snap-start bg-black w-full h-screen flex items-center justify-center text-8xl">
					<div
						class="max-w-md bg-white border border-black rounded-lg shadow dark:bg-gray-800 dark:border-gray-700 h-auto mx-auto"
					>
						<img class="rounded-t-lg" src={imgUrl} alt="" />
						<div class="p-5">
							<h5 class="mb-2 font-bold tracking-tight text-gray-900 dark:text-white text-lg">
								Languages used in this project
							</h5>
							<p class="mb-3 font-normal text-gray-700 dark:text-gray-400 text-sm">
								Javascript, HTML, CSS
							</p>
						</div>
					</div>
				</div>
				<div class="snap-start bg-black w-full h-screen flex items-center justify-center text-8xl">
					<div
						class="max-w-md bg-white border border-black rounded-lg shadow dark:bg-gray-800 dark:border-gray-700 h-auto mx-auto no-scrollbar"
					>
						<img class="rounded-t-lg" src={imgUrl2} alt="" />
						<div class="p-5">
							<h5 class="mb-2 font-bold tracking-tight text-gray-900 dark:text-white text-lg">
								Languages used in this project
							</h5>
							<p class="mb-3 font-normal text-gray-700 dark:text-gray-400 text-sm">
								Javascript, HTML, CSS, openprops(CSS)
							</p>
						</div>
					</div>
				</div>
				<div class="snap-start bg-black w-full h-screen flex items-center justify-center text-8xl">
					<div
						class="max-w-md bg-white border border-black rounded-lg shadow dark:bg-gray-800 dark:border-gray-700 h-auto mx-auto"
					>
						<img class="rounded-t-lg" src={imgUrl1} alt="" />
						<div class="p-5">
							<h5 class="mb-2 font-bold tracking-tight text-gray-900 dark:text-white text-lg">
								Languages used in this project
							</h5>
							<p class="mb-3 font-normal text-gray-700 dark:text-gray-400 text-sm">
								CSS animations
							</p>
						</div>
					</div>
				</div>
				<div class="snap-start bg-black w-full h-screen flex justify-center text-8xl">
					<button
						class=" items-end text-black hover:bg-gray-800 focus:ring-4 focus:outline-none focus:ring-gray-500 font-medium rounded-lg text-sm px-4 py-2 text-center ml-3 md:mr-0 dark:bg-white dark:hover:bg-gray-700 dark:focus:ring-gray-800 cursor-pointer transition-all hover:-translate-y-[.15rem] delay-150 duration-500 hover:animate-pulse h-10 w-20 mt-5"
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
		class="snap-start hover:bg-orange-900 w-1/2 flex-shrink-0 h-screen flex items-center justify-center text-4xl max-md:text-2xl max-sm:text-xl text-white scroll-smooth dark:focus:ring-orange-800 cursor-pointer transition-all hover:-translate-y-[.15rem] delay-150 duration-500 hover:animate-pulse"
		on:click={scrollingR}
	>
		BackEnd
	</button>
	<div
		class="snap-start bg-white w-1/2 flex-shrink-0 h-screen flex text-4xl max-md:text-2xl max-sm:text-xl"
	>
		<div class="snap-y snap-mandatory h-screen w-full overflow-scroll bg-black no-scrollbar">
			<div class=" snap-start bg-white w-full h-screen flex items-center justify-center text-8xl">
				<div
					class="flex flex-col h rounded-lg bg-white shadow-[0_2px_15px_-3px_rgba(0,0,0,0.07),0_10px_20px_-2px_rgba(0,0,0,0.04)] dark:bg-neutral-700 md:max-w-xl md:flex-row"
				>
					<div class="flex flex-col justify-start p-6 max-w-md w-[50vw] h-auto">
						<h5 class="mb-2 text-xl font-medium text-neutral-800 dark:text-neutral-50">
							Team development
						</h5>

						<span class="flex items-center text-sm font-medium text-gray-900 dark:text-white"
							><span
								class="flex w-2.5 h-2.5 bg-black rounded-full mr-1.5 flex-shrink-0"
							/>express</span
						>
						<span class="flex items-center text-sm font-medium text-green-700 dark:text-white"
							><span
								class="flex w-2.5 h-2.5 bg-green-800 rounded-full mr-1.5 flex-shrink-0"
							/>node.js</span
						>
						<span class="flex items-center text-sm font-medium text-green-700 dark:text-white"
							><span
								class="flex w-2.5 h-2.5 bg-green-600 rounded-full mr-1.5 flex-shrink-0"
							/>mongoDB</span
						>
						<span class="flex items-center text-sm font-medium text-green-700 dark:text-white"
							><span
								class="flex w-2.5 h-2.5 bg-orange-600 rounded-full mr-1.5 flex-shrink-0"
							/>REST</span
						>
					</div>
				</div>
			</div>
			<div class="snap-start bg-white w-full h-screen flex items-center justify-center text-8xl">
				<div
					class="flex flex-col rounded-lg bg-white shadow-[0_2px_15px_-3px_rgba(0,0,0,0.07),0_10px_20px_-2px_rgba(0,0,0,0.04)] dark:bg-neutral-700 md:max-w-xl md:flex-row"
				>
					<div class="flex flex-col justify-start p-6 max-w-md w-[50vw] h-auto">
						<h5
							class="mb-2 text-xl font-medium text-neutral-800 dark:text-neutral-50 border-r-black"
						>
							C# code with mosh
						</h5>

						<span class="flex items-center text-sm font-medium text-gray-900 dark:text-white"
							><span
								class="flex w-2.5 h-2.5 bg-green-400 rounded-full mr-1.5 flex-shrink-0"
							/>C#</span
						>
					</div>
				</div>
			</div>
			<div class="snap-start bg-white w-full h-screen flex items-center justify-center text-8xl">
				<div
					class="flex flex-col rounded-lg bg-white shadow-[0_2px_15px_-3px_rgba(0,0,0,0.07),0_10px_20px_-2px_rgba(0,0,0,0.04)] dark:bg-neutral-700 md:max-w-xl md:flex-row"
				>
					<div class="flex flex-col justify-start p-6">
						<h5
							class="mb-2 text-xl font-medium text-neutral-800 dark:text-neutral-50 max-w-md w-[50vw] h-auto"
						>
							PHP LinkedIn
						</h5>

						<span class="flex items-center text-sm font-medium text-green-700 dark:text-white"
							><span
								class="flex w-2.5 h-2.5 bg-indigo-600 rounded-full mr-1.5 flex-shrink-0"
							/>php</span
						>
						<span class="flex items-center text-sm font-medium text-green-700 dark:text-white"
							><span
								class="flex w-2.5 h-2.5 bg-orange-600 rounded-full mr-1.5 flex-shrink-0"
							/>REST</span
						>
					</div>
				</div>
			</div>
			<div class="snap-start bg-white w-full h-screen flex justify-center text-8xl">
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
