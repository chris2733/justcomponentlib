<template>
	<div class="panel">
		<h2 v-if="!currentCategory">Select Category</h2>
		<ul v-for="(item, key) in componentList" :key="item">
			<ul v-for="(subitem, subkey) in item" :key="subitem">
				<li v-if="typeof subitem !== 'object' && subitem !== null">
					<codepenIframe :parent="key" :title="subkey" :link="subitem" v-if="key == currentCategory"/>
				</li>
				<li v-if="typeof subitem === 'object' && subitem !== null">
					<ul v-for="(subsubitem, subsubkey) in subitem" :key="subsubitem">
						<li v-if="typeof subsubitem !== 'object' && subsubitem !== null">
							<codepenIframe :parent="subkey" :title="subsubkey" :link="subsubitem" v-if="subkey == currentCategory"/>
						</li>
						<li v-if="typeof subsubitem === 'object' && subsubitem !== null">
							<ul v-for="(subsubsubitem, subsubsubkey) in subsubitem" :key="subsubsubitem">
								<li v-if="typeof subsubsubitem !== 'object' && subsubsubitem !== null">
									<codepenIframe :parent="subsubkey" :title="subsubsubkey" :link="subsubsubitem" v-if="subsubkey == currentCategory"/>
								</li>
							</ul>
						</li>
					</ul>
				</li>
			</ul>
		</ul>
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
.topbar {
	background: #404040;
	color: #fff;
}
</style>
