<template>
	<v-container fluid pa-0>
		<v-sheet class="black" width="100vw">
			<v-img
				v-for="i in lenjpg"
				:key="i"
				:src="require('../assets/TL/TL' + i + '.jpg')"
				eager
				max-width="750px"
				class="mx-auto"
			/>
		</v-sheet>
	</v-container>
</template>

<script>
export default {
	name: "Story",
	props: ["num"],
	data: () => ({ lenjpg: 0 }),
	methods: {
		lengths() {
			const raws = require.context("../assets/TL/", false, /^.*\.jpg$/);
			this.lenjpg = raws.keys().length;
		},
	},
	created() {
		this.lengths();
	},
};
</script>
