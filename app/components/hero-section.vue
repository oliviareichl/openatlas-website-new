<script setup lang="ts">
const props = defineProps<{
	title: string;
	subtitle: string;
	buttonLinks: Array<{ title: string; link: string }>;
	newsDate: string;
	currentVersion: string;
	images: Array<{ src: string; alt?: string | undefined }>;
}>();
</script>

<template>
	<div class="grid grid-cols-2 gap-5">
		<div class="flex flex-col gap-4">
			<h1 class="font-heading text-black font-medium text-[2.5rem]/12">{{ props.title }}</h1>
			<span class="text-lg">{{ props.subtitle }}</span>
			<div class="flex flex-row gap-4">
				<UButton
					color="neutral"
					class="border uppercase"
					variant="outline"
					size="xl"
					:to="props.buttonLinks[0]?.link"
					target="_blank"
					>{{ props.buttonLinks[0]?.title }}</UButton
				>
				<UButton
					color="neutral"
					class="uppercase"
					size="xl"
					:to="props.buttonLinks[1]?.link"
					target="_blank"
					>{{ props.buttonLinks[1]?.title }}</UButton
				>
				<UButton
					color="neutral"
					class="border uppercase"
					variant="outline"
					size="xl"
					:to="props.buttonLinks[2]?.link"
					target="_blank"
				>
					{{ props.buttonLinks[2]?.title }}</UButton
				>
			</div>
			<NuxtImg
				:alt="props.images[1]?.alt"
				class="block object-contain my-7"
				preload
				:src="props.images[1]?.src"
			/>

			<div>
				<div class="flex flex-row items-center gap-2 mb-2">
					<UBadge size="xl" lass="bg-secondary">News</UBadge>
					<span>{{ props.newsDate }}</span>
				</div>
				<div class="flex flex-row gap-1.5 items-end">
					<span>OpenAtlas version</span>
					<span>{{ props.currentVersion }}</span>
					<NuxtLink
						class="text-sm text-primary opacity-80 font-semibold hover:opacity-100 transition"
						href="/news"
						target="_blank"
						>read more</NuxtLink
					>
				</div>
			</div>
		</div>
		<NuxtImg
			:alt="props.images[0]?.alt"
			class="block object-contain w-600"
			preload
			:src="props.images[0]?.src"
		/>
	</div>
</template>
