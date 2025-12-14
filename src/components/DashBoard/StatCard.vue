<template>
	<div
		class="bg-white rounded-2xl shadow-lg p-6 border border-gray-100 hover:shadow-2xl hover:-translate-y-2 transition-all duration-500 overflow-hidden group"
	>
		<div class="flex items-center justify-between relative">
			<div class="z-10">
				<p class="text-gray-500 text-sm font-medium">{{ title }}</p>
				<p class="text-4xl font-bold text-gray-800 mt-3">{{ value }}</p>
				<div class="flex items-center mt-4">
					<span :class="`text-sm font-medium ${trendColor}`">{{ trend }}</span>
				</div>
			</div>
			<div
				:class="`w-16 h-16 rounded-xl ${iconBg} flex items-center justify-center shadow-lg transform group-hover:scale-110 group-hover:rotate-6 transition-all duration-500`"
			>
				<svg
					class="w-8 h-8"
					:class="iconColor"
					fill="none"
					stroke="currentColor"
					viewBox="0 0 24 24"
				>
					<path
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="1.5"
						:d="iconPath"
					/>
				</svg>
			</div>
			<div
				class="absolute -right-12 -top-12 w-24 h-24 bg-gradient-to-br from-gray-50 to-transparent rounded-full opacity-50 group-hover:opacity-100 transition-all duration-700"
			></div>
		</div>
	</div>
</template>

<script setup>
defineProps({
	title: String,
	value: [String, Number],
	trend: String,
	trendColor: String,
	iconBg: String,
	iconColor: String,
	iconPath: String,
})
</script>
