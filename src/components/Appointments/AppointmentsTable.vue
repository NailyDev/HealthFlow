<template>
	<div
		class="bg-white rounded-2xl shadow-lg p-6 border border-gray-100 overflow-hidden"
	>
		<div class="flex justify-between items-center mb-8">
			<h2 class="text-2xl font-bold text-gray-800">Recent Appointments</h2>
			<button
				class="bg-gradient-to-r from-blue-500 to-blue-600 text-white px-6 py-2 rounded-lg font-medium hover:shadow-xl hover:-translate-y-0.5 transition-all duration-300"
			>
				View All
			</button>
		</div>

		<div class="overflow-x-auto">
			<table class="w-full">
				<thead>
					<tr class="text-left text-gray-500 border-b">
						<th class="pb-4 font-medium">Patient</th>
						<th class="pb-4 font-medium">Time</th>
						<th class="pb-4 font-medium">Doctor</th>
						<th class="pb-4 font-medium">Status</th>
					</tr>
				</thead>
				<tbody>
					<tr
						v-for="appointment in appointments"
						:key="appointment.id"
						class="border-b hover:bg-gradient-to-r hover:from-blue-50 hover:to-transparent transition-all duration-300 group"
					>
						<td class="py-5">
							<div class="flex items-center">
								<div
									class="w-12 h-12 rounded-xl bg-gradient-to-br from-gray-100 to-gray-200 mr-4 flex items-center justify-center transform group-hover:scale-110 transition-transform duration-300"
								>
									<span class="text-gray-600 font-bold">{{
										appointment.initials
									}}</span>
								</div>
								<div>
									<p class="font-semibold text-gray-800">
										{{ appointment.patient }}
									</p>
									<p class="text-sm text-gray-500">
										{{ appointment.condition }}
									</p>
								</div>
							</div>
						</td>
						<td class="py-5">
							<p class="font-semibold text-gray-800">{{ appointment.time }}</p>
							<p class="text-sm text-gray-500">{{ appointment.date }}</p>
						</td>
						<td class="py-5">
							<div class="flex items-center">
								<div
									class="w-8 h-8 rounded-full bg-gradient-to-r from-blue-100 to-cyan-100 mr-2"
								></div>
								<span class="text-gray-700">{{ appointment.doctor }}</span>
							</div>
						</td>
						<td class="py-5">
							<span
								:class="`px-4 py-1.5 rounded-full text-sm font-semibold ${appointment.statusClass} transform group-hover:scale-105 transition-transform duration-300`"
							>
								{{ appointment.status }}
							</span>
						</td>
					</tr>
				</tbody>
			</table>
		</div>
	</div>
</template>

<script setup>
const appointments = [
	{
		id: 1,
		patient: 'John Smith',
		initials: 'JS',
		condition: 'Regular Checkup',
		time: '10:00 AM',
		date: 'Today',
		doctor: 'Dr. Johnson',
		status: 'Confirmed',
		statusClass:
			'bg-gradient-to-r from-green-100 to-green-50 text-green-700 border border-green-200',
	},
	{
		id: 2,
		patient: 'Emma Wilson',
		initials: 'EW',
		condition: 'Dental Cleaning',
		time: '11:30 AM',
		date: 'Today',
		doctor: 'Dr. Davis',
		status: 'Pending',
		statusClass:
			'bg-gradient-to-r from-yellow-100 to-yellow-50 text-yellow-700 border border-yellow-200',
	},
	{
		id: 3,
		patient: 'Michael Brown',
		initials: 'MB',
		condition: 'Physical Therapy',
		time: '2:00 PM',
		date: 'Today',
		doctor: 'Dr. Taylor',
		status: 'Confirmed',
		statusClass:
			'bg-gradient-to-r from-green-100 to-green-50 text-green-700 border border-green-200',
	},
]
</script>
