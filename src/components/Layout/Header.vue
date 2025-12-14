<template>
	<header
		class="fixed top-0 left-0 right-0 bg-white/90 backdrop-blur-md shadow-md py-4 px-6 z-50 border-b border-gray-100"
	>
		<div class="container mx-auto flex justify-between items-center">
			<div class="flex items-center space-x-3">
				<div
					class="w-10 h-10 bg-gradient-to-br from-blue-500 to-purple-600 rounded-xl flex items-center justify-center shadow-lg transform hover:scale-110 transition-transform duration-300"
				>
					<span class="text-white font-bold text-xl">H</span>
				</div>
				<h1 class="text-2xl font-bold text-gray-800 animate-pulse-once">
					HealthFlow
				</h1>
			</div>

			<nav class="hidden md:flex space-x-6">
				<a
					v-for="item in navItems"
					:key="item.name"
					:href="item.href"
					class="text-gray-600 hover:text-blue-600 font-medium transition-all duration-300 relative group"
				>
					{{ item.name }}
					<span
						class="absolute bottom-0 left-0 w-0 h-0.5 bg-blue-600 group-hover:w-full transition-all duration-300"
					></span>
				</a>
			</nav>

			<div class="flex items-center space-x-4">
				<button
					class="p-2 rounded-full hover:bg-gray-100 transition-all duration-300 transform hover:rotate-12 relative"
				>
					<svg
						class="w-6 h-6 text-gray-600"
						fill="none"
						stroke="currentColor"
						viewBox="0 0 24 24"
					>
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9"
						/>
					</svg>
					<span
						class="absolute -top-1 -right-1 w-5 h-5 bg-red-500 text-white text-xs rounded-full flex items-center justify-center animate-bounce"
						>3</span
					>
				</button>
				<div
					class="w-10 h-10 bg-gradient-to-r from-blue-100 to-blue-200 rounded-full flex items-center justify-center cursor-pointer transform hover:scale-105 transition-transform duration-300"
				>
					<span class="text-blue-600 font-semibold">JD</span>
				</div>
			</div>
		</div>
	</header>
</template>

<script setup>
const navItems = [
	{ name: 'Dashboard', href: '#' },
	{ name: 'Patients', href: '#' },
	{ name: 'Appointments', href: '#' },
	{ name: 'Reports', href: '#' },
]
</script>

<style>
.animate-pulse-once {
	animation: pulse 2s ease-in-out;
}
@keyframes pulse {
	0%,
	100% {
		opacity: 1;
	}
	50% {
		opacity: 0.7;
	}
}
</style>
