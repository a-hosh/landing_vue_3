<template>
	<main>
		<h1 class="text-center pb-6 text-3xl md:text-4xl lg:text-5xl font-semibold text-indigo-500">
			Newsletter
		</h1>
		<p class="text-gray-600 text-center lg:px-24">
			We'll keep you updated by email and social medias as well.
		</p>

		<section class="mt-10 md:flex flex-wrap justify-between gap-10">
			<template 
				v-for="(feed, i) in newsletters" 
				:key="i">
				<FeedList :feed="feed" />
			</template>
		</section>
	</main>
</template>

<script setup>
	import { computed } from 'vue'
	import FeedList from '@/components/FeedList.vue'
	import Newsletter from '@/newsletters.js' 

	const newsletters = computed (()=> {
		return Newsletter.sort((a, b) => {
			return (a.publishDate > b.publishDate) ? -1 : 1;
		});
	})
</script>
