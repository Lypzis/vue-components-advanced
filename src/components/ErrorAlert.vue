<template>
	<dialog open>
		<!-- remember things placed inside 'error-alert' tag will replace 'slot' here -->
		<slot></slot>
	</dialog>
</template>

<style scoped>
	dialog {
		position: fixed;
		margin: 0;
		top: 20vh;
		left: 30%;
		width: 40%;
		background-color: #fff;
		box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
		padding: 1rem;
	}
</style>
