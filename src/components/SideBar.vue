<template>
	<nav class="sidebar">
		<ul v-for="(item, key) in ComponentList" :key="item">
			<li>
				{{ key }}
			</li>
			<ul v-for="(subitem, subkey) in item" :key="subitem">
				<li v-if="typeof subkey === 'string'">
					{{ subkey }}
				</li>
				<ul v-for="(subsubitem, subsubkey) in subitem" :key="subsubitem">
					<li v-if="typeof subsubkey === 'string'">
						{{ subsubkey }}
					</li>
					<ul v-for="(subsubsubitem, subsubsubkey) in subitem" :key="subsubsubitem">
						<li v-if="typeof subsubsubkey === 'string'">
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
	data() {
		return {
			ComponentList: {
				Navigation: {
					Types: {
						Menus: {
							Megamenu: 'https://codepen.io/Chris2733/pen/RwwZpdL'
						},
						Scrollbars: {
							Scrollbar: 'https://codepen.io/Chris2733/pen/RwwZpdL'
						}
					},
				},
				Clipboard: {
					'clipboardjs': 'https://codepen.io/Chris2733/pen/QWjqvjP',
					'Round button': 'https://codepen.io/jonsp/pen/GRJKrYv'
				},
				Javascript: {
					assorted: 'https://codepen.io/jonsp/pen/PoqYVZv'
				}
			},
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
