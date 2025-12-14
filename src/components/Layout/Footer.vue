<template>
	<footer
		class="bg-gradient-to-r from-gray-800 to-gray-900 text-white py-8 mt-12"
	>
		<div class="container mx-auto px-6">
			<div class="flex flex-col md:flex-row justify-between items-center">
				<div class="mb-6 md:mb-0">
					<p class="text-gray-400 text-sm">
						© 2024 HealthFlow. All rights reserved.
					</p>
				</div>
				<div class="flex space-x-6">
					<a
						v-for="link in links"
						:key="link.name"
						:href="link.href"
						class="text-gray-400 hover:text-white transition-all duration-300 hover:scale-105"
					>
						{{ link.name }}
					</a>
				</div>
			</div>
		</div>
	</footer>
</template>

<script setup>
const links = [
	{ name: 'Privacy Policy', href: '#' },
	{ name: 'Terms of Service', href: '#' },
	{ name: 'Contact', href: '#' },
]
</script>
