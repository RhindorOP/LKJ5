<template>
	<v-container fluid pa-0 style="position:relative">
		<v-sheet class="black" style="position:absolute" width="100vw">
			<v-img
				v-for="i in lenwebp"
				:key="i"
				:src="require('../assets/RAW/Raw' + i + '.webp')"
				eager
				max-width="750px"
				class="mx-auto"
			/>
		</v-sheet>
		<v-sheet class="transparent" style="position:absolute" width="100vw">
			<!-- <v-img
				v-show="num"
				v-for="i in lenpng"
				:key="i"
				:src="require('../assets/TL/TL' + i + '.png')"
				eager
				max-width="750px"
				class="mx-auto"
			/>-->
			<v-sheet
				v-show="num"
				v-for="i in 100"
				:key="i"
				elevation="10"
				max-width="750px"
				class="text-center text-h2 text-md-h1 font-weight-bold py-10"
				style="margin: 25px auto 750px"
			>TO BE<br/>TRANSLATED</v-sheet>
		</v-sheet>
	</v-container>
</template>

<script>
export default {
	name: "Story",
	props: ["num"],
	data: () => ({ lenwebp: 0, lenpng: 0 }),
	methods: {
		lengths() {
			const raws = require.context("../assets/RAW/", false, /^.*\.webp$/);
			this.lenwebp = raws.keys().length;
			// const tl = require.context("../assets/TL/", false, /^.*\.png$/);
			// this.lenpng = tl.keys().length;
		},
	},
	created() {
		this.lengths();
	},
};
</script>
