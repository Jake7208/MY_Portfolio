<script>
	const icon1 = new URL('./social/GitHub-Logo.png', import.meta.url).href;
	const icon2 = new URL('./social/slack.png', import.meta.url).href;
	const icon3 = new URL('./social/LinkedIn_Icon.png', import.meta.url).href;
	const icon4 = new URL('./social/discord-icon.png', import.meta.url).href;
</script>

<div
	class="snap-y snap-mandatory h-1/4 w-1/4 max-md:w-1/2 max-sm:w-screen overflow-scroll no-scrollbar"
>
	<div
		class="snap-start w-full h-[25vh] flex items-center justify-center text-8xl animation-scroll"
	>
		<img class="h-26 w-28" src={icon1} alt="" />
	</div>

	<div
		class="snap-start w-full h-[25vh] flex items-center justify-center text-8xl animation-scroll"
	>
		<img class="h-28 w-28" src={icon3} alt="" />
	</div>
	<div
		class="snap-start w-full h-[25vh] flex items-center justify-center text-8xl animation-scroll"
	>
		<img class="h-20 w-26" src={icon2} alt="" />
	</div>
	<div
		class="snap-start w-full h-[25vh] flex items-center justify-center text-8xl animation-scroll"
	>
		<img class="h-20 w-25" src={icon4} alt="" />
	</div>
</div>
