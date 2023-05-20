<script>
	import emailjs from '@emailjs/browser';

	function sendEmail(e) {
		emailjs.sendForm('service_xpuykgj', 'template_k3hfzym', e.target, 'eNbHiinaHtqA7lUwR').then(
			(result) => {
				console.log('SUCCESS!', result.text);
			},
			(error) => {
				console.log('FAILED. . .', error.text);
			}
		);
	}
	function scrolling() {
		let left = document.querySelector('#scroll-stuff');
		left.scrollBy(-500, 0);
	}
</script>

<section class="flex justify-center items-center bg-white dark:bg-black">
	<div class="py-8 lg:py-16 px-4 mx-auto max-w-screen-md">
		<button
			class="flex justify-start py-3 px-5 text-white hover:bg-orange-800 focus:ring-4 focus:outline-none focus:ring-orange-300 font-medium rounded-lg text-sm text-center ml-3 md:mr-0 dark:bg-orange-600 dark:hover:bg-orange-700 dark:focus:ring-orange-800 cursor-pointer transition-all hover:-translate-y-[.15rem] delay-150 duration-500 hover:animate-pulse"
			on:click={scrolling}>Back</button
		>
		<h2
			class=" text-3xl max-sm:text-lg tracking-tight font-extrabold text-center text-gray-900 dark:text-white"
		>
			Contact Me
		</h2>
		<p class=" font-light text-center text-gray-500 dark:text-gray-400 max-sm:text-lg text-xl">
			Want to send me A message? Want to offer me a job? Let me know.
		</p>
		<form class="space-y-8" on:submit={sendEmail}>
			<div>
				<label for="email" class="block mb-2 text-sm font-medium text-gray-900 dark:text-gray-300"
					>Your email</label
				>
				<input
					type="email"
					name="email"
					id="email"
					class="shadow-sm bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-orange-500 focus:border-orange-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-orange-500 dark:focus:border-orange-500 dark:shadow-sm-light"
					placeholder="name@gmail.com"
					required
				/>
			</div>
			<div>
				<label for="Name" class="block mb-2 text-sm font-medium text-gray-900 dark:text-gray-300"
					>Your name</label
				>
				<input
					type="text"
					name="from_name"
					class="shadow-sm bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-orange-500 focus:border-orange-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-orange-500 dark:focus:border-orange-500 dark:shadow-sm-light"
					placeholder="First name"
					required
				/>
			</div>

			<label for="subject" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white"
				>Select Reason For Contact</label
			>
			<select
				name="subject"
				id="subject"
				required
				class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
			>
				<option>Collaboration</option>
				<option>Job Offer</option>
				<option>Projects</option>
				<option>Networking</option>
				<option>Other</option>
			</select>

			<div class="sm:col-span-2">
				<label for="message" class="block mb-2 text-sm font-medium text-gray-900 dark:text-gray-400"
					>Your message</label
				>
				<textarea
					name="message"
					id="message"
					rows="6"
					class="block p-2.5 w-full text-sm text-gray-900 bg-gray-50 rounded-lg shadow-sm border border-gray-300 focus:ring-orange-500 focus:border-orange-500 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-orange-500 dark:focus:border-orange-500"
					placeholder="Leave a comment..."
				/>
			</div>

			<button
				type="submit"
				value="Send"
				class="py-3 px-5 text-sm font-medium text-center text-white rounded-lg bg-orange-700 sm:w-fit hover:bg-orange-800 focus:ring-4 focus:outline-none focus:ring-orange-300 dark:bg-orange-600 dark:hover:bg-orange-700 dark:focus:ring-orange-800"
				>Send message</button
			>
		</form>
	</div>
</section>
<!-- name="email"
name="from_name" -->
<!-- value="Send"  -->
