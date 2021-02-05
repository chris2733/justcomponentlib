<template>
	<div class="container-fluid p-0">
	{{ currentMenuItem }}
		<div class="row no-gutters">
			<div class="col-12">
				<TopBar />
			</div>
			<div class="col-md-4 col-lg-3">
				<SideBar @update-current-category="updateCurrentCategory" :component-list="ComponentList" />
			</div>
			<div class="col-md-8 col-lg-9">
				<ViewPanel :component-list="ComponentList" />
			</div>
		</div>
	</div>
</template>

<script>
import TopBar from "./components/TopBar.vue";
import SideBar from "./components/SideBar.vue";
import ViewPanel from "./components/ViewPanel.vue";

export default {
	name: "App",
	components: {
		TopBar,
		SideBar,
		ViewPanel,
	},
	data() {
		return {
			currentMenuItem: "none",
			ComponentList: {
				Navigation: {
					Types: {
						Menus: {
							Megamenu: 'https://codepen.io/Chris2733/pen/RwwZpdL'
						},
						Scrollbars: {
							Scrollbar: 'https://codepen.io/Chris2733/pen/rNONWKR'
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
		}
	},
	methods: {
		updateCurrentCategory(key) {
			this.currentMenuItem = key;
		},
	},
};
</script>

<style lang="scss">
.mainbody {
}
</style>
