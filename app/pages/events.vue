<script setup lang="ts">
const route = useRoute();

const contentPath = computed(() => {
	if (route.path === "/") {
		return "/";
	}

	return route.path;
});

const { data: content } = await useAsyncData(
	() => `content-${contentPath.value}`,
	() => queryCollection("pages").path(`/pages${contentPath.value}`).first(),
);
</script>

<template>
	<MainContent class="container grid content-start py-8">
		<div class="prose-events">
			<ContentRenderer v-if="content?.body" :value="content.body"> </ContentRenderer>
		</div>
	</MainContent>
</template>
