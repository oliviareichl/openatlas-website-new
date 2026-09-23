<script setup lang="ts">
const props = defineProps<{
	label: string;
}>();

const items = [{ label: props.label ?? "Information", slot: "information" }];
</script>

<template>
	<div class="pb-4">
		<UAccordion
			class="border-b border-neutral-300"
			:items="items"
			:ui="{
				label: 'text-lg',
				content: 'pb-2',
			}"
		>
			<template #information>
				<slot />
			</template>
		</UAccordion>
	</div>
</template>
