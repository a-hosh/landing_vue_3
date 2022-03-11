<template>
	<main>
		<h1 class="text-center pb-6 text-3xl md:text-4xl lg:text-5xl font-semibold text-indigo-500">
			Sessions
		</h1>
		<section class="mt-10 md:flex flex-wrap justify-between gap-5">
			<template 
				v-for="(event, i) in events" 
				:key="i">
				<div class="md:w-5/12 mb-8 md:mb-0">
					<span class="text-xl text-purple-700 font-medium leading-snug">
						<span class="border-b-2 border-purple-700">
							{{ i + 1 }}.
						</span>
						{{ event.title }}
					</span>
					<p class="my-4">
						{{ event.content }}
					</p>
				</div>
			</template>
		</section>

		<section class="mt-12">
			<p class="text-indigo-500 font-semibold text-xl lg:text-2xl md:text-center mb-5">
				Key Speakers
			</p>
			<div class="md:flex justify-evenly gap-6">
				<template 
					v-for="(speaker, i) in speakers" 
					:key="i">
					<CardProfile :profile="speaker" />
				</template>
			</div>
		</section>
	</main>
</template>

<script setup>
	import events from '@/events.js'
	import speakers from '@/speakers.js'
	import CardProfile from '@/components/CardProfile.vue'
</script>