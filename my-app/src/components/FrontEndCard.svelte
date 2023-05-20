<script>
	const imgUrl = new URL('./projects/js.png', import.meta.url).href;
	const imgUrl1 = new URL('./projects/animated.png', import.meta.url).href;
	const imgUrl2 = new URL('./projects/frontend-design.png', import.meta.url).href;
	const imgUrl3 = new URL('./projects/resume.png', import.meta.url).href;
	const imgUrl4 = new URL('./projects/dice.png', import.meta.url).href;
</script>

<div
	class="max-w-md bg-white border border-gray-200 rounded-lg shadow dark:bg-gray-800 dark:border-gray-700 h-auto mx-auto"
>
	<img class="rounded-t-lg" src={imgUrl3} alt="" />
	<div class="p-5">
		<h5 class="mb-2 font-bold tracking-tight text-gray-900 dark:text-white text-lg">
			Languages used in this project
		</h5>
		<p class="mb-3 font-normal text-gray-700 dark:text-gray-400 text-sm">
			HTML, CSS, svelte.js, C# , Azure
		</p>
	</div>
</div>
