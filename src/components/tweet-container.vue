<template>
	<section id="tweets">
		<button id="view-toggle-button" @click="toggleView()">
			{{this.listView ? 'View as grid' : 'View as list'}}
		</button>
		<tweets
			id="tweets-container"
			:class="this.listView ? 'list-view' : 'grid-view'"
		></tweets>
	</section>
</template>

<script>
import Tweets from "./tweets.vue";

export default {
	name: "tweet-container",

	methods: {
		toggleView() {
			this.listView = !this.listView;
		},
	},

	components: {
		Tweets,
	},

	data() {
		return {
			listView: false,
		};
	},
};
</script>

<style lang="scss" scoped>
#tweets-container {
	display: grid;
	gap: 2rem;
	padding: 2rem;

	&.list-view {
		grid-template-columns: 1fr;
	}

	&.grid-view {
		grid-template-columns: repeat(auto-fit, minmax(20rem, 1fr));
	}	
}
</style>