<template>
	<nav aria-label="Primary" class="sidebar">
		<ul v-for="(item, key) in componentList" :key="item">
			<li>
				{{ key }}
				<ul>
					<li v-for="(subitem, key) in item" :key="key" @click="menuItemClick(subitem.group)">
						{{subitem.group}}
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
	computed: {
	},
	methods: {
		menuItemClick(key) {
			event.stopPropagation();
			this.$emit("update-current-category", key);
		},
	},
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.sidebar {
	background: #6b6b6b;
	color: #fff;
	padding: 25px 0;
	height: 100%;
	min-height: 100vh;
	ul {
		padding: 0 0 0 16px;
		li {
			list-style-type: none;
			ul {
				margin: 10px 0 0 0;
			}
		}
	}
	> ul {
		padding: 0 0 0 40px;
	}
}
</style>
