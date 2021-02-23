<template>
    <div class="iframewrapper">
        <h3>{{ title }}</h3>
        <iframe height="100" style="width: 100%;" scrolling="no" data-default-tab="result" preview="true" :src="embedLink" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
        </iframe>
    </div>
</template>

<script>
export default {
	name: "codepen iframe",
    props: ['parent','title','link'],
	data() {
		return {
		}
	},
	computed: {
        embedLink() {
            // replace pen link with embed link
            let regexLinkReplace = /\/pen\//;
            const embedLink = this.link.replace(regexLinkReplace, '/embed/');
            return `${embedLink}?height=280&theme-id=dark`;
        }
	},
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.iframewrapper {
}
</style>
