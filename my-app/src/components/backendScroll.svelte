<script>
	const icon1 = new URL('./backend/CSharp.png', import.meta.url).href;
	const icon2 = new URL('./backend/jwt.jpg', import.meta.url).href;
	const icon3 = new URL('./backend/node.png', import.meta.url).href;
	const icon4 = new URL('./backend/php.png', import.meta.url).href;
	const icon5 = new URL('./backend/Rest.png', import.meta.url).href;
</script>

<div
	class="snap-y snap-mandatory h-1/4 w-1/4 max-md:w-1/2 max-sm:w-screen overflow-scroll no-scrollbar bg-indigo-300"
>
	<div class="snap-start w-full h-[25vh] flex items-center justify-center text-8xl">
		<img class="h-20 w-20" src={icon1} alt="" />
	</div>

	<div class="snap-start w-full h-[25vh] flex items-center justify-center text-8xl">
		<img class="h-20 w-25" src={icon3} alt="" />
	</div>
	<div class="snap-start w-full h-[25vh] flex items-center justify-center text-8xl">
		<img class="h-20 w-25" src={icon2} alt="" />
	</div>
	<div class="snap-start w-full h-[25vh] flex items-center justify-center text-8xl">
		<img class="h-20 w-25" src={icon4} alt="" />
	</div>
	<div class="snap-start w-full h-[25vh] flex items-center justify-center text-8xl">
		<img class="h-20 w-25" src={icon5} alt="" />
	</div>
</div>
