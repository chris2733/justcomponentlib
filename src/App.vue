<template>
	<div class="container-fluid p-0">
		<div class="row no-gutters">
			<div class="col-12">
				<TopBar />
			</div>
			<div class="col-md-4 col-lg-3">
				<SideBar @update-current-category="updateCurrentCategory" :component-list="componentList" />
			</div>
			<div class="col-md-8 col-lg-9">
				<ViewPanel :current-category="currentCategory" :component-list="componentList" />
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
			currentCategory: null,
			componentList: {
				Navigation: [
					{
						group: 'Menus',
						content: {
							Megamenu: 'https://codepen.io/Chris2733/pen/RwwZpdL'
						},
					},
					{
						group: 'Scrollbars',
						content: {
							Scrollbar: 'https://codepen.io/Chris2733/pen/rNONWKR',
							'Slider scroll': 'https://codepen.io/spindogs/pen/YzWOyyP'
						},
					},
				],
				Media: [
					{	
						group: 'Video',
						content: {
							Video: 'https://codepen.io/Chris2733/pen/xxbKwMm'
						},
					}
				],
				Javascript: [
					{	
						group: 'Assorted',
						content: {
							'clipboardjs': 'https://codepen.io/Chris2733/pen/QWjqvjP',
							'Round button': 'https://codepen.io/jonsp/pen/GRJKrYv',
							'Mouse follow': 'https://codepen.io/spindogs/pen/yLJxNrp'
						},
					}
				]
			}
		}
	},
	methods: {
		updateCurrentCategory(key) {
			this.currentCategory = key;
		},
	},
};
</script>

<style lang="scss">
.mainbody {
}
</style>
