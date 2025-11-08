<template>
	<section
		class="min-h-screen bg-[#0b0b0d] text-gray-300 py-20 px-6 md:px-12"
	>
		<!-- Header -->
		<div class="text-center mb-14">
			<h1
				class="text-4xl md:text-5xl font-extrabold text-transparent bg-clip-text bg-gradient-to-r from-yellow-400 to-yellow-600 pb-3"
			>
				Pameran Kegagalan
			</h1>
			<p class="text-gray-500 mt-3">
				Setiap proyek gagal punya kisah. Mari kita dengarkan.
			</p>
		</div>

		<!-- Filter Section -->
		<div
			class="flex flex-col md:flex-row gap-4 items-center justify-between mb-10 bg-[#111] p-4 rounded-2xl border border-[#2a2a2a]"
		>
			<input
				v-model="search"
				type="text"
				placeholder="Cari proyek..."
				class="w-full md:w-1/3 px-4 py-2 bg-[#1a1a1a] text-gray-200 rounded-lg outline-none focus:ring-2 focus:ring-yellow-500"
			/>
			<select
				v-model="statusFilter"
				class="w-full md:w-1/5 px-4 py-2 bg-[#1a1a1a] text-gray-200 rounded-lg outline-none focus:ring-2 focus:ring-yellow-500"
			>
				<option value="">Semua Status</option>
				<option value="abandoned">Abandoned</option>
				<option value="unfinished">Unfinished</option>
				<option value="complete">Completed (Ugly)</option>
			</select>
		</div>

		<!-- Content State -->
		<div v-if="pending" class="text-center py-20 text-gray-500">
			<span class="animate-pulse">Menggali arsip digital...</span>
		</div>

		<div v-else-if="error" class="text-center py-20 text-red-500">
			Gagal memuat data. Coba lagi nanti.
		</div>

		<div v-else>
			<!-- Empty State -->
			<div
				v-if="filteredProjects.length === 0"
				class="text-center py-20 text-gray-500"
			>
				<img
					src="https://cdn-icons-png.flaticon.com/512/7486/7486716.png"
					alt="empty"
					class="w-24 h-24 mx-auto mb-4 opacity-50"
				/>
				<p>Belum ada proyek yang cocok dengan filter.</p>
			</div>

			<!-- Grid Projects -->
			<div
				v-else
				class="grid gap-8 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4"
			>
				<article
					v-for="proj in filteredProjects"
					:key="proj.id"
					class="group bg-[#121212] border border-[#2a2a2a] rounded-2xl overflow-hidden hover:border-yellow-500 transition-all duration-300"
				>
					<div class="relative h-48 overflow-hidden">
						<img
							:src="proj.image || defaultImage"
							:alt="proj.title"
							class="object-cover w-full h-full group-hover:scale-105 transition-transform duration-500"
						/>
						<div
							class="absolute inset-0 bg-gradient-to-t from-[#0b0b0d]/70 to-transparent"
						></div>
					</div>
					<div class="p-5">
						<h2
							class="text-lg font-semibold text-yellow-400 group-hover:text-yellow-300 transition"
						>
							{{ proj.title }}
						</h2>
						<p class="text-sm text-gray-400 mt-1 line-clamp-2">
							{{ proj.description }}
						</p>

						<div class="flex justify-between items-center mt-4">
							<span
								class="text-xs uppercase px-2 py-1 rounded-full"
								:class="statusColor(proj.status)"
							>
								{{ proj.status }}
							</span>
							<NuxtLink
								:to="`/projects/${proj.slug}`"
								class="text-xs text-yellow-500 hover:text-yellow-300 transition"
								>Lihat Detail</NuxtLink
							>
						</div>
					</div>
				</article>
			</div>
		</div>
	</section>
</template>

<script setup>
import { ref, computed } from "vue";

const { data: projects, pending, error } = await useFetch("/api/projects");

const search = ref("");
const statusFilter = ref("");

const defaultImage = "https://cdn-icons-png.flaticon.com/512/1048/1048953.png";

const filteredProjects = computed(() => {
	if (!projects.value) return [];
	return projects.value.filter(
		(p) =>
			p.title.toLowerCase().includes(search.value.toLowerCase()) &&
			(statusFilter.value === "" || p.status === statusFilter.value)
	);
});

function statusColor(status) {
	switch (status) {
		case "abandoned":
			return "bg-red-900/50 text-red-400";
		case "unfinished":
			return "bg-yellow-900/40 text-yellow-400";
		case "complete":
			return "bg-green-900/40 text-green-400";
		default:
			return "bg-gray-800 text-gray-400";
	}
}
</script>

<style scoped>
.line-clamp-2 {
	display: -webkit-box;
	-webkit-line-clamp: 2;
	-webkit-box-orient: vertical;
	overflow: hidden;
}
</style>
