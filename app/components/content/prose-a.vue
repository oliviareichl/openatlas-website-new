<script setup lang="ts">
const { href } = defineProps<{
	href?: string;
}>();
</script>

<template>
	<a
		class="text-primary border-b border-transparent hover:border-primary font-medium rounded-xs outline-primary/25 focus-visible:outline-3 focus-visible:has-[>code]:outline-0 [&>code]:border-dashed [&>code]:outline-primary/25 focus-visible:[&>code]:outline-3 hover:[&>code]:border-primary hover:[&>code]:text-primary focus-visible:[&>code]:border-primary focus-visible:[&>code]:text-primary transition-colors [&>code]:transition-colors"
		:href="href"
		:target="href?.startsWith('https') ? '_blank' : undefined"
		:rel="href?.startsWith('https') ? 'noopener noreferrer' : undefined"
	>
		<slot />
	</a>
</template>
