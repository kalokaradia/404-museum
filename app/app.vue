<script setup lang="ts">
import { Analytics } from "@vercel/analytics/nuxt";
const site = {
	title: "404 Museum - The Archive of Lost Codes by Kaloka Radia Nanda",
	description:
		"404 Museum adalah arsip digital karya eksperimental, framework gagal, dan ide-ide yang hilang di perjalanan kreatif Kaloka Radia Nanda. Dari Radian.js hingga Templite, semuanya tersimpan di sini.",
	url: "https://yourdomain.com",
	image: "https://yourdomain.com/og-image.png",
};
</script>

<template>
	<Analytics />
	<Head class="scroll-smooth">
		<!-- Basic SEO -->
		<Title>{{ site.title }}</Title>
		<Meta name="description" :content="site.description" />
		<Meta
			name="keywords"
			content="Kaloka Radia Nanda, 404 Museum, coding project, lost code, unfinished projects, abandoned frameworks, Radian.js, Purworejo Coding, web development, creative coding, museum digital, arsip proyek, experimental JavaScript, frontend micro framework"
		/>
		<Meta name="author" content="Kaloka Radia Nanda" />
		<Meta
			name="robots"
			content="index, follow, max-snippet:-1, max-image-preview:large, max-video-preview:-1"
		/>
		<Meta name="theme-color" content="#FFD400" />
		<Meta name="charset" content="utf-8" />
		<Meta name="viewport" content="width=device-width, initial-scale=1.0" />
		<Meta name="application-name" content="404 Museum" />
		<Meta
			name="category"
			content="Personal Portfolio, Web Development, Creative Archive"
		/>
		<Meta name="rating" content="general" />
		<Meta name="revisit-after" content="7 days" />
		<Meta name="referrer" content="no-referrer-when-downgrade" />
		<Link rel="canonical" :href="site.url" />

		<!-- Open Graph -->
		<Meta property="og:type" content="website" />
		<Meta property="og:title" :content="site.title" />
		<Meta property="og:description" :content="site.description" />
		<Meta property="og:image" :content="site.image" />
		<Meta property="og:url" :content="site.url" />
		<Meta property="og:site_name" content="404 Museum" />
		<Meta property="og:locale" content="id_ID" />
		<Meta property="og:image:width" content="1200" />
		<Meta property="og:image:height" content="630" />
		<Meta
			property="og:image:alt"
			content="Logo 404 Museum – Arsip Proyek Kegagalan"
		/>

		<!-- Twitter -->
		<Meta name="twitter:card" content="summary_large_image" />
		<Meta name="twitter:title" :content="site.title" />
		<Meta name="twitter:description" :content="site.description" />
		<Meta name="twitter:image" :content="site.image" />
		<Meta name="twitter:creator" content="@kaloka" />
	</Head>

	<NuxtPage />
	<FooterComp />
</template>

<style>
body {
	font-family: "Poppins", sans-serif;
	scrollbar-width: thin; /* Firefox */
	scrollbar-color: #facc15 #111; /* Warna thumb dan track */
}

/* Chrome, Edge, dan Safari */
::-webkit-scrollbar {
	width: 10px;
	height: 10px;
}

::-webkit-scrollbar-track {
	background: #111; /* warna dasar track */
}

::-webkit-scrollbar-thumb {
	background: linear-gradient(to bottom, #facc15, #b8860b);
	border-radius: 10px;
	border: 2px solid #111;
	transition: background 0.3s;
}

::-webkit-scrollbar-thumb:hover {
	background: linear-gradient(to bottom, #ffdb4d, #c79a00);
}
</style>
