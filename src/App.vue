<template>
	<div class="min-h-screen bg-gradient-to-br from-gray-50 to-blue-50">
		<Header />
		<main class="pt-20">
			<Dashboard />
		</main>
		<Footer />
	</div>
</template>

<script setup>
import Footer from './components/Layout/Footer.vue'
import Header from './components/Layout/Header.vue'
import Dashboard from '/src/views/Dashboard.vue'
</script>
