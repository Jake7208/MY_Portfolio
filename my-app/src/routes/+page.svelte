<script>
	import Typed from 'typed.js';
	import { onMount } from 'svelte';

	let typedElement;
	onMount(() => {
		const options = {
			strings: [
				"Hello I'm Jacob",
				"I'm A full stack developer with a focus in backend",
				'Want to learn more about me?'
			],
			typeSpeed: 50,
			backSpeed: 50,
			loop: true
		};
		const typed = new Typed(typedElement, options);
	});
</script>

<div class="text-3xl">
	<span bind:this={typedElement} />
</div>
