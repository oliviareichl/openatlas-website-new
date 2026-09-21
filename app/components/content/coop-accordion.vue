<script setup lang="ts">
const props = defineProps<{
	label: string;
}>();

const items = [{ label: props.label ?? "Information", slot: "information" }];
</script>

<template>
	<UAccordion
		:items="items"
		:ui="{
			label: 'text-lg',
		}"
	>
		<template #information>
			<slot />
		</template>
	</UAccordion>
</template>
