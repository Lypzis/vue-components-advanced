<template>
	<div class="card">
		<!-- 'if' prevents 'undefined', completely removing header if not provided -->
		<header v-if="$slots.header">
			<!-- if more than one slot, a name must be given to specify where it is going, defaults to no name given -->
			<slot name="header">
				<!-- will only appear if there is no v-slot:header in the component -->
				<h2>The Default</h2>
			</slot>
		</header>
		<!-- it means the component that will be wrapped by this one -->
		<slot></slot>
	</div>
</template>

<script>
	export default {
		mounted() {
			console.log(this.$slots);
			// the slots created(available)
			console.log(this.$slots.default);
			console.log(this.$slots.header);
		},
	};
</script>

<style scoped>
	.card {
		margin: 2rem auto;
		max-width: 30rem;
		border-radius: 12px;
		box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
		padding: 1rem;
	}

	header {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}
</style>
