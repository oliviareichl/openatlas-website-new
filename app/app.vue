<template>
	<NuxtLayout>
		<UApp>
			<NuxtPage />
		</UApp>
		<NuxtLoadingIndicator class="bg-neutral-950 dark:bg-white" :color="false" />
		<TailwindIndicator />
		<NuxtRouteAnnouncer />
	</NuxtLayout>
</template>
