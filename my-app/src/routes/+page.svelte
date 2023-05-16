<script>
	import Typed from 'typed.js';
	import { onMount } from 'svelte';
	import LongCard from '../components/longCard.svelte';

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
</script>

<html lang="en">
	<head>
		<meta charset="UTF-8" />
		<meta name="viewport" content="width=device-width, initial-scale=1.0" />
		<title>My Portfolio</title>
		<style>
			/* Add any additional styles you need */
		</style>
	</head>
	<body>
		<ul class="fixed md:static md:float-right">
			<li class="mr-6">
				<a class="text-[#FC7823]" href="#">Home</a>
			</li>
			<li class="mr-6">
				<a class="text-[#FC7823]" href="https://www.linkedin.com/in/jacob-price1/">LinkedIn </a>
			</li>
			<li class="mr-6">
				<a class="text-[#f79d65] hover:text-[#FC7823]" href="https://github.com/Jake7208"
					>GitHub
				</a>
			</li>
		</ul>

		<div class="flex items-center justify-center h-[75vh]">
			<div class="text-8xl lg:text-8xl md:text-6xl">
				<span bind:this={typedElement} />
			</div>
		</div>
		<LongCard />
	</body>
</html>
