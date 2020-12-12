<template>
	<section id="tweets">
		<button id="view-toggle-button" @click="toggleView()">Change View</button>
		<section
			id="tweets-container"
			:class="this.listView ? 'list-view' : 'grid-view'"
		>
			<article class="tweet" v-for="(tweet, index) in tweets" :key="index">
				<h1 class="tweet__author">Author: {{ tweet.author }}</h1>
				<h2 class="tweet__date">Published on: {{ tweet.date }}</h2>
				<p class="tweet__content">{{ tweet.content }}</p>
			</article>
		</section>
	</section>
</template>

<script>
export default {
	name: "tweets",

	methods: {
		toggleView() {
			this.listView = !this.listView;
			console.log(!this.listView);
		},
	},

	data() {
		return {
			listView: false,
			tweets: [
				{
					author: "Harry",
					content: "I want the nimbus 3000",
					date: "October 10, 2001 ",
				},
				{
					author: "Ron",
					content: "I hate spiders!",
					date: "October 20, 2001 ",
				},
				{
					author: "Hermione",
					content: "You're gonna get us killed, or worse... expelled",
					date: "October 05, 2001 ",
				},
			],
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

	.tweet {
		display: grid;
		grid-template-columns: 1fr 1fr;
		grid-auto-rows: auto 1fr;
		padding: 1rem;
		gap: 1rem;
		background-color: lightgray;
		border-radius: 10px;

		.tweet__author {
			grid-column: 1;
			grid-row: 1;
		}
		.tweet__date {
			grid-column: 2;
			grid-row: 1;
		}
		.tweet__content {
			grid-column: 1 / 3;
			grid-row: 2;
		}
	}

	h1 {
		font-size: larger;
	}

	h2 {
		font-size: large;
	}
}
</style>>