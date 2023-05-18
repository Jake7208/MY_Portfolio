<script>
	const imgUrl = new URL('./me.png', import.meta.url).href;
	function scrollingR() {
		let right = document.querySelector('#scroll-stuff');
		right.scrollBy(500, 0);
	}
</script>

<div class="grid grid-cols-1 md:grid-cols-2 max-sm:grid-cols-1p-10 bg-black text-white h-auto">
	<div>
		<img
			class="object-contain h-auto w-full md:max-h-[80vh] md:w-96 black-and-white-filter ml-[7rem] max-sm:hidden max-md:hidden max-lg:hidden"
			src={imgUrl}
			alt=""
		/>
	</div>
	<div class="flex flex-col justify-center items-center">
		<!-- Added 'items-center' class -->
		<h2 class="font-bold text-4xl max-md:text-2xl max-sm:text-xl mb-6">
			Hi, I'm <span class="text-[#FC7823]">Jacob Price</span>
		</h2>
		<p class="text-lg max-md:text-md max-sm:text-sm">
			I'm a <span class="text-[#FC7823] font-bold">Full Stack Developer</span> experienced in
			MongoDB, Node.js, and Express. I recently
			<span class="text-[#FC7823] font-bold">graduated from Bridgerland Technical College,</span>
			where I honed my coding skills and developed a passion for creating innovative web applications.
			Throughout my education, I gained hands-on experience in building dynamic and user-friendly websites.
			Collaboration has played a crucial role in my growth as a developer. Thriving in team environments,
			I bring exceptional communication skills to group projects. Working alongside talented individuals
			has not only enhanced my technical abilities but also sharpened my problem-solving capabilities.
			My commitment to quality coding practices and attention to detail ensures the delivery of clean
			and efficient code. I stay up-to-date with the latest advancements in web development to deliver
			cutting-edge solutions. Every project presents an opportunity for growth and creativity, and I
			am eager to embark on new ventures. Please take a moment to explore my portfolio, and feel free
			to reach out with any questions or potential collaborations. Let's join forces and build something
			extraordinary together!
		</p>

		<button
			class="w-56 text-white bg-black hover:bg-orange-800 focus:ring-4 focus:outline-none focus:ring-orange-300 font-medium rounded-lg text-sm px-4 py-2 text-center md:mr-0 dark:bg-orange-600 dark:hover:bg-orange-700 dark:focus:ring-orange-800 cursor-pointer transition-all hover:-translate-y-[.15rem] delay-150 duration-500 hover:animate-pulse mt-4 justify-center align-middle"
			on:click={scrollingR}>Contact Me</button
		>
	</div>
</div>

<style>
	.black-and-white-filter {
		filter: grayscale(100%);
	}
</style>
