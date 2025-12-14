<template>
	<div class="slide-up-enter-active">
		<div class="container mx-auto px-6 py-8">
			<div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
				<div class="lg:col-span-2 space-y-8">
					<div class="grid grid-cols-1 md:grid-cols-3 gap-6">
						<StatCard
							v-for="stat in stats"
							:key="stat.title"
							:title="stat.title"
							:value="stat.value"
							:trend="stat.trend"
							:trendColor="stat.trendColor"
							:iconBg="stat.iconBg"
							:iconColor="stat.iconColor"
							:iconPath="stat.iconPath"
						/>
					</div>
					<AppointmentsTable />
				</div>
				<div class="space-y-8">
					<QuickActions />
					<RecentActivity />
				</div>
			</div>
		</div>
	</div>
</template>

<script setup>
import AppointmentsTable from '../components/Appointments/AppointmentsTable.vue'
import QuickActions from '../components/Dashboard/QuickActions.vue'
import RecentActivity from '../components/Dashboard/RecentActivity.vue'
import StatCard from '../components/Dashboard/StatCard.vue'

const stats = [
	{
		title: 'Total Patients',
		value: '1,248',
		trend: '↑ 12% from last month',
		trendColor: 'text-green-500',
		iconBg: 'bg-gradient-to-br from-blue-100 to-blue-200',
		iconColor: 'text-blue-600',
		iconPath:
			'M12 4.354a4 4 0 110 5.292M15 21H3v-1a6 6 0 0112 0v1zm0 0h6v-1a6 6 0 00-9-5.197m13.5-7.25a3.5 3.5 0 11-7 0 3.5 3.5 0 017 0z',
	},
	{
		title: "Today's Appointments",
		value: '24',
		trend: '↓ 3 from yesterday',
		trendColor: 'text-red-500',
		iconBg: 'bg-gradient-to-br from-green-100 to-emerald-200',
		iconColor: 'text-green-600',
		iconPath:
			'M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z',
	},
	{
		title: 'Revenue This Month',
		value: '$42,580',
		trend: '↑ 8% from last month',
		trendColor: 'text-green-500',
		iconBg: 'bg-gradient-to-br from-purple-100 to-purple-200',
		iconColor: 'text-purple-600',
		iconPath:
			'M12 8c-1.657 0-3 .895-3 2s1.343 2 3 2 3 .895 3 2-1.343 2-3 2m0-8c1.11 0 2.08.402 2.599 1M12 8V7m0 1v8m0 0v1m0-1c-1.11 0-2.08-.402-2.599-1M21 12a9 9 0 11-18 0 9 9 0 0118 0z',
	},
]
</script>

<style>
.slide-up-enter-active {
	animation: slideUp 0.6s ease-out;
}
@keyframes slideUp {
	from {
		opacity: 0;
		transform: translateY(30px);
	}
	to {
		opacity: 1;
		transform: translateY(0);
	}
}
</style>
