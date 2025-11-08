<template>
	<section
		class="min-h-[100dvh] w-full bg-gradient-to-b from-[#0a0a0a] to-[#141414] text-gray-200 flex flex-col justify-center items-center px-6 md:px-16 py-24 relative overflow-hidden"
	>
		<!-- Background Glow -->
		<div
			class="absolute inset-0 bg-[radial-gradient(circle_at_center,_rgba(255,215,0,0.05),_transparent_70%)] pointer-events-none"
		></div>

		<!-- Content -->
		<div class="relative z-10 max-w-4xl text-center">
			<!-- Title -->
			<h1
				class="text-5xl md:text-7xl font-extrabold text-transparent bg-clip-text bg-gradient-to-r from-yellow-400 to-amber-500 pb-4 mb-8 drop-shadow-[0_0_10px_rgba(255,215,0,0.3)]"
			>
				Tentang 404 Museum
			</h1>

			<!-- Subtext -->
			<p
				class="text-lg text-gray-400 leading-relaxed max-w-2xl mx-auto mb-10"
			>
				Sebuah ruang digital tempat proyek-proyek gagal disimpan, bukan
				untuk disesali — tapi untuk dirayakan. Karena setiap error
				adalah bagian dari evolusi logika dan ambisi.
			</p>

			<!-- Divider -->
			<div
				class="w-32 h-[2px] bg-gradient-to-r from-transparent via-yellow-400 to-transparent opacity-60 mx-auto mb-10"
			></div>

			<!-- Core Message -->
			<div
				class="text-gray-300 text-base leading-relaxed space-y-6 max-w-3xl mx-auto"
			>
				<p>
					Setiap developer punya tumpukan folder proyek gagal yang tak
					pernah melihat dunia. Di
					<span class="text-yellow-400 font-semibold">404 Museum</span
					>, folder itu kami buka, diberi cahaya, dan dijadikan arsip
					kehormatan.
				</p>

				<p>
					Tujuannya sederhana: mengingat bahwa kegagalan bukan aib,
					tapi bukti bahwa kita pernah mencoba membangun sesuatu.
					Bahkan kalau hasilnya cuma error dan commit “fix: maybe
					works now”.
				</p>

				<p>
					Museum ini adalah tempat untuk menertawakan masa lalu sambil
					bersiap menulis baris kode berikutnya. Jangan takut menambah
					koleksi — mungkin nanti proyek gagalmu justru jadi karya
					paling berarti.
				</p>
			</div>

			<!-- Decorative Quote -->
			<blockquote
				class="mt-16 italic text-yellow-400/80 text-xl md:text-2xl font-medium"
			>
				“Setiap bug punya cerita. Setiap crash punya pelajaran.”
			</blockquote>

			<!-- Link back -->
			<div class="mt-16">
				<NuxtLink
					to="/"
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
					Kembali ke beranda
				</NuxtLink>
			</div>
		</div>
	</section>
</template>

<script setup lang="ts"></script>

<style scoped>
@import "tailwindcss";

p {
	@apply text-gray-300 leading-relaxed;
}
blockquote {
	text-shadow: 0 0 8px rgba(255, 215, 0, 0.25);
}
</style>
