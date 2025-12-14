<template>
	<div class="bg-white rounded-2xl shadow-lg p-6 border border-gray-100">
		<h2 class="text-xl font-bold text-gray-800 mb-6 flex items-center">
			<svg
				class="w-6 h-6 mr-2 text-gray-600"
				fill="none"
				stroke="currentColor"
				viewBox="0 0 24 24"
			>
				<path
					stroke-linecap="round"
					stroke-linejoin="round"
					stroke-width="2"
					d="M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2"
				/>
			</svg>
			Recent Activity
		</h2>
		<div class="space-y-5">
			<div
				v-for="activity in activities"
				:key="activity.id"
				class="flex items-start p-3 rounded-xl hover:bg-gray-50 transition-all duration-300 group"
			>
				<div
					:class="`w-12 h-12 rounded-xl ${activity.bg} flex items-center justify-center mr-4 transform group-hover:scale-110 transition-transform duration-300`"
				>
					<svg
						class="w-6 h-6 text-white"
						fill="none"
						stroke="currentColor"
						viewBox="0 0 24 24"
					>
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							:d="activity.icon"
						/>
					</svg>
				</div>
				<div class="flex-1">
					<p class="font-medium text-gray-800">{{ activity.title }}</p>
					<p class="text-sm text-gray-500 mt-1">{{ activity.time }}</p>
				</div>
				<div
					class="w-2 h-2 rounded-full bg-blue-500 opacity-0 group-hover:opacity-100 transition-opacity duration-300"
				></div>
			</div>
		</div>
	</div>
</template>

<script setup>
const activities = [
	{
		id: 1,
		title: 'New patient registered',
		time: '10 min ago',
		icon: 'M18 9v3m0 0v3m0-3h3m-3 0h-3m-2-5a4 4 0 11-8 0 4 4 0 018 0zM3 20a6 6 0 0112 0v1H3v-1z',
		bg: 'bg-gradient-to-br from-blue-500 to-cyan-400',
	},
	{
		id: 2,
		title: 'Appointment confirmed',
		time: '25 min ago',
		icon: 'M5 13l4 4L19 7',
		bg: 'bg-gradient-to-br from-green-500 to-emerald-400',
	},
	{
		id: 3,
		title: 'Report generated',
		time: '1 hour ago',
		icon: 'M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z',
		bg: 'bg-gradient-to-br from-purple-500 to-pink-400',
	},
	{
		id: 4,
		title: 'Payment received',
		time: '2 hours ago',
		icon: 'M12 8c-1.657 0-3 .895-3 2s1.343 2 3 2 3 .895 3 2-1.343 2-3 2m0-8c1.11 0 2.08.402 2.599 1M12 8V7m0 1v8m0 0v1m0-1c-1.11 0-2.08-.402-2.599-1M21 12a9 9 0 11-18 0 9 9 0 0118 0z',
		bg: 'bg-gradient-to-br from-yellow-500 to-orange-400',
	},
]
</script>
