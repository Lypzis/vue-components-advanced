<template>
	<div>
		<!-- can also be written as 
    <TheHeader />
    -->
		<the-header></the-header>
		<button @click="setSelectedComponent('active-goals')">
			Active Goals
		</button>
		<button @click="setSelectedComponent('manage-goals')">
			Manage Goals
		</button>
		<!-- 
		<active-goals
			v-if="selectedComponent === 'active-goals'"
		></active-goals>
		<manage-goals
			v-if="selectedComponent === 'manage-goals'"
		></manage-goals> -->

		<!-- 'keep-alive' will make the component to not disappear from existence
			when switching between them keeping information. -->
		<!-- 'component' provided by vue, swap between components just as if using v-if -->
		<keep-alive>
			<component :is="selectedComponent"> </component>
		</keep-alive>
	</div>
</template>

<script>
	// Keep components local if only used in one place, else register it in 'main.js' to be available globally
	import TheHeader from './components/layout/TheHeader.vue';
	import ActiveGoals from './components/ActiveGoals.vue';
	import ManageGoals from './components/ManageGoals.vue';

	export default {
		components: {
			// the name is different from 'the-header', but vue understands anyway and converts it
			TheHeader,
			ActiveGoals,
			ManageGoals,
		},

		data() {
			return {
				selectedComponent: 'active-goals',
				activeUser: {
					name: 'Maximilian Schwarzmüller',
					description: 'Site owner and admin',
					role: 'admin',
				},
			};
		},
		methods: {
			setSelectedComponent(cmp) {
				this.selectedComponent = cmp;
			},
		},
	};
</script>

<style>
	html {
		font-family: sans-serif;
	}

	body {
		margin: 0;
	}
</style>
