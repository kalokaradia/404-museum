<template>
	<footer class="bg-[#0b0b0b] text-gray-400">
		<div
			class="max-w-6xl mx-auto px-6 py-12 grid grid-cols-1 md:grid-cols-3 gap-8"
		>
			<!-- Kolom 1: Branding & Deskripsi -->
			<div>
				<h2 class="text-xl font-bold text-yellow-500">404 Museum</h2>
				<p class="mt-4 text-sm">
					Arsip digital proyek-gagal developer yang layak dikenang.
					Bersama kita belajar, tertawa, dan bangkit lagi.
				</p>
			</div>
			<!-- Kolom 2: Link Cepat -->
			<div>
				<h3
					class="font-semibold text-sm text-yellow-400 uppercase tracking-wider"
				>
					Navigasi
				</h3>
				<ul class="mt-4 space-y-2 text-sm">
					<li>
						<NuxtLink to="/" class="hover:text-white"
							>Home</NuxtLink
						>
					</li>
					<li>
						<NuxtLink to="/projects" class="hover:text-white"
							>Projects</NuxtLink
						>
					</li>
					<li>
						<NuxtLink to="/about" class="hover:text-white"
							>About</NuxtLink
						>
					</li>
					<li>
						<NuxtLink
							to="mailto:kalokaradia@gmail.com"
							class="hover:text-white"
							>Contact</NuxtLink
						>
					</li>
				</ul>
			</div>
			<!-- Kolom 3: Sosial & Legal -->
			<div>
				<h3
					class="font-semibold text-sm text-yellow-400 uppercase tracking-wider"
				>
					Ikuti Kami
				</h3>
				<div class="mt-4 flex space-x-4">
					<!-- Ganti href dengan link sosial mu -->
					<NuxtLink
						to="https://x.com/kalokaradia"
						class="text-gray-400 hover:text-white"
						><span class="sr-only">Twitter</span
						><Icon
							name="uil:twitter"
							style="color: grey"
							size="24px"
					/></NuxtLink>
					<NuxtLink
						to="https://github.com/kalokaradia"
						class="text-gray-400 hover:text-white"
						><span class="sr-only">GitHub</span
						><Icon
							name="uil:github"
							style="color: grey"
							size="24px"
					/></NuxtLink>
					<NuxtLink
						to="https://instagram.com/kalokaradia"
						class="text-gray-400 hover:text-white"
						><span class="sr-only">Instagram</span
						><Icon
							name="uil:instagram"
							style="color: grey"
							size="24px"
					/></NuxtLink>
				</div>
				<p class="mt-6 text-xs text-gray-500">
					© {{ new Date().getFullYear() }} Kaloka Radia Nanda. All
					rights reserved.
				</p>
			</div>
		</div>
		<div class="border-t border-yellow-500/20 mt-8"></div>
	</footer>
</template>

<script setup>
// kosong sekarang
</script>

<style scoped>
/* Bisa tambahkan custom style jika mau efek khusus */
</style>
