<template>
	<div class="panel">
		<ul v-for="(item, key) in componentList" :key="item">
			<li>
				{{ key }}
				<p>keyname: {{ key }}</p>
			</li>
			<ul v-for="(subitem, subkey) in item" :key="subitem">
				<li v-if="typeof subitem !== 'object' && subitem !== null">
					{{ subkey }} - {{ subitem }}
					<p>keyname: {{ key }}</p>
				</li>
				<li v-if="typeof subitem === 'object' && subitem !== null">
					{{ subkey }}
					<ul v-for="(subsubitem, subsubkey) in subitem" :key="subsubitem">
						<li v-if="typeof subsubitem !== 'object' && subitem !== null">
							{{ subsubkey }} - {{ subitem }}
							<p>keyname: {{ subkey }}</p>
						</li>
						<li v-if="typeof subsubitem === 'object' && subsubitem !== null">
							{{ subsubkey }}
							<ul v-for="(subsubsubitem, subsubsubkey) in subsubitem" :key="subsubsubitem">
								<li v-if="typeof subsubsubitem !== 'object' && subitem !== null">
									{{ subsubsubkey }} - {{ subsubsubitem }}
									<p>keyname: {{ subsubkey }}</p>
								</li>
								<li v-if="typeof subsubsubitem === 'object' && subsubsubitem !== null">
									{{ subsubsubkey }}
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
export default {
	name: "view panel",
	props: ["componentList"],
	data() {
		return {
		}
	},
	computed: {
		iframeStr() {
			return `<iframe height="500" style="width: 100%;" scrolling="no" data-default-tab="result" preview="true" src="https://codepen.io/Chris2733/embed/GwwXPa?height=280&theme-id=dark" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
		</iframe>`
		}
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
