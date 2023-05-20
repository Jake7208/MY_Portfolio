<div
	class="flex flex-col rounded-lg bg-white shadow-[0_2px_15px_-3px_rgba(0,0,0,0.07),0_10px_20px_-2px_rgba(0,0,0,0.04)] dark:bg-neutral-700 md:max-w-xl md:flex-row"
>
	<slot />
	<div class="flex flex-col justify-start p-6">
		<h5 class="mb-2 text-xl font-medium text-neutral-800 dark:text-neutral-50">Card title</h5>

		<span class="flex items-center text-sm font-medium text-gray-900 dark:text-white"
			><span class="flex w-2.5 h-2.5 bg-orange-600 rounded-full mr-1.5 flex-shrink-0" />HTML</span
		>
		<span class="flex items-center text-sm font-medium text-gray-900 dark:text-white"
			><span class="flex w-2.5 h-2.5 bg-blue-600 rounded-full mr-1.5 flex-shrink-0" />CSS</span
		>
		<span class="flex items-center text-sm font-medium text-gray-900 dark:text-white"
			><span
				class="flex w-2.5 h-2.5 bg-indigo-600 rounded-full mr-1.5 flex-shrink-0"
			/>bootstrap</span
		>
	</div>
</div>
