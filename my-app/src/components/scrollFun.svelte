<script>
	const icon1 = new URL('./frontend/HTML.png', import.meta.url).href;
	const icon2 = new URL('./frontend/CSS.png', import.meta.url).href;
	const icon3 = new URL('./frontend/JS.png', import.meta.url).href;
	const icon4 = new URL('./frontend/bootstrap.png', import.meta.url).href;
	const icon5 = new URL('./frontend/Tailwind.png', import.meta.url).href;
</script>

<div
	class="snap-y snap-mandatory h-screen w-1/4 max-md:w-1/2 max-sm:w-screen overflow-scroll no-scrollbar bg-orange-200"
>
	<div
		class="snap-start w-full h-[25vh] flex items-center justify-center text-4xl animation-scroll"
	>
		<h3>HTML</h3>
		<img class="h-20 w-20" src={icon1} alt="" />
	</div>
	<div
		class="snap-start w-full h-[25vh] flex items-center justify-center text-4xl animation-scroll"
	>
		<h3>CSS</h3>
		<img class="h-20 w-20" src={icon2} alt="" />
	</div>
	<div
		class="snap-start w-full h-[25vh] flex items-center justify-center text-4xl animation-scroll"
	>
		<h3>JavaScript</h3>
		<img class="h-20 w-20" src={icon3} alt="" />
	</div>
	<div
		class="snap-start w-full h-[25vh] flex items-center justify-center text-4xl animation-scroll"
	>
		<img class="h-20 w-20" src={icon4} alt="" />
	</div>
	<div
		class="snap-start w-full h-[25vh] flex items-center justify-center text-8xl animation-scroll"
	>
		<img class="h-20 w-25" src={icon5} alt="" />
	</div>
</div>
