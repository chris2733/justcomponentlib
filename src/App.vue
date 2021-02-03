<template>
	<div class="container-fluid p-0">
		<div class="row">
			<div class="col-12">
				<TopBar />
			</div>
			<div class="col-md-4 col-lg-3">
				<SideBar />
			</div>
			<div class="col-md-8 col-lg-9">
				<ViewPanel />
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
};
</script>

<style lang="scss">
.mainbody {
}
</style>
