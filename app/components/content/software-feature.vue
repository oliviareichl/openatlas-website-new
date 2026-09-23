<script setup lang="ts">
const props = defineProps<{
	logo?: string;
	image?: string;
	video?: string;
	buttonLinks?: Array<{ title: string; link: string }>;
	reverse?: boolean;
}>();
</script>

<template>
	<section
		class="py-8 group relative isolate after:absolute after:top-20 after:bottom-[-0.5rem] after:-z-10 after:rounded-3xl after:bg-black/80"
		:class="{
			'after:left-50 after:right-[-2rem]': !reverse,
			'after:left-[-2rem] after:right-50': reverse,
		}"
	>
		<div
			class="grid items-center gap-2 lg:grid-cols-2 lg:gap-15 text-white z-20"
			:class="{ 'lg:[&>*:first-child]:order-2': reverse }"
		>
			<div
				class="aspect-[4/3] overflow-hidden rounded-2xl scale-100 transition-transform duration-[1200ms] ease-out group-hover:scale-[1.05]"
			>
				<video
					v-if="props.video"
					:src="props.video"
					autoplay
					muted
					loop
					playsinline
					class="absolute inset-0 z-50 size-full object-cover rounded-3xl"
				/>

				<NuxtImg
					v-else-if="props.image"
					:src="props.image"
					:alt="props.image"
					class="absolute inset-0 z-50 object-cover size-full rounded-3xl bg-white"
				/>
			</div>

			<div class="max-w-xl pt-8">
				<NuxtImg v-if="props.logo" :src="props.logo" alt="" class="w-44" />

				<div class="[&_h2]:mt-0 [&_h2]:text-4xl pt-2">
					<slot />
				</div>

				<div
					v-if="props.buttonLinks != null && props.buttonLinks.length > 0"
					class="flex flex-row gap-4 pt-4"
				>
					<div v-for="(button, index) in buttonLinks" :key="button.title">
						<UButton
							class="border uppercase"
							:variant="index % 2 === 0 ? 'outline' : 'solid'"
							size="xl"
							:to="button.link"
							target="_blank"
							:class="[
								'font-heading text-white',
								index % 2 === 0 ? 'border' : 'bg-white text-black',
							]"
							>{{ button.title }}
						</UButton>
					</div>
				</div>
			</div>
		</div>
	</section>
</template>
