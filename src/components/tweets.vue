<template>
	<section id="tweets">
		<button id="view-toggle-button" @click="toggleView()">Change View</button>
		<section id="tweets-container" :class="this.listView ? 'list-view' : 'grid-view'">
			<article class="tweet" v-for="(tweet, index) in tweets" :key="index">
				<h1>Author: {{ tweet.author }}</h1>
				<p>{{ tweet.content }}</p>
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
		}
	},

  data() {
    return {
			listView: false,
      tweets: [
        {
          author: "Harry",
          content: "I want the nimbus 3000",
        },
        {
          author: "Ron",
          content: "I hate spiders!",
        },
        {
          author: "Hermione",
          content: "You're gonna get us killed, or worse... expelled",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
	#tweets-container {
		display: grid;

		&.list-view {
			grid-template-columns: 1fr;
		}

		&.grid-view { 
			grid-template-columns: repeat(auto-fit, minmax(20rem, 1fr));
		}
	}
</style>>