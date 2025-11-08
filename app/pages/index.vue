<template>
	<section
		class="min-h-[100dvh] w-full flex flex-col justify-center items-center bg-[#0b0b0d] text-center relative overflow-hidden px-6 pb-20"
	>
		<!-- Gradient spotlight background -->
		<div
			class="absolute inset-0 bg-[radial-gradient(circle_at_center,_rgba(255,215,0,0.05),_transparent_70%)]"
		></div>

		<!-- Navbar placeholder -->
		<nav
			class="absolute top-0 left-0 w-full flex justify-between items-center py-6 px-10 text-sm text-gray-300"
		>
			<div class="font-semibold text-yellow-500">404 Museum</div>
			<ul class="flex gap-6">
				<li><NuxtLink to="/">Home</NuxtLink></li>
				<li><NuxtLink to="/projects">Projects</NuxtLink></li>
				<li><NuxtLink to="/about">About</NuxtLink></li>
			</ul>
		</nav>

		<!-- Hero content -->
		<div class="relative z-10 flex flex-col items-center mt-20">
			<div
				class="text-xs uppercase tracking-widest text-yellow-400 bg-yellow-400/10 border border-yellow-400/30 rounded-full px-3 py-1 mb-6"
			>
				Made by Kaloka
			</div>

			<h1
				class="text-4xl md:text-6xl font-bold text-white leading-tight max-w-3xl"
			>
				Arsip Proyek Gagal
				<span class="text-yellow-400">yang Layak Dikenang</span>
			</h1>

			<p class="mt-5 text-gray-400 max-w-xl text-base md:text-lg">
				Tempat semua percobaan, bug, dan setengah ide yang pernah aku
				tulis —diabadikan biar gak hilang ditelan `git rm -rf`.
			</p>

			<div class="flex gap-4 mt-10">
				<NuxtLink
					to="/projects"
					class="px-6 py-3 bg-yellow-500 text-black font-semibold rounded-lg hover:bg-yellow-400 transition-all duration-300"
				>
					Lihat Koleksi
				</NuxtLink>
				<NuxtLink
					to="/about"
					class="px-6 py-3 border border-yellow-500 text-yellow-400 rounded-lg hover:bg-yellow-500/10 transition-all duration-300"
				>
					Tentang Museum
				</NuxtLink>
			</div>
		</div>

		<!-- Decorative image mock -->
		<div class="mt-20 relative z-0 w-full flex justify-center">
			<div
				class="w-[90%] md:w-[70%] bg-[#111] rounded-2xl border border-yellow-500/10 shadow-[0_0_50px_rgba(255,215,0,0.05)] overflow-hidden"
			>
				<div
					class="aspect-video flex items-center justify-center text-gray-600 text-sm"
				>
					<NuxtImg
						src="/home-img.png"
						alt="komputer tua yang berdebu"
						class="bg-cover"
					/>
				</div>
			</div>
		</div>
	</section>
</template>

<script setup>
// kosongin aja dulu
</script>
