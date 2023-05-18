<script>
	const icon1 = new URL('./database/mongoDB.jpg', import.meta.url).href;
	const icon2 = new URL('./database/MySQL.jpg', import.meta.url).href;
</script>

<div
	class="snap-y snap-mandatory h-1/4 w-1/4 max-md:w-1/2 max-sm:w-screen overflow-scroll no-scrollbar bg-pink-300"
>
	<div class="snap-start w-full h-[25vh] flex items-center justify-center text-8xl">
		<img class="h-20 w-25" src={icon1} alt="" />
	</div>

	<div class="snap-start w-full h-[25vh] flex items-center justify-center text-8xl">
		<img class="h-20 w-25" src={icon2} alt="" />
	</div>
</div>
