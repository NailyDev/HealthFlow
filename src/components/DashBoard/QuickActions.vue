<template>
	<div
		class="bg-gradient-to-br from-white to-blue-50 rounded-2xl shadow-lg p-6 border border-blue-100"
	>
		<h2 class="text-xl font-bold text-gray-800 mb-6 flex items-center">
			<svg
				class="w-6 h-6 mr-2 text-blue-600"
				fill="none"
				stroke="currentColor"
				viewBox="0 0 24 24"
			>
				<path
					stroke-linecap="round"
					stroke-linejoin="round"
					stroke-width="2"
					d="M13 10V3L4 14h7v7l9-11h-7z"
				/>
			</svg>
			Quick Actions
		</h2>
		<div class="space-y-4">
			<button
				v-for="action in actions"
				:key="action.label"
				:class="`w-full ${action.bg} hover:shadow-xl text-white py-4 rounded-xl font-medium flex items-center justify-center transition-all duration-300 transform hover:-translate-y-1 hover:scale-[1.02] active:scale-95`"
			>
				<svg
					class="w-5 h-5 mr-3"
					fill="none"
					stroke="currentColor"
					viewBox="0 0 24 24"
				>
					<path
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="2"
						:d="action.icon"
					/>
				</svg>
				{{ action.label }}
			</button>
		</div>
	</div>
</template>

<script setup>
const actions = [
	{
		label: 'New Appointment',
		bg: 'bg-gradient-to-r from-blue-600 to-blue-700',
		icon: 'M12 4v16m8-8H4',
	},
	{
		label: 'Add Patient',
		bg: 'bg-gradient-to-r from-green-600 to-emerald-700',
		icon: 'M18 9v3m0 0v3m0-3h3m-3 0h-3m-2-5a4 4 0 11-8 0 4 4 0 018 0zM3 20a6 6 0 0112 0v1H3v-1z',
	},
	{
		label: 'Generate Report',
		bg: 'bg-gradient-to-r from-purple-600 to-purple-700',
		icon: 'M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z',
	},
]
</script>
