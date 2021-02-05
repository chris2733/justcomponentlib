<template>
	<nav class="sidebar">
		<ul v-for="(item, key) in componentList" :key="item">
			<li v-if="typeof item === 'object' && item !== null" @click="menuItemClick(key)">
				{{ key }}
				<ul v-for="(subitem, subkey) in item" :key="subitem">
					<li v-if="typeof subitem === 'object' && subitem !== null" @click="menuItemClick(subkey)">
						{{ subkey }}
						<ul v-for="(subsubitem, subsubkey) in subitem" :key="subsubitem">
							<li v-if="typeof subsubitem === 'object' && subsubitem !== null" @click="menuItemClick(subsubkey)">
								{{ subsubkey }}
								<ul v-for="(subsubsubitem, subsubsubkey) in subsubitem" :key="subsubsubitem">
									<li v-if="typeof subsubsubitem === 'object' && subsubsubitem !== null" @click="menuItemClick(subsubsubkey)">
										{{ subsubsubkey }}
									</li>
								</ul>
							</li>
						</ul>
					</li>
				</ul>
			</li>
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
	methods: {
		menuItemClick(key) {
			event.stopPropagation();
			// if item has sub items
			if (!event.target.querySelector('li')) {
				this.$emit("update-current-category", key);
			}
		}
	},
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.sidebar {
	background: #6b6b6b;
}
</style>
