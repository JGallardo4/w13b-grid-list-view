<template>
	<section id="tweets">
		<button
			id="view-toggle-button"
			class="button is-link is-outlined"
			@click="toggleView()"
		>
			{{ this.listView ? "View as grid" : "View as list" }}
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

	beforeMount() {
		if(screen.width <= 690) {
			this.listView = true;
		}
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
#tweets {
	display: grid;
	grid-auto-columns: auto 1fr;
	padding: 1rem;
	gap: 1rem;

	#view-toggle-button {
		place-self: center;
	}

	#tweets-container {
		display: grid;
		gap: 1rem;

		&.list-view {
			grid-template-columns: 1fr;
		}

		&.grid-view {
			grid-template-columns: repeat(auto-fit, minmax(20rem, 1fr));
		}
	}
}

@media only screen and (max-width: 690px) {
	#view-toggle-button {
		display: none;
	}
}
</style>