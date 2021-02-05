<template>
	<nav class="sidebar">
		<ul v-for="(item, key) in componentList" :key="item">
			<li>
				{{ key }}
			</li>
			<ul v-for="(subitem, subkey) in item" :key="subitem">
				<li v-if="typeof subitem === 'object' && subitem !== null">
					{{ subkey }}
				</li>
				<ul v-for="(subsubitem, subsubkey) in subitem" :key="subsubitem">
					<li v-if="typeof subsubitem === 'object' && subsubitem !== null">
						{{ subsubkey }}
					</li>
					<ul v-for="(subsubsubitem, subsubsubkey) in subsubitem" :key="subsubsubitem">
						<li v-if="typeof subsubsubitem === 'object' && subsubsubitem !== null">
							{{ subsubsubkey }}
						</li>
					</ul>
				</ul>
			</ul>
		</ul>
	</nav>
</template>

<script>
export default {
	name: "sidebar",
	props: ["componentList"],
	data() {
		return {
		};
	},
	computed: {
	},
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.sidebar {
	background: #6b6b6b;
}
</style>
