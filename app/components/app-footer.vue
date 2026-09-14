<script lang="ts" setup>
import { MailIcon } from "@lucide/vue";

import type { NuxtLinkProps } from "#app";

const t = useTranslations();

const contentLinks = computed(() => {
	return {
		about: { href: { path: "/" }, label: t("AppFooter.links.about") },
		cooperations: { href: { path: "/cooperations" }, label: t("AppFooter.links.cooperations") },
		team: { href: { path: "/team" }, label: t("AppFooter.links.team") },
		events: { href: { path: "/events" }, label: t("AppFooter.links.events") },
		"work with us": { href: { path: "/work-with-us" }, label: t("AppFooter.links.work") },
		publications: { href: { path: "/publications" }, label: t("AppFooter.links.publications") },
		news: { href: { path: "/news" }, label: t("AppFooter.links.news") },
		software: { href: { path: "/software" }, label: t("AppFooter.links.software") },
		mission: { href: { path: "/mission-statement" }, label: t("AppFooter.links.mission") },
	} satisfies Record<string, { href: NuxtLinkProps["href"]; label: string }>;
});
const documentationLinks = computed(() => {
	return {
		features: {
			href: { path: "https://manual.openatlas.eu/features.html" },
			label: t("AppFooter.links.features"),
		},
		manual: { href: { path: "https://manual.openatlas.eu/" }, label: t("AppFooter.links.manual") },
		redmine: {
			href: { path: "https://redmine.openatlas.eu/projects/uni/wiki" },
			label: t("AppFooter.links.redmine"),
		},
		model: {
			href: { path: "https://demo.openatlas.eu/overview/model" },
			label: t("AppFooter.links.model"),
		},
		code: {
			href: { path: "https://github.com/craws/OpenAtlas" },
			label: t("AppFooter.links.code"),
		},
	} satisfies Record<string, { href: NuxtLinkProps["href"]; label: string }>;
});

const demoLinks = computed(() => {
	return {
		demo: { href: { path: "https://demo.openatlas.eu/" }, label: t("AppFooter.links.demo") },
		development: {
			href: { path: "https://demo-dev.openatlas.eu/" },
			label: t("AppFooter.links.development"),
		},
	} satisfies Record<string, { href: NuxtLinkProps["href"]; label: string }>;
});
</script>

<template>
	<footer class="bg-black text-white font-heading">
		<div class="container py-8 w-full">
			<nav :aria-label="t('AppFooter.navigation-secondary')">
				<div class="grid grid-cols-[auto_auto_auto_1fr] gap-40 max-w-full">
					<div class="grid grid-rows-[auto_1fr] gap-4">
						<span class="font-medium">Content</span>
						<ul class="flex flex-col gap-2" role="list">
							<li v-for="(link, key) of contentLinks" :key="key">
								<NuxtLink
									class="font-heading opacity-80 transition-opacity hover:opacity-100 focus-visible:opacity-100 aria-[current]:opacity-100"
									:href="link.href"
								>
									{{ link.label }}
								</NuxtLink>
							</li>
						</ul>
					</div>
					<div class="grid grid-rows-[auto_1fr] gap-4">
						<span clasS="font-medium">Documentation</span>
						<ul class="flex flex-col gap-2" role="list">
							<li v-for="(link, key) of documentationLinks" :key="key">
								<NuxtLink
									class="font-heading opacity-80 transition-opacity hover:opacity-100 focus-visible:opacity-100 aria-[current]:opacity-100"
									:href="link.href"
									external
									target="_blank"
								>
									{{ link.label }}
								</NuxtLink>
							</li>
						</ul>
					</div>
					<div class="grid grid-rows-[auto_1fr] gap-4">
						<span class="font-medium">Demo Version</span>
						<ul class="flex flex-col gap-2" role="list">
							<li v-for="(link, key) of demoLinks" :key="key">
								<NuxtLink
									class="font-heading opacity-80 transition-opacity hover:opacity-100 focus-visible:opacity-100 aria-[current]:opacity-100"
									:href="link.href"
									external
									target="_blank"
								>
									{{ link.label }}
								</NuxtLink>
							</li>
						</ul>
					</div>
					<div class="grid grid-rows-[auto_1fr] gap-4 ml-auto">
						<NuxtLink :href="contentLinks.about.href">
							<NuxtImg
								alt=""
								class="block object-contain w-50"
								preload
								src="/assets/images/oad-logo-dark.png"
							/>
						</NuxtLink>
						<ul class="flex flex-col gap-2" role="list">
							<li>
								<a
									href="mailto:openatlas@oeaw.ac.at"
									class="cursor-pointer font-heading opacity-80 transition-opacity hover:opacity-100 focus-visible:opacity-100 aria-[current]:font-medium aria-[current]:opacity-100"
								>
									<div class="flex flex-row items-center gap-1">
										<MailIcon :size="16" />
										<span>openatlas.oeaw.ac.at</span>
									</div>
								</a>
							</li>
							<li>
								<NuxtLink
									class="font-heading opacity-80 transition-opacity hover:opacity-100 focus-visible:opacity-100 aria-[current]:font-medium aria-[current]:opacity-100"
									href="/imprint"
								>
									{{ t("AppFooter.links.imprint") }}
								</NuxtLink>
							</li>
						</ul>
					</div>
				</div>
			</nav>
		</div>
	</footer>
</template>
