<template>
	<section>
		<base-card>
			<!-- now vue knows to place it at the header slot in the BaseCard-->
			<!-- v-slot:header = #header in short for v-slot -->
			<template #header>
				<h3>{{ fullName }}</h3>
				<base-badge
					:type="role"
					:caption="role.toUpperCase()"
				></base-badge>
			</template>
			<!-- 'default' is a vue reserved name -->
			<template #default>
				<p>{{ infoText }}</p>
			</template>
		</base-card>
	</section>
</template>

<script>
	export default {
		props: ['fullName', 'infoText', 'role'],
	};
</script>
