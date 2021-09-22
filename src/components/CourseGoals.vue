<template>
	<ul>
		<li v-for="goal in goals" :key="goal">
			<!-- scoped slot makes the data of goal=item available for use "outside" -->
			<slot :item="goal" anotherProp="..."></slot>
		</li>
	</ul>
</template>

<script>
	export default {
		data() {
			return {
				goals: ['Finish the course', 'Learn Vue'],
			};
		},
	};
</script>
