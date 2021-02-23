<template>
	<div class="panel">
		<section class="text-center py-5" v-if="currentCategory == null">
			<h2>Select Category</h2>
		</section>
		<div v-for="item in componentList" :key="item">
			<div v-for="subitem in item" :key="subitem">
				<div v-for="(linkItem, key) in subitem.content" :key="key">
					<codepenIframe :parent="subitem.group" :title="key" :link="linkItem" v-if="subitem.group == currentCategory"/>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
import codepenIframe from "./CodepenIframe.vue";

export default {
	name: "view panel",
	props: ["currentCategory", "componentList"],
	components: {
		codepenIframe,
	},
	data() {
		return {
		}
	},
	methods: {
	}
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>
