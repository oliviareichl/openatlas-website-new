<script setup lang="ts">
import ProjectCard from "@/components/project-card.vue";
import SoftwareCard from "@/components/software-card.vue";
const route = useRoute();

const contentPath = computed(() => {
	if (route.path === "/") {
		return "/";
	}

	return route.path;
});

const { data: projects } = await useAsyncData(
	() => `content-${contentPath.value}`,
	() => queryCollection("projects").all(),
);

const selectedStatus = ref<string[]>([]);
const selectedDomains = ref<string[]>([]);

const statusTags = computed(() => {
	if (!projects.value) return [];

	return [...new Set(projects.value.flatMap((project) => project.statusTags ?? []))].sort();
});

const domainTags = computed(() => {
	if (!projects.value) return [];

	return [...new Set(projects.value.flatMap((project) => project.domainTags ?? []))].sort();
});

const filteredProjects = computed(() => {
	if (!projects.value) return [];

	return projects.value
		.filter((project) => {
			const statusMatch =
				selectedStatus.value.length === 0 ||
				selectedStatus.value.every((tag) => project.statusTags?.includes(tag));

			const domainMatch =
				selectedDomains.value.length === 0 ||
				selectedDomains.value.every((tag) => project.domainTags?.includes(tag));

			return statusMatch && domainMatch;
		})
		.sort((a, b) => {
			const aOngoing = a.yearEnd === "ongoing";
			const bOngoing = b.yearEnd === "ongoing";

			// Ongoing projects first
			if (aOngoing && !bOngoing) return -1;
			if (!aOngoing && bOngoing) return 1;

			// Both ongoing → compare start year
			if (aOngoing && bOngoing) {
				return Number(b.yearStart) - Number(a.yearStart);
			}

			// Both finished → compare end year
			return Number(b.yearEnd) - Number(a.yearEnd);
		});
});

function toggleStatus(tag: string) {
	const index = selectedStatus.value.indexOf(tag);

	if (index === -1) {
		selectedStatus.value.push(tag);
	} else {
		selectedStatus.value.splice(index, 1);
	}
}

function toggleDomain(tag: string) {
	const index = selectedDomains.value.indexOf(tag);

	if (index === -1) {
		selectedDomains.value.push(tag);
	} else {
		selectedDomains.value.splice(index, 1);
	}
}
</script>
<template>
	<MainContent class="container grid content-start gap-y-8 py-8">
		<h1 class="font-heading text-4xl font-medium pb-5 border-b border-neutral-300">
			Cooperations & Projects
		</h1>
		<div class="font-heading">
			Listed below you can find projects from different fields of the humanities that used or are
			currently using OpenAtlas for their research. These projects cooperate closely with the
			OpenAtlas team. Their requirements and requested features were and are implemented within the
			main development of the software.
		</div>

		<div class="font-semibold mb-2">Status</div>

		<div class="flex flex-wrap gap-2 mb-4">
			<UBadge
				v-for="tag in statusTags"
				:key="tag"
				size="lg"
				class="cursor-pointer uppercase"
				:color="selectedStatus.includes(tag) ? 'primary' : 'neutral'"
				@click="toggleStatus(tag)"
			>
				{{ tag }}
			</UBadge>
		</div>

		<div class="font-semibold mb-2">Domain</div>

		<div class="flex flex-wrap gap-2 mb-6">
			<UBadge
				v-for="tag in domainTags"
				:key="tag"
				size="lg"
				class="cursor-pointer uppercase"
				:color="selectedDomains.includes(tag) ? 'primary' : 'neutral'"
				@click="toggleDomain(tag)"
			>
				{{ tag }}
			</UBadge>
		</div>
		<div v-if="projects != null && projects.length > 0">
			<ProjectCard
				v-for="item in filteredProjects"
				:project="item"
				:selected-status="selectedStatus"
				:selected-domains="selectedDomains"
				:key="item.id"
				class="mb-7"
			></ProjectCard>
		</div>
	</MainContent>
</template>
