<template>
	<section
		v-if="project"
		class="min-h-[100dvh] w-full flex flex-col justify-center bg-gradient-to-b from-[#0a0a0a] to-[#141414] text-gray-200 relative overflow-hidden"
	>
		<!-- Subtle Glow Background -->
		<div
			class="absolute inset-0 bg-[radial-gradient(circle_at_center,_rgba(255,215,0,0.05),_transparent_70%)] pointer-events-none"
		></div>

		<!-- Content -->
		<div class="relative z-10 px-6 md:px-16 py-24 max-w-4xl mx-auto">
			<!-- Title -->
			<h1
				class="text-5xl md:text-7xl font-extrabold mb-4 text-transparent bg-clip-text bg-gradient-to-r from-yellow-400 to-amber-500 drop-shadow-[0_0_10px_rgba(255,215,0,0.3)]"
			>
				{{ project.title }}
			</h1>

			<!-- Year -->
			<p class="text-sm text-gray-500 mb-10 uppercase tracking-widest">
				{{ project.year || "Tanpa Tahun" }}
			</p>

			<!-- Image -->
			<div
				v-if="project.image"
				class="mb-12 rounded-3xl overflow-hidden shadow-[0_0_25px_rgba(255,215,0,0.15)] border border-amber-900/30"
			>
				<img
					:src="project.image"
					:alt="project.title"
					class="w-full h-auto object-cover hover:scale-[1.02] transition-transform duration-500 ease-out"
				/>
			</div>

			<!-- Description -->
			<p class="text-lg text-gray-300 leading-relaxed mb-10">
				{{ project.description }}
			</p>

			<!-- Content (HTML-rendered) -->
			<div
				v-html="project.content"
				class="prose prose-invert prose-amber max-w-none mb-16"
			></div>

			<!-- Status Badge -->
			<div
				class="inline-block px-4 py-1 rounded-full text-sm font-semibold mb-10"
				:class="{
					'bg-yellow-500/10 text-yellow-400 border border-yellow-400/30':
						project.status === 'unfinished',
					'bg-red-500/10 text-red-400 border border-red-400/30':
						project.status === 'abandoned',
					'bg-green-500/10 text-green-400 border border-green-400/30':
						project.status === 'completed',
				}"
			>
				{{ project.status }}
			</div>

			<!-- Divider -->
			<div
				class="w-24 h-[2px] bg-gradient-to-r from-transparent via-yellow-400 to-transparent opacity-60 mb-12"
			></div>

			<!-- Back link -->
			<NuxtLink
				to="/projects"
				class="inline-flex items-center gap-2 text-yellow-400 font-semibold hover:text-yellow-300 transition-all"
			>
				<svg
					xmlns="http://www.w3.org/2000/svg"
					class="w-4 h-4"
					fill="none"
					viewBox="0 0 24 24"
					stroke="currentColor"
				>
					<path
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="2"
						d="M15 19l-7-7 7-7"
					/>
				</svg>
				Kembali ke daftar proyek
			</NuxtLink>
		</div>
	</section>

	<!-- Loading / Not Found -->
	<section
		v-else
		class="flex items-center justify-center min-h-[100dvh] text-gray-500 bg-[#0b0b0b]"
	>
		<p>Proyek tidak ditemukan.</p>
	</section>
</template>

<script setup lang="ts">
import { useRoute } from "vue-router";
import { ref, onMounted } from "vue";

const route = useRoute();
const slug = route.params.slug as string;

const project = ref<any>(null);

onMounted(async () => {
	try {
		const res = await $fetch("/api/projects");
		project.value = res.find((p: any) => p.slug === slug);
	} catch (err) {
		console.error("Gagal memuat proyek:", err);
	}
});
</script>

<style scoped>
.prose p {
	margin-bottom: 1rem;
}
.prose a {
	color: #fbbf24;
	text-decoration: none;
}
.prose a:hover {
	text-decoration: underline;
}
</style>
