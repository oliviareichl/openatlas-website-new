<script lang="ts" setup>
import type { NuxtLinkProps } from "#app";

const t = useTranslations();

const links = computed(() => {
	return {
		about: { href: { path: "/" }, label: t("AppHeader.links.about") },
		cooperations: { href: { path: "/cooperations" }, label: t("AppHeader.links.cooperations") },
		team: { href: { path: "/team" }, label: t("AppHeader.links.team") },
		events: { href: { path: "/events" }, label: t("AppHeader.links.events") },
		news: { href: { path: "/news" }, label: t("AppFooter.links.news") },
		publications: { href: { path: "/publications" }, label: t("AppHeader.links.publications") },
		"work with us": { href: { path: "/work-with-us" }, label: t("AppHeader.links.work") },
	} satisfies Record<string, { href: NuxtLinkProps["href"]; label: string }>;
});
</script>

<template>
	<header>
		<div class="container flex items-center justify-between gap-4 py-4">
			<NuxtLink :href="links.about.href">
				<NuxtImg
					alt=""
					class="block object-contain"
					preload
					src="/assets/images/logo-without-text.png"
				/>
			</NuxtLink>
			<nav :aria-label="t('AppHeader.navigation-main')">
				<ul class="flex items-center gap-4" role="list">
					<li v-for="(link, key) of links" :key="key">
						<NuxtLinkLocale
							class="font-heading opacity-80 transition-opacity hover:opacity-100 focus-visible:opacity-100 aria-[current]:opacity-100"
							:href="link.href"
						>
							{{ link.label }}
						</NuxtLinkLocale>
					</li>
					<li>
						<NuxtLink target="_blank" href="https://github.com/craws/OpenAtlas">
							<NuxtImg
								alt=""
								preload
								class="size-7"
								src="/assets/images/GitHub_Invertocat_Black.png"
							>
							</NuxtImg>
							<span class="sr-only">Link to Github</span>
						</NuxtLink>
					</li>
				</ul>
			</nav>

			<!-- <div class="flex items-center gap-4">
				<ColorSchemeSwitcher />
			</div> -->
		</div>
	</header>
</template>
