<template>
	<main>
		<h1 class="text-center pb-6 text-3xl md:text-4xl lg:text-5xl font-semibold text-indigo-500">
			FAQ's
		</h1>
			<p class="text-gray-600 text-center lg:px-24">
				Answers to our most frequently asked questions can be found below
			</p>
			<section class="w-full md:w-8/12 lg:w-6/12 md:mx-auto mt-10">
				<template 
					v-for="(list, i) in FAQ" 
					:key="i">
					<FAQlist :list="list" :num="i" />
				</template>
			</section>
	</main>
</template>

<script setup>
	import FAQlist from '@/components/FAQlist.vue'
	import FAQ from '@/FAQ.js'
</script>